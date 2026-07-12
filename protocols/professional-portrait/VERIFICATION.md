# Professional Portrait — Verification & Agentic Spec

**Companion to:** `PROTOCOL.md` (same folder)

**What this is:** Reference material for judging portrait candidates and for a possible future agentic execution. **Never paste this document into a portrait run.** The run document is the prompt in chat execution; process machinery in the prompt dilutes generation quality (the empirical finding that produced the v1.5 split — see PROTOCOL.md version history).

**When to open this file:**

- A candidate is borderline and you can't articulate what's off → Structured Identity Diff
- You want an objective identity score → InsightFace
- An agentic build is being considered → Profile B spec

**Version:** 1.0

---

# STRUCTURED IDENTITY DIFF

For borderline candidates. Self-judgment of one's own portrait is unreliable in both directions — hypercritical of features, forgiving of drift. The diff replaces "does it feel like me" with ratios checked one at a time.

Place the face crop of the candidate beside the face crop of the reference. Evaluate individually — do not batch-approve. Drift shows up in **ratios**, not individual features.

- ☐ Interocular distance relative to face width — matches
- ☐ Nose bridge width and nose length — match
- ☐ Philtrum length (nose base to upper lip) — matches
- ☐ Jaw angle and chin shape — match
- ☐ Hairline shape and hair direction — identical
- ☐ Ear position and size — match
- ☐ Glasses — identical frame, identical position
- ☐ Facial hair — preserved exactly
- ☐ Skin texture — wrinkles, moles, freckles present; no synthetic smoothing

Check at **two scales**: full resolution AND ~128px avatar crop. Smoothed-skin drift passes small and fails large; proportion drift can pass large and fail small.

Note: generative drift is systematically flattering — slightly more symmetry, slightly smoother skin, slightly stronger jaw. The eye forgives exactly these changes. The ratios don't.

---

# IDENTITY VERIFICATION — INSIGHTFACE

Objective identity scoring using the open-source InsightFace library (https://github.com/deepinsight/insightface). Optional tiebreaker in chat use; mandatory in-loop scoring in agentic use.

**License note:** InsightFace code is MIT-licensed, but the pretrained model packs (e.g., `buffalo_l`) are licensed for **non-commercial research use**. Fine for personal portrait runs. If this is ever executed inside commercial workflows (e.g., Cranberry), re-evaluate model licensing first.

## Setup (once, local)

```bash
pip install insightface onnxruntime numpy opencv-python
# buffalo_l model pack (~300MB) downloads automatically on first run
```

## Reference script

```python
#!/usr/bin/env python3
"""face_sim.py — cosine similarity between the largest face in two images.
Usage: python face_sim.py reference.jpg candidate.jpg"""
import sys
import cv2
import numpy as np
from insightface.app import FaceAnalysis

def largest_face_embedding(app, path):
    img = cv2.imread(path)
    if img is None:
        sys.exit(f"Could not read image: {path}")
    faces = app.get(img)
    if not faces:
        sys.exit(f"No face detected in: {path}")
    face = max(faces, key=lambda f: (f.bbox[2] - f.bbox[0]) * (f.bbox[3] - f.bbox[1]))
    return face.normed_embedding

def main():
    if len(sys.argv) != 3:
        sys.exit("Usage: python face_sim.py reference.jpg candidate.jpg")
    app = FaceAnalysis(name="buffalo_l", providers=["CPUExecutionProvider"])
    app.prepare(ctx_id=0, det_size=(640, 640))
    ref = largest_face_embedding(app, sys.argv[1])
    cand = largest_face_embedding(app, sys.argv[2])
    sim = float(np.dot(ref, cand))
    print(f"cosine_similarity: {sim:.4f}")

if __name__ == "__main__":
    main()
```

## Calibration (required before trusting thresholds)

Fixed thresholds misfire — same-identity similarity varies by subject, lighting, and photo age. Calibrate per subject:

1. Collect 5–10 pairs of **real** photographs of the subject (different days/lighting if possible).
2. Score every pair with the script.
3. The subject's real-pair band (min–mean) is the baseline. A generated candidate should score **within or near the low end of the real-pair band** to pass.

## Provisional bands *(uncalibrated — replace after calibration)*

- **≥ 0.50** — pass on identity score
- **0.35 – 0.50** — borderline; the Structured Identity Diff and the human decide
- **< 0.35** — fail; retry per PROTOCOL.md retry guidance

The score gates but does not replace the diff: embedding similarity can miss hairline, glasses, and expression errors that humans catch instantly, and the diff catches drift the embedding forgives.

## Reading scores across retries

Scores over successive attempts tell you whether simplification is working:

- 0.42 → 0.51 → 0.58 — converging; the retry ladder is buying accuracy, continue.
- 0.42 → 0.44 → 0.41 — flat; the generation tool has hit its identity ceiling for this face. Stop. No prompt discipline fixes this — the answer is a better reference photo or a different generation pipeline.

---

# FREEDOM BUDGET (drift pricing)

The generator has a freedom budget. Every liberty granted spends budget that would otherwise protect the face. This is the reasoning behind PROTOCOL.md's retry-by-simplification order.

| Liberty | Drift cost | Why |
|---|---|---|
| New pose (Step 5C) | **High** | New head angle → face re-synthesized rather than re-rendered |
| Full Body framing | **High** | Face rendered at a fraction of the pixels; fidelity tracks face pixel density |
| Clothing Replace | High | Full torso regeneration; bleed into neck/jaw |
| Clothing Upgrade | Moderate | Partial torso regeneration |
| Three Quarter framing | Moderate | Reduced face pixel density |
| Mood / lighting change | Low | Mostly grading, minimal geometry pressure |
| Background swap | Low | Nearly free when the face is otherwise anchored |

**Over-budget combination:** New pose + Clothing Replace/Upgrade together is the highest-risk configuration in chat execution. Expect identity retries.

**Marginal vs structural drift (retry classification):**

- **Structural** — wrong jaw, eye spacing, nose, face shape. Geometry is wrong. → Simplify per the retry ladder; regenerating with the same settings reproduces the same drift.
- **Marginal** — geometry right; slightly-off smile, slightly synthetic skin. → One straight regeneration is a legitimate first retry. One only. A second marginal failure counts as structural.

---

# PROFILE B — AGENTIC EXECUTION SPEC

**Status: spec'd, untested. Deliberately not built — assessed low ROI (2026-07-12). Kept as a definition of "done properly" in case tooling makes it cheap or Profile A results force the question.**

An agentic executor differs from chat execution in three capabilities:

1. **Programmatic generation** — image API calls, not a chat box.
2. **In-loop scoring** — InsightFace runs automatically on every candidate before any other validation.
3. **Autonomous retry** — generate → score → below threshold → simplify one liberty per the freedom budget → regenerate. Human sees only survivors, delivered side-by-side.

## Generation method hierarchy

Prefer lower-drift methods where the pipeline supports them:

1. **Face-locked / inpaint-around-face** — face pixels sourced from the reference; only pose/clothing/background generated. Lowest drift.
2. **Identity-adapter conditioning** — InstantID / PuLID / IP-Adapter FaceID class; face embedding conditions generation. Moderate.
3. **Full regeneration from image + prompt** — what chat execution does. Highest drift, last resort.

Method downgrade (3→2→1) is the first retry move — it buys more drift reduction than clothing and pose simplification combined.

## Loop spec

1. Intake arrives at activation; defaults applied for anything unspecified; confirm block logged.
2. Calibrate InsightFace threshold from real photo pairs of the subject (see calibration above) if not already on file.
3. Generate one candidate via the lowest-drift available method.
4. Score. Below fail line → skip diff, retry. In band → structured diff. Pass → deliver side-by-side.
5. Retry moves in order: method downgrade → clothing to Preserve → pose to Preserve → request better reference. Seed re-roll permitted once for marginal drift only.
6. Three retry cycles maximum, then report the limiting constraint.

## Full Body handling

Generate Waist Up, then outpaint the body — never generate the face small.

---

# REJECTED APPROACHES

**Composite mode (superimpose subject onto background, harmonize only)** — tested 2026-07-12, rejected. Subject/background lighting mismatch dominates the result, and chat execution re-renders every pixel regardless of instruction, yielding drift risk plus a pasted-on look. Viable only with true compositing tooling (Photoshop-class / background-removal APIs), which is outside this protocol's execution surface. Do not re-add without that tooling.

---

# VERSION HISTORY

- v1.0 — 2026-07-12 — Created in the v1.5 split of PROTOCOL.md. Collects the governance/verification content drafted in the (unshipped) PROTOCOL v1.4: structured identity diff, InsightFace scoring + calibration + license caveat, freedom budget with drift pricing and marginal/structural retry classification, Profile B agentic spec (untested, low-ROI, shelf status), composite-mode rejection record.

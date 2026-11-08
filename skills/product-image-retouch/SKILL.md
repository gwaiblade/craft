---
name: product-image-retouch
description: Turn a real product photo (typically an iPhone shot on a plain or uniform-colour background) into a clean, natural white-background listing image for Amazon, Shopify, Etsy, and marketplaces. Cuts the product out, removes background colour spill, cleans up and brightens it, and adds a grounded contact shadow, without changing the physical product. Use whenever the user wants to remove a background, cut out a product, clean up a product photo, make a listing or Amazon main image, or put a product on white, even if they don't say "retouch". Not for lifestyle scenes, composites, illustrations, or redesigning the product.
---

# Product image retouch

## Objective

**Retouch the photograph, not the product.** Accurately represent a fresh, representative sample of the product being sold, rather than every incidental flaw of the photographed sample. Target reaction: "This is the same product, just photographed properly."

Default method: **preservation-first natural retouch.** Keep source pixels wherever they already look right. Use masking, despill, tone, cleanup, and reflection reduction first. Limited reconstruction is a scoped exception (see below), never permission to redesign.

---

## Fidelity locks

The source photo is authoritative for product identity and arrangement. Preserve:

- identity, geometry, proportions, construction
- quantity of every retained component
- material identity, inherent texture and finish, colours
- packaging artwork, wording, logo, orientation
- included accessories
- camera angle, perspective, object orientation
- relative scale, placement, overlap

The only exception is a declared, reference-supported damage correction under the Cleanup boundary. Nothing else overrides these locks.

Do not beautify, symmetrize, redesign, or make the product look more premium. Do not add, duplicate, merge, or substitute components; remove objects only per the retention scope. Packaging is a physical reference, not a design brief. Fidelity locks guide refinement; source-derived pixels may be adjusted conventionally, and usable regions should be preserved rather than regenerated where possible. Everything must pass Verification.

---

## Cleanup boundary

This is the single definition of what cleanup may change. Other sections refer to it.

**Removable:** dust, lint, fingerprints, smudges, minor handling scratches, small scuffs, and other incidental surface imperfections a fresh sample would avoid.

**Incidental damage:** minor dents, bends, chips, or warps may be corrected without extra confirmation when they are specific to the photographed sample and an **undamaged reference** clearly establishes the intended shape, finish, and construction. This corrects the sample; it does not idealize the geometry.

**What counts as an undamaged reference:**
- another photo of the same product, supplied by the user or present in the session
- another unit of the same product visible in the same photo

**Not a reference:**
- the model's expectation of what the product "should" look like
- the opposite side of the same object, mirrored
- renders or marketing images, unless the user designates them

Without a qualifying reference, preserve the damage and note it in the Report. Do not stop to ask unless the damage makes the image unusable.

**Preserve:**
- inherent finish and texture: brushed or directional grain, machining or polishing lines, weave, print texture
- construction: seams, welds, rivets, molding marks, folds, edges
- representative features, natural material variation, and defects customers would normally receive

**Tie-break:** repeated patterns and consistent grain are evidence of inherent finish, not proof; a handling scratch can also be directional. Use available references and product context. If unsure, keep the feature.

---

## Naturalism

**Realism over perfection.** Bright, neutral, diffused light with visible midtones and restrained contrast.

- **Metal:** keep uneven reflections, highlight gradients, and both light and dark areas. Never uniform bright chrome.
- **Glass:** keep refraction, edge thickness, slight distortion.
- **Packaging:** keep material texture, folds, print variation.

Avoid CGI look, heavy HDR, glowing edges, artificial sharpness, synthetic texture, perfectly uniform lighting.

---

## Inputs

Use the request and session context first. Ask only when an unresolved detail materially affects faithful representation.

| Input | Default |
|---|---|
| Objects to retain | Product, included accessories, included packaging; exclude known demonstration props. Ask only if inclusion is unclear and affects the main image. |
| Undamaged reference | None. Damage is preserved unless a qualifying reference is available. |
| Intended use | Amazon main image |
| Shadow | Subtle contact shadow |
| Composition | Locked to source; crop may tighten |

If inclusion stays unresolved, don't invent bundle contents or call the image main-listing-ready; note it in the Report.

---

## Method

1. **Inventory** retained components, quantities, packaging, accessories, materials, orientation, distinctive details. **Declare** any damage corrections now: the region, the defect, and the reference. Only declared regions may change shape later.
2. **Edit Plan (automatic, internal).** Classify each major object/region as **PRESERVE**, **CONVENTIONAL RETOUCH**, **GENERATIVE RECONSTRUCTION**, or **EXCLUDE**. PRESERVE keeps source-derived pixels; CONVENTIONAL RETOUCH uses masking, despill, tone, cleanup, and reflection reduction on source-derived pixels; EXCLUDE follows the retention scope. Identify exact reconstruction regions and the legitimate photographic defect or declared reference-supported damage correction that justifies each. Apply the usable-pixel preference and packaging hard lock below before routing tools. Record background replacement and contact-shadow creation separately. The AI determines this plan; no user approval is required in normal operation. Update it only when conventional retouch establishes a justified need for reconstruction.
3. **Mask** retained objects and composite onto `#FFFFFF` at source resolution.
4. **Despill and refine edges.** Remove backdrop tint from edges, reflections, and glass; keep true product colour and believable transparency. No halos, no razor-cut edges.
5. **Tone:** global exposure/white balance/contrast, then gentle local lifts of dark areas and harsh highlights. No heavy dodge/burn on curved surfaces; it changes perceived curvature.
6. **Clean** surface imperfections per the Cleanup boundary. **Reduce** distracting room/photographer reflections without flattening light/dark variation. Preserve source-visible reflections of nearby product objects and packaging, including their reflected colours and shapes; do not erase these interactions when reducing room, photographer, or backdrop contamination.
7. **Reconstruct** only specifically identified regions in the Edit Plan that still fail after steps 4–6, and any declared damage corrections that need new pixels (see below).
8. **Contact shadow** beneath the product, following its footprint and a coherent light direction.
9. **Verify** before crop/resize.
10. **Crop, resize, export**, then inspect the exported file. Deliver only after Verification passes.

These are editing priorities, not a required layer stack. If clipping, blur, or lost detail makes essential geometry unknowable, request a better source; don't invent product facts.

---

## Usable-pixel preference and packaging hard lock

**Usable pixels (preference, not gate):** prefer preserving source pixels wherever they already look right. Use masking, despill, tone, cleanup, and reflection reduction before reaching for generative reconstruction, and keep whole-image regeneration out of the default path. When the only available tool is a whole-image generative editor, use it with the prompt locks below and judge the output by the Verification checks — don't refuse the job because a pixel-preserving path doesn't exist. If the output fails Verification on material drift, re-edit once with tighter prompt locks; if it still fails, note the limitation in the Report rather than looping.

**Packaging hard lock:** packaging containing artwork, logos, or text must remain source-derived; never generatively reconstruct it. Conventional tone, despill, and cleanup are allowed within the existing boundaries. If a broader edit alters packaging, composite the original source-derived packaging back into the output and verify it before delivery. Damage corrections do not override this lock.

---

## Limited reconstruction

Allowed **without confirmation** for two purposes only:
- **Photographic defects** in specifically identified regions that steps 4–6 can't fix naturally: severe environmental reflections in metal or glass, unusably dark surfaces, contaminated highlights, lighting artifacts.
- **Declared, reference-supported damage corrections** from step 1, scoped in the Edit Plan and subject to the packaging hard lock.

Never for a preference for a prettier shape or finish.

**Scope rules:**
- **Prefer masked/regional edits.** Target only the identified affected regions and preserve source-derived pixels outside them. Composite only corrected regions back into the source-derived image when necessary. Do not send the whole product through generation merely for convenience. When only a whole-image generative tool is available, use explicit prompt locks and judge the output by Verification — don't refuse the job.
- **Fidelity boundary.** Scope is limited by what changes, not surface area alone. A broad reflection correction may be necessary without changing product facts. Stop and request a better source or reference when identity, geometry, finish, construction, or source-derived packaging cannot be preserved and verified. Broader coverage requires closer verification, not automatic approval.
- **Never** generatively reconstruct packaging containing artwork, logos, or text; never guess hidden construction or missing detail.
- All Fidelity locks and the Cleanup boundary apply.

**Prompts.** Use the variant that matches the job. Add the damage clause only for declared corrections, and supply the reference image to the editor with it.

Photographic defect:

> Use the supplied photograph as the authoritative reference. Only correct the photographic appearance of the selected region: [defect, e.g. backdrop reflection on the lid]. Keep the product's geometry, edges, inherent finish, texture, and unaffected details unchanged. Render soft, neutral, believable softbox-style light with realistic light/dark variation. Do not reshape, redesign, smooth away texture, symmetrize, or invent detail. No CGI appearance.

Damage clause (append only for a declared correction):

> In [region], the photographed sample has [defect, e.g. a small dent in the rim]. Restore only that region to the form shown in the supplied reference image. Change nothing outside it.

Every reconstructed region is listed in the Report and gets extra scrutiny in the overlay check.

---

## Verification

**Automatic self-check, not user approval.** Run the checks before delivery. Re-edit outputs that fail on material drift (as defined in the overlay check); for marginal cases, deliver with a note in the Report rather than looping. Ask the user only when source/product facts are genuinely unknowable or required fidelity cannot be achieved with available tools, not to approve the Edit Plan, reconstruction routing, or verification.

- **Overlay** output on source at ~50% opacity before crop (translation and uniform scale only). Silhouettes, feature edges, placement, construction, and orientation should align outside the reconstruction regions. Expect some sub-pixel drift from resampling; judge drift by whether the product reads as the same item at normal viewing size and 100%, not by a bit-exact match. Only damage corrections declared in step 1 may change shape, and those must be checked against their reference separately. Tone differences are expected. If tools can't overlay, compare side by side and say so.
- **Component count** matches inventory.
- **Spill:** no backdrop tint; true colour kept.
- **Edges:** no halos, fringing, or clipped detail at 100%.
- **Packaging:** wording, artwork, logo unchanged; no invented legibility.
- **Cleanup:** inherent and representative features remain; damage corrections match the reference without upgrading the product.

**Re-edit before delivery if any of these happen as visible material drift:** geometry visibly changed outside declared damage-correction regions, symmetrization, redesigned shape, components moved or substituted, altered packaging, metal went chrome/CGI, texture went synthetic, or lighting went dramatic. If re-edit fails the same check twice, deliver the better of the two with the limitation noted in the Report — don't regenerate indefinitely.

Final check, at normal size and 100%, both must be yes before delivery:
> Does this faithfully represent the product being sold, including its inherent features and included items?
> Does it look like the same product and arrangement, photographed better?

---

## Report

After delivering, state briefly (omit empty items):
- objects excluded, and any unresolved inclusion
- regions reconstructed; damage corrected, with the reference used
- damage preserved for lack of a reference
- checks not performed
- output specs not met (e.g. source resolution too low)
- tool limitations encountered (e.g. only whole-image generation available; sub-pixel drift accepted)

---

## Output spec

- 2000 × 2000 px, square; PNG flattened on `#FFFFFF`, no alpha; sRGB
- Product ~85% of frame where shape permits, room for shadow, no clipping
- No aggressive upscaling or invented texture

## Amazon main image

Pure white; no promotional text, badges, graphics, borders, or scene. Keep text printed on the product or included packaging. Show only the product and included accessories/packaging; exclude demonstration props (e.g. a glass not included). Reconstruction must not introduce features, finishes, accessories, or packaging details absent from the real product. This is not a guarantee of category-specific acceptance.

---

## Gotchas

- **Despill before judging tone.** Stainless and glass mirror the backdrop.
- **Brushed finish looks like scratches.** Apply the Cleanup tie-break.
- **Mirroring is symmetrizing.** The other side of the same object is not a damage reference.
- **Editors over-read repair language.** Keep the damage clause out of prompts that aren't fixing declared damage.
- **Whole-image generative editors drift silently.** Prefer regional edits or compositing when possible; when whole-image regeneration is the only option, use explicit prompt locks and judge by Verification. Re-edit outputs that drift materially — don't loop on sub-pixel differences.
- **Over-polish is product drift.** Fidelity beats polish; realism beats perfection.

## Tools

Prefer pixel-preserving masking and adjustment tools for the default path; use a source-referenced generative editor only when the task requires reconstruction or when nothing else is available. Judge all outputs by Verification, not by tool choice. Note tool limitations in the Report.

**Shooting tip:** light grey or white backdrop and diffused daylight cut spill and dark metal at the source.

---

## Version history

- v2.0 — 2026-11-08 — Rewrite based on draft iteration SKILL7 (session Oct 2 2026). Added: region-by-region Edit Plan (PRESERVE / CONVENTIONAL RETOUCH / GENERATIVE RECONSTRUCTION / EXCLUDE), Cleanup boundary with damage-correction-with-reference rule, packaging hard lock, Report after delivery, and specific prompt templates for photographic defects and damage corrections. Softened two SKILL7 clauses that would reject most generative-editor outputs: the usable-pixel rule is now a preference rather than a gate; overlay verification judges material drift rather than bit-exact alignment, with a two-attempt ceiling before accepting the better output with a Report note. Supersedes v1.0 (frozen at commit 458f2f5 for rollback).
- v1.0 — 2026-11-08 — Adopted into `gwaiblade/craft/skills/product-image-retouch/` per CANON_SKILL. Pre-adoption draft had YAML frontmatter (`name`, `description`) and structured sections (Objective, Product fidelity rule, Naturalism rule, Composition lock, Permitted improvements, Lighting target, Background, Reconstruction strength, Method, Verification, Output spec, Amazon main image guidance, Prompt construction, Gotchas); format mirrored sibling skill `product-image-extraction` and was preserved intact on adoption.

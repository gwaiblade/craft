# Amazon A+ Visual Assets Prompt Creator

**Purpose:** Generate a complete AI image prompt system for an Amazon A+ listing from the Section 9 Visual Brief Handoff. Output is one evaluated, copyable prompt or design brief per module — a cohesive visual system, not disconnected images.

**When to run:** After completing the `amazon-aplus-content` protocol, with its Section 9 block in hand.

**Inputs:** Section 9 Session Context (9A + 9B + 9C); product reference images; optional style references; module Visual Briefs pasted one at a time.

**Output:** Per-module prompt blocks (Session Header + Per-Image Payload) or design briefs, each scored and approved via the evaluation gate.

**Skills called:** none

**Version:** 2.1

---

## Purpose

Generate a complete AI image prompt system for an Amazon A+ listing, based on the strategy and visual briefs produced by the **Amazon A+ Content protocol (`amazon-aplus-content`)**.

This document handles:

• receiving the Visual Brief Handoff from the Protocol  
• collecting product reference images  
• confirming and developing lifestyle directions  
• designing listing image structure  
• building composition plans per image  
• generating AI image prompts for every asset

The output is a **cohesive, conversion-focused visual system** — not disconnected individual images.

# OPENING — HARD GATE: REQUEST SECTION 9

When the user initiates this protocol, respond **immediately and only** with:

> "Welcome to the Visual Assets Prompt Creator. To begin, please paste your **Section 9 Session Context** (the combined 9A + 9B + 9C block) from the CANON CONTENTDESIGN Amazon A+ Content Protocol."

**Do not proceed to any step. Do not ask for images. Do not ask about style. Wait.**

If the user tries to proceed without pasting Section 9, respond:

> "I need the Section 9 context block before we can start — it contains the product profile, visual pillars, and narrative ladder that everything else is built from. Please paste it and we'll get going."

If the user has not run the Protocol yet, respond:

> "It looks like the A+ Content Protocol hasn't been run yet. Please run it first: Run CANON CONTENTDESIGN Amazon A+ for \[Product Name or ASIN\] Once it's complete, copy the Section 9 block from the output and paste it here."

# STEP 0 — CONFIRM SECTION 9 RECEIPT

Once the user pastes the Section 9 block, confirm receipt by outputting a brief structured summary:

> "Section 9 loaded. Here's what I have:
>
> **Product:** \[Product Name\] — \[Category\] **Positioning:** \[Brand Positioning\] **Target Customer:** \[Target Customer\] **Physical Description:** \[one-line summary — shape, material, color\]
>
> **Visual Narrative Pillars:** \[list pillar names\]
>
> **Narrative Ladder Stages:** \[list stages\]
>
> Does this look correct? If anything is off, let me know before we continue."

Only proceed to Step 0A after the user confirms the summary is correct.

# STEP 0A — PRODUCT IMAGE ASSETS

Ask the user to upload product reference images.

**Required:**

• Primary product photo (mandatory)

**Optional but recommended:**

• Additional angles • Packaging image • Brand logo

**Important:**

The product must remain **pixel-faithful** to the reference images in all generated scenes.

Do not alter:

• proportions • curvature • thickness • materials • surface texture • product geometry

# STEP 0B — STYLE REFERENCES

Ask the user:

**Do you have any visual style references to share?**

This may include:

• Inspiration images (mood, lighting, scene direction) • Competitor listings with visuals you want to match or differentiate from • Brand photography guidelines or lookbooks • Color palette or texture references

| **Reference Type**           | **Provided?** | **Notes** |
|------------------------------|---------------|-----------|
| Mood / inspiration images    | Yes / No      |           |
| Competitor visual examples   | Yes / No      |           |
| Brand photography guidelines | Yes / No      |           |
| Color or texture references  | Yes / No      |           |

If style references are provided, extract the following and apply them throughout composition planning and prompt generation:

• Dominant color palette • Lighting character (hard / soft / warm / cool / natural / studio) • Scene density (minimal / layered / busy) • Overall mood

If no style references are provided, continue. Visual style will be determined by brand positioning and the style selection in Step 1.

# STEP 1 — STYLE SELECTION

Once Section 9 is confirmed, ask the user to select a visual style.

This populates the BRAND VISUAL STYLE field in the Session Header and applies consistently across all prompts.

> "Before we build the Session Header — please select the visual style for this project:"

| **Style**          | **Description**                                            | **Best For**             |
|--------------------|------------------------------------------------------------|--------------------------|
| High-End Editorial | Clean, controlled studio light, minimal props, luxury feel | Premium positioning      |
| Food Integrated    | Product surrounded by ingredients, cooking action, steam   | Food and cookware        |
| Product Placement  | Product naturally present in a lived-in scene              | Everyday / lifestyle     |
| Flat Lay           | Overhead, styled surface, organized composition            | Detail and feature shots |

Note: If different image types need different styles (e.g. Food Integrated for lifestyle shots, Flat Lay for feature tiles), the user can specify — apply per module accordingly.

**Style language blocks** (appended to Session Header and relevant Per-Image Payloads):

*High-End Editorial:*

Studio controlled lighting. Minimal background. Clean shadows.

Premium material emphasis. No clutter.

*Food Integrated:*

Food styling present. Steam or cooking action visible.

Ingredients as supporting props. Warm ambient light.

*Product Placement:*

Lived-in natural environment. Product in casual use context.

Ambient available light. Imperfect, authentic scene.

*Flat Lay:*

Overhead 90-degree angle. Styled flat surface.

Symmetrical or intentional asymmetric arrangement.

Clean negative space for copy overlay.

# STEP 1B — AUTHENTICITY LEVEL

After style is selected, ask the user to choose an authenticity level.

This controls the visual aesthetic of all photography prompts — how produced vs. organic the images feel. It is appended to the Session Header and carried into every photography prompt.

> "What authenticity level best fits this brand?"

| **Level**                | **Description**                                                                     | **Feel**                                  |
|--------------------------|-------------------------------------------------------------------------------------|-------------------------------------------|
| **Studio Polished**      | Fully controlled environment, professional lighting, clean surfaces, styled props   | High-end commercial, aspirational         |
| **Editorial / Campaign** | Intentional but not sterile — human presence, styled imperfection, magazine-quality | Lifestyle brand, premium but approachable |
| **Instagram Organic**    | Natural light, real environments, casual framing, lived-in details                  | Relatable, community-built, trust-forward |
| **User-Generated (UGC)** | Shot-on-phone aesthetic, imperfect angles, no visible production, raw authenticity  | Social proof, peer-to-peer trust          |

**Authenticity language blocks** (appended to Session Header):

*Studio Polished:*

AUTHENTICITY BENCHMARK: The standard is a hero shot from a premium cookware or kitchen brand campaign —

think Made In, Staub, or Le Creuset product photography. Lighting is fully controlled and intentional.

Every surface, prop, and shadow placement is deliberate. Nothing accidental in the frame.

The image should look like it cost money to produce.

*Editorial / Campaign:*

AUTHENTICITY BENCHMARK: The standard is a well-art-directed magazine spread — not a stock photo,

not a product catalog shot. Human presence or traces of use are welcome. Imperfection is intentional,

not accidental. The image should feel like it was made by a creative director with a point of view,

not assembled from defaults.

*Instagram Organic:*

AUTHENTICITY BENCHMARK: The standard is a highly-engaged food or lifestyle creator's feed —

shot in real environments with available light, casual framing, and lived-in details that feel

discovered rather than constructed. It should look like a real person's kitchen, not a set.

Color tones are natural. Nothing feels retouched or perfected.

*User-Generated (UGC):*

AUTHENTICITY BENCHMARK: The standard is a genuine customer photo that went viral because it felt

so real — slightly imperfect exposure, unconventional angle, no visible production infrastructure.

It must be indistinguishable from a photo taken by an enthusiastic buyer on their phone.

Any trace of professional production breaks the illusion entirely.

# STEP 2 — BUILD SESSION HEADER

Once product images, style references, and style selection are confirmed, build the Session Header.

The Session Header is built **once** and carried into every prompt without modification.

=== SESSION HEADER ===

PROJECT: \[Product Name\] — Amazon A+ Visual System

PRODUCT DESCRIPTION:

\[From 9A — Product Physical Description.

Shape, material, color, finish, dimensions, distinctive features.\]

PRODUCT FIDELITY:

The product must remain pixel-faithful to the reference image provided.

Do not alter proportions, curvature, thickness, materials, surface texture, or product geometry.

Do not reinterpret the product shape or finish in any way.

BRAND VISUAL STYLE:

\[Confirmed style name — e.g. Food Integrated\]

\[Style language block from Step 1\]

\[Style reference notes from Step 0B, if provided\]

AUTHENTICITY LEVEL:

\[Confirmed level name — e.g. Editorial / Campaign\]

\[Authenticity language block from Step 1B\]

GLOBAL RESTRICTIONS:

Ultra realistic commercial lifestyle photography only.

No illustration.

No CGI look.

No cartoon style.

No HDR effect.

No exaggerated reflections.

No artificial textures.

DO NOT PRODUCE — COMMON AI AESTHETIC TELLS (any of these is a failure):

\- Harsh rim lighting that makes the product glow unnaturally

\- Impossibly perfect steam or smoke with no turbulence

\- Oversaturated food colors that look lacquered, not real

\- Perfectly symmetrical prop arrangements — real kitchens are never perfectly symmetrical

\- Marble surfaces with overly dramatic veining used as a default

\- Floating or disconnected shadows that don't match the light source

\- Bokeh so extreme it looks like a composited background

\- Hands or people that look anatomically wrong or blurred to hide errors

\- Ingredients or props that look 3D-rendered rather than photographed

\- Any purple or teal gradient — a signature default of AI image generators

\- Clean white cards or white vignettes used as a default background

\- Typography or text appearing anywhere in the image unless explicitly requested

CONSISTENCY LOCK: \[Leave blank until first module is approved.\]

\- Approved lighting:

\- Approved color temperature:

\- Approved surface / background:

\- Product rendering notes:

=== END SESSION HEADER ===

Output the completed Session Header to the user. Then **stop**.

Prompt the user:

> "Session Header is ready. Please paste the Visual Brief for the first module you'd like to generate — I'll build the prompt for it."

**Do not proceed further until the user pastes a module brief.**

# STEP 3 — MODULE SIZE COMPOSITION RULES

*Reference table — apply when expanding each module brief into a composition plan.*

| **Module Size** | **Composition Rule**                                                              |
|-----------------|-----------------------------------------------------------------------------------|
| 1464 × 600      | Cinematic widescreen — place key subject in left two-thirds, breathing room right |
| 970 × 600       | Hero lifestyle — product centered or slightly left, scene fills background        |
| 970 × 300       | Horizontal strip — product anchored left or right, copy space on opposite side    |
| 300 × 300       | Square — product centered, minimal background distraction                         |
| 220 × 220       | Tight square — single feature detail, macro framing                               |

# STEP 4 — PER-MODULE GENERATION LOOP

This step repeats for every module until the user is done.

## 4A — RECEIVE MODULE VISUAL SUGGESTION

The user pastes a single module Visual Suggestion from Section 9D of the Protocol output.

The suggestion will vary in format depending on its Visual Type. Before expanding, identify the Visual Type:

| **Visual Type**                           | **Handling**                                                                              |
|-------------------------------------------|-------------------------------------------------------------------------------------------|
| Photography (Lifestyle / Studio / Action) | Expand into full prompt using Session Header + Per-Image Payload                          |
| Annotated Photo                           | Generate photography prompt for base image, then list annotations as overlay instructions |
| Infographic / Chart                       | Output a structured design brief — not an AI photography prompt                           |
| Diagram / Illustration                    | Output a structured design brief — not an AI photography prompt                           |
| Graphic / Text-led                        | Output a structured design brief — not an AI photography prompt                           |

For non-photography types, skip the Per-Image Payload format and instead output a **Design Brief** (Step 4C-Alt).

## 4B — EXPAND INTO COMPOSITION PLAN

*For photography types only.*

Using the Visual Suggestion and the composition rule for its module size (Step 3), expand into a full composition plan:

Module: \[name\]

Visual Type: \[confirmed type\]

Insight Used: \[from Insight Source field — state specifically how this drives the scene\]

Scene: \[expanded from suggestion\]

Camera Angle: \[from suggestion\]

Lens: \[from suggestion — confirm it suits the scene type\]

Framing: \[tight / mid / wide — derived from module size rule\]

Lighting: \[from suggestion — note quality, direction, temperature\]

Props: \[from suggestion, with each prop's specific role noted\]

Product Visibility: \[Hero / Integrated / Supporting\]

Key Message: \[from suggestion\]

Module Size: \[pixel dimensions\]

## 4C — BUILD PER-IMAGE PAYLOAD

*For photography types only.*

Format the composition plan as a Per-Image Payload:

=== IMAGE: \[Module Name\] ===

Scene:

Composition:

Camera Angle:

Lighting:

Props:

Lens:

Product Visibility:

Key Message:

Module Size:

=== END IMAGE PAYLOAD ===

## 4C-ALT — BUILD DESIGN BRIEF

*For non-photography types (Infographic, Diagram, Graphic, Annotated Photo).*

Output a structured design brief instead of a photography prompt:

=== DESIGN BRIEF: \[Module Name\] ===

Visual Type: \[Infographic / Chart / Diagram / Illustration / Graphic / Annotated Photo\]

Insight This Solves: \[from Insight Source\]

What It Must Prove: \[Key Message from suggestion\]

Content / Data:

\[Exact content, numbers, labels, or claims to include\]

Layout:

\[Describe structure — e.g. 3-column comparison, left-right split, centered with callouts\]

Visual Style:

\[Clean line / flat color / brand palette / minimal / bold typography\]

Typography Notes:

\[Any specific hierarchy — e.g. large stat number, supporting label below\]

Overlay / Annotation Notes: \[if annotated photo — list each callout and what it indicates\]

Module Size: \[pixel dimensions\]

=== END DESIGN BRIEF ===

## 4D — OUTPUT COMPLETE PROMPT OR DESIGN BRIEF

**For photography modules** — output as a single copyable block labeled:

PROMPT — \[Module Name\]

\[SESSION HEADER — in full\]

\[PER-IMAGE PAYLOAD — in full\]

**For non-photography modules** — output the Design Brief as a standalone block labeled:

DESIGN BRIEF — \[Module Name\]

\[DESIGN BRIEF — in full\]

Design briefs do not use the Session Header — they are standalone instructions for a designer or design tool.

## 4E — APPROVAL, SCORING, AND STRATEGIC DECISION

After outputting the prompt, run the following evaluation before asking the user to proceed.

### Evaluation Criteria

Score each criterion from 1–5. State the score and a one-line reason.

**1. Product Fidelity** — Does the prompt faithfully describe the product as it appears in the reference image? Does it protect against any known AI distortion risks for this product type?

| **Score** | **Meaning**                                                                |
|-----------|----------------------------------------------------------------------------|
| 5         | Every distinctive physical detail is locked. No room for reinterpretation. |
| 3         | Core shape and material described, but some details are vague or missing.  |
| 1         | Generic product description. AI could render a different product entirely. |

**2. Distinctiveness** — Could this image belong to any competitor's listing, or is it specific to this product, positioning, and insight?

| **Score** | **Meaning**                                                                         |
|-----------|-------------------------------------------------------------------------------------|
| 5         | Scene, props, and angle are derived directly from a specific insight. Unrepeatable. |
| 3         | Competent scene direction but could apply to multiple similar products.             |
| 1         | Generic lifestyle or studio setup. No evidence of research grounding.               |

**3. Authenticity Match** — Does the prompt actively guide toward the selected authenticity level, or would the output likely look AI-produced regardless?

| **Score** | **Meaning**                                                                           |
|-----------|---------------------------------------------------------------------------------------|
| 5         | Prompt language directly counters the AI aesthetic tells for this authenticity level. |
| 3         | Authenticity level is named but not enforced through specific prompt language.        |
| 1         | No authenticity direction. Default AI aesthetic is likely.                            |

**4. Key Message Clarity** — If the image is generated and the copy is removed, will the viewer understand what this module is communicating?

| **Score** | **Meaning**                                                          |
|-----------|----------------------------------------------------------------------|
| 5         | Scene and composition alone carry the key message without ambiguity. |
| 3         | Message is implied but depends on copy to complete it.               |
| 1         | Image direction is decorative — no clear message without text.       |

### Scoring Output Format

Output the evaluation as:

EVALUATION — \[Module Name\]

Product Fidelity: \[1–5\] — \[one-line reason\]

Distinctiveness: \[1–5\] — \[one-line reason\]

Authenticity Match: \[1–5\] — \[one-line reason\]

Key Message Clarity: \[1–5\] — \[one-line reason\]

Total: \[sum\] / 20

Assessment: \[APPROVE / REVISE / PIVOT\]

### Strategic Decision Gate

**If Total ≥ 16 — APPROVE**

> "Prompt looks strong. Does this work for you, or any final adjustments before we lock it?"

If user confirms, update the Consistency Lock (first module only) and move to the next module.

**If Total 11–15 — REVISE**

Identify the lowest-scoring criterion and revise that specific element of the prompt. Output the revised prompt and re-evaluate. Do not ask the user — revise once automatically, then present.

> "I've revised the prompt to improve \[criterion\]. Here's the updated version: \[revised prompt + new scores\]."

**If Total ≤ 10, or after one REVISE cycle the score does not improve — PIVOT**

Do not iterate further on the same direction. Propose a fundamentally different visual approach for this module:

> "This direction isn't landing well on \[weakest criteria\]. I'd recommend a different approach for this module — here's what I'm thinking: \[brief description of alternate visual type, scene, or concept\]. Want me to build that out instead?"

Wait for user confirmation before generating the pivoted prompt.

### After Approval

1.  If this is the **first module approved**, prompt:

> "Please note the visual details you want locked — lighting, color temperature, surface/background, and any product rendering observations. I'll add them to the Session Header's Consistency Lock."
>
> Update the Consistency Lock. All subsequent prompts carry the updated header.

2.  Ask:

> "Please paste the Visual Suggestion for the next module, or let me know if you're done."

3.  Return to **Step 4A**.

# FINAL OUTPUT

Each module produces one labeled, copyable prompt block — **Session Header + Per-Image Payload**.

Prompts are generated one at a time, in the order the user provides module briefs.

No bulk generation. No pre-planning. Each prompt is reviewed and approved before the next begins.

*End of CANON DESIGN — Amazon A+ Content Visual Assets Prompt Creator*

---

# VERSION HISTORY

- v2.1 — 2026-08-09 — Adopted into `gwaiblade/craft/protocols/amazon-aplus-visual-assets/` per CANON_PROTOCOL. Renamed from CANON DESIGN — Amazon A+ Content Visual Assets Prompt Creator. Canonical header block added; upstream references updated to `amazon-aplus-content`. Content otherwise unchanged from v2. Cranberry's `aplus-visual-assets` v3.0 is an independent fork of this line.
- v2 — Pre-adoption version (source .docx). Hard gate on Section 9, authenticity levels with benchmark blocks, AI-tells blocklist, scoring gate with APPROVE/REVISE/PIVOT, consistency lock.
- v1 — Initial protocol.

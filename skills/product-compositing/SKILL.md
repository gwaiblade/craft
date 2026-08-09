# Product compositing (lifestyle integration)

**When to use:** Integrating an extracted product image (typically from a white-background photo — see `remove-background`) into a lifestyle environment for e-commerce, A+ content, social visuals, or brand campaigns. The goal is **product integrity with realistic photographic integration** — the product must remain exactly itself while the scene around it looks genuinely photographed.

**Rules (non-negotiable — apply in every mode):**

- The product must remain **pixel-accurate and proportionally identical** to the source image
- Do NOT: resize disproportionately, stretch or compress geometry, redesign handles/lids/spouts/rivets/rims/packaging, modify branding or typography, artificially smooth texture, add unrealistic or CGI gloss
- Only adjust: lighting, shadows, color temperature, environmental reflections (and food placement, in Food-Integrated mode)
- The final image must resemble a **real photograph**: no CGI perfection, no HDR effect, no oversaturation, no artificial lighting behavior. Allow subtle imperfections.

**Tools I use:**

- Generative image models with reference-image input — compositing is prompt-driven; the mode blocks below are the prompt vocabulary
- `remove-background` skill upstream for the product extraction itself

**Method:**

1. Start from a clean product extraction (pixel-faithful, per `remove-background`)
2. Select a mode: **Master Lifestyle** (default), **High-End Editorial**, or **Food-Integrated**
3. Define the scene using the mode's variable menus: environment, surface, background depth, camera angle, lens feel, negative space, light source, light direction, shadow strength, mood, props
4. Generate with the shared Rules plus the mode's specific constraints; use the mode's short-form execution line as the prompt backbone
5. QC: shadows and reflections match the light direction, product geometry untouched, scale of props believable, nothing reads as AI-rendered

**Gotchas:**

- Floating or disconnected shadows that don't match the scene's light source are the fastest realism killer
- Reflections and highlights must align with the environmental light direction — no generic shine, no floating highlights
- Props must respect physical scale; a slightly wrong-sized napkin or utensil breaks the whole composite
- In food scenes: food must conform to the vessel's geometry — no floating, intersecting, or boundary-ignoring food; steam must be subtle, irregular, and fade naturally upward
- Avoid overly stylized environments in lifestyle mode and storytelling clutter in editorial mode — each mode has a distinct failure direction

---

## MODE 1 — MASTER LIFESTYLE (default)

Standard lifestyle integration for e-commerce, A+ content, and social visuals.

**Environment / Setting:** kitchen stove, outdoor camp, café counter, wooden dining table, marble countertop

**Surface material:** oak wood, linen, quartz, stone, concrete

**Background depth:** shallow depth of field / medium blur / deep focus

**Camera angle:** 90° flat lay / 45° lifestyle / eye level / slightly lower angle

**Lens feel:** 35mm natural / 50mm neutral / 85mm compressed

**Negative space:** more top / more bottom / more left / more right / balanced / square crop / 4:5 crop

**Light source:** soft window light / sunny outdoor / warm indoor / neutral daylight

**Light direction:** left / right / backlit / top

**Shadow strength:** very soft / natural / defined

**Mood:** casual authentic, premium minimal, rustic, cozy, clean commercial. Avoid overly stylized environments.

**Props:** specify clearly whether packaging and accessories are removed. Optional: cloth napkin, ingredients, condiments, kitchen tools. Props must support the scene, not overpower the product, and respect physical scale.

**Short-form execution:**

> Place the product in the specified environment with realistic lighting, natural shadows, and believable environmental integration. Maintain exact proportions and avoid redesign.

---

## MODE 2 — HIGH-END EDITORIAL

For brand campaigns, hero website visuals, and premium marketing imagery. Focus: **elevated composition and controlled lighting** — magazine photography, not e-commerce catalog.

**Additional constraint:** reflections and highlights must align with the environmental light direction. No floating highlights or generic shine.

**Environment / Setting:** intentional and refined — architectural interior, marble slab, dark walnut table, stone surface, minimal studio texture

**Surface material:** premium tactile materials only. Avoid cluttered counters or busy environments.

**Background depth:** shallow depth of field preferred; clear subject separation; background supports composition, never competes

**Camera angle:** slightly lower hero angle / slightly elevated editorial angle / controlled dramatic 45°. Avoid neutral catalog eye-level.

**Lens feel:** 50–85mm compression preferred; product should visually dominate the frame

**Negative space:** intentional and graphic, often supporting layout or copy — more space above, rule-of-thirds framing, centered hero composition

**Light source:** sculpted window light / directional natural light / controlled contrast lighting. A **single dominant direction** drives the lighting.

**Shadow strength:** natural to slightly defined — depth without artificiality. Avoid flat lighting, even studio wash, overexposed highlights.

**Mood:** premium, refined, elevated, architectural

**Props:** minimal and intentional — subtle background materials, architectural textures, supporting surface elements. Avoid storytelling clutter, multiple competing objects, overly styled lifestyle props. The product remains the focal point.

**Realism:** allow natural light falloff, subtle shadow variation, minor environmental imperfections.

**Short-form execution:**

> Place the product in a premium minimal environment using sculpted directional lighting, shallow depth of field, and intentional negative space. Maintain exact proportions and realistic photographic behavior.

---

## MODE 3 — FOOD-INTEGRATED

For cookware or vessels containing food. Focus: **food realism and cooking authenticity.**

**Additional constraint:** food must conform naturally to the container geometry — no floating, intersecting, or ignoring the physical boundaries of the vessel. Food placement is an allowed adjustment in this mode.

**Environment / Setting:** realistic cooking or serving environments — kitchen stove, outdoor camp cooking setup, wooden dining table, rustic kitchen board, café preparation counter

**Surface material:** appropriate for cooking or serving — wood, stone, stove grate, ceramic countertop

**Background depth:** medium depth of field preferred; shallow allowed for food emphasis. The vessel and food remain the visual focus.

**Camera angle:** 45° preferred / slightly lower angle for depth / flat lay only when composition requires it

**Lens feel:** 35–50mm natural perspective. Avoid extreme wide-angle distortion.

**Negative space:** balanced composition supporting the food presentation — slight space above, balanced framing around the vessel

**Light source:** soft window light / natural daylight / warm cooking light. Direction must remain consistent between shadows on the food and on the vessel.

**Shadow strength:** natural and soft. Avoid harsh specular highlights on liquids and artificial gloss on food surfaces.

**Mood:** authentic, appetizing, natural, casual. Food should appear **fresh and edible**, not stylized like a render.

**Props:** minimal and realistic — garnish, peripheral condiments, cooking utensils, ingredients related to the dish. No floating garnish, no unrealistic ingredient stacking; ingredients naturally placed, supporting the cooking context.

**Realism:** food surfaces show irregular textures, natural ingredient layering, non-uniform liquid surfaces. Steam is subtle, irregular, fades naturally upward. Avoid CGI gloss, perfect symmetry, artificial saturation, unrealistic liquid surfaces.

**Short-form execution:**

> Integrate realistic food inside the vessel using natural ingredient placement, irregular textures, subtle steam, and authentic cooking lighting. Maintain exact product proportions and realistic photographic behavior.

---

## Version history

- v1.1 — 2026-08-09 — Adopted into `gwaiblade/craft/skills/product-compositing/` per CANON_SKILL. Reclassified from three protocols (Master Lifestyle, High-End Editorial, Food-Integrated) to one skill with three modes; shared Product Protection and Realism rules consolidated into the Rules section. Content otherwise unchanged.
- v1.0 — 2026-03-29 — Source document: Product Lifestyle Compositing Protocols (three-protocol structure).

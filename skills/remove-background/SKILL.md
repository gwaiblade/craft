# Remove background (product extraction)

**When to use:** Extracting a product from a photo for e-commerce use (Amazon, Shopify, marketplaces) where the output must be pixel-faithful to the physical item. The objective is **extraction, not recreation** — accurate representation aligns customer expectation, keeps listings marketplace-compliant, and reduces mismatch returns.

**Rules (non-negotiable):**

- Never alter proportions, curvature, thickness, geometry, reflections, metal grain, surface texture, or highlights/shadows intrinsic to the product
- No redesign, surface smoothing, reconstruction, geometry correction, artificial relighting that changes form perception, or AI beautification
- Allowed adjustments only: full background removal → pure white (#FFFFFF); realistic contact shadow (follows footprint, respects original light direction, subtle); **global-only** tone adjustments (exposure, contrast, white balance, clarity) that don't touch surface detail

**Tools I use:**

- PhotoRoom Pro — default masking tool
- Adobe Photoshop (Select Subject + Refine Edge) — complex edges, manual control
- ClipDrop Background Remover / Remove.bg — quick passes on simple subjects
- Generative AI — composition assistance only, never extraction (see Gotchas)

**Method:**

1. Decide before touching the image:
   - Integrity mode — strict pixel-faithful extraction (default), or controlled reconstruction explicitly allowed
   - Intended use — Amazon main, Amazon secondary, infographic base, lifestyle composite, or ad asset
   - Objects to retain — explicit list (e.g. pot, lid, chopsticks, packaging)
   - Shadow level — subtle (Amazon-safe), medium premium, or dramatic studio
2. Mask and remove the background completely using a non-generative tool
3. Place retained objects on pure white, geometry untouched
4. Add contact shadow — product footprint, original light direction, natural weight
5. Global tone pass if needed
6. QC before export: geometry unchanged, reflections authentic, metal grain preserved, edges clean, shadow natural, no artifacts, image matches the physical item exactly
7. Export high-resolution, sized for the marketplace

**Gotchas:**

- Generative models **reconstruct objects rather than mask them** — their output is a studio recreation, not pixel preservation. Fine for composites, disqualifying for authentic extraction.
- Amazon main image rules: pure white background, product fills ~85% of frame, no props, no text, no graphics. Packaging may appear only if it's included in the purchase.
- Metal and reflective surfaces lose grain quietly — "refine edge" and clarity sliders smooth texture without you noticing. Zoom-check at 100% during QC.
- A contact shadow that ignores the original light direction reads fake instantly and undermines the whole extraction.

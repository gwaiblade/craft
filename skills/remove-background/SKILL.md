---
name: product-image-extraction
description: Extract a product from a photo onto a pure white background for e-commerce listings (Amazon, Shopify, marketplaces), preserving pixel-faithful integrity of the product. Use when the user asks to remove a background, cut out a product, prepare a listing image, or make an Amazon main image. Do not use for lifestyle composites, illustrations, or any task where the product may be redrawn or restyled.
---

# Product image extraction

**Objective: extraction, not recreation.** The output must depict the physical item exactly as photographed. Accurate representation aligns customer expectation, keeps listings marketplace-compliant, and reduces mismatch returns.

## Integrity rule (non-negotiable)

Every pixel inside the retained subject mask must be identical to the source, except for a declared global tone transform applied uniformly to the whole image.

Never alter proportions, curvature, thickness, geometry, reflections, metal grain, surface texture, or highlights and shadows intrinsic to the product. No redesign, surface smoothing, reconstruction, geometry correction, artificial relighting, or AI beautification.

This rule is enforced by **output check**, not by tool choice — see Verification. Any tool is permissible if its output passes. In practice, generative fill, inpaint, and outpaint will not pass, because they synthesize pixels rather than mask them.

## Permitted operations

- **Background removal.** Full removal, replaced with pure white `#FFFFFF`.
- **Global tone transform.** Exposure, contrast, white balance, clarity. Must be a single transform applied uniformly to every pixel. No local, masked, region-selective, or auto-enhance adjustments.
- **Contact shadow.** Rendered on the background layer only, never composited over product pixels. Follows the product footprint, respects the original light direction, subtle by default.

Nothing else.

## Inputs to resolve before processing

Ask the user. If the session is non-interactive, apply the stated default.

| Input | Default |
|---|---|
| Integrity mode | **Strict** (pixel-faithful). Controlled reconstruction only if explicitly requested. |
| Objects to retain | **None — abort and request.** There is no safe guess. |
| Intended use | Amazon main image |
| Shadow level | Subtle |

Shadow levels: subtle (Amazon-safe), medium premium, dramatic studio.

## Method

Order matters. Steps 1–3 establish the reference the verification in step 6 depends on.

1. Segment the product. Produce an alpha mask covering exactly the objects to retain.
2. Composite the masked subject onto pure white at source resolution. **Do not resize or tone-adjust yet.**
3. Verify integrity now, against the source (see Verification). A failure here is unrecoverable — go back to step 1 with a different tool.
4. Render the contact shadow onto the white background layer, beneath the subject.
5. Apply the global tone transform, if any, to the full canvas.
6. Resize and export.

Tone and resize come last because both change pixel values everywhere and destroy the ability to diff against the source.

## Verification

**Mechanical gates, run at step 3, before tone and resize:**

- Masked-interior diff against the source is zero. Every retained pixel is bit-identical.
- Mask edges show no partial-alpha halo beyond ~2 px, and no residual background color fringing.
- No retained object is clipped by the source frame.

**Reject the source rather than repair it.** If the photo has motion blur, a cropped product, or an unrecoverable background, stop and say so. Fixing any of these requires geometry correction or reconstruction, which the integrity rule forbids.

**Human sign-off, before publishing:**

- Reflections and metal grain read as authentic at 100% zoom
- Shadow direction matches the original light
- The image matches the physical item

## Output spec

- **2000 × 2000 px**, square canvas
- **PNG**, flattened on `#FFFFFF`. No alpha channel in the deliverable.
- sRGB
- Product **plus its shadow** occupies ~85% of the frame

## Amazon main image compliance

Pure white background, no text, no graphics, no props. Items that ship in the box are product, not props — an included lid, chopsticks, or spoon may appear. Packaging may appear only if it is included in the purchase.

## Gotchas

- **Generative models reconstruct rather than mask.** Their output is a studio recreation and will fail the masked-interior diff. Fine for composites, disqualifying here.
- **Metal and reflective surfaces lose grain quietly.** Edge-refinement and clarity controls smooth texture without obvious signs. The step-3 diff catches this; a visual pass often does not.
- **A shadow that ignores the original light direction reads fake instantly** and undermines the extraction it was meant to finish.
- **Tone transforms that are "global" in a UI are sometimes not.** Auto-tone, auto-contrast, and adaptive clarity are frequently region-adaptive. If the transform cannot be expressed as one function applied to every pixel, it is not permitted.

## Appendix: tools (human operators)

Non-generative maskers, roughly in order of control: Adobe Photoshop (Select Subject + Refine Edge), PhotoRoom Pro, ClipDrop Background Remover, Remove.bg.

An agent should select whatever segmentation or matting tool it has that outputs an alpha mask, then rely on the step-3 verification rather than on the tool's reputation.

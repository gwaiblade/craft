---
description: Turn ordinary product photos into clean, natural-looking
  e-commerce product photography for Amazon, Shopify, and marketplaces.
  Preserve the real product's identity, geometry, proportions, quantity,
  packaging, accessories, orientation, and composition while improving
  the background, exposure, lighting, reflections, and overall
  photographic presentation. Use when the user provides a real product
  photo and wants a cleaner white-background listing image without
  making the product look redesigned, CGI, or artificially perfect.
name: product-image-retouch
---

# Product image retouch

## Objective

**Retouch and reconstruct the photography, not the product.**

The output must look like the **same physical objects from the source
photograph**, photographed in the same arrangement under a simple
professional product-photography setup.

The source image is authoritative for what the product is.

Do not turn it into an idealized, redesigned, more premium, more
symmetrical, or CGI-like version of the product.

The target reaction is:

> "This is the same product, just photographed properly."

Not:

> "This is a render of what the product might look like."

------------------------------------------------------------------------

## Product fidelity rule --- non-negotiable

Preserve the source photograph's:

-   product identity
-   geometry and proportions
-   construction and physical features
-   quantity of every component
-   materials and colors
-   packaging design and wording
-   included accessories
-   camera angle and perspective
-   object orientation
-   relative scale
-   relative placement and overlap

Do not beautify the physical product.

Do not make imperfect objects more symmetrical.

Do not change shapes, thicknesses, corner radii, curves, handles, racks,
molds, stones, utensils, lids, sticks, or accessories.

Do not add, remove, duplicate, merge, or substitute components.

Packaging is a physical product reference, not a design brief. Preserve
its artwork, typography, colors, logo, proportions, orientation, and
visible construction.

------------------------------------------------------------------------

## Naturalism rule

**Realism is more important than perfection.**

Preserve enough real-world imperfection that the result still reads as
photography.

For reflective metal, retain:

-   subtle uneven reflections
-   realistic highlight gradients
-   minor surface variation
-   slight scratches or manufacturing marks where visible
-   natural dark and light areas

For glass, retain:

-   realistic refraction
-   edge thickness
-   minor distortion
-   subtle reflections

For cardboard and packaging, retain:

-   physical texture
-   slight edge wear
-   folds and seams
-   realistic print variation

Do not make surfaces perfectly smooth, perfectly reflective, perfectly
symmetrical, or uniformly lit.

Avoid the appearance of:

-   CGI
-   3D rendering
-   excessive HDR
-   luxury advertising renders
-   hyper-polished chrome
-   artificial sharpness
-   synthetic material textures

A slightly imperfect but believable photograph is better than a flawless
artificial one.

------------------------------------------------------------------------

## Composition lock

Unless the user explicitly asks for a new composition, maintain the
source composition.

Preserve:

-   camera position
-   camera height
-   viewing angle
-   perspective
-   orientation of every object
-   relative positions
-   overlap
-   foreground/background relationships
-   approximate spacing

Do not automatically rearrange the products into a cleaner catalogue
composition.

Cropping may be tightened, but the physical arrangement should remain
recognizably the same.

------------------------------------------------------------------------

## Permitted improvements

The image may be reconstructed where necessary to improve the
**photography**.

Allowed:

-   remove the original background
-   replace it with clean white
-   brighten exposure
-   neutralize white balance
-   soften harsh lighting
-   improve tonal separation
-   reduce distracting room reflections
-   remove minor dust or photographic blemishes
-   clean obvious background contamination
-   improve edge separation
-   create subtle realistic contact shadows
-   improve overall clarity
-   tighten the crop

These improvements must not materially alter the physical product.

------------------------------------------------------------------------

## Lighting target

Create the appearance of a **simple professional softbox product
shoot**, not a dramatic commercial render.

Default lighting:

-   bright
-   neutral
-   soft
-   diffused
-   natural
-   restrained contrast
-   broad realistic highlights
-   visible midtone detail
-   soft contact shadows

The image should not be dark.

Avoid:

-   dramatic lighting
-   hard rim lights
-   deep shadows
-   crushed blacks
-   glowing edges
-   cinematic contrast
-   excessive specular highlights

Reflective metal should still contain both light and dark reflections so
its shape and material remain believable.

Do not solve dark metal by making the entire object uniformly bright
silver.

------------------------------------------------------------------------

## Background

Replace the improvised or distracting background with a clean e-commerce
white background.

For Amazon main images:

`#FFFFFF`

Remove:

-   paper wrinkles
-   backdrop seams
-   room edges
-   furniture
-   dirty white areas
-   obvious background color casts

Retain subtle contact shadows so objects remain grounded.

Do not make products appear to float.

------------------------------------------------------------------------

## Reconstruction strength

Default reconstruction strength:

**Restrained / natural.**

Think:

> competent professional photographer cleaning up an iPhone product
> photo

not:

> advertising studio recreating the product from scratch

When uncertain, change less.

------------------------------------------------------------------------

## Method

### 1. Read the source physically

Before editing, identify:

-   every product/component
-   exact quantity
-   packaging
-   accessories
-   important geometry
-   materials
-   camera angle
-   orientation
-   relative placement
-   distinctive product details

Treat these as locked references.

### 2. Preserve the scene geometry

Keep the original camera logic and arrangement.

Do not improve the composition unless explicitly requested.

### 3. Improve the photographic environment

Replace the background and improve:

-   exposure
-   white balance
-   lighting softness
-   tonal clarity
-   distracting reflections
-   contact shadows

### 4. Preserve material reality

Do not over-clean reflective metal, glass, wood, cardboard, silicone, or
other materials.

Keep believable variation and imperfection.

### 5. Compare against the source

Before accepting the output, check:

-   same products
-   same quantity
-   same geometry
-   same proportions
-   same packaging
-   same accessories
-   same orientation
-   same composition
-   same material identity

If an aesthetic improvement changed any of these, the edit went too far.

------------------------------------------------------------------------

## Verification

Reject or regenerate if:

-   product geometry changed
-   objects became more symmetrical than the source
-   components were added or removed
-   accessories changed shape
-   packaging artwork or wording changed materially
-   camera angle changed without instruction
-   objects were rearranged
-   reflective surfaces became CGI-like
-   products became excessively smooth or pristine
-   lighting became dramatic or artificial
-   the result looks like a render instead of a photograph

Human sign-off:

At normal viewing size and at 100% zoom, ask:

> Does this still look like the exact physical item in the source
> photograph?

and:

> Does it look like that item was photographed better, rather than
> regenerated?

Both should be yes.

------------------------------------------------------------------------

## Output spec

Default:

-   2000 × 2000 px
-   square canvas
-   sRGB
-   clean white background
-   bright neutral exposure
-   subtle realistic contact shadows
-   product occupies approximately 80--90% of the useful frame where
    appropriate

Do not upscale aggressively enough to make textures synthetic.

------------------------------------------------------------------------

## Amazon main image guidance

For an Amazon main image:

-   pure white background
-   no added text
-   no badges
-   no decorative graphics
-   no borders
-   no unrelated props
-   no environmental scene

Packaging may appear if included with the purchase.

Accessories may appear if included with the purchase.

Props used only to demonstrate the product --- such as a drinking glass
that is not included --- should normally be excluded from the main image
and reserved for secondary listing images.

------------------------------------------------------------------------

## Prompt construction

When invoking a generative image editor, communicate the task in this
order:

1.  establish the source as authoritative
2.  lock product geometry and quantity
3.  lock camera angle, orientation, and composition
4.  describe permitted photographic improvements
5.  establish bright, natural lighting
6.  prevent over-polishing and CGI appearance

Use this core instruction:

> Use the supplied photograph as the authoritative physical reference.
> Preserve the exact product identity, geometry, proportions,
> construction, quantity, packaging design, accessories, camera angle,
> orientation, relative placement, and material characteristics.
>
> This is photographic retouching, not product redesign.
>
> Maintain the original composition and object orientation. Do not
> rearrange, beautify, symmetrize, reshape, redesign, or make the
> objects more premium.
>
> Replace the improvised background with a clean white e-commerce
> background. Brighten the image and create soft, neutral, believable
> studio illumination similar to a simple large softbox setup. Reduce
> distracting environmental reflections only where necessary.
>
> Preserve realistic stainless-steel reflections, minor scratches,
> cardboard texture, glass distortion, manufacturing variation, and
> other subtle physical imperfections. Do not make reflective surfaces
> perfectly smooth, uniformly bright, or CGI-like.
>
> The finished image should look like the exact same physical objects
> from the source photograph photographed under better conditions ---
> not a 3D render or an AI recreation.

------------------------------------------------------------------------

## Gotchas

-   **Over-polishing is product drift.** Perfect metal, perfect
    symmetry, and flawless packaging often make the result less
    accurate, not more professional.
-   **Orientation matters.** Small changes to the box angle, tongs,
    product rotation, or camera height can make the output feel like a
    different shoot.
-   **Reflective objects need imperfection.** Some dark reflections and
    environmental variation are necessary for stainless steel to look
    real.
-   **Do not confuse lighting improvement with material replacement.**
    Brightening stainless steel should not turn it into perfect chrome.
-   **Generative reconstruction is permitted only in service of better
    photography.** It must not become permission to reinterpret the
    physical product.
-   **Packaging text is fragile.** Preserve the source packaging as
    literally as possible rather than asking the model to redesign or
    clean up the graphics.
-   **When fidelity and polish conflict, choose fidelity.**
-   **When realism and perfection conflict, choose realism.**

------------------------------------------------------------------------

## Version history

- v1.0 — 2026-11-08 — Adopted into `gwaiblade/craft/skills/product-image-retouch/` per CANON_SKILL. Pre-adoption draft had YAML frontmatter (`name`, `description`) and structured sections (Objective, Product fidelity rule, Naturalism rule, Composition lock, Permitted improvements, Lighting target, Background, Reconstruction strength, Method, Verification, Output spec, Amazon main image guidance, Prompt construction, Gotchas); format mirrored sibling skill `product-image-extraction` and was preserved intact on adoption.

# Sculpture image and perception overlay process

Recorded October 5, 2026. Final visual reference: release `v1.1.1`, commit `0624153`.

## 1. Source and art direction

The starting reference was Aly’s photograph of the classical Laocoon sculpture group. A project copy is `public/design-system/sculpture.jpeg`. The original supplied filename was `6E3B7FBB-B876-4CA4-8D0E-5D090D14919C_1_105_c.jpeg`.

The chosen mood board was **02 / Sculptural Editorial**, stored in `moodboards/02-sculptural-editorial.png`. The intended treatment was warm honey-colored marble, brown midtones, a deep espresso background, and a soft fade into dark negative space for page copy.

An earlier generated asset, `public/design-system/editorial-cover.png`, reconstructed the mood board’s close-up after removing its typography and interface elements. It was superseded because the desired composition should be closer to the original photograph. See `docs/editorial-cover-source.md` for its prompt.

We also tried displaying the original photo with brightness/contrast and cropping adjustments. The crop was not satisfactory, so Aly requested a generated reinterpretation with the original photo’s content and the mood board’s color treatment. No final numeric brightness/contrast settings are recorded here; the current result is generated imagery, not a reproducible filter applied to the original.

## 2. Generate the v2 background

Output: `public/design-system/editorial-photo-v2.png`, 1536 × 1024 pixels, landscape 3:2.

Inputs: original sculpture photo for content; mood board 02 for coloration and atmosphere. The aim was to preserve the recognizable central bearded figure, surrounding figures, hands, and snake arrangement, with dark negative space on the left. Generation can reinterpret details, so this is not an unchanged photograph or a pixel-exact restoration.

Recorded generation prompt:

> Create a photorealistic website hero background. Original photo controls the sculpture anatomy, recognizable bearded man's head and torso, original hand and snake arrangement, and youthful figure on the right. Mood board controls only warm honey-beige stone highlights, brown midtones and near-black espresso background with a cinematic fade. Landscape 1536x1024; sculpture group on the right, quiet dark negative space on the left; preserve the sculptural narrative rather than an anonymous arm-only crop. No UI, text, borders, inset images, invented objects or robotic elements. Avoid blown highlights and heavy dark overlays on the stone.

The generation record is also saved in `docs/editorial-photo-v2-source.md`. Reusing the prompt may produce a different image; preserve the existing PNG when an exact match is required.

## 3. Add editable perception graphics

Two attempts to generate augmented mood boards were blocked by the image tool’s moderation of the classical sculpture’s nudity. We then switched, with Aly’s approval, to HTML/SVG overlays on the existing v2 PNG.

This step did **not** alter the PNG’s pixels, color, fade, or composition. The annotations are separate vector geometry in the same 1536 × 1024 coordinate space. They are manually authored artistic references to machine vision, not detections computed by a vision model.

Palette:

| Role | Color |
| --- | --- |
| Espresso background | `#241e19` |
| Bone bounding-box stroke | `#eee4d2` |
| Sandstone geometry in exploratory versions | `#b39770` |
| Muted bronze palette accent | `#796440` |

## 4. Refinement history

The first editable Perception Atelier study included head boxes, a torso volume, landmark points and links, planes, and on-image labels. Labels and leader lines were removed; mood-board headings and descriptions stayed outside the image.

We explored a left-face box, a snake spline, revised bottom/right planes, and angle arcs. The spline, planes, and angles were removed. That state was saved in `moodboards/perception-atelier-waypoint-01.html`, retaining three face boxes, the original torso volume, and connected landmarks.

We then tried revising the torso perspective and replacing it with sightlines. Both experiments were rejected, and the working mood board was restored from the waypoint before integration into the site.

Finally, the torso volume, landmark connecting lines, and landmark dots were removed from the live overlay. **The final site uses only three face boxes.** The saved waypoint and restored mood board are historical references and still contain the earlier volume and landmarks; use the live SVG as the final source of truth.

## 5. Exact final bounding-box geometry

Asset: `public/design-system/perception-atelier-overlay.svg`.

| Face | Left x | Top y | Right x | Bottom y | Corner length |
| --- | ---: | ---: | ---: | ---: | ---: |
| Central | 725 | 61 | 987 | 299 | 28 |
| Right | 1385 | 517 | 1531 | 688 | 28 |
| Left | 476 | 438 | 628 | 583 | 24 |

Coordinates are source-image units. Each box has a faint closed rectangle and stronger L-shaped corners:

- Fill: none.
- Stroke: bone `#eee4d2`.
- Primary corner stroke: 1.2 units.
- Faint perimeter stroke: 0.65 units, 55% opacity.
- No text, dots, torso volume, sightlines, planes, spline, or angle arcs.

## 6. Site compositing and crop

`src/components/EditorialHero.astro` renders the PNG and transparent SVG as two identically positioned image layers. On desktop both use `object-fit: contain` and `object-position: right top`. On mobile both use `object-fit: cover` and `object-position: 62% center`.

The homepage’s separate CSS fade adds darkness at the bottom on desktop and additional side/bottom shading on mobile for text readability. These are page presentation effects, not edits baked into the PNG.

`src/components/CollectionHero.astro` applies the same overlay to Projects and Blog. Both layers use `object-fit: cover`, with `object-position: right 38%` on desktop and `65% center` on mobile. The cover’s separate gradients darken the left and bottom for copy. These pages therefore crop the same artwork differently from the homepage, while the overlay stays registered to the image.

Keep the source image and overlay dimensions, fit, and position identical. Otherwise the boxes drift away from the faces. The decorative SVG has empty alt text and `aria-hidden`; page copy remains separate and accessible.

## 7. Repeat the process with another image

1. Preserve the source and record whether the final image is an original, edited photo, or generated reinterpretation.
2. Consult `docs/perception-atelier-design-system.md`. Select a page-specific palette from the image, adjusting text and control colors for readable contrast.
3. Create a transparent SVG with the new image’s exact dimensions and viewBox.
4. Fit open-corner boxes to identifiable subjects using the same stroke hierarchy. Do not reuse sculpture coordinates.
5. Composite the image and SVG with matching responsive fit and position. Keep labels outside the artwork.
6. Inspect the rendered desktop/mobile crops and text readability; build the site.
7. Record the approved state, version the change, and tag its release when a commit is authorized.

The live visual specimen is `/design-system/#perception`. The final simplification was released as `v1.1.1`.

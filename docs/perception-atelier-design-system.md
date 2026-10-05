# Perception Atelier — current portfolio direction

This extends the original Stone Gallery foundation. The live site uses sculptural editorial composition, Anton headlines, Inter prose, and image-derived page palettes. The historical waypoint reference is `moodboards/perception-atelier-waypoint-01.html`; the live overlay is `src/assets/overlays/perception-atelier-overlay.svg`.

## Required for future images

1. The primary image influences the color scheme **for its page**, without changing other pages. Select a dark anchor, light neutral, middle tone, and restrained accent from the image. Derive canvas, section surfaces, ink, muted text, rules, links, focus, and overlay colors from that palette. Adjust sampled colors for readable contrast instead of using every sample literally. Carry the palette through header and footer.
2. Add subject-fitted bounding boxes in the sculpture hero’s style. For the canopy image, fitted rock-surface perspective planes may replace boxes, as approved by the user. Keep image content, composition, and fade intact. Every new image needs separately authored coordinates; do not reuse the sculpture overlay.

Current reference: espresso `#241e19`, bone `#eee4d2`, sandstone `#b39770`, bronze `#796440`. New pages may have different hues but preserve restrained contrast, typography, and geometry. Technical screenshots, PCB imagery, plots, and LiDAR visualizations retain meaningful original colors.

## Annotation grammar

- Thin open-corner boxes, with a faint complete perimeter. Use light-neutral outlines by default; on light images, dark image-derived outlines are allowed for visibility. The fresco study uses umber `#302A25`, 2px non-scaling corner strokes, and a 1px perimeter at 55% opacity. In the reference’s 1536 × 1024 coordinates: 1.2-unit primary stroke; 0.65-unit faint stroke at 55% opacity; approximately 24–28-unit corner lengths.
- Boxes fit identifiable subjects tightly without cutting them off. Sparse 2.5-unit landmark dots and subtle links are optional.
- Bronze perspective volumes are optional when well aligned to the subject; the current sculpture uses only three face boxes. Its torso volume, landmark dots, and connecting lines have been removed.
- No on-image text, decorative labels, label leader lines, or neon HUD effects. Sightlines, angle estimates, snake splines, and the bottom/right planes were rejected for this reference and must not return by default.
- The overlays are artistic perception studies, not results from a real vision model. Never present invented confidence scores or measurements.

## Implementation and review

Use a separate SVG overlay so linework stays editable. Give it the source image’s dimensions and viewBox; apply exactly the same `object-fit` and `object-position` as the underlying image. Keep both layers in the same container, below copy and readability fades. Decorative overlays use empty alt text and `aria-hidden`; meaningful information belongs in accessible page content. Inspect desktop and mobile alignment and crops.

Scope palette overrides to a page container or body rather than global root tokens. Reuse the site’s semantic CSS tokens (`--color-bg`, `--color-text`, `--color-text-secondary`, `--color-accent`, `--color-border`, and related tokens); theme-specific surfaces and fades must use the same page palette instead of hardcoded sculpture colors when introducing a new theme. The existing sculpture is the default theme, not a universal palette for all future pages.

Check text contrast (4.5:1 normal text, 3:1 large text), keyboard focus, overlay visibility, and mobile crop. Do not add motion unless it improves the composition; respect reduced motion. The visual specimen is at `/design-system/#perception`.

## Canopy plane study

The projects hero uses `src/assets/editorial/canopy-editorial-v2.png` with the separate user-supplied `src/assets/overlays/canopy-shade.svg`. Preserve its translucent geometry and dashed boundary as supplied. The overlay shares the artwork's 3:2 aspect ratio and remains decorative, below readability fades. These are manually authored artistic surface studies, not measured plane estimation. This exception applies to the canopy image; the sculpture keeps its three face boxes.

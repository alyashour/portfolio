# Portfolio

This is my personal website.

## Dev

Do `npm run astro dev` for a live server.
Do `npm run astro build` to build static files.

## Images

All images are taken by me but may be enhanced by AI for sharpness or color.

## Asset organization

- `src/assets/projects/`: project screenshots, demos, and related photography, imported by Astro components.
- `src/assets/editorial/`: artwork used by pages and the design-system specimen.
- `src/assets/textures/`: background materials, referenced through relative CSS URLs or image imports.
- `src/assets/overlays/`: editable SVG annotations, imported as image URLs to preserve their separate layers.
- `public/`: files requiring a stable public URL, such as `favicon.ico`.

Use Astro's `<Image>` for processed project images. Editorial layers currently use imported image metadata with `<img src={image.src}>` to preserve their existing rendering and overlay alignment.

## Style ownership

Keep a component's structure, typography, spacing, and responsive rules in its scoped Astro `<style>` block. Page-only layouts and controls belong in that page. Shared stylesheets own resets, common primitives, collection surfaces, and page/theme palette tokens; components consume those tokens instead of being restyled by external selectors. Header and footer theme variants stay with their components. The design-system specimen keeps its own shared foundation stylesheet.

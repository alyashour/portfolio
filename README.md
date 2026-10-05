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

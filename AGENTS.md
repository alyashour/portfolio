# Project instructions

## Design system

Before working on the site's design, read `docs/perception-atelier-design-system.md` and consult the visual specimen in `src/pages/design-system.astro` (`/design-system/`). The original foundation is `docs/stone-gallery-design-system.md`; the current Perception Atelier rules take precedence where they differ. Follow the design system for implementation and review, including page-specific image-derived palettes and consistent subject-fitted vision overlays.

If a requested change conflicts with the design system, explicitly identify the conflict and formally ask the user whether to treat it as a design-system change. Do not implement the conflicting change until the user approves it. Once approved, update the design-system documentation and visual specimen first, then apply the change to the site. An explicit user request to change the design system itself counts as approval for that specified change.

## Versioning and releases

Use semantic versioning for completed change sets: MAJOR for incompatible changes, MINOR for backward-compatible features, and PATCH for backward-compatible fixes or documentation-only changes. Choose the next version by inspecting both the current package version and existing Git tags; never move or overwrite an existing release tag.

For each completed change set, update `package.json` and the root package metadata in `package-lock.json`. The footer in `src/components/SiteFooter.astro` reads the package version; always ensure it displays the updated `vX.Y.Z` version and retains the source link to `https://github.com/alyashour/portfolio` across site pages.

Run the production build and appropriate checks before a release commit. When committing an approved change set, create an annotated Git tag `vX.Y.Z` on its release commit. Keep iterative drafts within the same pending change set rather than bumping on every edit. Do not commit or push solely because these instructions exist; commit when the user requests it, and push only when authorized.

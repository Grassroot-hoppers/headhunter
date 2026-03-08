# AGENTS.md

## Cursor Cloud specific instructions

### Overview

This is a **documentation-heavy repo with one static website**. There are zero runtime dependencies, no package manager, no build step, and no test framework.

- **Website**: `website/` — static HTML/CSS/JS pitch deck (see `.cursor/rules/website.mdc` for design system details)
- **Docs**: Markdown files across `docs/`, `product/`, `ops/`, `automation/`, `resources/`
- **Deployment**: GitHub Pages via `.github/workflows/pages.yml` (deploys `website/` on push to `main`)

### Running the website locally

```
python3 -m http.server 8080 --directory website
```

Then open `http://localhost:8080/` in a browser. Any static HTTP server works.

### Lint / Test / Build

There are no linters, automated tests, or build steps configured in this repo. The site is vanilla HTML with no toolchain. Validation is manual: open in a browser and verify visually.

### Gotchas

- The site loads Google Fonts externally; it needs internet access to render correctly with Fraunces/DM Sans/JetBrains Mono.
- There are 5 HTML files in `website/` — `index.html` plus 4 flywheel detail pages. Test all of them if making CSS changes.
- The `SPEC.md` in the repo root is the project source of truth. Always read it before making significant changes (per `.cursor/rules/project.mdc`).

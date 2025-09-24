# Repository Guidelines

This repo hosts Markdown slides built with Marp and deployed to GitHub Pages. Use this guide to add or maintain decks consistently and keep CI green.

## Project Structure & Module Organization
- `slides/marp/` — Primary Marp decks (`*.md`) with front matter. Use kebab-case filenames (e.g., `bouldering-shoes.md`).
- `slides/etc/` — Other notes or non-Marp markdown.
- `assets/images/` — Images used by slides. Prefer local assets over external URLs.
- `.marprc.yml` — Marp config (input includes `slides/marp/*.md`, output to `output/`).
- `.github/workflows/pages.yml` — CI that builds HTML and publishes to Pages on `master`.
- `index.md` — Landing page deck linking to generated HTML.

## Build, Test, and Development Commands
- Build all slides: `npx @marp-team/marp-cli -c .marprc.yml --html -o output slides/marp/*.md index.md`
- Preview a slide locally: `npx @marp-team/marp-cli --preview slides/marp/ooarai.md`
- Clean artifacts (local only): `rm -rf output/*`
- CI runs automatically on push to `master` and uploads `output/` to Pages.

## Coding Style & Naming Conventions
- Front matter: `marp: true`, `theme: default|gaia`, `paginate: true`; set `backgroundColor` if needed.
- Slide delimiter is `---`. Start with a single `#` title slide.
- Filenames and image names in `kebab-case` (no spaces). Use relative paths, e.g., `![w:300](../../assets/images/thing.png)`.
- Keep content in Japanese to match existing decks; concise bullets over paragraphs.

## Testing Guidelines
- No unit tests; “tests” are build + manual checks.
- Ensure Marp build succeeds and generated `output/*.html` opens without console errors.
- Check links and image paths; prefer local images for reliability (Pages blocks some remote assets).

## Commit & Pull Request Guidelines
- Follow Conventional Commits seen in history: `feat: ...`, `fix: ...`, `docs: ...`, `chore: ...` with short Japanese subject.
- Branch naming: `feature/<topic>` or `fix/<topic>`; one topic per PR.
- PRs include: purpose, affected files, preview (screenshot or link to built HTML), and related issue/notes.
- Do not commit `output/` artifacts; they are produced by CI.

## Security & Configuration Tips
- Do not commit secrets or credentials. Keep images small and licensed. Respect `.marprc.yml` include/exclude and keep `output` as the publish root.


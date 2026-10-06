# AGENTS.md

## Purpose
Provide quick project context and editing rules for automated agents.

## Project summary
- Static Astro site for Equidiretta.tv
- Deployed on Codeberg Pages (build output in `dist/`)
- Content-first workflow: non-developers edit `config.json`, `/contents`, `/blog`

## Where to edit content
- `config.json`: venues, links, images, CTA label, GA ID
- `/contents/*.md`: venue program/schedule blocks (HTML/Markdown)
- `/blog/*.md`: blog posts (frontmatter + Markdown)
- `public/`: static assets (PDFs, images); use `/images/...` and `/filename.pdf` links

## Key routes
- `/` -> `src/pages/index.astro`
- `/blog/` and `/blog/[slug]/`
- `/live/[slug]/` and `/live/[slug]/[link]/`
- `/contatti/`, `/privacy/`, `/cookie/`

## Conventions
- Keep SEO copy in Italian.
- Always include venue name + location + "live streaming eventi equestri" in venue intros.
- Avoid changing layout components unless requested.

## Build
- `pnpm build`

## Deploy flow
- Local: `pnpm build` to generate `dist/` for checks.
- Push to `develop`: Woodpecker CI builds via `.woodpecker.yml`.
- CI deploys build output to `main` for Codeberg Pages.

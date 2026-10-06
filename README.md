# Equidiretta.tv (Astro)

This project is a static Astro site deployed via Codeberg Pages.
The goal is to keep content updates simple: most edits happen in `config.json`,
`/contents`, and `/blog`.

## Quick content updates (no code)

### 1) Live venues, links, and labels
Edit `config.json`:
- `groups[]` controls each venue (title, slug, location, image, live links).
- `actions.vedi` controls the CTA label on cards (e.g. "streaming").
- `analytics.gaId` holds the GA ID (e.g. `G-XXXX`).

### 1b) Images and PDFs
- Put site-wide assets in `public/` (they are served from `/`).
- Venue images go in `public/images/` and should match `config.json` `image` values.
- PDFs (programs, brochures) go in `public/` and can be linked as `/filename.pdf`.
### 2) Venue programs / schedules
Edit the Markdown files in `/contents`:
- Each file is loaded by the matching `programma` field in `config.json`.
- These files accept HTML + Markdown (they are rendered as HTML).
- Keep the first paragraph SEO-friendly (venue + location + "live streaming eventi equestri").
- You can link PDFs with `/filename.pdf` and images with `/images/filename.jpg`.

### 3) Blog posts
Add a Markdown file in `/blog`:
- Filename becomes the slug, e.g. `2026-02-04.md` -> `/blog/2026-02-04/`.
- Frontmatter supports: `title`, `date`, `description` (optional), `excerpt` (optional).
- You can include images with `/images/filename.jpg` and PDFs with `/filename.pdf`.

Example:
```md
---
title: "Titolo articolo"
date: 2026-02-04
description: "Breve descrizione..."
---

Contenuto del post...
```

## Astro routing overview
- `/` -> `src/pages/index.astro` (home / live list)
- `/blog/` -> `src/pages/blog/index.astro`
- `/blog/[slug]/` -> `src/pages/blog/[slug]/index.astro`
- `/live/[slug]/` -> `src/pages/live/[slug]/index.astro`
- `/live/[slug]/[link]/` -> `src/pages/live/[slug]/[link]/index.astro`
- `/contatti/`, `/privacy/`, `/cookie/` -> simple static pages

## Build & deploy
- Dev: `pnpm dev`
- Build: `pnpm build`
- Output: `dist/`
 
### Deploy flow (Codeberg Pages)
- Local: run `pnpm build` to generate `dist/` for checks.
- Push to `develop`: Codeberg CI/CD (Woodpecker) pulls the repo and builds using `.woodpecker.yml`.
- CI publishes: build output is deployed to the `main` branch for Codeberg Pages.
- Hosting: served via Codeberg Pages (see Codeberg Pages docs).

## SEO notes
- Meta title/description are set in `Layout`/`BaseHead`.
- Sitemap is generated automatically via `@astrojs/sitemap`.
- Cookie consent gates GA loading.

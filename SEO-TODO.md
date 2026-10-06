# SEO TODO

## On-page content
- [x] Add a short keyword-rich intro on each venue page (live/[slug]) mentioning venue + location + "live streaming eventi equestri".
- [x] Update each `contents/*.md` with a brief opening paragraph including venue name, city, and "live streaming eventi equestri".
- [x] Add a short intro on `/blog/` mentioning "notizie" and "live streaming eventi equestri".
- [ ] Add a short FAQ section on home targeting queries like "come vedere live streaming equestri".
- [ ] Add a short "Chi siamo / missione" block on home with trust + keywords.
- [ ] Add a per-venue keywords mini-section (city/region + disciplines like salto ostacoli, pony, CSI).

## Metadata
- [x] Add `meta name="robots" content="index, follow"` in `BaseHead.astro`.
- [x] Use a more descriptive title pattern for blog posts (e.g., "{title} | Live streaming equestri").
- [ ] Provide a relevant OG image per page (home, blog, venues) instead of a single default.
- [ ] Add custom meta descriptions for `/blog/`, `/contatti/`, `/cookie/`, `/privacy/`.
- [ ] Add per-page OG title/description overrides (home/blog/venue).

## Internal linking
- [ ] Add a text link list of venues on the homepage (if not present or moved too low).
- [x] Add "Altre arene in diretta" links on `/live/[slug]/[link]/` to other arenas for the same venue.
- [x] Add links from blog posts to relevant venue live pages.
- [ ] Add a "Le sedi in diretta" link list in the footer.
- [ ] Add "Articoli correlati" on blog posts.

## Technical
- [x] Verify `sitemap-index.xml` includes blog + live pages.
- [x] Ensure `robots.txt` allows crawling of blog/live pages.
- [x] Confirm canonical URLs are correct for all routes (BaseHead uses Astro.site + pathname).
- [ ] Add `width` and `height` attributes for key images to reduce layout shifts.
- [ ] Decide if policy pages should be `noindex` (if yes, add `meta robots` overrides on those pages).

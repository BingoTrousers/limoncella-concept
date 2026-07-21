# Limoncella

An editorial-style landing page for **Limoncella** — a fictional Italian restaurant perched above a fictional coastal town, Amber Cove. Built as a design concept: golden-hour hero, sensory storytelling, a six-dish menu, a photographic gallery, and a postcard-style hours & location block.

## View it

The page is `index.html` plus a folder of photographs in `images/`. No build step, no dependencies beyond two Google Fonts loaded via `<link>`.

```bash
python3 -m http.server 8080
# open http://localhost:8080/
```

Or just open `index.html` directly in a browser.

## Notes

- The hero, the lemon-grove story image, and the gallery tiles are free-license stock photographs (from [Unsplash](https://unsplash.com), no attribution required) stored in `images/`; per-file credits are listed in an HTML comment at the bottom of `index.html`. The dividers, postcard map, and stamp are still hand-drawn inline SVG.
- The restaurant, its address, phone number, and socials are invented placeholder content.
- Typography: Cormorant Garamond (display/italic) + Jost (body/labels), both from Google Fonts.

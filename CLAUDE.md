# Limoncella — project notes

Single-file HTML landing page (`index.html`) for a fictional Amalfi Coast restaurant. Design concept piece, not a production app.

## Structure

Everything — HTML, CSS, JS — lives in `index.html`. No build tooling, no package.json, no dependencies except two Google Fonts pulled via `<link>` (Cormorant Garamond, Jost).

Sections, top to bottom, follow one evening's light (see the `ore HH:MM` eyebrows on each section): hero (sunset) → story → menu → gallery → hours/location (dusk) → footer (night).

All visuals — hero panorama, lemon grove, gallery tiles, postcard map — are hand-authored CSS gradients + inline SVG. There are no external image assets and none should be added without discussion; that constraint is intentional to keep the file self-contained.

## Working on this file

- Edit CSS in the single `<style>` block; it's organized by section with comment headers.
- SVG paths in this file often use `C` commands without a space after the letter (e.g. `C238,14`) in older blocks and *with* a space in newer ones (e.g. `C 90,405`) — check the exact surrounding text before using Edit's `old_string`, don't assume spacing.
- Reveal-on-scroll and hero parallax are vanilla JS at the bottom of the file (IntersectionObserver + a `--shift` CSS custom property driven by scroll position). Respects `prefers-reduced-motion`.
- No test suite. Verify changes visually — headless Chromium is available at `/home/charl/.cache/ms-playwright/chromium_headless_shell-1228/chrome-headless-shell-linux64/chrome-headless-shell` and can screenshot the file directly (`--screenshot=out.png file:///path/to/index.html`) even though Playwright itself isn't installed as an npm package.

## Environment gotcha

The git repo at `/home/charl` (home directory root) is **not** related to this project — it appears to be an accidental `git init` in `$HOME` with an unrelated project (`yashoku-blog`) staged inside it, plus dotfiles and `.ssh`. This project has its own independent repo rooted at `fable-concept/`. Never run git commands here assuming the home-directory repo is relevant, and never stage/push anything from outside this directory.

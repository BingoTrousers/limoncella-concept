# Limoncella — project notes

HTML landing page (`index.html` plus an `images/` folder) for a fictional Amalfi Coast restaurant. Design concept piece, not a production app.

## Structure

All code — HTML, CSS, JS — lives in `index.html`; the only local assets are the photographs in `images/`. No build tooling, no package.json, no dependencies except two Google Fonts pulled via `<link>` (Cormorant Garamond, Jost).

Sections, top to bottom, follow one evening's light (see the `ore HH:MM` eyebrows on each section): hero (sunset) → story → menu → gallery → hours/location (dusk) → footer (night).

The scene imagery — hero panorama, the La Storia lemon grove, and the seven gallery tiles — are free-license stock photographs stored locally in `images/` and wired in as CSS `background-image` / `.hero-photo` (credits are in an HTML comment near the bottom of `index.html`). The smaller decorative marks — section dividers, the postcard map, the postal stamp, the favicon — are still hand-authored inline SVG and should stay that way. When sourcing replacement photos, they must be genuinely free to use: Unsplash images flagged `premium`/`plus` (Unsplash+) are **not** free, come watermarked, and must be avoided — verify the `premium`/`plus` fields via `unsplash.com/napi/photos/<id>` before using one.

## Working on this file

- Edit CSS in the single `<style>` block; it's organized by section with comment headers.
- SVG paths in this file often use `C` commands without a space after the letter (e.g. `C238,14`) in older blocks and *with* a space in newer ones (e.g. `C 90,405`) — check the exact surrounding text before using Edit's `old_string`, don't assume spacing.
- Reveal-on-scroll and hero parallax are vanilla JS at the bottom of the file (IntersectionObserver + a `--shift` CSS custom property driven by scroll position). Respects `prefers-reduced-motion`.
- No test suite. Verify changes visually — headless Chromium is available at `/home/charl/.cache/ms-playwright/chromium_headless_shell-1228/chrome-headless-shell-linux64/chrome-headless-shell` even though Playwright itself isn't installed as an npm package. Serve over HTTP for screenshots (`python3 -m http.server`) so the relative `images/` paths resolve. Two headless gotchas: `chrome-headless-shell --screenshot` captures only the window viewport from the top (URL `#anchors` don't move it), and the hero is `min-height:100svh` so it stretches to fill any tall window — to shoot a lower section, render a temp copy with the hero height pinned and the sections above it `display:none`.

## Environment gotcha

The git repo at `/home/charl` (home directory root) is **not** related to this project — it appears to be an accidental `git init` in `$HOME` with an unrelated project (`yashoku-blog`) staged inside it, plus dotfiles and `.ssh`. This project has its own independent repo rooted at `fable-concept/`. Never run git commands here assuming the home-directory repo is relevant, and never stage/push anything from outside this directory.

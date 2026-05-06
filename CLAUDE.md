# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Static academic personal homepage for Zhiyuan Yao, hosted at https://zhiyuan-21.github.io/HomePage/. No build step, no package manager, no test suite — changes are deployed by pushing to the `master` branch (GitHub Pages).

## Development

Preview locally by opening any `.html` file in a browser, or serve with:
```
python3 -m http.server 8000
```

## Architecture

All pages are standalone HTML files with inline `<style>` blocks — there is no shared CSS build pipeline. The files share no template system.

- [index.html](index.html) — main homepage. Layout: fixed 240 px left sidebar (`w3-sidebar`) + scrollable main content (`margin-left:240px`). CSS custom properties (`--accent`, `--ink`, etc.) are defined in the inline `<style>` block. Smooth-scroll anchor navigation is handled by jQuery.
- [shattering.html](shattering.html) — movie companion page for the shattering/coagulation paper. Self-contained with its own inline styles (serif academic aesthetic, dark-red accent).
- [stream_penetration.html](stream_penetration.html) — movie companion page for stream penetration simulations. Same pattern.
- [stylesheet.css](stylesheet.css) — legacy Lato font-face declarations; **not linked from index.html** (index.html loads Montserrat/Roboto from Google Fonts CDN). Kept for reference.
- [w3.css](w3.css) — local copy of the W3Schools CSS framework used for grid, sidebar, and responsive utilities.
- [font-awesome.min.css](font-awesome.min.css) — local Font Awesome 4 fallback; index.html loads FA 4.7.0 from the cdnjs CDN instead.

## Key conventions

- The accent color in `index.html` is `#1f4f82` (dark blue). The shattering/penetration companion pages use `#7a1f1f` (dark red) to distinguish them visually.
- Font Awesome icon class names follow FA 4.x syntax (`fa fa-envelope`, `fa fa-github`, etc.) — do not use FA 5/6 syntax.
- The sidebar navigation links use `#hash` anchors matching `id` attributes on `<section>` elements in the main content.
- Google Search Console ownership is verified via [googlea78b6845d7771292.html](googlea78b6845d7771292.html) — do not delete this file.

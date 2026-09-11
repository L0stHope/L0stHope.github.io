# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal portfolio site for Alex (GitHub user `L0stHope`), hosted on GitHub Pages as a user site. The repo name `L0stHope.github.io` means it's served from the root of the `main` branch at https://l0sthope.github.io/ — pushing to `main` deploys it.

## Structure

- `index.html` — the whole site: a single page with sections `#projekte`, `#ueber-mich`, `#kontakt`. No framework, no build step, no package manager, no tests.
- `style.css` — all styling. Theme colors are CSS custom properties on `:root` (dark default), overridden in a `prefers-color-scheme: light` block — change colors there, not per rule. The signature look is the hard offset "pixel" shadow (`--px`, `--shadow`) on cards and buttons.
- Projects are `<article class="card">` blocks in `.project-grid`; add a project by copying a card. To add a screenshot, replace the `.card-media-label` placeholder with an `<img>` inside `.card-media` (it's cropped to 16:9 via `object-fit: cover`).
- `images/` — project screenshots (e.g. `BioTopia*.png`, `Project_Forest*.png`, `Maya1.jpg`). Not yet committed or referenced from `index.html`.

## Conventions

- Site content is in **German** (`<html lang="de">`); keep new copy in German unless told otherwise.
- Keep it dependency-free static HTML/CSS unless the user asks for something heavier. Fonts are system stacks on purpose — don't add Google Fonts via CDN (embedding them from Google's servers is a GDPR issue for German sites; self-host if a webfont is needed).
- Reference images with relative paths (`images/...`). GitHub Pages is case-sensitive, so filenames must match exactly even though Windows isn't.

## Local preview

Open `index.html` directly in a browser, or serve the folder:

```
python -m http.server 8000
```

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS portfolio website for Thiliban Manivarma (Computational Biophysics Ph.D. researcher). No build system, no package manager, no test runner.

## Previewing & Development

Open the file directly in a browser — no server needed:

```powershell
# Windows
Start-Process "index_new.html"
```

## Deployment

Pushing to the `main` branch automatically deploys the entire repository root to GitHub Pages via `.github/workflows/static.yml`. No build step — GitHub Pages serves the files as-is.

## File Roles

| File | Role |
|---|---|
| `index_new.html` | **Active file** — the live portfolio. All CSS is embedded in its `<style>` block. |
| `index.html` | Older version kept as a content reference. |
| `style.css` | External stylesheet — **not linked** by `index_new.html`. Applies only to `index.html`. |
| `scripts.js` | Tab-switching utility — not currently used by either HTML file. |
| `flux_scaled.png` | Profile photo, referenced at the root path from both HTML files. |

## Architecture Notes

- `index_new.html` is entirely self-contained: all CSS lives in its embedded `<style>` block, not in `style.css`. When editing styles, edit the `<style>` block inside `index_new.html`.
- Design uses **Deep Navy (`#0a1628`) + Teal (`#0fa3b1`)** as the primary palette, loaded with Google Fonts (Raleway for headings, Inter for body) via CDN.
- Section layout uses alternating full-width `<div class="full-band [white-bg|light-bg|navy-bg]">` bands with a centered `.section-inner` for content — **not** `<section>` elements — so that backgrounds span the full viewport width.
- Responsive breakpoints: `≤768px` (tablet) and `≤480px` (mobile).

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-page marketing/landing site for Kinga Conesa, an online personal trainer and
nutritionist. The site is **`index.html`** (~1390 lines, ~57 KB — all CSS and JS inline)
plus images served from `fotos/`. There is no build system, no package manager, no framework,
and no tests — it is plain HTML5 + CSS3 + vanilla JavaScript.

## Running / previewing

- **Fastest:** open `index.html` directly in a browser.
- **Development:** VSCode + the *Live Server* extension (right-click `index.html` →
  "Open with Live Server", or "Go Live"). Serves at `http://localhost:5500` with auto-reload
  on save.

There is nothing to install, compile, lint, or test. "Deploy" = push the static file to a
host (Vercel via GitHub auto-deploy, or drag `index.html` onto Netlify Drop).

## Architecture (it all lives in `index.html`)

The file is three blocks, in order:

1. **`<style>` (≈ lines 20–1003)** — all CSS. A design system is defined as CSS variables in
   `:root` (lines ~21–45): the warm peach/coral palette — the `--color-rose*` variable names are
   kept for stability but now hold warm coral/peach values — serif/sans font stacks, spacing scale,
   radii, transitions. **Change colors/spacing once in `:root`** and it
   propagates everywhere. Class naming is BEM (`.block__element--modifier`).
2. **`<body>` (≈ lines 1005–1291)** — semantic sections, each marked by an HTML comment:
   NAV → HERO (`#top`) → ENTRENAMIENTO (`#train`) → NUTRICIÓN (`#nutri`) → TARIFAS →
   SOBRE MÍ → CTA → CONTACTO → FOOTER → floating WhatsApp button.
3. **`<script>` (≈ lines 1294–end)** — all vanilla JS. Handles: nav background-on-scroll,
   mobile hamburger toggle, the expandable section pattern, and the contact-form handler.

### Expandable-section pattern (important)

"Entrenamiento" and "Nutrición" are not separate pages. They are hidden `.section-expand`
panels (`#train`, `#nutri`) revealed by `openSec(id)` / `closeSec(id)`, wired via inline
`onclick` on the hero CTAs and nav links. `openSec` closes any other open panel first, then
scrolls the opened one into view. When adding a similar collapsible block, replicate this
`.section-expand` / `.section-expand--open` structure and the open/close calls.

### Images

- **All photos live in `fotos/` and are referenced by relative path** (`src="fotos/..."`).
  Kinga's photos: `kinga-hero.jpg` (hero), `entreno-1..4.jpg` (training gallery — `entreno-2.jpg`
  is also reused in "Sobre mí"). Nutrition gallery: `nutri-1..4.jpg`. To swap a photo,
  replace the file in `fotos/` (keeping the name) or update the `src`.
- Galleries crop via CSS `aspect-ratio` + `object-fit: cover` (`.gallery__item` 4/5,
  `.media-photo` 9/16), so they don't need `width`/`height` on the `<img>`; the hero does have
  `width`/`height` + `fetchpriority="high"`.

### Contact / conversion

- The contact `<form>` has **no backend**: `sendForm()` builds a `wa.me` deep link from the
  fields (name, chosen service, goal, email) and opens WhatsApp with the message pre-filled.
  Validation uses the browser's native `reportValidity()`. A `#formStatus` `aria-live` region
  announces the result.
- Other conversions are hardcoded links: WhatsApp `https://wa.me/34618915226` (with a per-plan
  `?text=`) and `mailto:lauraconesam1@gmail.com`. The tarifa cards each deep-link to WhatsApp.
  The WhatsApp number is centralized as `WA_NUMBER` in the script **only for the form**; the
  static `wa.me` links in the markup are intentionally left literal so they work without JS.

## Conventions & gotchas

- **Site UI language is Spanish** (`<html lang="es">`); user-facing copy should stay Spanish.
  The companion docs (`SETUP_VSCODE.md`, `WORKFLOW_PROFISSIONAL.md`) are written in Portuguese.
- Because everything is one file, edits are made by **finding the relevant section comment or
  BEM class** rather than navigating modules. Use search (`Ctrl+F`) for `hero__title`,
  `tarifa-card__price`, `about__text`, etc.
- Keep the **no-dependencies / single-file** property unless explicitly asked to split it — it
  is the project's deliberate "production-ready" design choice.
- This repo is a **git repository** on branch `main`, published at
  `https://github.com/mauriciogasparetto/kinga-website` (public). Deploys to Vercel via the
  GitHub integration — each `git push` to `main` triggers an automatic redeploy. `.gitignore`
  excludes `.claude/settings.local.json` and OS/editor junk.

## Companion docs

- `SETUP_VSCODE.md` — VSCode + Live Server + extensions setup (Portuguese).
- `WORKFLOW_PROFISSIONAL.md` — intended git/GitHub/Vercel workflow and commit-message
  conventions (`feat:`, `fix:`, `style:`, `refactor:`, `docs:`).

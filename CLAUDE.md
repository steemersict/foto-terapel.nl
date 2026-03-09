# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Foto-TerApel.nl — Fotografieportfolio website voor authentieke sfeerfotografie uit Ter Apel. Nederlandstalige site (lang="nl").

## Commands

```bash
npm run dev        # Dev server op localhost:4321
npm run build      # Productie-build naar ./dist/
npm run preview    # Preview van productie-build
```

## Tech Stack

- **Astro 5** (statische site, geen SSR)
- **Tailwind CSS v4** via `@tailwindcss/vite` plugin (niet de oude PostCSS-integratie)
- **TypeScript** in strict mode (`astro/tsconfigs/strict`)

## Architecture

Multi-page statische site met component-based opbouw:

- `src/layouts/Layout.astro` — Base HTML layout, laadt Google Fonts (Newsreader + Dancing Script + Material Symbols) en global CSS
- `src/pages/index.astro` — Homepage met hero, citaat, bento grid portfolio, contactformulier
- `src/pages/portfolio.astro` — Portfolio overzicht met masonry grid en filter buttons
- `src/pages/over-mij.astro` — Over mij pagina met bio en CTA
- `src/pages/tarieven.astro` — Tarieven & Pakketten met pricing cards en extra opties
- `src/pages/contact.astro` — Contactformulier met contactgegevens
- `src/components/Header.astro` — Sticky header met navigatie, actieve pagina-indicatie via `activePage` prop
- `src/components/Footer.astro` — Footer met copyright, locatie en social links
- `src/styles/global.css` — Tailwind import + design tokens + bento grid + masonry CSS

## Design Systeem

- **Licht thema**: achtergrond `#f7f7f7` (background-light), tekst `slate-900`
- **Accentkleur**: saliegroen `#a3b18b` (primary)
- **Typografie**: Newsreader (serif, display) + Dancing Script (handwriting, citaten)
- **Icons**: Material Symbols Outlined
- **Dark mode kleur**: `#1a1b17` (background-dark) — voorbereid maar niet actief

## Branching

Werk altijd op een feature branch (`feature/...` of `fix/...`), nooit direct op main. Maak een PR naar main.

# Distro L. Desk: landing page

A single long-scroll, static guide to Linux in 2026 (18 sections, see the page map in `content/landing.md`), styled as Soft UI / neumorphism.

## Source files (read these before building)
- `brand.md`: logo (dLD), amber accent, typefaces, image brief. Overrides `design.md` for color, type and logo.
- `design.md`: visual system (tokens, shadows, components, layout, motion, accessibility). Follow it exactly.
- **Figma file**: the approved visual design. The code implements it.
- `data/distros.json`: single source for distro facts and the finder rules.
- `content/copy.md`: **final copy for every section**, including microcopy, alt text and the 404 page. Use it word for word; don't invent copy or numbers.
- `content/landing.md`: layout, visuals and interaction notes for each section.
- `research/distros-2026.md`: fact base with sources. Every fact on the page must come from here.

## Stack
- Plain **HTML + CSS + a small vanilla JS file**. No framework and no build step needed.
- Structure:
  ```
  index.html
  assets/css/tokens.css     # design.md tokens as CSS custom properties
  assets/css/main.css       # layout + components
  assets/js/main.js         # theme toggle, keycap press, timeline, distro finder
  data/distros.json         # distro facts + finder rules
  assets/fonts/             # self-hosted Inter + JetBrains Mono (woff2)
  assets/img/               # og-image.png, favicon.svg, screenshots
  ```
- Run locally: `python3 -m http.server 8000`, then open http://localhost:8000
- Hosting: any static host (GitHub Pages, Netlify, Cloudflare Pages).

## Rules
- Semantic HTML (`header`, `nav`, `main`, `section` with headings, `footer`). One `h1`.
- Mobile-first. Test at 360, 768, 1280 and 1920px wide. No horizontal scroll.
- Light theme is the default. Dark theme: respect `prefers-color-scheme`, and let the manual toggle override it (stored in localStorage inside try/catch).
- Support `prefers-reduced-motion`, `prefers-contrast: more` and `forced-colors`.
- The page works without JS: finder answers fall back to a static table, and the timeline to a list.
- No trackers, no external scripts. Fonts are self-hosted.
- All external links go to **official** project sites, with `rel="noopener"`.
- No official distro logos until trademark use is approved; use text monograms.
- No fake testimonials, user counts or benchmark numbers.
- Long page: sticky section index, expandable panels for deep content, `FAQPage` JSON-LD.
- Dense data (comparison table, apps table, glossary) stays flat; soft depth is only for controls and cards (`design.md` §6).
- Every number on the page links to its source in the sources list.

## Definition of done
- Lighthouse ≥ 90 in all four categories on mobile.
- WCAG 2.2 AA: contrast, visible focus, keyboard-only navigation, 44px targets.
- Checklist in `design.md` §10 passes.
- Includes: favicon, Open Graph image and meta tags, `robots.txt`, `sitemap.xml`, 404 page.

# brand.md: Distro L. Desk

The identity layer on top of `design.md`. Where they differ, **this file wins** for color, type and logo. `design.md` still governs shadows, shape, components and accessibility.

## Decisions (confirmed)

| Topic | Decision |
|---|---|
| Name | **Distro L. Desk**, a nod to Philip K. Dick |
| Logo | **Typographic monogram "dLD."** in Geist Bold (concept A, now with a period), paired with a two-line mono label |
| Default theme | **Light**, with a dark theme via toggle or system preference |
| Visual style | **Contemporary editorial**: a modern digital publication about Linux plus an OS discovery tool. Asymmetric compositions, big display type with serif accents, numbered chapters, thin rules, real desktop screenshots as the main visual. See `design.md` §17 |
| Distro keys | **Neutral** soft keycaps with text monograms; no distro brand colors or logos |
| Design tool | **Figma**. The code implements the Figma file. |
| Images | **Provided by the site owner** (see §6 for the brief) |
| Palette | **Editorial warm & blue** (September 2026): warm off-white canvas, charcoal ink, one identity blue, mist panels, peach only as a soft glow. See §3 |
| Typefaces | **Geist** (UI and text, ~85–90%) · **Instrument Serif** (italic accents in headlines, big figures) · **IBM Plex Mono** (labels, numbering, versions). Replace Inter and JetBrains Mono |
| Tone of the hero | **Plain language for non-technical visitors**: no version numbers, jargon or distro abbreviations above the fold |

---

## 1. Personality

**A modern digital publication about Linux, with a friendly discovery tool at its center.** Warm paper-like canvas, confident type, a touch of serif, precise mono labels, and real Linux desktops as the hero of every page. Informed by desktop-OS details (window dots, thin rules, numbered figures), never styled like a developer tool. It should feel trustworthy enough for a newcomer and exact enough for an Arch user.

- **Is:** tactile, quiet, exact, warm, independent
- **Isn't:** hacker-green-on-black, neon cyberpunk, corporate SaaS, playful cartoon

The Philip K. Dick reference stays **quiet**: one line in the footer and the 404 page. No robots, no glitch effects, no sci-fi imagery.

---

## 2. Logo: typographic monogram "dLD"

### Idea
The lowercase **d** and the capital **D** mirror each other: the d's bowl faces left and the D's bowl faces right. The **L** stands between them like a spine. So the monogram is roughly symmetrical, a small typographic object that sits on the desk.

### Final: concept A, "Mirror"
"dLD." set in Geist Bold with tight spacing (−6%), the d and D optically matched so they read as a pair; the period adds an editorial full stop. In the header it sits next to a two-line IBM Plex Mono label: DISTRO L. DESK / THE FRIENDLY LINUX GUIDE. Concepts B (pressed L) and C (terminal cursor) were explored and dropped.

### Lockups
- **Monogram:** `dLD` (app icon, social avatar, favicon at 32px and up; a single `d` at 16px)
- **Horizontal:** `dLD` + `Distro L. Desk` (header)
- **Wordmark only:** `Distro L. Desk` in Geist SemiBold (footer, running text)

### Rules
- Minimum size: monogram 16px tall (favicon build), horizontal lockup 24px tall.
- Clear space: the height of the "L" on all sides.
- Colors: ink on the light surface, white on the hero gradient and dark surfaces. The favicon tile is ink (`#1F0B0C`) with white letters.
- The monogram is flat, set in ink (`#1F0B0C`) on light backgrounds and white on the hero gradient.
- The monogram is flat. No drop shadow, emboss or gradient on the letters, following `design.md`'s rule that text stays flat.
- Deliver as outlined SVG. Letters get optical adjustments (the d and D bowls matched by eye, not only by the font's metrics).

---

## 3. Color

A restrained, editorial palette. Hierarchy comes from typography, composition and the Linux screenshots, not from big gradients.

### Light theme (default)
| Token | Value | Use | Contrast |
|---|---|---|---|
| `--canvas` | `#F3F1EB` | Page background (warm off-white) | — |
| `--card` | `#FFFFFF` | Cards, windows, pills | — |
| `--ink` | `#262924` | Headlines and body text | 13.1:1 |
| `--ink-muted` | `#5F625C` | Secondary text | 5.5:1 |
| `--blue` | `#456FA5` | Identity color: primary buttons, links, serif accent words, checks, selected states | 4.6:1 as text · white on blue 5.2:1 |
| `--blue-deep` | `#3A5F8F` | Blue text on mist panels | 5.1:1 on mist |
| `--mist` | `#D6E4F1` | Illustration panels, screenshot placeholders, glow | — |
| `--peach` | `#F0B99F` | **Glow only** (diffuse, behind screenshots). Never text | 1.5:1 |
| `--pill` | `#ECEAE3` | Tabs track, alternative pills | — |
| `--rule` | `#A9A99F` | Thin rules (at 45–60% opacity), unselected borders | — |
| Window dots | `#E6A08B` · `#E7C98A` · `#A9C39A` | The three dots on screenshot windows | decorative |

### Dark theme
| Token | Value |
|---|---|
| `--canvas` | `#171816` |
| `--card` | `#20221F` |
| `--ink` / `--ink-muted` | `#EEEBE3` (15:1) / `#A9ABA4` (7.7:1) |
| `--blue` | `#8FB3E0` (8.2:1); primary button text becomes `#171816` |
| `--mist` | `#1F2A36` |
| `--peach` | `#F0B99F` (glow only) |

### Usage rules
- **Blue is the only strong color.** One primary (blue) button per view; the rest are white or text links.
- **Peach is atmosphere**, a soft blurred glow behind a screenshot, never a background for text.
- **Selected states:** blue 1.5px border + blue check circle. Not color alone.
- The previous palettes (yellow, then blue-to-peach hero gradient with espresso buttons) are retired.

## 4. Typography

| Role | Typeface | Use |
|---|---|---|
| UI and text | **Geist** (Regular, Medium, SemiBold, Bold; OFL) | Everything by default: nav, body, buttons, cards, headings |
| Editorial accent | **Instrument Serif** (Regular, Italic; OFL) | Only (1) one or two italic words inside a big headline, e.g. "a *fresh start*", "matters *most*", colored `--blue`; (2) large figures in the facts ("Free.", "2031"); (3) the distro name in the recommendation. **Never** in navigation, buttons, cards, form controls or body text |
| Technical labels | **IBM Plex Mono** (Regular, Medium; OFL) | Chapter labels (`01 / DISCOVER`), eyebrows, figure captions (`FIG. 01 / THE DESKTOP`), window titles, versions, counts |

**Scale (desktop / mobile)**
| Style | Font | Size / line height | Tracking |
|---|---|---|---|
| Display (hero) | Geist SemiBold + Instrument Serif Italic accent | 88/88 (serif word 100) · mobile 46/48 (serif 52) | −4% (serif −1%) |
| H1 section | Geist SemiBold (+ serif accent) | 56/60 · mobile 38/42 | −3% |
| H2 | Geist SemiBold | 36/42 | −2% |
| H3 | Geist SemiBold | 22/28 | −1% |
| Body large | Geist Regular | 19/30 | 0 |
| Body | Geist Regular | 16/25 | 0 |
| Label / button | Geist Medium | 15/20 | 0 |
| Figure | Instrument Serif Regular | 84 (lead fact), 64 (others) | −2% |
| Mono label | IBM Plex Mono Medium | 12/16, uppercase | +8% |
| Mono small | IBM Plex Mono Regular | 13/18 | 0 |

## 5. Iconography

- **Lucide** (ISC license): 1.75px stroke, 20px default, 24px in feature items.
- Icons are flat and use `--ink`, `--link` or `--accent-blue`. They are never embossed.
- Use real-world metaphors where they help people understand (lock = encryption, rotate-ccw = rollback, gamepad = gaming, usb = live USB).

---

## 6. Image brief (for the site owner)

You'll provide the images. This list says what the page needs and in what format.

| # | Image | Where | Size (export) | Notes |
|---|---|---|---|---|
| 1–6 | Desktop screenshot of each featured distro: Ubuntu 26.04, Omarchy 4, Fedora 44, Pop!_OS COSMIC, Linux Mint, Debian 13 | §6 profile "More details" panel | 2560×1600 (16:10) | Default wallpaper and theme, one or two apps open, no personal data. Light mode where the distro has one. |
| 7–13 | Screenshots of the other distros: Zorin 18, elementary 8.1, Bazzite, CachyOS, SteamOS, openSUSE, NixOS | §7 cards (optional) | 1600×1000 | Same rules; can be added later |
| 14–20 | One screenshot per desktop environment: GNOME 50, Plasma 6.7, COSMIC, Cinnamon, Hyprland, Pantheon, Xfce | §10 (optional; drawn layouts are the fallback) | 1600×1000 | Same app open in each (e.g. Files) for a fair comparison |
| 21 | Open Graph image | Link previews | 1200×630 | I'll design this in Figma. No photo needed. |

**Format:** PNG originals. The build exports AVIF + WebP at 1× and 2×.
**Rights:** only screenshots you take yourself, or images whose license allows reuse. Keep a note of the source of each file.
**Naming:** `distro-ubuntu-26.04.png`, `desktop-gnome-50.png`, and so on.
**Until they arrive:** Figma uses neutral placeholders at the correct aspect ratio.

---

## 7. Voice (short version)

See `content/copy.md` for the full rules. In brief: second person, short sentences, specific facts with versions and dates, no hype, and nothing presented as "just works".

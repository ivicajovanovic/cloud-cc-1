# brand.md: Distro L. Desk

The identity layer on top of `design.md`. Where they differ, **this file wins** for color, type and logo. `design.md` still governs shadows, shape, components and accessibility.

## Decisions (confirmed)

| Topic | Decision |
|---|---|
| Name | **Distro L. Desk**, a nod to Philip K. Dick |
| Logo | **Typographic monogram "dLD", concept A (Mirror)**: final |
| Default theme | **Light**, with a dark theme via toggle or system preference |
| Visual style | **Relaxed Soft UI**: airy split layouts, illustrated blue panels, white pills and cards with one gentle drop shadow. The strong two-sided neumorphic shadows are retired (see `design.md` §16) |
| Distro keys | **Neutral** soft keycaps with text monograms; no distro brand colors or logos |
| Design tool | **Figma**. The code implements the Figma file. |
| Images | **Provided by the site owner** (see §6 for the brief) |
| Palette | **Relaxed blue & espresso** (replaces yellow, chosen by the site owner from two reference designs): soft grey page, dusty-blue panels, espresso-to-brown buttons, a blue accent, and a blue-to-peach hero gradient. See §3 |
| Typefaces | **Inter** + **JetBrains Mono**: final |
| Tone of the hero | **Plain language for non-technical visitors**: no version numbers, jargon or distro abbreviations above the fold |

---

## 1. Personality

**Calm, friendly, laid back.** Airy light-grey pages, soft dusty-blue panels with simple diagrams, white pills and cards, and warm espresso buttons. Monospace labels add a small technical accent. It should feel trustworthy enough for a newcomer and exact enough for an Arch user.

- **Is:** tactile, quiet, exact, warm, independent
- **Isn't:** hacker-green-on-black, neon cyberpunk, corporate SaaS, playful cartoon

The Philip K. Dick reference stays **quiet**: one line in the footer and the 404 page. No robots, no glitch effects, no sci-fi imagery.

---

## 2. Logo: typographic monogram "dLD"

### Idea
The lowercase **d** and the capital **D** mirror each other: the d's bowl faces left and the D's bowl faces right. The **L** stands between them like a spine. So the monogram is roughly symmetrical, a small typographic object that sits on the desk.

### Final: concept A, "Mirror"
"dLD" set in Inter Black with tight spacing (−6%), the d and D optically matched so they read as a pair. Concepts B (pressed L) and C (terminal cursor) were explored and dropped.

### Lockups
- **Monogram:** `dLD` (app icon, social avatar, favicon at 32px and up; a single `d` at 16px)
- **Horizontal:** `dLD` + `Distro L. Desk` (header)
- **Wordmark only:** `Distro L. Desk` in Inter Semibold (footer, running text)

### Rules
- Minimum size: monogram 16px tall (favicon build), horizontal lockup 24px tall.
- Clear space: the height of the "L" on all sides.
- Colors: ink on the light surface, white on the hero gradient and dark surfaces. The favicon tile is ink (`#1F0B0C`) with white letters.
- The monogram is flat, set in ink (`#1F0B0C`) on light backgrounds and white on the hero gradient.
- The monogram is flat. No drop shadow, emboss or gradient on the letters, following `design.md`'s rule that text stays flat.
- Deliver as outlined SVG. Letters get optical adjustments (the d and D bowls matched by eye, not only by the font's metrics).

---

## 3. Color

Taken from the owner's two reference designs (sampled from the images) and adjusted where needed for WCAG AA. Contrast ratios are against the surface they're used on.

### Light theme (default)
| Token | Value | Use | Contrast |
|---|---|---|---|
| `--surface` | `#F4F4F4` | Page background | — |
| `--card` | `#FFFFFF` | Cards, pills, secondary buttons | — |
| `--panel-blue` | `#C4D5E9` | Illustration panels | — |
| `--pill` | `#EEF2F8` | Pale pill fills, pressed states | — |
| `--ink` | `#1F0B0C` | Headings, primary text, selected pill fill | 17.2:1 on surface |
| `--ink-muted` | `#625E5F` | Body text (darkened from the reference's `#6F6B6C` so it also passes on blue panels) | 5.8:1 surface · 4.3:1 panel* |
| `--cta` → `--cta-end` | `#271010` → `#754211` | Primary button: linear gradient, left to right | white text 8.3–18:1 |
| `--on-cta` | `#FFFFFF` | Text on the primary button | — |
| `--accent-blue` | `#258EFA` | Icons, dashed lines, cursor, indicator dots (graphics only) | 3.0:1 (non-text minimum) |
| `--link` | `#1A64B8` | Blue text: links, pill labels | 5.4:1 surface · 5.3:1 pill |
| `--hero-top` | `#3F74A4` | Hero gradient, top (behind all white hero text) | white text ≥ 4.5:1 |
| `--hero-mid` | `#A9BBD0` | Hero gradient, middle | — |
| `--peach` | `#FBE3D7` | Hero gradient, bottom | — |
| `--control-edge` | `#A7AEB9` | Input borders, dividers | 3:1 boundary |

\* Body text directly on a blue panel should be avoided; panels hold illustrations and pills, while text sits on the grey surface.

**Hero gradient:** `linear-gradient(180deg, #3F74A4 0%, #3F74A4 42%, #A9BBD0 70%, #FBE3D7 100%)`. On mobile, hold the deep blue to 60%. All white text must sit in the deep-blue zone.

### Dark theme
| Token | Value |
|---|---|
| `--surface` | `#131516` |
| `--card` | `#1C1F22` |
| `--panel-blue` | `#1C2836` |
| `--pill` | `#232A33` |
| `--ink` | `#F2EFEC` (16:1) |
| `--ink-muted` | `#A8A4A5` (7.4:1) |
| `--cta` → `--cta-end` | `#F2EFEC` → `#F3C9B5` (light button, espresso text `#271010`) |
| `--accent-blue` / `--link` | `#6AAEF7` (7.9:1) |
| Hero gradient | `#1B3552` → `#22303F` → `#3A2A25` |

### Usage rules
- **One primary (espresso) button per view.** On the hero gradient, the main button is **white** with ink text (as in the reference).
- **Selected states:** a selected pill turns **ink** (espresso-black) with white text. Indicator dots use `--accent-blue`.
- **Links:** `--link`, underlined in body text.
- **Blue panels** carry illustrations (rings, dashed paths, pills, screenshot cards). They don't carry running text.
- **Yellow `#FCC624` is retired.**

## 4. Typography

| Role | Typeface | Weights | Use |
|---|---|---|---|
| Display and UI | **Inter** (OFL) | 400, 500, 600, 700 | Headings, body, buttons |
| Data and labels | **JetBrains Mono** (OFL) | 400, 600, 700 | Version numbers, dates, key numbers, eyebrows, commands, table figures, monograms on keys |

- Self-host both as woff2 subsets (Latin + Latin Extended).
- Eyebrows (small labels above headings): JetBrains Mono Medium (the family has no SemiBold), 12–13px, uppercase, +0.06em tracking, `--ink-muted`.
- Key numbers (e.g. "7.0", "2031"): JetBrains Mono 700, 40–56px, with tabular figures.
- Commands (`apt`, `dnf`, `sudo-rs`): JetBrains Mono in an inset "chip".
- Everything else follows the type scale in `design.md` §3.5.

---

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

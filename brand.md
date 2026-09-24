# brand.md: Distro L. Desk

The identity layer on top of `design.md`. Where they differ, **this file wins** for color, type and logo. `design.md` still governs shadows, shape, components and accessibility.

## Decisions (confirmed)

| Topic | Decision |
|---|---|
| Name | **Distro L. Desk**, a nod to Philip K. Dick |
| Logo | **Typographic monogram "dLD", concept A (Mirror)**: final |
| Default theme | **Light**, with a dark theme via toggle or system preference |
| Distro keys | **Neutral** soft keycaps with text monograms; no distro brand colors or logos |
| Design tool | **Figma**. The code implements the Figma file. |
| Images | **Provided by the site owner** (see §6 for the brief) |
| Accent color | **Yellow `#FCC624`**: final (chosen by the site owner) |
| Typefaces | **Inter** + **JetBrains Mono**: final |
| Tone of the hero | **Plain language for non-technical visitors**: no version numbers, jargon or distro abbreviations above the fold |

---

## 1. Personality

**Calm, friendly, precise, a little uncanny.** It looks like a well-made physical control desk: soft material, one warm yellow indicator light, labels set in monospace. It should feel trustworthy enough for a newcomer and exact enough for an Arch user.

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
- Colors: ink on the light surface, light ink on the dark surface. The favicon tile is ink with the letters in yellow.
- The monogram is flat. No drop shadow, emboss or gradient on the letters, following `design.md`'s rule that text stays flat.
- Deliver as outlined SVG. Letters get optical adjustments (the d and D bowls matched by eye, not only by the font's metrics).

---

## 3. Color

Built on `design.md` §3, replacing its blue accent with **yellow `#FCC624`**. Contrast ratios are measured against the surface they're used on.

**Important:** the yellow has only **1.25:1** contrast against the light surface. So it's used **only as a fill** with dark text on top, never as text or a thin line on the light surface. Small yellow indicators (dots, lamps) always get a 1.5px `--yellow-ink` outline so the state stays visible.

### Light theme (default)
| Token | Value | Use | Contrast |
|---|---|---|---|
| `--surface` | `#E0E5EC` | Page and element material | — |
| `--ink` (= `--text`) | `#2F3547` | Body text, logo | 9.6:1 |
| `--ink-muted` | `#586074` | Secondary text | 5.0:1 |
| `--yellow` | `#FCC624` | **Fills only**: primary button, active indicator dots, finder result lamp | 1.25:1 (fill only) |
| `--on-yellow` | `#1F1A12` | Text and icons on yellow fills | 10.9:1 |
| `--yellow-ink` | `#735500` | Yellow-family **text, links, focus ring, outlines** on the light surface | 5.5:1 |

### Dark theme
| Token | Value | Use | Contrast |
|---|---|---|---|
| `--surface` | `#2A2D34` | Page and element material | — |
| `--ink` | `#E4E7EE` | Body text, logo | 11.1:1 |
| `--ink-muted` | `#A9B0BF` | Secondary text | 6.3:1 |
| `--yellow` | `#FCC624` | Fills | 8.7:1 |
| `--on-yellow` | `#1F1A12` | Text on yellow fills | 10.9:1 |
| `--yellow-ink` | `#FCC624` | Links, focus ring, yellow text | 8.7:1 |

### Usage rules
- **Yellow is scarce.** One primary button per view, active states, the indicator lights. Never as a section background.
- **Links:** `--yellow-ink`, always underlined in body text.
- **Status colors** (success, danger, warning) stay as in `design.md`, but they're rarely needed on this site.
- **Keys are neutral:** surface material + ink icon or monogram. The only color is a small yellow indicator dot (with outline) when a key is active.

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
- Icons are flat and use `--ink` or `--yellow-ink`. They are never embossed.
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

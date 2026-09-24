# brand.md: Distro L. Desk

The identity layer on top of `design.md`. Where they differ, **this file wins** for color, type and logo. `design.md` still governs shadows, shape, components and accessibility.

## Decisions (confirmed)

| Topic | Decision |
|---|---|
| Name | **Distro L. Desk**, a nod to Philip K. Dick |
| Visual direction | **A contemporary Linux desktop, presented with the precision of a premium software product.** GNOME is the reference for spacing, clarity and product presentation. The real Linux desktops are the visual identity. See `design.md` §18 |
| Logo | **"dLD."** in Inter SemiBold (600), flat, in `--text`. The full name "Distro L. Desk" appears in the footer and page title |
| Default theme | **Light**, with a dark theme via toggle or system preference |
| Palette | Background `#F8F9FA`, text `#202124`, accent `#3584E4` (text and button fills use `#1C71D8`), secondary surfaces `#EAF2FC`, borders `#DDE2E8` |
| Typefaces | **Inter** 400 and 600 for everything; **IBM Plex Mono** 11px only for technical labels. No serif |
| Shape | 8px radius for controls, 16px for large surfaces; 1px borders; shadows only on floating elements |
| Distro keys | Text only; no distro brand colors or official logos |
| Design tool | **Figma**. The code implements the Figma file. |
| Images | **Real screenshots, provided by the site owner** (see §6). They are the most important design asset |
| Tone of the hero | **Plain language for non-technical visitors**: no version numbers, jargon or distro abbreviations above the fold |
| Retired | The editorial direction (Geist, Instrument Serif, beige canvas, peach glow, window dots, numbered chapters), and before it the relaxed Soft UI and neumorphism |

---

## 1. Personality

**Clear, calm and exact, like a well-made desktop.** The site presents Linux desktops the way a good software company presents its product: big, real screenshots, generous spacing, a clear hierarchy and one blue for action. It's friendly to a newcomer through plain language and clarity, not through decoration.

- **Is:** clear, precise, calm, honest, useful
- **Isn't:** editorial-decorative, hacker-green-on-black, neon, dark-tech, corporate SaaS with stat cards, a fake OS application

The Philip K. Dick reference stays **quiet**: one line in the footer and the 404 page.

---

## 2. Logo: "dLD."

The lowercase **d** and the capital **D** mirror each other around the **L**. The period is a full stop.

- Set in **Inter SemiBold**, 24px in the header (20px on mobile), tracking −4%.
- Colors: `--text` (`#202124`) on light and `#E8EAED` on dark. The favicon is a `#202124` rounded tile (8px radius at 32px) with the white letters "dL" or, at 16px, a single "d".
- Flat: no shadow, gradient or outline. Clear space equals the height of the "L".
- The link has `aria-label="Distro L. Desk, home"`.

---

## 3. Color

Hierarchy comes from the screenshots, type and spacing. The blue is used for action and selection only.

### Light theme (default)
| Token | Value | Use | Contrast |
|---|---|---|---|
| `--bg` | `#F8F9FA` | Page background | — |
| `--surface` | `#FFFFFF` | Controls, menus | — |
| `--surface-2` | `#EAF2FC` | Secondary surfaces: selected options, callouts, image placeholders | — |
| `--text` | `#202124` | Headings and body | 15.3:1 |
| `--text-muted` | `#5F6368` | Secondary text, mono captions | 5.7:1 |
| `--accent` | `#3584E4` | Focus rings, selected borders, checks, icons | 3.6:1 (non-text, ≥ 3:1) |
| `--accent-strong` | `#1C71D8` | Primary button fill, links | white on it 4.8:1 · as text 4.5:1 |
| `--accent-on-surface-2` | `#1A5FB4` | Blue text on `#EAF2FC` | 5.6:1 |
| `--border` | `#DDE2E8` | 1px borders | decorative |
| `--control-edge` | `#8A9099` | Checkbox and input edges | 3.05:1 |

### Dark theme
| Token | Value |
|---|---|
| `--bg` / `--surface` / `--surface-2` | `#1C1D1F` / `#26272A` / `#1E2A3A` |
| `--text` / `--text-muted` | `#E8EAED` (14.2:1) / `#9AA0A6` (6.5:1) |
| `--accent` / `--accent-strong` | `#78AEED` (7.4:1); primary button label `#1C1D1F` |
| `--accent-on-surface-2` | `#99C1F1` |
| `--border` | `#3A3D42` |

### Rules
- **One primary button per view.** Everything else is a secondary button or a text link.
- **Selected states** use a blue border, a filled check and a tinted fill, not color alone.
- No gradients, glows or colored panels behind images.

## 4. Typography

| Role | Typeface | Use |
|---|---|---|
| Everything | **Inter** 400 (Regular) and 600 (SemiBold); OFL; self-hosted woff2 (variable or two static files) | Headings, body, nav, buttons, options |
| Technical labels | **IBM Plex Mono** Regular, 11px, uppercase, +6% | Screenshot captions ("UBUNTU / GNOME"), versions, "YOUR MATCH". Never decorative |

**Scale (desktop / mobile)**
| Style | Size / line height | Weight | Tracking |
|---|---|---|---|
| Display (h1) | 72/76, max 850px · 42/46 | 600 | −2.5% |
| H2 | 44/50 · 32/38 | 600 | −2% |
| H3 | 24/30 · 20/26 | 600 | −1% |
| Body large | 18/28, max 560px · 16/24 | 400 | 0 |
| Body | 16/24 | 400 | 0 |
| Label / button | 16/24 | 600 | 0 |
| Small | 14/20 | 400 | 0 |
| Mono label | 11/16, uppercase | Plex Mono 400 | +6% |

## 5. Iconography

- **Lucide** (ISC license): 1.75px stroke, 20px default, 24px in feature items.
- Icons are flat and use `--text`, `--text-muted` or `--accent`. Keep them few: check marks, arrows, the external-link mark and the theme toggle.
- Use real-world metaphors where they help people understand (lock = encryption, rotate-ccw = rollback, gamepad = gaming, usb = live USB).

---

## 6. Image brief (for the site owner)

The screenshots are the website's visual identity, so they come **before** any further color or type work. Every screenshot is real: taken by you, or used under a license that allows it. Nothing is redrawn.

### Priority 1: needed before the next design round (3 images)
| File | Shows | Used in |
|---|---|---|
| `distro-ubuntu-26.04.png` | Ubuntu 26.04, **GNOME** desktop | Hero (full width), Desktops, Ubuntu profile, recommender |
| `distro-linux-mint.png` | Linux Mint 22.x, **Cinnamon** desktop | Desktops, Mint profile, recommender |
| `distro-fedora-kde-44.png` | Fedora 44 **KDE Plasma** edition | Desktops, Fedora profile |

### Priority 2: before launch
| File | Shows | Used in |
|---|---|---|
| `distro-omarchy-4.png` | Omarchy 4 (Hyprland) | Profile, recommender |
| `distro-popos-24.04.png` | Pop!_OS 24.04, COSMIC | Profile, recommender |
| `distro-debian-13.png` | Debian 13, GNOME | Profile |
| `distro-linux-mint-xfce.png` | Linux Mint, Xfce edition | Recommender |
| `distro-zorin-18.png` · `distro-elementary-8.1.png` · `distro-bazzite.png` · `distro-xubuntu.png` · `distro-fedora-44.png` (GNOME Workstation) | — | Recommender, More versions |

Every recommender candidate needs a screenshot, because the result shows it full width.

### Capture rules (the same for every image, so they look like one set)
- **Size:** 2560×1600 (16:10) PNG. The build crops 16:9 for the hero from the **bottom**, so top bars and panels stay visible.
- **Content:** the distro's default wallpaper and theme, light mode where it exists, 100% scaling, English (US) language.
- **Apps:** the same composition everywhere: the **Files** app open on the left half with Documents, Pictures, Music and Downloads, and the app menu or launcher closed. Leave the dock/taskbar visible.
- **Clean:** no personal names, emails, Wi-Fi names, notifications or browser tabs. The clock should read a neutral time.
- **Mobile crop:** the build uses one art-directed crop per image (about 4:5). Put the main app window roughly in the left 60% so the crop keeps both it and the panel.
- **Rights:** note the source of every file in `assets/img/SOURCES.md`.

The Open Graph image (1200×630) will be made from the Ubuntu screenshot and the hero headline.

---

## 7. Voice (short version)

See `content/copy.md` for the full rules. In brief: second person, short sentences, specific facts with versions and dates, no hype, and nothing presented as "just works".

# design.md: Soft UI (Neumorphism)

> **Project direction (latest, September 2026):** Distro L. Desk uses the **Linux desktop, product-precise** direction (§18). It overrides §17 (editorial), §16 (relaxed Soft UI) and the neumorphic rules. Accessibility, motion and component-state rules below still apply; where a value differs, §18 wins.

This document defines the visual language for our interfaces: **Soft UI**, better known as *neumorphism*. Designers and engineers should both work from it. It covers the principles, design tokens, component recipes, accessibility rules and the do's and don'ts that come from how the style has been used in real products (and from its well-known failures).

> **In one sentence:** controls look like they are pressed out of, or into, the same soft material as the background. A single light source lights them, and they stay legible because we use color, type and contrast where shadow alone can't do the job.

---

## 1. What the style is and where it comes from

| Concept | Meaning for us |
|---|---|
| **Skeuomorphism** | UI that copies a physical object (a trash can for delete, a floppy disk for save, leather-stitched calendars). It is easy to understand because people already know the object. Taken too far it gets cluttered and dated. |
| **Flat design** | The reaction against skeuomorphism: no depth, only color and type. Clean, but affordances can get weaker, because it can be hard to tell what is clickable. |
| **Neumorphism (new + skeuomorphism)** | A middle path. Shapes stay minimal and flat-colored, but pairs of soft shadows make them look **extruded from** or **pressed into** the surface. You get the tactile quality of skeuomorphism with the restraint of flat design. |

The style became popular around 2019–2020 through Dribbble concept work (Alexander Plyuto's banking app shot; the name "neumorphism" was popularized by Michal Malewicz). Its influence shows in polished fintech, productivity and control-panel interfaces, and in soft-depth details in Apple's platform UI. The early wave also drew a lot of criticism for **low contrast and weak affordance**. This spec is written to keep the tactile appeal while fixing those problems.

### Where it works well
- Fintech dashboards, wallets and balance cards
- Productivity tools, timers, focus apps
- Smart-home, audio and hardware-style control panels (knobs, toggles, sliders)
- Settings screens, calculators, music players
- Small, focused surfaces with a limited number of controls

### Where it does not work well
- Content-dense UIs (tables, feeds, long forms, admin panels)
- Anything where users must scan many controls quickly
- Brand surfaces that need strong color or photography as the main visual
- Products with strict accessibility requirements where soft UI would be the **only** affordance (see §7)

---

## 2. Core principles

1. **One material.** Elements and background share the same base color. Depth comes only from light and shadow, not from a different fill. That is what makes things look *molded*, not *placed*.
2. **One light source: top-left.** Every raised element has a light highlight toward the top-left and a dark shadow toward the bottom-right. Never mix directions on one screen.
3. **Depth tells you state.** *Raised* = available or resting. *Pressed/inset* = active, selected, or an input well. *Flat* = disabled or structural. The same depth always means the same thing.
4. **Soft, not sharp.** Large blur radius, low opacity, generous corner radius. Nothing should look like a hard drop shadow.
5. **Restraint.** Use depth only on things you can touch or that you need to group. Most text, icons and dividers stay flat. If everything is raised, nothing stands out.
6. **Color does the work shadow can't.** Every primary action, state and alert uses a real accent color, label or icon, not a shadow on its own.
7. **Physical metaphor, with a purpose.** Borrow from real objects (switches, dials, keys, buttons) when it helps people understand the control. Don't add decorative realism (textures, stitching, gloss).

---

## 3. Design tokens

> **Project note:** for Distro L. Desk, the accent (`--accent`) is replaced by the **blue & espresso** tokens in `brand.md` §3, and the typefaces by `brand.md` §4. Every other token below still applies.

### 3.1 Color: light theme (default)

| Token | Value | Use |
|---|---|---|
| `--surface` | `#E0E5EC` | Page background **and** default element fill |
| `--surface-raised` | `#E6EBF2` | Optional subtle top gradient stop for convex elements |
| `--surface-sunken` | `#D6DCE4` | Optional fill for deep wells |
| `--shadow-light` | `#FFFFFF` (at 0.8–1 opacity) | Highlight (top-left) |
| `--shadow-dark` | `#A3B1C6` (at 0.6–0.7 opacity) | Shadow (bottom-right) |
| `--text` | `#2F3547` | Primary text (≈ 9:1 on surface) |
| `--text-muted` | `#586074` | Secondary text (≈ 4.9:1 on surface, passes AA) |
| `--accent` | `#3B5BDB` | Primary action, selected state, focus ring (≈ 4.8:1 on surface) |
| `--on-accent` | `#FFFFFF` | Text/icons on accent fills (≈ 6:1) |
| `--success` | `#2B8A3E` | Positive values, confirmations |
| `--danger` | `#C92A2A` | Errors, destructive actions |
| `--warning` | `#B35C00` | Warnings (use with icon + text) |
| `--control-edge` | `#9AA6B8` | 1px edge for inputs/controls that need 3:1 boundary contrast |

**Rules for the base color**
- Never use pure white (`#FFF`) or pure black (`#000`) as the surface. The highlight or the shadow won't show up.
- Pick a light, slightly desaturated base (lightness ~88–92%) and derive the shadows from the **same hue**: highlight = base lightened ~10–15%, shadow = base darkened ~20–25% with a slight shift toward the hue. Pastel tints work (soft blue, sand, sage) as long as the shadows are derived from them.
- Keep the whole screen on **one** surface color. Cards don't get a different background.

### 3.2 Color: dark theme

| Token | Value |
|---|---|
| `--surface` | `#2A2D34` |
| `--shadow-light` | `#363A43` |
| `--shadow-dark` | `#1C1E23` |
| `--text` | `#E4E7EE` |
| `--text-muted` | `#A9B0BF` |
| `--accent` | `#7C94F0` |
| `--on-accent` | `#10131A` |
| `--control-edge` | `#5B616E` |

Dark neumorphism depends mostly on the **dark** shadow. Keep the highlight subtle (a small lightness step above the surface), or the element looks outlined instead of lit.

### 3.3 Elevation / shadow scale

Every depth level is a **pair** of shadows: dark at `+x,+y`, light at `−x,−y`. Blur ≈ 2× the offset.

| Token | Offset | Blur | Use |
|---|---|---|---|
| `--elev-1` | 3px | 6px | Chips, small icon buttons, toggles |
| `--elev-2` | 6px | 12px | Buttons, inputs, list items |
| `--elev-3` | 10px | 20px | Cards, panels |
| `--elev-4` | 16px | 32px | Hero cards, large dials (use sparingly) |

Guidelines:
- Offset scales with element size: roughly **5–10% of the element's smaller dimension**. Small elements with big shadows look muddy.
- Nested elements use a **lower** level than their parent.
- Don't go past `--elev-4`. Deep shadows break the "same material" illusion.

### 3.4 Shape

| Token | Value | Use |
|---|---|---|
| `--radius-sm` | 10px | Chips, small buttons |
| `--radius-md` | 16px | Buttons, inputs |
| `--radius-lg` | 24px | Cards, panels |
| `--radius-full` | 9999px | Pills, toggles, round icon buttons, dials |

Soft UI needs generous radii. Sharp corners with soft shadows look wrong.

### 3.5 Typography

- **Family:** a clean humanist or geometric sans with good weight range, e.g. `Inter`, `Manrope`, `Nunito Sans`, or the system stack (`-apple-system, "Segoe UI", Roboto, sans-serif`).
- **Text is flat.** No shadows, embossing or debossing on text. It hurts legibility.
- Use **weight and color** for hierarchy, because the surface is low-contrast:

| Token | Size / line-height | Weight |
|---|---|---|
| `--type-display` | 40 / 48 | 700 |
| `--type-h1` | 28 / 36 | 700 |
| `--type-h2` | 22 / 30 | 600 |
| `--type-h3` | 18 / 26 | 600 |
| `--type-body` | 16 / 24 | 400–500 |
| `--type-small` | 14 / 20 | 500 |
| `--type-caption` | 12 / 16 | 600 (uppercase optional, +0.04em tracking) |

- Body text minimum 16px. Prefer weight 500 for UI labels. Thin weights disappear on soft backgrounds.
- Numbers in fintech views: use tabular figures (`font-variant-numeric: tabular-nums`).

### 3.6 Spacing

8-point grid: `4, 8, 12, 16, 24, 32, 48, 64`.
Shadows need room: keep at least **2× the shadow offset** between neighboring raised elements, or their shadows merge into a grey smear. Soft UI layouts should feel **airy**. Leave more whitespace than you would in a flat design.

### 3.7 Motion

| Token | Value |
|---|---|
| `--dur-fast` | 120ms (press) |
| `--dur-base` | 200ms (hover, toggle) |
| `--ease` | `cubic-bezier(0.2, 0.8, 0.2, 1)` |

- Animate `box-shadow` (and optionally `transform: scale(0.98)`) between raised and inset when pressed. That is how the style feels physical.
- Respect `prefers-reduced-motion`: switch state instantly, no scale.

---

## 4. Reference CSS

```css
:root {
  --surface: #E0E5EC;
  --shadow-light: rgba(255, 255, 255, 0.9);
  --shadow-dark: rgba(163, 177, 198, 0.65);
  --text: #2F3547;
  --text-muted: #586074;
  --accent: #3B5BDB;
  --on-accent: #FFFFFF;
  --control-edge: #9AA6B8;

  --radius-md: 16px;
  --radius-lg: 24px;
  --dur-fast: 120ms;
  --dur-base: 200ms;
  --ease: cubic-bezier(0.2, 0.8, 0.2, 1);

  /* Raised (convex / extruded) */
  --raised-1: 3px 3px 6px var(--shadow-dark), -3px -3px 6px var(--shadow-light);
  --raised-2: 6px 6px 12px var(--shadow-dark), -6px -6px 12px var(--shadow-light);
  --raised-3: 10px 10px 20px var(--shadow-dark), -10px -10px 20px var(--shadow-light);

  /* Inset (concave / pressed) */
  --inset-1: inset 2px 2px 4px var(--shadow-dark), inset -2px -2px 4px var(--shadow-light);
  --inset-2: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light);
}

@media (prefers-color-scheme: dark) {
  :root {
    --surface: #2A2D34;
    --shadow-light: rgba(54, 58, 67, 0.9);
    --shadow-dark: rgba(20, 22, 26, 0.8);
    --text: #E4E7EE;
    --text-muted: #A9B0BF;
    --accent: #7C94F0;
    --on-accent: #10131A;
    --control-edge: #5B616E;
  }
}

body {
  background: var(--surface);
  color: var(--text);
  font-family: Inter, -apple-system, "Segoe UI", Roboto, sans-serif;
}

/* Card */
.card {
  background: var(--surface);
  border-radius: var(--radius-lg);
  box-shadow: var(--raised-3);
  padding: 24px;
}

/* Button: raised at rest, inset when pressed */
.btn {
  background: var(--surface);
  color: var(--text);
  border: none;
  border-radius: var(--radius-md);
  padding: 12px 20px;
  font-weight: 600;
  box-shadow: var(--raised-2);
  transition: box-shadow var(--dur-base) var(--ease), transform var(--dur-fast) var(--ease);
  cursor: pointer;
}
.btn:hover  { box-shadow: var(--raised-1); }
.btn:active { box-shadow: var(--inset-2); transform: scale(0.98); }

/* Primary: color, not just shadow, marks the main action */
.btn--primary {
  background: var(--accent);
  color: var(--on-accent);
  box-shadow: var(--raised-2);
}

/* Focus: always a visible, high-contrast ring */
.btn:focus-visible,
.input:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
}

/* Input: an inset well with a real edge for boundary contrast */
.input {
  background: var(--surface);
  color: var(--text);
  border: 1px solid var(--control-edge);
  border-radius: var(--radius-md);
  padding: 12px 16px;
  box-shadow: var(--inset-2);
}

.btn:disabled {
  box-shadow: none;
  color: var(--text-muted);
  opacity: 0.6;
  cursor: not-allowed;
}

@media (prefers-reduced-motion: reduce) {
  * { transition: none !important; }
  .btn:active { transform: none; }
}

@media (prefers-contrast: more) {
  :root { --shadow-dark: rgba(90, 100, 120, 0.9); }
  .btn, .card { border: 1px solid var(--control-edge); }
}
```

**Optional convex / concave fill.** Add a subtle gradient in the light direction for rounded, lit surfaces (dials, round buttons):

```css
.convex  { background: linear-gradient(145deg, #F0F5FC, #CACED4); }
.concave { background: linear-gradient(145deg, #CACED4, #F0F5FC); }
```

Use gradients only on circular and large controls. On everyday buttons they add noise.

---

## 5. Component recipes

| Component | Resting | Hover | Active / selected | Focus | Disabled |
|---|---|---|---|---|---|
| **Button (secondary)** | `raised-2`, text label | `raised-1` (slightly closer) | `inset-2`, scale 0.98 | 2px accent outline | flat, muted text |
| **Button (primary)** | Accent fill + `raised-2` | Accent 8% darker | `inset-2` on accent | Accent outline, offset 3px | flat, 50% accent |
| **Icon button** | Round, `raised-1`, icon ≥ 20px, `aria-label` | `raised-1` + icon in accent | `inset-1`, icon in accent | outline | flat |
| **Toggle / switch** | Inset track (`inset-1`), raised knob (`raised-1`) | — | Track fills with accent; knob slides | outline around track | flat, muted |
| **Checkbox / radio** | Inset well with edge | — | Accent fill + check/dot icon | outline | flat |
| **Segmented control / tabs** | Inset track | — | Selected segment **raised** + accent text | outline | — |
| **Text input** | Inset well + `--control-edge` border + visible label above | — | — | Accent border + outline | flat, muted |
| **Slider** | Inset track, raised round thumb | Thumb `raised-2` | Filled track in accent | Outline on thumb | flat |
| **Dial / knob** | Large convex circle `raised-3`, indicator dot in accent | — | Indicator rotates; value shown as text | outline | flat |
| **Card** | `raised-3`, radius-lg | Optional `raised-2` if clickable | — | outline if clickable | — |
| **List item** | Flat inside a raised card; selected row `inset-1` | Subtle inset | `inset-1` + accent marker | outline | — |
| **Modal / sheet** | `raised-4` + 30–40% scrim | — | — | Focus trapped | — |
| **Alerts / toasts** | Flat surface, **colored** icon + left accent bar + text | — | — | — | — |
| **Progress / meters** | Inset track; fill in accent | — | — | — | — |

Notes:
- **Pressed = inset** is the key interaction. Every tappable raised control must show a visible inset response.
- **Toggles and segmented controls should not rely on depth alone.** The "on" state must also change color or icon, or show a text label.
- **Icons:** use simple line or duotone icons in `--text` or `--accent`. Real-world metaphors (bell, trash, lock, save) are encouraged where they clarify meaning, the useful part of skeuomorphism. Never add embossed, glossy or textured icon art.

---

## 6. Layout and composition

- **Few elements per view.** Aim for one clear focal card or control cluster per screen region.
- **Group through containment.** A raised card holds flat content. Inset wells hold inputs. Don't raise every row.
- **Maximum two depth levels** visible in one area (e.g. a raised card containing inset inputs). Three levels deep gets confusing.
- **Mix with flat.** Headers, navigation text, body copy, charts and tables stay flat on the surface. Use soft UI where people touch things.
- **Grid:** 12-column desktop / 4-column mobile, 24px gutters (16px mobile). Keep the extra breathing room around shadows.
- **Charts** (fintech): draw on a flat or inset panel, and use accent, success and danger colors for series. Don't add shadows to chart marks.

---

## 7. Accessibility (non-negotiable)

Neumorphism's biggest criticism is accessibility: controls defined only by faint shadows fail users with low vision, on low-quality screens, or in bright sunlight. These rules fix that:

1. **Text contrast:** body text ≥ **4.5:1**, large text (≥ 24px, or ≥ 18.66px bold) ≥ **3:1** against the surface (WCAG 2.2 SC 1.4.3). The tokens in §3 already meet this. Recheck any new color.
2. **Non-text contrast:** a control's boundary or state indicator must reach **3:1** against adjacent colors (SC 1.4.11). Shadows usually don't. Get there with an accent fill, a `--control-edge` border, an icon, or a text label.
3. **Never use depth alone to show state.** Selected, on/off, error and disabled states must also change color, icon or text (SC 1.4.1).
4. **Visible focus:** every interactive element gets a solid 2px accent outline with an offset on `:focus-visible` (SC 2.4.7 / 2.4.11). Never remove outlines without a replacement.
5. **Target size:** at least 44×44px touch targets (minimum 24×24px per SC 2.5.8).
6. **Labels:** inputs always have a visible label, not just a placeholder inside an inset well. Icon-only buttons need `aria-label`.
7. **Respect user preferences:** support `prefers-contrast: more` (strengthen shadows, add borders), `prefers-reduced-motion`, `forced-colors: active` (let system colors apply; shadows disappear, so borders must remain), and dark mode.
8. **Test** in bright light and on a cheap low-contrast display, at 200% zoom, with a screen reader, and keyboard-only.

---

## 8. Do's and don'ts

**Do**
- ✅ Use one surface color and derive both shadows from it
- ✅ Keep light coming from the top-left everywhere
- ✅ Use raised for "available", inset for "active/input"
- ✅ Give primary actions a solid accent fill
- ✅ Keep text flat, dark and weight ≥ 400
- ✅ Leave generous spacing so shadows don't collide
- ✅ Use real-world metaphors (switches, knobs, trash, lock) when they make a control easier to understand
- ✅ Test contrast with tools (WebAIM, Stark, the browser DevTools contrast checker)

**Don't**
- ❌ Put neumorphic elements on pure white, pure black or photo backgrounds
- ❌ Give an element a different fill from its background (it stops looking molded)
- ❌ Mix light directions or shadow scales randomly
- ❌ Make everything raised: tables, every list row, body text containers
- ❌ Emboss or deboss text
- ❌ Use only shadow to show the difference between on and off, or selected and unselected
- ❌ Hide input boundaries (an inset well with no edge and a placeholder-only label)
- ❌ Stack shadows three or more levels deep
- ❌ Add decorative realism: textures, stitching, gloss, bevel-and-emboss filters

---

## 9. Implementation notes

- **Tokens first.** Define colors, shadow pairs, radii and motion as CSS custom properties (or design tokens in Figma/Style Dictionary). Components reference tokens only, with no raw hex or shadow values.
- **Performance:** large blurred `box-shadow`s cost paint time. Avoid animating shadows on long lists. For heavy animation, animate `opacity` on a pseudo-element that holds the pressed shadow instead of re-painting `box-shadow`.
- **Theming:** because shadows derive from the surface, a new theme only needs `--surface`, the two shadow colors, text colors and accent.
- **Figma:** build components with the same two drop shadows (or inner shadows for inset) as effect styles named `raised/1–4` and `inset/1–2`, so design and code stay in sync.
- **Generators** like neumorphism.io are fine for exploring values, but copy the result into tokens rather than pasting one-off shadow values.

---

## 10. Review checklist (before shipping a screen)

- [ ] One surface color; all elements share it (except accent-filled primaries)
- [ ] Light from the top-left everywhere; shadow levels match element size
- [ ] Primary action is clearly visible without looking at shadows
- [ ] All text ≥ 4.5:1 (large ≥ 3:1)
- [ ] All control boundaries/state indicators ≥ 3:1
- [ ] Every state (hover, pressed, selected, focus, disabled, error) is defined and visible
- [ ] Focus ring visible on every interactive element
- [ ] Touch targets ≥ 44px
- [ ] Works in dark mode, high contrast, forced colors and reduced motion
- [ ] No more than two depth levels in any region; spacing ≥ 2× shadow offset
- [ ] Soft UI is used only on touchable or grouping elements; content stays flat

---

## 11. Layout system (Distro L. Desk)

| Breakpoint | Width | Columns | Gutter | Side margin |
|---|---|---|---|---|
| `sm` | 360–599px | 4 | 16px | 16px |
| `md` | 600–1023px | 8 | 24px | 32px |
| `lg` | 1024–1439px | 12 | 24px | 48px |
| `xl` | ≥ 1440px | 12 | 32px | auto (content max 1200px) |

- **Content width:** 1200px max for the page, **68ch max** for running text.
- **Figma frames:** design at **1440** (desktop) and **390** (mobile); check 768 before handoff.
- **Section rhythm:** 128px between sections on desktop, 80px on mobile. Headings sit 24px above the intro text and 48px above the content.
- **Sticky section index:** desktop has a vertical, raised control strip at the left edge of the grid (collapses to dots below 1280px). Mobile has a horizontal scrolling strip under the header that appears after the hero.
- **Header:** 72px desktop, 60px mobile. It's the flat surface color with a subtle `raised-1` shadow once the page scrolls.

## 12. Page components (beyond §5)

| Component | Used in | Depth | Notes |
|---|---|---|---|
| **Keycap** | Hero, distro profiles | Raised `2` → inset on press | Square 88px (desktop) / 64px (mobile), radius 20px. JetBrains Mono monogram, `--accent-blue` indicator dot when active (in the relaxed hero, keys are white pills that turn ink when selected) |
| **Readout** | Hero numbers, gaming stats | Inset well | Mono 700 figure + Inter label + source superscript |
| **Switch row** | Finder | Inset track + raised thumb | Segmented control with 2–4 options; active option is a white raised segment with ink text |
| **Result lamp** | Finder result | Raised card with a round `--accent-blue` "lamp" | The lamp lights up (fill fades in) when a result appears |
| **Timeline slider** | Calendar | Inset track, raised thumb | Ticks for each release; planned releases get hollow ticks |
| **Profile card** | Distros | Raised `3` | Expands in place; the facts row is a flat 4-column definition list |
| **Mini card** | More distros | Flat on surface, with a thin `--control-edge` border | Deliberately flat: there are many of them |
| **Data table** | Compare, Apps | Flat, in an inset container | Sticky first column, zebra rows with 4% ink, filter chips above (raised → inset when active) |
| **Callout** | Why now, Gaming, Hardware, Switch | Flat, 4px `--accent-blue` left bar | Icon + title + text |
| **Desktop schematic** | Desktops | Inset "screen" with flat shapes | Drawn in CSS/SVG, 16:10 |
| **Step rail** | Switch guide | Inset vertical track that fills with `--accent-blue` as you scroll | Numbered raised dots |
| **Accordion** | FAQ, source list | Raised when closed, inset when open | Chevron rotates |
| **Glossary search** | Glossary | Inset input | Results filter live; count announced |
| **Source mark** | Everywhere | Flat | Superscript mono number links to the source list |
| **Logo** | Header, footer, 404 | Flat | See `brand.md` §2 |
| **Section opening** | Every section | Flat | Eyebrow (mono) + h2 + "In short" lead paragraph (`body-lg`, max 60ch). Always visible |
| **Details panel** | Most sections | Summary is a raised pill button ("Show the details" + chevron); open panel content is flat | Native `<details>`/`<summary>`. Open state: button becomes inset, chevron rotates. Content is in the HTML either way, for search engines and find-in-page |
| **Deep-dive divider** | Between §10 and §11 | Flat | Thin `--control-edge` rule with a centered one-line note |

## 13. Flat vs. soft, per section

Depth is only for things you touch or that group content. Everything else stays flat.

| Section | Soft (raised/inset) | Flat |
|---|---|---|
| Hero | Keycaps, buttons, readouts | Headline, subhead |
| Why now | — | Text, callout |
| What's new | Icon wells (small) | Six items |
| Calendar | Slider, selected-release card | List fallback |
| Distros | Profile cards, buttons | Facts, text |
| More distros | Group filter chips | Mini cards |
| Compare | Filter chips, table container (inset) | Table |
| Finder | Switches, result card | Questions |
| Desktops | Schematic "screens" (inset) | Text |
| Update models | Four tiles | — |
| Apps | — | Steps, table |
| Gaming | Readouts | Text, callout |
| Hardware | — | Table, callout |
| Switch | Step rail | Steps |
| Glossary | Search input | Definitions |
| FAQ | Accordion items | Answers |
| Help / footer | Final CTA button | Everything else |

## 14. Motion (Distro L. Desk)

| Interaction | Motion | Duration |
|---|---|---|
| Key / button press | raised → inset + scale 0.98 | 120ms |
| Switch toggle | Thumb slides, track fills | 200ms |
| Finder result | Card rises (inset → raised), lamp fades in | 240ms |
| Timeline scrub | Selected card cross-fades | 160ms |
| Accordion | Height + chevron rotate | 200ms |
| Section enter (optional) | Fade + 8px rise, once only | 300ms |
| Logo cursor (concept C only) | One blink on load | 1 blink |

With `prefers-reduced-motion`: state changes are instant, and there are no scale, rise or blink effects.

## 15. Redesigning in Figma (owner workflow)

The site owner can redesign any section in the Figma file. The file has what's needed:

- **Layout grid styles:** `Desktop 1440 · 12 columns` (24px gutters, 120px margins), `Tablet 768 · 8 columns` (24px gutters, 32px margins), `Mobile 390 · 4 columns` (16px gutters, 16px margins), each with a hidden 8px baseline grid. Toggle with Ctrl/Cmd + G.
- **Guide lines** on every page frame at the content edges (desktop x = 120 and 1320, plus the center at 720; mobile x = 16 and 374).
- **The `00 Read me · How to redesign` board** with the rules:
  - Keep using the color variables, text styles, effect styles and components, so the code can match.
  - The espresso gradient is for the primary button only; blue text uses `--link` `#1A64B8`; the bright `--accent-blue` is for graphics only (see `brand.md` §3).
  - Text stays flat; soft depth only for controls and grouping cards.
  - Touch targets ≥ 44px; text contrast ≥ 4.5:1.
  - Free to change: layout, order within a section, sizes, spacing, icons, illustrations, the flat/soft balance, and wording (then tell Claude so `content/copy.md` is updated).
- **Naming:** `NN Section name · Desktop 1440` / `· Mobile 390`, numbered from the page map in `content/landing.md`. Foundation boards are lettered (A · Foundations, B · Logo, C · Components).
- **Handoff:** add **"✓ Ready"** to a frame's name when it's ready to be built.

## 16. Relaxed Soft UI (current direction, overrides §2–§4 shadows)

Chosen by the site owner from two reference designs: airy, calm, less "3D".

**What changed**
- **Page:** light grey `#F4F4F4`; no more "everything is the same material".
- **Depth:** **one gentle drop shadow** per level instead of the two-sided light/dark neumorphic pair.

| Token | Value |
|---|---|
| `--shadow-1` | `0 2px 6px rgba(31,42,58,.08)` (pills, small buttons) |
| `--shadow-2` | `0 6px 18px rgba(31,42,58,.10)` (buttons, cards) |
| `--shadow-3` | `0 18px 44px rgba(31,42,58,.10)` (large cards, photo cards) |
| `--inset-1` | `inset 0 1px 3px rgba(31,42,58,.10)` (switch tracks, pressed states) |

- **Cards and pills are white** (`--card`), with 12–24px radius (999px for pills).
- **Primary button:** espresso→brown gradient, 12px radius, white text. Secondary: white, ink text.
- **Selected pill / key:** ink fill + white text + icon. Pressed buttons may still use `--inset-1`.

**Layout patterns (from the references)**
1. **Gradient hero:** centered eyebrow, headline (72/76 desktop, 40/46 mobile, −3.5% tracking, white), white subtitle, a white main button + white text link, and a glassy **screen mockup** (white 35% fill, 1.5px white border, background blur) holding a distro screenshot. The mockup is cut off by the bottom of the hero.
2. **Alternating split rows:** text column (eyebrow, big headline 46/54 with −3% tracking, muted body, one action) beside an **illustrated blue panel** (628×510 desktop, 24px radius). Rows alternate text-left / panel-left. On mobile: text, then panel.
3. **Illustrated panels:** `--panel-blue` with 1–2 thin white concentric rings, a soft white radial glow in one corner, and content drawn with white pills (blue `--link` labels), a dashed `--accent-blue` path, tilted white **screenshot cards** (8px white frame, `--shadow-3`, ±5° rotation) and a blue cursor. No stock photos of people.
4. **Pill rows:** choices as white pills with an icon and label, wrapping and centered.

**Where the patterns are used (Figma)**
- `02 Hero v3`: gradient hero, "What matters to you?" pill row, number cards.
- `03 What is Linux v3`: split row 1 (the "many versions, one core" ring diagram) and split row 2 (screenshot cards, "Running from USB").
- Frames marked `(old)` are the previous neumorphic versions, kept for reference.

## 17. Contemporary editorial direction (superseded by §18)

**Goal:** a modern digital publication about Linux combined with a well-presented OS discovery tool. Distinctive through typography, composition and real Linux imagery, not effects.

### Principles
1. **Designed compositions, not templates.** Prefer asymmetry: in the hero, copy takes the left ~45–55%, the desktop visual takes the rest and may bleed past the content column or the viewport edge.
2. **Big, tight display type** with one serif-italic accent phrase in blue (see `brand.md` §4). Keep paragraphs to 2–3 short lines.
3. **The product is the visual.** Real desktop screenshots (owner-provided) are the largest visual element. Show them as a floating **window** (white frame, 14px radius, title bar with three dots and a mono title) with a smaller overlapping window (e.g. Files) for depth. **No laptop or phone mockups.**
4. **Restraint with color.** Warm canvas everywhere; blue for identity and interaction; peach only as a localized blurred glow behind screenshots (LAYER_BLUR ~90px, peach at ~55%, mist behind).
5. **Editorial structure.** Five numbered chapters, mono chapter labels (`01 / DISCOVER`), thin rules (1px `--rule` at 45–60%) above chapters and fact columns, figure captions (`FIG. 01 / THE DESKTOP`).
6. **Unequal weight for unequal information.** Facts sit in columns under rules; the lead fact is larger. No rows of identical stat cards.
7. **Linux-informed details, used sparingly:** window dots, mono window titles, a terminal-flavored touch in the switching guide. Nothing that makes the page feel like a developer tool.
8. **Mobile has its own rhythm:** a bigger headline, full-width primary + secondary buttons, a large screenshot (full content width), option tiles in a 2-column grid, the recommendation directly below the choices, and facts in varied layouts (one full-width lead fact, then two side by side).

### Numbered chapters
Chapter labels are structural (they match the navigation), not decoration. Don't number individual cards except in the preference list and the switching steps, where order has meaning.

### Components (new or changed)
| Component | Spec |
|---|---|
| Header | `dLD.` (Geist Bold 26, −6%) + two-line mono label "DISTRO L. DESK / THE FRIENDLY LINUX GUIDE"; nav **Explore · Compare · Switch**; one primary button **Find your Linux →**. A thin rule under the header. Mobile: logo + Menu pill only |
| Primary button | Solid `--blue`, white Geist Medium label, 10px radius, `shadow-1`. Secondary: white, ink text. Tertiary: underlined text link |
| Desktop window | See principle 3. Title bar 10px dots `#E6A08B/#E7C98A/#A9C39A`, gap 6; title in mono small |
| Distro tabs | Pill track `--pill`, selected tab white with `shadow-1`. Switches the screenshot (Ubuntu · Linux Mint · Fedora); `role="tablist"` |
| Fact column | Rule on top, mono label, Instrument Serif figure (84 lead / 64 others), short Geist text, optional link |
| Preference row (desktop) | White or canvas row, 14px radius, mono number, label, check circle on the right. Selected: white, 1.5px blue border, filled blue check, `shadow-1`. Unselected: canvas fill, 1px rule border, empty circle. Real checkboxes (`role="checkbox"`, `aria-checked`) |
| Preference tile (mobile) | 2-column grid, icon + check on top, label below, same selected styling |
| Recommendation card | White, 22px radius, `shadow-3`. Mono "YOUR MATCH" + matched preferences; distro name in Instrument Serif 64 (mobile 48) + edition; screenshot window (desktop); three reasons with blue check icons; "Trade-off:" line; primary "Get [distro]" + "Read the profile"; rule; "ALSO CONSIDER" pills. It updates live (`aria-live="polite"`) |

### Figma
- `02 Hero v4` and `03 Find your fit` are the reference frames for this direction (desktop 1440 + mobile 390).
- `04 What is Linux v3` and `06 Distro cards` pick up the new palette and fonts automatically but still use the previous layouts; restyle them with these principles.
- Frames marked `(old)` are superseded.

---

## 18. Linux desktop, product-precise (current; overrides §16–§17)

**The idea:** discovering a Linux desktop that fits you. **The real Linux desktops are the visual identity.** Type, layout, spacing and interaction support them. There are no ornaments.

**Reference:** GNOME, for spacing, interface clarity and product presentation, not as a UI kit to copy. The website must never look like a fake OS app. For example, the recommender is not styled like GNOME Settings.

### What is removed
- The serif (Instrument Serif), the warm beige canvas, the peach glow, the window dots and drawn "desktop windows".
- Decorative numbering: no chapter numbers (`01 / DISCOVER`) and no numbered cards. Numbers stay only in the switching steps, where order matters.
- Statistics in or right below the hero (Free. / 2031 / 30k+). Those facts live in their own sections.
- Small mono labels that carry no information (figure numbers, window titles, "FIG. 01").
- No dark default, no extra terminal elements, no new visual style on top of this one.

### Tokens
| Token | Light | Dark | Use / contrast |
|---|---|---|---|
| `--bg` | `#F8F9FA` | `#1C1D1F` | Page background |
| `--surface` | `#FFFFFF` | `#26272A` | Controls, menus |
| `--surface-2` | `#EAF2FC` | `#1E2A3A` | Secondary surfaces (selected option fill, callouts) |
| `--text` | `#202124` | `#E8EAED` | Text, 15.3:1 / 14.2:1 |
| `--text-muted` | `#5F6368` | `#9AA0A6` | Secondary text, 5.7:1 / 6.5:1 |
| `--accent` | `#3584E4` | `#78AEED` | Non-text accents: focus ring, selected border, check marks (3.6:1 vs bg, passes the 3:1 non-text rule) |
| `--accent-strong` | `#1C71D8` | `#78AEED` | Primary button fill (white label 4.8:1) and link text (4.5:1). Dark: button label `#1C1D1F` (7.4:1) |
| `--accent-on-surface-2` | `#1A5FB4` | `#99C1F1` | Blue text on `--surface-2` (5.6:1) |
| `--border` | `#DDE2E8` | `#3A3D42` | 1px borders on surfaces and screenshots |
| `--control-edge` | `#8A9099` | `#8A9099` | Checkbox squares and input edges (3:1) |

`#3584E4` is the GNOME accent blue. It's used as the identity color wherever it doesn't carry text. On white it's only 3.8:1, so text and button fills use the darker `#1C71D8`, and the two read as one blue.

### Type (Inter, two weights: 400 and 600)
| Style | Desktop | Mobile | Weight / tracking |
|---|---|---|---|
| Display (hero h1) | 72 / 76 (1.05), max width 850px | 42 / 46 | 600, −2.5% |
| H2 (section) | 44 / 50, max width 760px | 32 / 38 | 600, −2% |
| H3 | 24 / 30 | 20 / 26 | 600, −1% |
| Body large (hero support, section intros) | 18 / 28, max width 560px | 16 / 24 | 400 |
| Body | 16 / 24 | 16 / 24 | 400 |
| Label / button | 16 / 24 | 16 / 24 | 600 |
| Small | 14 / 20 | 14 / 20 | 400 |
| Technical label | IBM Plex Mono 11 / 16, uppercase, +6% | same | Regular. **Only** for information: screenshot captions ("UBUNTU / GNOME"), versions, "YOUR MATCH" |

No italics for emphasis in headlines, and no colored words in headlines.

### Shape, borders, shadows, spacing
- **Radius:** 8px for controls (buttons, options, inputs, pills); 16px for large surfaces (screenshots, panels).
- **Borders:** 1px `--border`. Screenshots get a 1px border so light desktops keep an edge on the light page.
- **Shadows:** only on floating interface elements (sticky header after scroll, menus, popovers, toasts): `0 1px 2px rgb(32 33 36 / .06), 0 8px 24px rgb(32 33 36 / .08)`. None on cards, screenshots or buttons.
- **Spacing:** 8px base (4, 8, 12, 16, 24, 32, 48, 64, 96, 128). Section padding: 128 desktop, 80 mobile.
- **Layout:** content width **1280px**, centered (80px margins in a 1440 frame). 12 columns, 32px gutters. Mobile: **24px** side margins, 4 columns, 16px gutters.

### Screenshots (the main visual)
- **Real screenshots only.** Never reconstruct a desktop in Figma or HTML/CSS. No browser or laptop frames, and no colored rectangles behind images.
- The same capture rules for every image (see `brand.md` §6): consistent size, default wallpaper, one or two apps open, light mode where available.
- **Crops are art-directed per breakpoint** with `<picture>` sources: desktop shows the full 16:9 view. Mobile uses a deliberate crop (about 4:5 or 1:1) of the part that makes the desktop recognizable, such as the dock and an open app. Never shrink the whole 2560px desktop into a 342px box.
- **Caption:** below the image, a mono technical label `UBUNTU / GNOME` in `--text-muted`.
- **Placeholders** (until the owner delivers images): a flat `--surface-2` box with 16px radius at the exact aspect ratio, with a centered mono label giving the file name. No drawn UI inside.

### Components
| Component | Spec |
|---|---|
| Header | 80px high. `dLD.` (Inter 600, 24px) on the left; nav **Explore · Find your Linux · Switch** (Inter 400, 16px, `--text`), a theme toggle icon button. No header button: the hero holds the only primary. After scrolling, the header gets a `--surface` fill and the floating shadow. Mobile: 64px, logo + Menu button |
| Primary button | 48px high, 8px radius, `--accent-strong` fill, white Inter 600 16px, 24px side padding, trailing arrow. Hover: `#1A5FB4`. One per view |
| Secondary button | 48px, 8px radius, `--surface` fill, 1px `--border`, `--text` label |
| Text link | `--accent-strong`, underline on hover and focus |
| Preference option | Minimum **56px** high, full column width, 8px radius, `--surface` fill, 1px `--border`, 16px padding. A 20px checkbox square on the left (1.5px `--control-edge`, 4px radius), label Inter 400 16px. Selected: `--surface-2` fill, 1.5px `--accent` border, filled `--accent` checkbox with a white check. Real `<input type="checkbox">` in a `<fieldset>` |
| Focus ring | 2px `--accent` outline with 2px offset, on everything focusable |
| Screenshot figure | `<figure>`: image (16px radius, 1px border) + mono caption |

### Section recipes
**Hero.** Left-aligned in the 1280 column. The h1 (72px, max 850px) is followed by 24px of space, then the support copy (18px, max 560px), then 40px of space and the buttons (primary + secondary, gap 12). After 64px comes a full-width 16:9 screenshot (1280×720) with its caption. No statistics, no tabs, no floating windows.

**Three desktops** (right after the hero). H2 + one short intro line, then three screenshots in a row (3 × 405px, 32px gutters) at the same 16:10 ratio and crop logic. Under each: a mono caption (`UBUNTU / GNOME DESKTOP`), the name in Inter 600 20px, and one plain sentence. Mobile: a single column of stacked images at 342×256 with deliberate crops, or a horizontal scroll-snap row showing 85% of a card so the next one peeks in.

**Find your Linux** (the recommender). Two columns, **40 / 60** (about 480 / 768 px with a 32px gap):
- **Left:** h2 "Find your Linux.", the fieldset legend "What matters most to you?" (h3 size), the preference options (8px gap) and a "Clear" text link under the list.
- **Right (the result, `aria-live="polite"`):** mono "YOUR MATCH", the name (Inter 600 40px) and edition, one sentence, a **full-width screenshot** (768×480), three reasons (check icon + text), a "Good to know" caveat line, then "Explore [Name] →" (primary) and "Official site ↗" (text link). Below that, after a 1px border, "Also consider": three plain text links with one short line each.
- No white card, no heavy shadow, no nested containers. The result sits directly on the page background.
- Mobile: the preferences stack above the result. Options are full width (56px), and the result follows with a cropped screenshot at 342×260.

**Mobile rhythm (390):** 24px margins; h1 42px; body 16px; primary button full width (342×48); the screenshot sits right below the buttons, 342 wide with a cropped 4:5 view (342×428) so the desktop stays recognizable.

### Figma
Reference frames: `02 Hero v5`, `03 Desktops`, `04 Find your Linux v2` (Desktop 1440 + Mobile 390). The `(old)` frames are superseded, including `02 Hero v4` and `03 Find your fit`.

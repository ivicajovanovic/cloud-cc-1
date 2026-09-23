# design.md: Soft UI (Neumorphism)

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

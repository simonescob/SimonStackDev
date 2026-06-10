# Style Reference — SimonStackDev

Design system extracted from `index.html`. All values are defined in the Tailwind config and custom CSS.

---

## Color Palette

### Background & Surface

| Token                      | Hex         | Usage                              |
|----------------------------|-------------|------------------------------------|
| `background`               | `#0C0C0C`   | Page background, footer            |
| `surface`                  | `#131313`   | Nav background base                |
| `surface-elevated`         | `#161616`   | Glass panel base                   |
| `surface-dim`              | `#0C0C0C`   | Alias for background               |
| `surface-container-lowest` | `#0E0E0E`   | About section background           |
| `surface-container-low`    | `#1C1B1B`   | FAQ item background, stats strip   |
| `surface-container`        | `#201F1F`   | —                                  |
| `surface-container-high`   | `#2A2A2A`   | Project card image area, FAQ hover |
| `surface-container-highest`| `#353534`   | —                                  |
| `surface-variant`          | `#353534`   | —                                  |

### Text

| Token                | Hex / Value  | Usage                           |
|----------------------|--------------|---------------------------------|
| `on-surface`         | `#E5E2E1`    | Headings, primary body text     |
| `on-background`      | `#E5E2E1`    | Body default                    |
| `on-surface-variant` | `#BDC9CA`    | Secondary descriptive text      |
| `text-primary`       | `#E5E5E5`    | High-contrast text override     |
| `text-muted`         | `#8A8A8A`    | Muted labels, trust signals     |
| `outline`            | `#879395`    | —                               |
| `outline-variant`    | `#3E494A`    | Footer border, scrollbar thumb  |

### Brand / Primary

| Token                   | Hex / Value              | Usage                                     |
|-------------------------|--------------------------|-------------------------------------------|
| `primary`               | `#79DAE7`                | Accent text, icons, hover states          |
| `primary-container`     | `#5BBECB`                | CTA buttons, nav "Hire Me"                |
| `on-primary`            | `#00363C`                | Text on `primary` backgrounds             |
| `on-primary-container`  | `#004B52`                | Text on `primary-container` buttons       |
| `secondary`             | `#95D0D9`                | —                                         |
| `secondary-container`   | `#095159`                | —                                         |
| `on-secondary`          | `#00363C`                | —                                         |
| `on-secondary-container`| `#87C2CB`                | —                                         |
| `accent-glow`           | `rgba(91,190,203,0.15)`  | Glow overlays                             |

### Semantic / Utility

| Color          | Value       | Usage                    |
|----------------|-------------|--------------------------|
| Green (status) | `#4ADE80`   | Availability ping dot    |
| Skill tag bg   | `rgba(40,102,110,0.2)` | Pill background |
| Skill tag border | `rgba(40,102,110,0.4)` | Pill border    |
| Fixed-price badge bg | `rgba(40,102,110,0.2)` | — |
| Hero icon tint | `rgba(121,218,231,0.2)` | Project card icons |
| CTA section bg | `#79DAE7`   | Full-width inverted CTA  |
| CTA section text | `#00363C` | Dark text on teal CTA    |
| Theme color    | `#0C0C0C`   | Browser tab color        |

---

## Typography

### Font Families

| Role          | Family          | Weights loaded   |
|---------------|-----------------|------------------|
| Display / Headings | **Sora**   | 400, 600, 700, 800 |
| Body copy     | **Inter**       | 400, 500, 600    |
| Monospace / Labels | **JetBrains Mono** | 400, 500 |
| Icons         | Material Symbols Outlined | — |

### Type Scale

| Token               | Size    | Line Height | Letter Spacing | Weight | Font     |
|---------------------|---------|-------------|----------------|--------|----------|
| `display-xl`        | 72px    | 1.1         | -0.04em        | 800    | Sora     |
| `display-xl-mobile` | 48px    | 1.1         | -0.03em        | 800    | Sora     |
| `headline-lg`       | 40px    | 1.2         | -0.02em        | 700    | Sora     |
| `headline-lg-mobile`| 32px    | 1.2         | —              | 700    | Sora     |
| `headline-md`       | 24px    | 1.4         | —              | 600    | Sora     |
| `body-lg`           | 18px    | 1.6         | —              | 400    | Inter    |
| `body-md`           | 16px    | 1.6         | —              | 400    | Inter    |
| `label-mono`        | 14px    | 1.0         | 0.05em         | 500    | JetBrains Mono |

**Pattern:** Headings use `font-{token} text-{token}` together. Mobile variant switches at `md:` breakpoint.

```html
<h1 class="font-display-xl-mobile md:font-display-xl text-display-xl-mobile md:text-display-xl">
```

---

## Spacing

| Token                  | Value   | Usage                              |
|------------------------|---------|------------------------------------|
| `gutter`               | 32px    | Horizontal page padding (`px-gutter`) |
| `section-gap-desktop`  | 160px   | Vertical section padding on desktop |
| `section-gap-mobile`   | 80px    | Vertical section padding on mobile  |
| `card-padding`         | 40px    | Internal card padding              |
| `base`                 | 8px     | Base spacing unit                  |

```html
<section class="py-section-gap-mobile md:py-section-gap-desktop">
  <div class="max-w-container-max mx-auto px-gutter">
```

### Layout

| Token            | Value   |
|------------------|---------|
| `container-max`  | 1200px  |

---

## Component Patterns

### Navigation

- Fixed, full-width, `z-50`
- Background: `rgba(19,19,19,0.85)` with `backdrop-filter: blur(16px)`
- Border: `border-b border-white/10`
- Height: `h-20`
- Logo: `font-headline-md text-headline-md font-bold text-on-surface`
- Nav links: `text-on-surface-variant hover:text-primary transition-colors duration-300 font-body-md`
- CTA button: `bg-primary-container text-on-primary-container px-6 py-2 rounded-lg font-semibold hover:opacity-90 active:scale-95 transition-all text-sm`

### Glass Panel (Cards)

```css
.glass-panel {
  background: rgba(22, 22, 22, 0.8);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.08);
  transition: all 0.3s ease;
}
.glass-panel:hover {
  border-color: #5BBECB;
  box-shadow: 0 10px 30px -10px rgba(91, 190, 203, 0.2);
}
```

Used for offer card (hero), "What I Build" cards, project cards.

### Hero Glow

```css
.hero-glow {
  background: radial-gradient(circle at 60% 50%, rgba(91, 190, 203, 0.1) 0%, transparent 60%);
}
```

Absolute overlay, `pointer-events-none`.

### CTA Buttons

**Primary (filled):**
```html
class="bg-primary-container text-on-primary-container px-8 py-4 rounded-lg font-bold
       hover:shadow-[0_0_20px_rgba(91,190,203,0.4)] active:scale-95 transition-all"
```

**Secondary (outlined):**
```html
class="border border-primary-container text-primary-container px-8 py-4 rounded-lg font-bold
       hover:bg-primary/5 transition-all"
```

### Availability Badge

```html
<div class="inline-flex items-center gap-2 pl-3 pr-4 py-1.5 rounded-full border border-white/10"
     style="background: rgba(22,22,22,0.8);">
  <span class="relative flex h-2.5 w-2.5">
    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
    <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-green-400"></span>
  </span>
  <span class="font-label-mono text-label-mono text-on-surface uppercase tracking-widest">Available for Work</span>
</div>
```

### Skill / Tech Tags (Pills)

```html
<span class="px-5 py-2 font-label-mono text-label-mono
             bg-[rgba(40,102,110,0.2)] border border-[rgba(40,102,110,0.4)]
             text-primary rounded-full">
  React
</span>
```

### Fixed-Price Badge

```html
<span class="font-label-mono text-label-mono text-primary uppercase tracking-widest
             px-3 py-1 rounded-full
             bg-[rgba(40,102,110,0.2)] border border-[rgba(40,102,110,0.4)]">
  Fixed price
</span>
```

### Project Tech Stack Tags (Footer of cards)

```html
<span class="font-label-mono text-label-mono text-text-muted uppercase">Next.js</span>
```

Separated by `flex-wrap gap-3`, `border-t border-white/5` above.

### FAQ Accordion

- Container: `bg-surface-container-low rounded-lg hover:bg-surface-container-high transition-colors`
- Answer panel: `background: #1c1b1b`, `border-x border-b border-surface-container-high rounded-b-lg`
- Toggle icon: `material-symbols-outlined` rotates `180deg` on open via inline style

### CTA Section (Inverted)

Full-width teal block:
```html
<section style="background: #79dae7; color: #00363c;">
  <!-- button: background: #00363c; color: #79dae7 -->
</section>
```

### Stats Row

Numbers: `font-display-xl-mobile md:font-headline-lg text-display-xl-mobile md:text-headline-lg text-primary`
Labels: `font-label-mono text-label-mono text-text-muted uppercase tracking-widest`

### Section Headings Pattern

```html
<h2 class="font-headline-lg-mobile md:font-headline-lg text-headline-lg-mobile md:text-headline-lg text-on-surface">
```

Underline accent (About section):
```html
<div class="h-1 w-20 bg-primary"></div>
```

---

## Scrollbar

```css
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: #0C0C0C; }
::-webkit-scrollbar-thumb { background: #3e494a; border-radius: 3px; }
```

---

## Animation & Interaction

| Effect                   | Implementation                                               |
|--------------------------|--------------------------------------------------------------|
| Section fade-in          | IntersectionObserver adds `opacity-100 translate-y-0`, removes `opacity-0 translate-y-8` |
| Transition duration      | `duration-700` on sections, `duration-300` on hover states   |
| CTA glow on hover        | `hover:shadow-[0_0_20px_rgba(91,190,203,0.4)]`               |
| Button press             | `active:scale-95`                                            |
| Card icon scale          | `group-hover:scale-110 transition-transform duration-500`    |
| LeaseScan icon rotate    | `group-hover:rotate-12 transition-transform duration-700`    |
| Card border glow         | `.glass-panel:hover { border-color: #5BBECB; box-shadow: ... }` |
| Availability ping        | `animate-ping` on `bg-green-400` dot                        |
| Hero card glow wrapper   | `-inset-1 bg-primary/10 blur-2xl group-hover:bg-primary/20`  |
| Smooth scroll            | `scroll-behavior: smooth` on body + JS `scrollIntoView`      |
| Material icon settings   | `font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24` |

---

## Dark Mode

Class strategy: `<html class="dark">`. Tailwind config: `darkMode: "class"`. All colors are defined for dark mode only — no light theme tokens exist.

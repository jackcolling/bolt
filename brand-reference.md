# Bolt Brand Reference Guide

> Quick reference for creating on-brand Bolt emails and communications.

---

## Tone of Voice

### Three Core Principles

1. **Thoughtfully concise** - Get to the point. Respect the reader's time.
2. **Knowingly playful** - Smart, witty, confident. Not silly or juvenile.
3. **Comfortably at ease** - Approachable and relaxed. Never stiff or corporate.

### Writing Guidelines
- Keep copy short and punchy
- Use clever wordplay when appropriate (e.g., "Put the 'dash' in dashboard")
- Avoid jargon and overly formal language
- Be confident but not arrogant

---

## Color Palette

### Primary Colors

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **Lightning Yellow** | `#E1FF00` | `rgb(225, 255, 0)` | Hero color, highlights, CTAs on dark backgrounds |
| **Bolt Black** | `#11190C` | `rgb(17, 25, 12)` | Primary text, logo on light backgrounds |
| **Dark Grey** | `#787664` | `rgb(120, 118, 100)` | Secondary elements |
| **Mid Grey** | `#CAC4B7` | `rgb(202, 196, 183)` | Backgrounds, borders |
| **Light Grey** | `#F3F1EE` | `rgb(243, 241, 238)` | Backgrounds |

### Color Combinations for Text

| Background | Text Color | Highlight |
|------------|------------|-----------|
| Lightning Yellow | Bolt Black | — |
| Bolt Black | Light Grey | Lightning Yellow |
| Dark Grey | Light Grey | Lightning Yellow |
| Light Grey | Bolt Black | — |
| Mid Grey | Bolt Black | — |

### Rules
- Never layer bright colors on bright colors
- Never layer dark colors on dark colors
- Always ensure legibility and sufficient contrast

---

## Typography

### Primary Typeface (Headlines)
**Agrandir Narrow** by Pangram Pangram
- **Bold** - Headlines
- **Medium** - Sublines

### Secondary Typeface (Body)
**Inter** by Rasmus Andersson
- **Semi Bold** - Emphasis, key words
- **Medium** - Body copy, buttons, annotations

### Font Files

**Agrandir** - Located in `assets/Agrandir/`:
| File | Usage |
|------|-------|
| `Agrandir-Narrow.otf` | **Primary** - Headlines & sublines |
| `Agrandir-TextBold.otf` | Bold body text |
| `Agrandir-Regular.otf` | Regular weight |
| `Agrandir-Tight.otf` | Tight spacing variant |
| `Agrandir-Grand*.otf` | Display sizes |
| `Agrandir-Wide*.otf` | Wide variants |

**Inter** - Load from official CDN:
```html
<link rel="stylesheet" href="https://rsms.me/inter/inter.css">
```
Or via CSS import:
```css
@import url('https://rsms.me/inter/inter.css');
```

### Hierarchy
1. **Headline**: Agrandir Narrow Bold
2. **Subline**: Agrandir Narrow Medium
3. **Body copy**: Inter Medium
4. **Annotations**: Inter Medium
5. **Buttons**: Inter Medium/Semi Bold

### Email-Safe Fallbacks
Since Agrandir may not render in all email clients:
- Headlines: Arial Black, Helvetica Bold, sans-serif
- Body: Arial, Helvetica, sans-serif

---

## Logo Usage

### File Location
`assets/bolt-logo.svg`

### Color Variants
| Background | Logo Color |
|------------|------------|
| Lightning Yellow | Bolt Black (`#11190C`) |
| Dark backgrounds | Light Grey (`#F3F1EE`) or Lightning Yellow (`#E1FF00`) |
| Light backgrounds | Bolt Black (`#11190C`) |
| Photography | Light Grey or Lightning Yellow |

### Rules
- Maintain clear space around logo (1x height on all sides)
- Minimum size: 30pt
- Never use secondary colors for logo
- **Don't**: Add gradients, make 3D, stretch, fill the bolt, use multiple colors, add strokes

---

## Email-Specific Guidelines

### Structure
- Keep emails scannable and concise
- Use clear visual hierarchy
- Single primary CTA per email

### Buttons
- Background: Lightning Yellow (`#E1FF00`) or Bolt Black (`#11190C`)
- Text: Bolt Black on yellow, Light Grey on black
- Font: Inter Medium/Semi Bold
- Rounded corners acceptable

### Highlights
Use Lightning Yellow to highlight key words or phrases in headlines on dark backgrounds.

### Footer
- Include Bolt logo
- Keep minimal and clean

---

## Sample Headlines

- "Shockingly simple checkout."
- "Checkout faster than you can say 'one-click.'"
- "Put the 'dash' in dashboard."
- "The very very very very simple checkout."
- "Checkout in (half) the blink of an eye."

---

## Quick Reference CSS Variables

```css
:root {
  /* Colors */
  --bolt-lightning-yellow: #E1FF00;
  --bolt-black: #11190C;
  --bolt-dark-grey: #787664;
  --bolt-mid-grey: #CAC4B7;
  --bolt-light-grey: #F3F1EE;

  /* Typography */
  --font-primary: 'Agrandir Narrow', Arial Black, sans-serif;
  --font-secondary: 'Inter', Arial, Helvetica, sans-serif;
}
```

---

*Reference: Bolt Brand Guidelines, January 2024*

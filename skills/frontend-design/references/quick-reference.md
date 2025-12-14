# Bolt Brand Quick Reference

Fast lookup for frontend development. Full details in `../../BRAND-ASSET-GUIDE.md`.

## Logo Files (CRITICAL)

| Background Color | Logo File | Example |
|------------------|-----------|---------|
| Light (white, light grey) | `assets/blacklogo.png` | Light page header |
| **Yellow (#E1FF00)** | `assets/blacklogo.png` | Yellow CTA section |
| Dark (Bolt Black #11190C) | `assets/lightLogo.png` | Dark navigation |

**Implementation:**
```html
<img src="assets/blacklogo.png" alt="Bolt"> <!-- Light backgrounds -->
<img src="assets/lightLogo.png" alt="Bolt"> <!-- Dark backgrounds -->
```

**CSS:**
```css
.logo {
  height: 32px; /* Set height */
}
.logo img {
  height: 32px;
  width: auto;  /* Auto width for aspect ratio */
  display: block;
}
```

## Colors

```css
/* Copy-paste ready */
--lightning-yellow: #E1FF00;
--bolt-black: #11190C;
--dark-grey: #787664;
--mid-grey: #CAC4B7;
--light-grey: #F3F1EE;
```

**Common Combinations:**
- Text on light: `color: #11190C` on `background: #F3F1EE` or `#FFFFFF`
- Text on dark: `color: #F3F1EE` on `background: #11190C`
- Primary CTA: `background: #E1FF00`, `color: #11190C`
- Secondary text: `color: #787664`

## Typography

```css
/* Headlines */
font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif;

/* Body & UI */
font-family: 'Inter', Arial, Helvetica, sans-serif;
```

**Font Loading:**
```html
<style>
  @font-face {
    font-family: 'Agrandir Narrow';
    src: url('assets/Agrandir/Agrandir-Narrow.otf') format('opentype');
  }
  @import url('https://rsms.me/inter/inter.css');
</style>
```

**Sizes:**
- H1: 36-48px
- H2: 24-32px
- H3: 18-24px
- Body: 16px (min)
- Small: 14px (min)

## Buttons

**Primary:**
```css
background: #E1FF00;
color: #11190C;
padding: 14px 32px;
border-radius: 5px;
font-weight: 600;
```

**Hover:**
```css
background: #11190C;
color: #E1FF00;
transform: translateY(-2px);
transition: all 0.2s ease;
```

## Common Values

- Border radius: `5px`
- Transition: `all 0.2s ease`
- Line height (body): `1.4-1.6`
- Line height (headlines): `1.1-1.3`
- Box shadow (subtle): `0 2px 8px rgba(17, 25, 12, 0.08)`
- Box shadow (card): `0 4px 16px rgba(17, 25, 12, 0.1)`

## Quick Checks

Before shipping:
- ✅ Using PNG logo files (not text)
- ✅ Correct logo for background (black on light, light on dark)
- ✅ Only brand palette colors
- ✅ Agrandir + Inter fonts with fallbacks
- ✅ 5px border-radius
- ✅ 16px min body text
- ✅ Smooth transitions (0.2s ease)

---
name: frontend-design
description: Create on-brand web components, pages, and interfaces for Bolt. Use this skill when building HTML/CSS for buttons, navigation, layouts, landing pages, or any web interface. Ensures brand guidelines are followed, correct logo files are used, and code is production-ready.
---

# Frontend Design

Build bold, distinctive web interfaces that follow Bolt brand guidelines.

## When to Use This Skill

Use this skill for:
- Creating HTML/CSS components (buttons, navigation, cards, forms, etc.)
- Building page layouts and showcases
- Landing pages and marketing pages
- Component libraries and pattern libraries
- Any web interface work

## Process

### 1. Load Brand Context

**REQUIRED:** Before writing any code, read the brand guidelines:
- `../../BRAND-ASSET-GUIDE.md` - Complete brand guide with all rules
- `references/quick-reference.md` - Fast lookup for colors, fonts, logo files

### 2. Plan the Component

Ask yourself:
- What's the purpose of this component?
- Where will it be used (marketing site, app, documentation)?
- What brand personality should it convey (energy, professionalism, playfulness)?
- What are the key interactions (hover, click, scroll)?

### 3. Build with Brand Standards

**Critical Rules:**

#### Logo Usage
- **ALWAYS use PNG files, NEVER text**
- `blacklogo.png` for light/yellow backgrounds (DEFAULT)
- `lightLogo.png` for dark backgrounds (Bolt Black #11190C)
- Set `height` in pixels, `width: auto` for proper scaling
- Minimum 80px width for digital

#### Colors (Brand Palette Only)
```css
/* Primary Colors */
--lightning-yellow: #E1FF00;  /* Hero color, CTAs, highlights */
--bolt-black: #11190C;         /* Primary text, dark backgrounds */

/* Secondary Colors */
--dark-grey: #787664;          /* Secondary text */
--mid-grey: #CAC4B7;           /* Borders, dividers */
--light-grey: #F3F1EE;         /* Backgrounds, cards */
```

**Never use:**
- Pure black (#000000) - use Bolt Black instead
- Any colors outside this palette
- Yellow for body text (accessibility)

#### Typography
```css
/* Headlines */
font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif;
/* Fallback to Arial Black if Agrandir unavailable */

/* Body copy, UI elements */
font-family: 'Inter', Arial, Helvetica, sans-serif;
```

**Font Loading:**
```html
<!-- Agrandir (local) -->
<style>
  @font-face {
    font-family: 'Agrandir Narrow';
    src: url('assets/Agrandir/Agrandir-Narrow.otf') format('opentype');
    font-weight: 400;
  }
</style>

<!-- Inter (CDN) -->
<style>
  @import url('https://rsms.me/inter/inter.css');
</style>
```

#### Sizing & Spacing
- Body text: 16px minimum (14px for captions/small text)
- Headlines: 36-48px (H1), 24-32px (H2), 18-24px (H3)
- Line height: 1.4-1.6 for body, 1.1-1.3 for headlines
- Border radius: 5px (brand standard)
- Generous whitespace - let elements breathe

#### Buttons (Primary)
```css
background-color: #E1FF00;
color: #11190C;
padding: 14px 32px;
border-radius: 5px;
font-family: 'Inter', Arial, Helvetica, sans-serif;
font-size: 16px;
font-weight: 600;
transition: all 0.2s ease;
```

Hover state:
```css
background-color: #11190C;
color: #E1FF00;
transform: translateY(-2px);
```

### 4. Code Quality Standards

**HTML:**
- Semantic HTML5 elements
- Proper alt text for all images
- Accessibility: ARIA labels where needed, keyboard navigation support
- Clean indentation (2 spaces)

**CSS:**
- Mobile-first responsive design
- Use CSS custom properties for colors
- Smooth transitions (0.2s ease standard)
- No inline styles (except for email templates)
- Comments for complex sections

**Assets:**
- Always use `assets/blacklogo.png` or `assets/lightLogo.png`
- Reference fonts from `assets/Agrandir/`
- Optimize images (no huge file sizes)

### 5. Test Your Work

Before finishing, verify:
- [ ] Correct logo file used for background color
- [ ] All colors from brand palette only
- [ ] Agrandir Narrow for headlines, Inter for body
- [ ] 16px minimum body text size
- [ ] 5px border-radius on buttons/cards
- [ ] Smooth transitions on interactive elements
- [ ] Responsive (works on mobile)
- [ ] No console errors
- [ ] Accessible (keyboard navigation, contrast ratios)

## Component Patterns

### Logo Implementation
```html
<!-- Light backgrounds (white, yellow, light grey) -->
<a href="#" class="logo">
  <img src="assets/blacklogo.png" alt="Bolt">
</a>

<style>
.logo {
  display: block;
  height: 32px; /* Adjust size as needed */
}

.logo img {
  height: 32px;
  width: auto;
  display: block;
}
</style>
```

```html
<!-- Dark backgrounds (Bolt Black) -->
<a href="#" class="logo">
  <img src="assets/lightLogo.png" alt="Bolt">
</a>

<style>
.logo {
  display: block;
  height: 32px;
}

.logo img {
  height: 32px;
  width: auto;
  display: block;
}
</style>
```

### Primary Button
```html
<a href="#" class="btn-primary">Get Started</a>

<style>
.btn-primary {
  display: inline-block;
  background-color: #E1FF00;
  color: #11190C;
  padding: 14px 32px;
  border-radius: 5px;
  font-family: 'Inter', Arial, Helvetica, sans-serif;
  font-size: 16px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.2s ease;
}

.btn-primary:hover {
  background-color: #11190C;
  color: #E1FF00;
  transform: translateY(-2px);
}
</style>
```

### Card Component
```html
<div class="card">
  <h3>Card Title</h3>
  <p>Card description goes here.</p>
  <a href="#" class="card-link">Learn more</a>
</div>

<style>
.card {
  background-color: #FFFFFF;
  border-radius: 5px;
  padding: 32px;
  box-shadow: 0 2px 8px rgba(17, 25, 12, 0.08);
}

.card h3 {
  font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif;
  font-size: 24px;
  font-weight: 700;
  color: #11190C;
  margin: 0 0 12px 0;
}

.card p {
  font-family: 'Inter', Arial, Helvetica, sans-serif;
  font-size: 16px;
  line-height: 1.6;
  color: #787664;
  margin: 0 0 20px 0;
}

.card-link {
  color: #11190C;
  font-weight: 600;
  text-decoration: none;
  transition: color 0.2s ease;
}

.card-link:hover {
  color: #E1FF00;
}
</style>
```

## Common Mistakes to Avoid

### ❌ WRONG
```html
<!-- Using text instead of logo file -->
<div class="logo">BOLT</div>

<!-- Wrong logo for background -->
<nav style="background: #11190C;">
  <img src="assets/blacklogo.png" alt="Bolt"> <!-- Should be lightLogo.png -->
</nav>

<!-- Off-brand colors -->
<button style="background: #FF5733;">Click</button>

<!-- Pure black instead of Bolt Black -->
<p style="color: #000000;">Text</p>

<!-- No fallback fonts -->
<h1 style="font-family: 'Agrandir Narrow';">Headline</h1>
```

### ✅ CORRECT
```html
<!-- Using actual logo file -->
<a href="#" class="logo">
  <img src="assets/blacklogo.png" alt="Bolt">
</a>

<!-- Correct logo for dark background -->
<nav style="background: #11190C;">
  <img src="assets/lightLogo.png" alt="Bolt">
</nav>

<!-- Brand colors only -->
<button style="background: #E1FF00; color: #11190C;">Click</button>

<!-- Bolt Black, not pure black -->
<p style="color: #11190C;">Text</p>

<!-- Proper fallback fonts -->
<h1 style="font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif;">Headline</h1>
```

## Output Format

When creating components:

1. **Explain the approach** - What you're building and why
2. **Write the code** - Clean, commented, production-ready
3. **Show the result** - What it looks like, how it works
4. **Note any decisions** - Why you chose specific patterns

Structure files as:
```
component-name.html
├── HTML structure
├── Embedded CSS (in <style> tag)
├── Embedded fonts (if needed)
└── Comments explaining key sections
```

## Quality Checklist

Before marking work as complete:

**Brand Compliance:**
- [ ] Logo files used correctly (blacklogo.png vs lightLogo.png)
- [ ] Only brand palette colors used
- [ ] Agrandir Narrow + Inter typography
- [ ] 5px border-radius consistently applied
- [ ] No off-brand visual elements

**Code Quality:**
- [ ] Semantic, accessible HTML
- [ ] Clean, organized CSS
- [ ] Proper font fallbacks
- [ ] Smooth transitions (0.2s ease)
- [ ] Mobile responsive

**User Experience:**
- [ ] Clear visual hierarchy
- [ ] Interactive states (hover, focus, active)
- [ ] Readable text sizes (16px+ body)
- [ ] Sufficient color contrast
- [ ] Fast load time

## Resources

- Brand guide: `../../BRAND-ASSET-GUIDE.md`
- Quick reference: `references/quick-reference.md`
- Logo files: `../../assets/blacklogo.png`, `../../assets/lightLogo.png`
- Fonts: `../../assets/Agrandir/`
- Examples: `../../button-showcase.html`, `../../navigation-showcase.html`

## Remember

> "We're building a bold, energy-focused brand. Every component should feel modern, confident, and slightly playful. Use Lightning Yellow intentionally—it's our signature. Keep layouts clean with generous whitespace. Make it feel fast, even when it's standing still."

When in doubt, reference existing showcases and always prioritize brand consistency over personal preference.

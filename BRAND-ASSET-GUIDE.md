# Bolt Brand Asset Creation Guide

Complete instructions for creating on-brand assets for Bolt. Use this guide when designing emails, web pages, marketing materials, social media, or any branded content.

---

## ⚡ CRITICAL: Use the Right Skill for the Job

**REQUIRED WORKFLOW:** When creating or reviewing Bolt brand assets, you MUST use the appropriate skill:

| Task | Skill to Use | Why |
|------|-------------|-----|
| **Creating web components** (buttons, nav, pages, layouts) | `frontend-design` | Ensures correct logo files, brand colors, typography from the start |
| **Creating HTML emails** | `email-coder` | Ensures email-safe code, inline CSS, proper table structure |
| **Reviewing any creative work** | `creative-director` | Catches brand violations, grades quality, provides actionable feedback |
| **Writing copy, headlines, CTAs** | `marketing-copywriter` | Matches brand voice (concise, playful, at ease) |

**Standard Workflow:**
1. **Create** using the appropriate creation skill (frontend-design or email-coder)
2. **Review** using creative-director skill before finalizing
3. **Iterate** based on feedback until Grade A or B

**Never create Bolt assets without using a skill.** Skills have built-in brand guardrails and checklists that prevent common mistakes.

---

## 📋 Essential Reading Before Starting Work

**Read these files FIRST:**
1. **PROJECT-MEMORY.md** - Persistent context, learnings, and decisions across sessions
2. **BRAND-ASSET-GUIDE.md** - This file (complete brand guidelines)
3. Skill-specific references (frontend-design, email-coder, etc.)

**Why:** PROJECT-MEMORY.md contains critical learnings from past mistakes (like logo file errors) that will save you time and prevent repeated errors.

---

## Quick Start

### Brand Essence
Bolt is a modern, energy-focused brand. We're fast, bold, and shockingly simple. The visual identity conveys power and speed while remaining approachable and playful.

### Brand Personality
- **Thoughtfully concise** — Say more with less
- **Knowingly playful** — Clever, confident wit
- **Comfortably at ease** — Relaxed, never aggressive

---

## Color System

### Primary Palette

| Color | Hex Code | RGB | Usage |
|-------|----------|-----|-------|
| **Lightning Yellow** | `#E1FF00` | rgb(225, 255, 0) | Hero color, CTAs, highlights, backgrounds |
| **Bolt Black** | `#11190C` | rgb(17, 25, 12) | Primary text, dark backgrounds, contrast |

### Secondary Palette

| Color | Hex Code | RGB | Usage |
|-------|----------|-----|-------|
| **Dark Grey** | `#787664` | rgb(120, 118, 100) | Secondary text, subtle elements |
| **Mid Grey** | `#CAC4B7` | rgb(202, 196, 183) | Borders, dividers, light text on dark |
| **Light Grey** | `#F3F1EE` | rgb(243, 241, 238) | Backgrounds, cards, containers |

### Color Usage Rules

**DO:**
- Use Lightning Yellow boldly and intentionally
- Default to Bolt Black for text on light backgrounds
- Use Light Grey for main backgrounds
- Maintain high contrast for accessibility
- Yellow dominates—it's our signature

**DON'T:**
- Use Lightning Yellow for body text (accessibility fail)
- Use pure black (#000000) — always use Bolt Black (#11190C)
- Add random accent colors outside the palette
- Use yellow on white (insufficient contrast)

### Color Combinations

**Winning Combinations:**
```
✓ Bolt Black text on Lightning Yellow backgrounds
✓ Bolt Black text on Light Grey backgrounds
✓ Light Grey or Mid Grey text on Bolt Black backgrounds
✓ Lightning Yellow text on Bolt Black backgrounds (CTAs, highlights)
✓ White text on Bolt Black backgrounds

✗ Lightning Yellow text on Light Grey (low contrast)
✗ Mid Grey text on Light Grey (low contrast)
✗ Any text on photos without contrast treatment
```

---

## Typography

### Font Stack

**Headlines & Display**
```css
font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif;
```
- Files: `assets/Agrandir/Agrandir-Narrow.otf` (and variants)
- Web fallback: Arial Black
- Use for: Headlines, section titles, large display text

**Body & UI**
```css
font-family: 'Inter', Arial, Helvetica, sans-serif;
```
- CDN: `@import url('https://rsms.me/inter/inter.css');`
- Web fallback: Arial, Helvetica
- Use for: Body copy, captions, buttons, UI elements

### Type Scale

| Element | Font | Size | Weight | Line Height | Letter Spacing |
|---------|------|------|--------|-------------|----------------|
| **Mega Headline** | Agrandir Narrow | 48-64px | 700 | 0.9-1.0 | -2px to -1px |
| **H1 Headline** | Agrandir Narrow | 36-48px | 700 | 1.05-1.1 | -1px to -0.5px |
| **H2 Subheadline** | Agrandir Narrow | 24-32px | 700 | 1.1-1.2 | -0.5px |
| **H3 Section Header** | Agrandir Narrow | 18-24px | 700 | 1.2-1.3 | 0 |
| **Body Large** | Inter | 18px | 500 | 1.5-1.6 | 0 |
| **Body Regular** | Inter | 16px | 400-500 | 1.6-1.7 | 0 |
| **Body Small** | Inter | 14px | 400-500 | 1.5-1.6 | 0 |
| **Caption/Label** | Inter | 12-13px | 600 | 1.4 | 1-2px (uppercase) |

### Typography Rules

**DO:**
- Keep headlines punchy (under 8 words ideal)
- Use Agrandir Narrow for visual impact
- Maintain 16px minimum for body copy
- Use 1.4-1.7 line height for readability
- Negative letter-spacing on large headlines
- Uppercase labels with increased letter-spacing (1-2px)

**DON'T:**
- Mix more than 2 typefaces in one design
- Use Agrandir for long-form body copy
- Go below 14px font size (12px minimum for captions)
- Use tight line-height on body text
- Stretch or condense fonts beyond their design

### Hierarchy Examples

```
MEGA IMPACT LAYOUT:
━━━━━━━━━━━━━━━━━━━━━
This is Bolt.               ← Agrandir Narrow, 64px, -2px spacing
Faster. Bolder.             ← Agrandir Narrow, 32px, -0.5px spacing
Shockingly simple.

The new brand is here.      ← Inter, 18px, regular
━━━━━━━━━━━━━━━━━━━━━


STANDARD LAYOUT:
━━━━━━━━━━━━━━━━━━━━━
Meet the new Bolt           ← Agrandir Narrow, 36px, -0.5px spacing

Same lightning-fast checkout.  ← Inter, 16px, medium
Bolder look.
━━━━━━━━━━━━━━━━━━━━━
```

---

## Logo Guidelines

### Logo Files

**CRITICAL: Always use the PNG logo files for web and digital applications.**

| File | Usage | Background | Format |
|------|-------|------------|--------|
| **`blacklogo.png`** | **PRIMARY - Use this by default** | Light backgrounds (white, yellow, light grey) | PNG |
| **`lightLogo.png`** | **For dark backgrounds** | Dark backgrounds (Bolt Black) | PNG |
| `bolt-logo.svg` | Alternate vector version | Light backgrounds | SVG |
| `bolt.svg` | Lightning bolt icon only | Decorative element, any background | SVG |

**Default Choice:**
- Light backgrounds → `blacklogo.png`
- Dark backgrounds → `lightLogo.png`

### Logo Usage

**Clearspace:**
- Minimum clearspace = height of the "O" in "Bolt" on all sides
- Never place other elements within clearspace

**Minimum Sizes:**
- Digital: 80px width minimum
- Email: 100px width recommended
- Print: 0.5 inches width minimum

**DO:**
- ✅ Use `blacklogo.png` on yellow/light backgrounds (PRIMARY)
- ✅ Use `lightLogo.png` on dark backgrounds
- ✅ Maintain aspect ratio always
- ✅ Provide generous clearspace
- ✅ Place on solid backgrounds
- ✅ Set height in pixels, let width scale automatically

**DON'T:**
- ❌ Stretch, rotate, or distort the logo
- ❌ Add effects (shadows, gradients, outlines, glows)
- ❌ Change logo colors
- ❌ Add taglines or text inside/touching the logo
- ❌ Place on busy background images
- ❌ Use low-resolution versions
- ❌ Use text instead of logo image files

### Lightning Bolt Icon (`bolt.svg`)

The standalone lightning bolt graphic can be used as:
- Decorative accent (various opacities: 0.1-0.3)
- Section divider
- Pattern element
- Visual punctuation
- Background element

**Usage tips:**
- Reduce opacity (15-30%) when used decoratively
- Scale between 40px-160px depending on context
- Use to create visual rhythm and energy
- Never use as a replacement for the full logo

---

## Design Elements

### Buttons & CTAs

**Primary Button (Yellow):**
```css
background-color: #E1FF00;
color: #11190C;
font-family: 'Inter', Arial, sans-serif;
font-size: 16-18px;
font-weight: 600-700;
padding: 14px 32px (or 18px 48px for large);
border-radius: 5px;
```

**Secondary Button (Outlined):**
```css
background-color: transparent;
border: 2px solid #11190C;
color: #11190C;
font-family: 'Inter', Arial, sans-serif;
font-size: 16px;
font-weight: 600;
padding: 14px 32px;
border-radius: 5px;
```

**Inverted Button (on dark backgrounds):**
```css
background-color: #E1FF00;
color: #11190C;
/* Same specs as primary */
```

### CTA Copy Guidelines
- Start with action verb: "Download," "Get," "Start"
- Be specific: "Download Brand Kit" > "Submit"
- Keep under 4 words when possible
- Create urgency without pressure
- Examples: "Get Started," "Download Now," "Learn More"

### Border Radius

Use consistent corner rounding:
- **Standard boxes/cards**: `border-radius: 5px;`
- **Buttons**: `border-radius: 5px;`
- **Images**: Usually none, but 5px acceptable for UI cards

### Spacing System

Use consistent spacing multiples:
```
4px   - Micro spacing (internal elements)
8px   - Tight spacing (related items)
16px  - Standard spacing (between elements)
24px  - Medium spacing (section breathing room)
32px  - Large spacing (section padding)
40px  - XL spacing (major sections)
48px  - XXL spacing (hero sections)
64px  - Hero padding
```

---

## Layouts & Composition

### Visual Hierarchy Principles

1. **One clear focal point** — What should viewers see first?
2. **Progressive disclosure** — Guide the eye logically through content
3. **Generous breathing room** — Don't fear whitespace (or "yellowspace")
4. **High contrast** — Important elements must stand out

### Layout Patterns

**Full-Width Hero:**
- Lightning Yellow or Bolt Black background
- Massive headline (48-64px)
- Lightning bolt graphic as accent
- Minimal copy, maximum impact

**Asymmetric Sections:**
- 70/30 or 60/40 column splits
- Alternating content and visual placement
- Creates dynamic rhythm
- Example: Text left, bolt graphic right → flip next section

**Stacked Impact:**
- Alternating background colors (yellow/black/grey)
- Full-bleed sections
- Clear visual separation
- Each section tells one story

**Grid Systems:**
- 600px max width for email
- 1200-1440px max for web
- 2-column layouts for features/products
- Always mobile-responsive (stack on mobile)

### Composition Checklist
- [ ] Is the main message visible in 3 seconds?
- [ ] Is there a clear visual path (F-pattern or Z-pattern)?
- [ ] Do CTAs stand out from surrounding content?
- [ ] Is spacing consistent throughout?
- [ ] Does it work on mobile (under 600px width)?

---

## Copywriting Guidelines

### Voice & Tone

**Thoughtfully Concise:**
- Every word earns its place
- "Get the brand kit" > "Download our comprehensive brand guidelines package"
- Fragments are fine: "Faster. Bolder. Shockingly simple."
- Avoid jargon and corporate speak

**Knowingly Playful:**
- Clever, not childish
- Confident wit: "Shockingly simple" not "Very easy to use"
- Surprising but appropriate
- Self-aware without being smug

**Comfortably at Ease:**
- Conversational, not formal
- "That's us. That's Bolt." not "This concludes our brand overview."
- Inviting and warm
- Never aggressive or pushy

### Copy Checklist
- [ ] Could this be shorter without losing meaning?
- [ ] Is there a more interesting way to say this?
- [ ] Does it sound like a conversation, not a lecture?
- [ ] Would someone actually say this out loud?
- [ ] Does it feel like Bolt talking?

### Taglines & Key Phrases

**Primary Tagline:**
```
Shockingly simple.
```

**Supporting Phrases:**
- "Lightning-fast checkout"
- "Faster. Bolder."
- "This is Bolt."
- "Speed meets trust."
- "Everywhere you look"

### Headline Formulas

```
[Action] + [Benefit]
→ "Get the brand kit"
→ "Download the guidelines"

[Big Statement]
→ "This is Bolt."
→ "Meet the new brand."

[Three-Part Rhythm]
→ "Faster. Bolder. Shockingly simple."
→ "In your pocket. On every corner. In your hands."

[Question + Answer]
→ "What's new? Everything."
→ "Ready? Let's go."
```

---

## Email-Specific Guidelines

### Email Structure
- **Max width**: 600px
- **Background**: Light Grey (#F3F1EE) or Bolt Black (#11190C) or Lightning Yellow (#E1FF00)
- **Content area**: White (#FFFFFF) or alternating sections
- **Padding**: 40px desktop, 24px mobile

### Email Coding Rules

**Always:**
- Inline all CSS on elements
- Use tables for layout (not div/flexbox)
- Include `role="presentation"` on layout tables
- Add `cellspacing="0" cellpadding="0" border="0"` to tables
- Use `display: block;` on all images
- Specify image width in pixels
- Include `height: auto` on images
- Include alt text on all images
- Use `border-radius: 5px;` for boxes

**Font Loading:**
```html
<style>
  @font-face {
    font-family: 'Agrandir Narrow';
    src: url('../assets/Agrandir/Agrandir-Narrow.otf') format('opentype');
    font-weight: 400;
    font-style: normal;
  }
  @import url('https://rsms.me/inter/inter.css');
</style>
```

**Asset Paths:**
- Email files in `emails/` folder use: `../assets/filename.ext`
- Always verify relative paths based on output location
- Never assume—check the file structure first

**Responsive:**
```css
@media screen and (max-width: 600px) {
  .email-container { width: 100% !important; }
  .stack-column { display: block !important; width: 100% !important; }
  .hide-mobile { display: none !important; }
  .padding-mobile { padding: 24px !important; }
}
```

### Email Typography
- Headlines: Arial Black (Agrandir fallback won't load everywhere)
- Body: Arial/Helvetica (Inter fallback)
- Minimum: 14px (12px for captions)
- Always provide web-safe fallbacks

---

## Imagery Guidelines

### Photo Style
- **Natural lighting** preferred over studio
- **Warm, inviting tones** that complement yellow
- **Real people, authentic moments** over stock poses
- **Clean compositions** — avoid clutter
- **High energy** — motion, action, emotion

### Image Don'ts
- ✗ Overly staged or fake smiles
- ✗ Heavy filters or dramatic effects
- ✗ Generic stock photo clichés
- ✗ Cluttered, busy compositions
- ✗ Low quality or pixelated images

### Image Treatment
- No filters unless matching brand aesthetic
- Can overlay lightning bolt graphic at low opacity
- Ensure sufficient contrast for overlaid text
- Maintain aspect ratios (no squishing)

---

## Asset Checklist

Before finalizing any Bolt brand asset, verify:

### Colors
- [ ] Only brand colors used (#E1FF00, #11190C, #787664, #CAC4B7, #F3F1EE)
- [ ] Lightning Yellow used intentionally and boldly
- [ ] Text has sufficient contrast for accessibility
- [ ] No pure black (#000000) — using Bolt Black (#11190C)

### Typography
- [ ] Agrandir Narrow for headlines
- [ ] Inter for body copy
- [ ] Proper fallback fonts specified
- [ ] 16px minimum for body (14px min for captions)
- [ ] Headlines under 8 words where possible
- [ ] Consistent line heights (1.4-1.7 for body)

### Logo
- [ ] **Using PNG logo files (`blacklogo.png` or `lightLogo.png`), NOT text**
- [ ] Correct logo version for background color (black on light, light on dark)
- [ ] Proper clearspace maintained
- [ ] Minimum size requirements met (80px+ width)
- [ ] No distortion, effects, or modifications
- [ ] High resolution (not pixelated)
- [ ] Height set in pixels with `width: auto` for proper scaling

### Layout
- [ ] Clear visual hierarchy
- [ ] Generous whitespace/breathing room
- [ ] CTAs stand out clearly
- [ ] Consistent spacing system used
- [ ] Mobile-responsive (if digital)

### Copy
- [ ] Thoughtfully concise
- [ ] Knowingly playful tone
- [ ] Comfortably at ease voice
- [ ] No jargon or corporate speak
- [ ] Sounds like Bolt talking

### Technical (Digital/Email)
- [ ] All CSS inlined (email)
- [ ] Images have alt text
- [ ] Images have display: block
- [ ] Asset paths verified and correct
- [ ] Border-radius: 5px on boxes
- [ ] Tables used for layout (email)
- [ ] Tested on mobile

---

## Quick Reference

### Copy This Code Block

```css
/* BOLT BRAND COLORS */
--lightning-yellow: #E1FF00;
--bolt-black: #11190C;
--dark-grey: #787664;
--mid-grey: #CAC4B7;
--light-grey: #F3F1EE;

/* BOLT TYPOGRAPHY */
font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif; /* Headlines */
font-family: 'Inter', Arial, Helvetica, sans-serif; /* Body */

/* BOLT SPACING */
padding: 40px; /* Desktop */
padding: 24px; /* Mobile */
border-radius: 5px; /* Standard */

/* BOLT BUTTON */
background: #E1FF00;
color: #11190C;
padding: 14px 32px;
border-radius: 5px;
font-weight: 600;
```

---

## Examples & Templates

### File Locations
- **Email Templates**: `emails/brand-announcement-v3.html` (reference the V3 for best practices)
- **Email Skill**: `skills/email-coder/SKILL.md`
- **Component Showcases**: `button-showcase.html`, `navigation-showcase.html`
- **Assets**: `assets/` folder
  - **Logos (USE THESE)**: `blacklogo.png` (primary), `lightLogo.png` (dark backgrounds)
  - Alternate logo: `bolt-logo.svg`
  - Icon: `bolt.svg` (lightning bolt graphic only)
  - Fonts: `assets/Agrandir/`
  - Images: Various product/lifestyle shots

### Skills to Use
- **email-coder**: For creating HTML emails with proper inline CSS and email-safe code
- **creative-director**: For reviewing assets against brand guidelines
- **frontend-design**: For creating bold, distinctive web interfaces
- **marketing-copywriter**: For writing punchy, on-brand copy

---

## When In Doubt

**Ask yourself:**
1. Does it feel electric and energetic?
2. Is Lightning Yellow making a bold statement?
3. Is the copy shorter than you think it should be?
4. Would someone remember this in 3 seconds?
5. Does it sound like Bolt talking?

**If yes to all five → Ship it.**

---

**Last updated**: December 2024
**Version**: 1.0

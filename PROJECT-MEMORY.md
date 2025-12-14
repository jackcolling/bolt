# Bolt Project Memory

**Purpose:** This document serves as persistent memory across sessions. It tracks decisions, patterns, learnings, and important context that should inform future work.

**When to use:** Read this file at the start of any Bolt brand work. Update it when making important decisions or discovering new patterns.

---

## Project Overview

**Brand:** Bolt
**Personality:** Modern, energy-focused, bold, playful, confident
**Visual Identity:** Lightning Yellow (#E1FF00) + Bolt Black (#11190C)
**Voice:** Thoughtfully concise, knowingly playful, comfortably at ease

---

## Critical Learnings

### Logo File Usage (HIGHEST PRIORITY)

**Issue Discovered:** 2025-12-14
**Problem:** Created navigation showcase using text-based logo and wrong logo file for yellow background
**Root Cause:** Not checking background color before choosing logo file

**Rule Established:**
1. **ALWAYS use PNG files** (`blacklogo.png` or `lightLogo.png`), NEVER text
2. **Light/yellow backgrounds** → `blacklogo.png`
3. **Dark backgrounds (Bolt Black #11190C)** → `lightLogo.png`
4. **Yellow backgrounds specifically** → Still use `blacklogo.png` (black logo has better contrast on yellow)

**Enforcement:**
- Updated BRAND-ASSET-GUIDE.md with critical warnings
- Updated creative-director skill to catch this error
- Created frontend-design skill with explicit logo instructions

---

## File Structure

```
bolt/
├── index.html                    # Component library hub (START HERE)
├── BRAND-ASSET-GUIDE.md          # Master brand guidelines
├── PROJECT-MEMORY.md             # This file - persistent context
├── assets/
│   ├── blacklogo.png             # PRIMARY logo (light backgrounds)
│   ├── lightLogo.png             # White logo (dark backgrounds)
│   ├── bolt-logo.svg             # Alternate vector
│   ├── bolt.svg                  # Lightning bolt icon only
│   └── Agrandir/                 # Font files
├── emails/
│   └── brand-announcement-v3.html # Reference for email best practices
├── showcases/                    # Component demonstration files
│   ├── button-showcase.html      # Button variations (7 options)
│   ├── navigation-showcase.html  # Navigation patterns (7 options)
│   └── footer-showcase.html      # Footer layouts (5 options)
└── skills/
    ├── email-coder/              # HTML email creation
    ├── creative-director/        # Brand review & critique
    ├── frontend-design/          # Web component creation
    └── marketing-copywriter/     # Brand voice copywriting
```

## Logo CDN Links

**Hosted on GitHub for web use:**

```
Black Logo (light/yellow backgrounds):
https://raw.githubusercontent.com/jackcolling/bolt/main/blacklogo.png

Light Logo (dark backgrounds):
https://raw.githubusercontent.com/jackcolling/bolt/main/lightLogo.png
```

All HTML showcases use these GitHub raw URLs for reliable, fast logo display.

---

## Skills & Their Usage

### When to Use Each Skill

| Skill | Use When | Key Responsibility |
|-------|----------|-------------------|
| **frontend-design** | Creating web components, pages, navigation, buttons, layouts | Ensure correct logo files, brand colors, typography |
| **email-coder** | Creating HTML emails | Inline CSS, email-safe code, proper table structure |
| **creative-director** | Reviewing any creative work | Grade against brand standards, catch errors before shipping |
| **marketing-copywriter** | Writing copy, headlines, CTAs, messaging | Match brand voice (concise, playful, at ease) |

### Skill Workflow Pattern

**For Web Components:**
1. Use `frontend-design` skill to create component
2. Use `creative-director` skill to review before finalizing

**For Emails:**
1. Use `email-coder` skill to build email
2. Use `creative-director` skill to review
3. (Optional) Use `marketing-copywriter` if copy needs work

---

## Design Patterns & Decisions

### Border Radius
**Decision:** 5px standard across all components
**Rationale:** Consistent brand element, not too rounded (playful) not too sharp (harsh)
**Applied to:** Buttons, cards, images, containers, form inputs

### Transitions
**Decision:** `all 0.2s ease` as standard
**Rationale:** Fast enough to feel responsive, slow enough to be smooth
**Applied to:** Hover states, color changes, transforms

### Logo Sizing
**Decision:** Set `height` in pixels, `width: auto`
**Rationale:** Maintains aspect ratio, prevents distortion
**Pattern:**
```css
.logo { height: 32px; }
.logo img { height: 32px; width: auto; display: block; }
```

### Button Hover Pattern
**Standard:** Background/text color swap + translateY(-2px)
**Example:**
- Default: Yellow background, black text
- Hover: Black background, yellow text, lift 2px
**Rationale:** Creates energy/movement while staying on-brand

---

## Common Mistakes & Solutions

### ❌ Mistake: Using Pure Black
**Wrong:** `color: #000000`
**Right:** `color: #11190C` (Bolt Black)
**Why:** Bolt Black is warmer, more on-brand than pure black

### ❌ Mistake: No Font Fallbacks
**Wrong:** `font-family: 'Agrandir Narrow'`
**Right:** `font-family: 'Agrandir Narrow', Arial Black, Helvetica, sans-serif`
**Why:** Custom fonts may fail to load; fallbacks ensure readability

### ❌ Mistake: Yellow Text on Light Backgrounds
**Wrong:** Yellow (#E1FF00) text on white background
**Right:** Use yellow for backgrounds/highlights, never body text
**Why:** Accessibility - insufficient contrast for readability

### ❌ Mistake: Text Logo Instead of PNG
**Wrong:** `<div class="logo">BOLT</div>`
**Right:** `<img src="assets/blacklogo.png" alt="Bolt">`
**Why:** Brand consistency, visual identity, professionalism

---

## Brand Voice Examples

### Thoughtfully Concise
- ❌ "We're excited to announce the launch of our new feature that will help you save time"
- ✅ "Save 5 hours weekly"

### Knowingly Playful
- ❌ "Click here to get started with our platform"
- ✅ "Light up your workflow"

### Comfortably at Ease
- ❌ "URGENT: Limited time offer expires soon!"
- ✅ "Worth a look before Friday"

---

## Technical Notes

### Font Loading Strategy
1. **Agrandir Narrow:** Load from local OTF file (`assets/Agrandir/Agrandir-Narrow.otf`)
2. **Inter:** Load from CDN (`https://rsms.me/inter/inter.css`)
3. **Always include fallbacks** in font-family declarations

### Color Implementation
**Use CSS custom properties for maintainability:**
```css
:root {
  --lightning-yellow: #E1FF00;
  --bolt-black: #11190C;
  --dark-grey: #787664;
  --mid-grey: #CAC4B7;
  --light-grey: #F3F1EE;
}
```

### Responsive Breakpoints (Recommended)
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

---

## Quality Standards

### Before Shipping Any Asset

**Brand Compliance:**
- [ ] Correct logo file for background color
- [ ] Only brand palette colors used
- [ ] Agrandir Narrow + Inter typography
- [ ] 5px border-radius on rounded elements
- [ ] Brand voice in all copy

**Code Quality:**
- [ ] Semantic HTML
- [ ] Font fallbacks specified
- [ ] Smooth transitions (0.2s ease)
- [ ] Mobile responsive
- [ ] Accessibility (alt text, ARIA, keyboard nav)

**Visual Quality:**
- [ ] Clear hierarchy
- [ ] Generous whitespace
- [ ] Readable text (16px+ body)
- [ ] Strong CTAs
- [ ] Consistent spacing

---

## Session History & Key Decisions

### 2025-12-14: Logo File Error Discovery
- **Issue:** Navigation showcase used wrong logo files
- **Impact:** Black logo on yellow background = poor contrast
- **Fix:** Updated all 7 navigation options with correct logo files
- **Prevention:** Created explicit documentation, updated skills, added to checklists

### 2025-12-14: Skills System Established
- **Created:** frontend-design skill for web component creation
- **Purpose:** Ensure brand guidelines followed during creation, not just review
- **Pattern:** Create with frontend-design → Review with creative-director

### 2025-12-14: PROJECT-MEMORY.md Created
- **Purpose:** Persistent context across sessions
- **Goal:** Never repeat the same mistakes, maintain consistency
- **Updates:** Add learnings whenever important decisions are made

### 2025-12-14: File Organization & Component Library
- **Created:** `index.html` as central hub for all components and resources
- **Organized:** Moved all showcase files to `showcases/` directory
- **Structure:** Clean separation between documentation, showcases, and assets
- **Components:** Buttons (7), Navigation (7), Footers (5)
- **Access:** Single entry point at `index.html` with navigation to all resources

---

## Future Considerations

### Potential Additions
- [ ] Dark mode guidelines (if needed)
- [ ] Animation library (motion design patterns)
- [ ] Icon system beyond lightning bolt
- [ ] Component naming conventions
- [ ] A11y testing checklist
- [ ] Performance budgets

### Questions to Resolve
- Should we create a CSS framework/library for common components?
- Do we need print-specific guidelines beyond the logo sizing?
- Should we establish a grid system (8px, 12px, etc.)?

---

## Update Log

| Date | Update | Impact |
|------|--------|--------|
| 2025-12-14 | Initial creation | Established memory system |
| 2025-12-14 | Logo file rules documented | Critical for brand consistency |
| 2025-12-14 | Skills workflow established | Clear process for creation + review |
| 2025-12-14 | File organization & hub created | `index.html` + `showcases/` directory for better navigation |

---

## Quick Links

**Start Here:**
- `index.html` - Component library hub with links to everything

**Essential Docs:**
- `BRAND-ASSET-GUIDE.md` - Complete brand guidelines
- `PROJECT-MEMORY.md` - This file (read at start of each session)

**Showcases:**
- `showcases/button-showcase.html` - 7 button options
- `showcases/navigation-showcase.html` - 7 navigation patterns
- `showcases/footer-showcase.html` - 5 footer layouts

**Skills:**
- `skills/frontend-design/` - Web component creation
- `skills/email-coder/` - HTML email creation
- `skills/creative-director/` - Brand review & critique
- `skills/marketing-copywriter/` - Brand voice copywriting

---

**Note:** Update this file whenever you make important decisions, discover patterns, or learn from mistakes. This is living documentation.

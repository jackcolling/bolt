---
name: creative-director
description: Analyze and critique creative work against brand guidelines. Use this skill when reviewing emails, designs, web pages, marketing materials, or any creative output to ensure quality and brand alignment. Provides detailed feedback, grades work on key criteria, and offers actionable suggestions for improvement. Acts as quality control before work goes to client.
---

# Creative Director

Review creative work with a critical eye. Grade output, identify issues, and provide actionable feedback to elevate quality.

## Review Process

### 1. Load Brand Context

Before reviewing, read the brand guidelines:
- `references/brand-guidelines.md` - Core brand rules

### 2. Evaluate Against Criteria

Score each criterion 1-5:
- **5** = Exceptional, exceeds standards
- **4** = Strong, meets all requirements
- **3** = Acceptable, minor issues
- **2** = Needs work, notable problems
- **1** = Does not meet standards

### 3. Provide Structured Feedback

Output format:

```
## Creative Review

### Overall Grade: [A/B/C/D/F]

### Scores

| Criterion | Score | Notes |
|-----------|-------|-------|
| Brand Alignment | X/5 | ... |
| Visual Hierarchy | X/5 | ... |
| Typography | X/5 | ... |
| Color Usage | X/5 | ... |
| Copy/Tone | X/5 | ... |
| Technical Execution | X/5 | ... |

### What's Working
- [Specific positives]

### Critical Issues
- [Must-fix problems]

### Suggestions
- [Actionable improvements]

### Final Verdict
[1-2 sentence summary and recommendation]
```

## Evaluation Criteria

### Brand Alignment
- Does it feel like the brand?
- Are brand colors used correctly?
- Is the logo treated properly?
- Does the tone match brand voice?

Questions to ask:
- Would someone recognize this as [brand] without seeing the logo?
- Does it reinforce or dilute the brand?

### Visual Hierarchy
- Is there a clear focal point?
- Does the eye flow naturally?
- Is important information prominent?
- Is there appropriate contrast?

Questions to ask:
- What do you see first, second, third?
- Can you understand the message in 3 seconds?

### Typography
- Are the correct typefaces used?
- Is hierarchy clear (headlines vs body)?
- Is text readable at intended size?
- Is spacing consistent?

Questions to ask:
- Does the typography feel on-brand?
- Are there any kerning or leading issues?

### Color Usage
- Are brand colors applied correctly?
- Is there sufficient contrast for readability?
- Are color combinations following guidelines?
- Is the hero color used effectively?
- **Is the correct logo file used for the background color?**

Questions to ask:
- Are any off-brand colors present?
- Does the color support the message?
- **Logo on light/yellow backgrounds: Is `blacklogo.png` being used?**
- **Logo on dark backgrounds: Is `lightLogo.png` being used?**
- Does the logo have sufficient contrast against its background?

### Copy/Tone of Voice
- Does it match brand voice principles?
- Is it concise and clear?
- Is the message compelling?
- Are CTAs strong and action-oriented?

Questions to ask:
- Does it sound like the brand talking?
- Would the target audience respond to this?

### Technical Execution
- Is the code/design production-ready?
- Are there any bugs or broken elements?
- Does it work across intended platforms?
- Are assets optimized?

Questions to ask:
- Would you be comfortable sending this to client?
- Are there any embarrassing errors?

## Grade Scale

| Grade | Score Range | Meaning |
|-------|-------------|---------|
| A | 27-30 | Excellent. Ship it. |
| B | 22-26 | Good. Minor polish needed. |
| C | 17-21 | Acceptable. Several improvements needed. |
| D | 12-16 | Below standard. Significant rework required. |
| F | <12 | Does not meet standards. Start over. |

## Review Mindset

### Be Specific
Not: "The colors feel off"
Instead: "The button uses #FF0000 instead of brand Lightning Yellow #E1FF00"

### Be Constructive
Not: "This headline is bad"
Instead: "The headline could be punchier. Try leading with the benefit: 'Save 5 hours weekly' instead of 'Our new feature'"

### Be Honest
- Don't sugarcoat problems
- Client trust depends on quality
- Better to catch issues now than after launch

### Prioritize Feedback
1. **Critical** - Must fix before delivery
2. **Important** - Should fix, impacts quality
3. **Nice to have** - Polish if time permits

## Common Issues to Watch For

### Brand
- **Wrong logo file for background (CRITICAL):**
  - `blacklogo.png` on dark backgrounds → Should be `lightLogo.png`
  - `lightLogo.png` on light/yellow backgrounds → Should be `blacklogo.png`
  - Text-based logo instead of PNG file → Always use actual logo files
- Off-brand colors (anything not in the palette)
- Missing or incorrect typography (should be Agrandir Narrow + Inter)
- Tone too formal/informal for brand voice

### Design
- No clear visual hierarchy
- Crowded layouts
- Inconsistent spacing
- Poor image quality

### Copy
- Too long/wordy
- Weak CTAs
- Jargon or unclear language
- Typos and grammar errors

### Technical
- Broken links/images
- Unresponsive layouts
- Slow load times
- Accessibility issues

## Quick Checklist

Before approving any creative:

- [ ] **Logo file used correctly:**
  - [ ] Using PNG files (`blacklogo.png` or `lightLogo.png`), NOT text
  - [ ] `blacklogo.png` on light/yellow backgrounds
  - [ ] `lightLogo.png` on dark backgrounds (Bolt Black)
  - [ ] Sufficient contrast between logo and background
- [ ] Brand colors only (no off-palette colors)
- [ ] Correct typography (Agrandir Narrow for headlines, Inter for body)
- [ ] Tone matches brand voice (concise, playful, at ease)
- [ ] Clear visual hierarchy (one focal point, logical flow)
- [ ] Strong CTA (action verb, specific, under 4 words)
- [ ] No spelling/grammar errors
- [ ] All links work
- [ ] Responsive/cross-platform tested
- [ ] Assets optimized

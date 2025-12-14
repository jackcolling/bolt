---
name: email-coder
description: Create production-ready HTML emails with proper inline CSS, cross-client compatibility, and responsive design. Use this skill when building HTML emails, email templates, newsletters, or any email-based communication. Handles Outlook quirks, mobile responsiveness, dark mode, and accessibility. Prevents common email coding mistakes like broken images, unsupported CSS, and rendering issues.
---

# Email Coder

Build bulletproof HTML emails that render correctly across all email clients.

## Critical Rules

### 1. Always Inline CSS

Email clients strip `<style>` tags. All styles MUST be inlined on elements.

```html
<!-- WRONG -->
<style>.button { background: #E1FF00; }</style>
<a class="button">Click</a>

<!-- CORRECT -->
<a style="background: #E1FF00; padding: 14px 32px; display: inline-block;">Click</a>
```

Keep a `<style>` block only for:
- `@media` queries (responsive)
- `@font-face` declarations
- Pseudo-classes (`:hover`) - but these won't work everywhere

### 2. Use Tables for Layout

Flexbox and Grid don't work. Use nested tables.

```html
<table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
  <tr>
    <td style="padding: 40px;">
      Content here
    </td>
  </tr>
</table>
```

Always include:
- `role="presentation"` (accessibility)
- `cellspacing="0" cellpadding="0" border="0"` (reset defaults)
- Explicit `width` on tables and cells

### 3. Asset Paths

**Before writing any image src, verify the output file location relative to assets.**

```
project/
├── assets/
│   └── logo.svg
└── emails/
    └── newsletter.html  ← Output here? Use ../assets/logo.svg
```

If output is in same directory as assets: `src="assets/logo.svg"`
If output is in subdirectory: `src="../assets/logo.svg"`

**Never assume paths. Always check the file structure first.**

### 4. Image Requirements

```html
<img
  src="../assets/image.png"
  alt="Descriptive text"
  width="600"
  style="display: block; width: 100%; max-width: 600px; height: auto;"
>
```

Required attributes:
- `alt` - Always (accessibility + images-off fallback)
- `width` - Always specify in pixels
- `style="display: block;"` - Prevents gaps in Outlook
- `height: auto` - Maintains aspect ratio

### 5. Fonts

**Web fonts are unreliable.** Always provide fallbacks.

```css
font-family: 'Custom Font', Arial Black, Helvetica, sans-serif;
```

Load web fonts in `<style>` (works in Apple Mail, iOS, some Android):
```html
<style>
  @import url('https://rsms.me/inter/inter.css');
</style>
```

### 6. Buttons

Never use `<button>`. Use table-based buttons for Outlook compatibility:

```html
<table role="presentation" cellspacing="0" cellpadding="0" border="0">
  <tr>
    <td style="border-radius: 4px; background-color: #E1FF00;">
      <a href="#" style="display: inline-block; padding: 14px 32px; font-family: Arial, sans-serif; font-size: 16px; font-weight: 600; color: #11190C; text-decoration: none;">
        Button Text
      </a>
    </td>
  </tr>
</table>
```

### 7. Max Width Container

Always constrain email width (600px standard):

```html
<table role="presentation" cellspacing="0" cellpadding="0" border="0" width="600" align="center" style="margin: 0 auto; max-width: 600px;">
```

## Email Structure Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>Email Title</title>
  <!--[if mso]>
  <noscript>
    <xml>
      <o:OfficeDocumentSettings>
        <o:PixelsPerInch>96</o:PixelsPerInch>
      </o:OfficeDocumentSettings>
    </xml>
  </noscript>
  <![endif]-->
  <style>
    /* Only @media, @font-face, and resets here */
    @media screen and (max-width: 600px) {
      .email-container { width: 100% !important; }
      .stack-column { display: block !important; width: 100% !important; }
    }
  </style>
</head>
<body style="margin: 0; padding: 0; background-color: #F3F1EE;">
  <!-- Wrapper -->
  <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
    <tr>
      <td style="padding: 40px 20px;">
        <!-- Container -->
        <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="600" align="center" class="email-container" style="margin: 0 auto;">
          <!-- Content rows here -->
        </table>
      </td>
    </tr>
  </table>
</body>
</html>
```

## Client-Specific Issues

### Outlook (Windows)

- Uses Word rendering engine
- No CSS `max-width` support - use `width` attribute
- No `background-image` on `<td>` - use VML fallback
- Adds gaps between tables - use `display: block` on images

MSO conditional comments:
```html
<!--[if mso]>
  Outlook-only content
<![endif]-->

<!--[if !mso]><!-->
  Non-Outlook content
<!--<![endif]-->
```

### Gmail

- Strips `<style>` from non-Gmail addresses
- Clips emails over 102KB
- Prefixes class names - avoid relying on classes

### Apple Mail / iOS

- Best web font support
- Supports most modern CSS
- Dark mode can invert colors

### Dark Mode

Add meta tag and provide dark mode overrides:

```html
<meta name="color-scheme" content="light dark">
<meta name="supported-color-schemes" content="light dark">
<style>
  @media (prefers-color-scheme: dark) {
    .dark-bg { background-color: #11190C !important; }
    .dark-text { color: #F3F1EE !important; }
  }
</style>
```

## Responsive Patterns

### Fluid Images
```html
<img src="image.png" width="600" style="display: block; width: 100%; max-width: 600px; height: auto;">
```

### Stacking Columns
```html
<table role="presentation" width="100%">
  <tr>
    <td width="50%" class="stack-column" style="display: inline-block; width: 50%;">
      Column 1
    </td>
    <td width="50%" class="stack-column" style="display: inline-block; width: 50%;">
      Column 2
    </td>
  </tr>
</table>
```

With CSS:
```css
@media screen and (max-width: 600px) {
  .stack-column { display: block !important; width: 100% !important; }
}
```

## Checklist Before Delivery

1. [ ] All CSS inlined on elements
2. [ ] All images have `alt`, `width`, `display: block`
3. [ ] Asset paths verified relative to output file location
4. [ ] Tables have `role="presentation"`, reset attributes
5. [ ] Fonts have fallback stack
6. [ ] Buttons use table structure
7. [ ] Width constrained to 600px max
8. [ ] Tested responsive `@media` queries
9. [ ] Under 102KB total size (Gmail clipping)

## References

- **Supported CSS**: See `references/css-support.md` for property compatibility
- **Testing tools**: Litmus, Email on Acid, Mailtrap

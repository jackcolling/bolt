# Email CSS Support Reference

## Safe to Use (High Support)

| Property | Notes |
|----------|-------|
| `background-color` | Inline only |
| `border` | All properties |
| `color` | Inline only |
| `font-family` | With fallbacks |
| `font-size` | Use `px` |
| `font-weight` | `normal`, `bold`, numeric |
| `line-height` | Use unitless or `px` |
| `margin` | Inline only |
| `padding` | Inline only; use on `<td>` |
| `text-align` | Works everywhere |
| `text-decoration` | Works everywhere |
| `vertical-align` | On `<td>` elements |
| `width` | Use attribute + inline |
| `height` | Use attribute + inline |

## Partial Support (Use with Caution)

| Property | Support Issues |
|----------|----------------|
| `background-image` | No Outlook support on `<td>` |
| `border-radius` | No Outlook 2007-2019 |
| `box-shadow` | No Outlook |
| `max-width` | No Outlook - use `width` attr |
| `display: inline-block` | Outlook needs `mso-` hack |
| `float` | Inconsistent - avoid |

## Not Supported (Avoid)

| Property | Reason |
|----------|--------|
| `flexbox` | No support |
| `grid` | No support |
| `position` | Stripped |
| `z-index` | Stripped |
| `transform` | No support |
| `animation` | Limited to Apple Mail |
| `calc()` | No support |
| `var()` | No support |
| `gap` | No support |

## Units

| Unit | Support |
|------|---------|
| `px` | Best support |
| `%` | Good for widths |
| `em` | Unreliable |
| `rem` | Not supported |
| `vw/vh` | Not supported |

## Selectors

| Selector | Support |
|----------|---------|
| Element (`p`) | Good in `<style>` |
| Class (`.name`) | Gmail prefixes |
| ID (`#name`) | Generally works |
| Attribute (`[attr]`) | Limited |
| Pseudo (`:hover`) | Apple Mail, iOS only |
| Pseudo (`::before`) | Very limited |

## Outlook-Specific

### VML Background Images

```html
<!--[if mso]>
<v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width:600px;height:400px;">
<v:fill type="tile" src="image.jpg" />
<v:textbox inset="0,0,0,0">
<![endif]-->
<div style="background-image: url('image.jpg'); width: 600px; height: 400px;">
  Content
</div>
<!--[if mso]>
</v:textbox>
</v:rect>
<![endif]-->
```

### MSO Properties

```css
/* Outlook-specific line-height */
mso-line-height-rule: exactly;

/* Outlook table spacing */
mso-table-lspace: 0pt;
mso-table-rspace: 0pt;

/* Outlook font fallback */
mso-font-alt: 'Arial';
```

## Gmail Specifics

- Strips `<style>` from external senders
- Clips at 102KB - shows "View entire message"
- Prefixes classes: `.button` → `.m_123_button`
- No support for `@import` in clipped emails

## Dark Mode

### Apple Mail / iOS
```css
@media (prefers-color-scheme: dark) {
  .dark-mode-bg { background-color: #000 !important; }
}
```

### Outlook (macOS)
Uses `[data-ogsc]` attribute:
```css
[data-ogsc] .dark-mode-text { color: #fff !important; }
```

### Gmail
No dark mode CSS support. Uses automatic inversion - test thoroughly.

## Fonts

### Web Font Loading

Best support (Apple Mail, iOS Mail, Android default):
```html
<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');
</style>
```

### Fallback Stack Examples

```css
/* Sans-serif */
font-family: 'Custom Sans', Arial, Helvetica, sans-serif;

/* Display/Bold */
font-family: 'Custom Display', Arial Black, Helvetica, sans-serif;

/* Serif */
font-family: 'Custom Serif', Georgia, 'Times New Roman', serif;

/* Monospace */
font-family: 'Custom Mono', 'Courier New', Courier, monospace;
```

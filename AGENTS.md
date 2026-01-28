# HTML Email Template Builder

This agent specializes in building HTML email templates for Bloomreach Engagement. It focuses on creating responsive, cross-client compatible email HTML using Jinja templating.

## Bloomreach Documentation Reference

- Jinja documentation: https://documentation.bloomreach.com/engagement/docs/jinja
- Jinja code snippets: https://documentation.bloomreach.com/engagement/docs/useful-jinja-snippets

## Jinja Instructions

- Prefer to use Bloomreach Jinja functionalities instead of regular Jinja.

### Jinja Best Practices

**Aggregate References:**

- Use aggregate IDs directly in aggregate references instead of creating separate variables
- **Good:** `{% set cart_item_ids = aggregates['685e4b7e99b5e4a91a1c6c89'] | default([]) %}`
- **Avoid:** `{% set aggregate_id = '685e4b7e99b5e4a91a1c6c89' %}{% set cart_item_ids = aggregates[aggregate_id] | default([]) %}`

**Default Values:**

- Always use `| default()` filter for optional values to prevent errors
- Use `| default('', true)` to also handle empty strings as missing values

**Loops and Conditionals:**

- Use `{% for item in items %}...{% endfor %}` for iteration
- Use `{% if condition %}...{% endif %}` for conditional rendering
- Combine with `{% else %}` for fallback content

**URL Personalization Syntax:**

- MandM project uses Bloomreach personalization syntax in URLs: `{objectID:Product_JJ33544|10}`
- This is NOT standard Jinja syntax (which uses `{{ }}`)
- Preserve this syntax exactly as provided in briefs - do not convert to Jinja template variables
- Example: `https://www.mandmdirect.com/01/jack-and-jones?BST={objectID:Product_JJ33544|10}`

## Useful Jinja Snippets

- **@documentation/useful_jinja_snippets.md** - Contains core Jinja snippets commonly used in Bloomreach Engagement, including price formatting, customer attribute handling, catalog access, date/time operations, and more.

## HTML Block Library

- **@documentation/html_block/blocks_README.md** - Overview of the modular email template component library
- **@documentation/html_block/blocks.md** - Detailed HTML block specifications (header, solo image, headline, three images, spacer, divider, buttons, footer)
- **@documentation/html_block/master_template.md** - Master HTML template structure and insertion point for blocks
- **@documentation/html_block/mandm_blocks.md** - Project-specific block short codes and parameters

Every email template must use the master template structure and place content at `{# Insert html blocks HERE #}`. Header and Footer blocks are mandatory.

### Block Implementation Methods

**Jinja `block()` Shortcodes:**
- Use Bloomreach's `block()` function for reusable components stored in the platform
- Format: `{{ block("block_id", {"PARAMETER": "value"}) }}`
- Available blocks are documented in `@documentation/html_block/mandm_blocks.md`
- Examples: Abandoned Cart, One Button, Quick Links, Spacer
- **Parameter Types:** Numeric parameters (e.g., `BORDER_SIZE`, `SPACE_AFTER`, `HEIGHT`) should be passed as numbers without quotes: `"BORDER_SIZE": 2` (not `"BORDER_SIZE": "2"`)
- String parameters (e.g., `TEXT`, `URL`, `BACKGROUND`) should be passed as quoted strings: `"TEXT": "SHOP NOW"`

**Raw HTML Blocks:**
- Use raw HTML when block shortcodes are not available or for project-specific components
- Header and Footer blocks for MandM project are currently implemented as raw HTML
- Follow patterns from `@documentation/html_block/blocks.md` for structure and styling
- Ensure all placeholders are clearly marked (e.g., `LOGO_PLACEHOLDER`, `ICON_PLACEHOLDER`)
- Maintain consistency with existing block patterns (table-based layout, inline styles, MSO compatibility)

**Best Practice:**
- Prefer Jinja `block()` shortcodes when available for easier maintenance and consistency
- Use raw HTML for Header/Footer or when specific customization is needed
- Always include placeholder comments (e.g., `{# Header #}`, `{# Footer #}`) for clarity

## HTML Email Best Practices

### General Structure

- Use table-based layout for maximum email client compatibility
- Maximum content width: **640px** (standard email width)
- Always use inline CSS styles for consistent rendering
- Include MSO conditional comments for Outlook compatibility: `<!--[if mso]>...<![endif]-->`

### Responsive Design

- Use the `.stack` class for columns that should stack on mobile
- Include media queries in `<style>` tag for mobile responsiveness
- Test responsive behavior at 660px breakpoint

### Cross-Client Compatibility

- Always include `role="presentation"` on layout tables
- Use `border="0" cellpadding="0" cellspacing="0"` on all tables
- Set explicit widths on table cells and images
- Use `display:block` on images to prevent gaps
- Include VML code for buttons in Outlook compatibility

### Images

- Full-width images: `width="640"` with `style="width:100%;max-width:640px;"`
- Always include `alt` text for accessibility
- **Alt Text Best Practice:** Include key campaign messages in alt text (combine subject line + pre-header for context)
- Example: `"JACK & JONES - Over 300 products! Up to 65% less than RRP"`
- Use `border="0"` on all images
- Host images on reliable CDN (e.g., brxcdn.com)

### Typography

- Use web-safe font stacks: `Arial, 'Helvetica Neue', Helvetica, sans-serif`
- Set font styles inline on each text element
- Use `mso-line-height-alt` for Outlook line-height compatibility

### Buttons

- Use VML roundrect for Outlook button compatibility
- Include both VML and HTML versions of buttons
- Match `fillcolor`, `stroke color`, `background-color`, and `color` across all button code

### Spacing

- Use spacer blocks instead of margin/padding where possible
- Include `line-height` matching `height` for spacers
- Use zero-width space character (`&#8202;`) to ensure proper rendering

### Colors

- Use hex color codes (e.g., `#28252c`)
- Define colors inline on elements, not in external stylesheets

## HTML Generation Guidelines

When generating email HTML:

1. Include complete HTML document structure: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
2. Include MSO conditional comments for Outlook compatibility
3. Include responsive CSS in `<style>` tag with media queries
4. Use table-based layout throughout
5. Apply all styles inline
6. Can contain Jinja template variables for personalization (e.g., `{{ customer.first_name }}`)
7. Use proper HTML entities (e.g., `&#8202;` for zero-width space)
8. Include VML code for buttons in Outlook

## Common Patterns

### Header/Footer

- Use complete HTML structure for precise control
- Header typically contains logo + navigation
- Footer contains social links, legal text, unsubscribe link

### Product Grids

- Use three-column layout with equal widths (33.333% each)
- Include 5px padding between images when stacked
- Make each image independently clickable

### Spacing

- Use spacer blocks between major sections (24px-36px standard)
- Consistent spacing improves readability

### Buttons

- Center-align buttons within their containers
- Use consistent styling across all CTAs
- Standard button height: 48px
- Standard button padding: 16px vertical, 26px horizontal

### Responsive Behavior

- Set `rowColStackOnMobile: true` concept for multi-column layouts
- Ensure content remains readable at mobile widths
- Test at 320px minimum width

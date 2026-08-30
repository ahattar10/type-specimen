# Type Specimen

A type specimen and design system reference page built with CSS custom properties (design tokens) for fonts, colors, spacing, and type scale.

## What This Is

A single-page reference documenting the typography, color palette, spacing, and core UI components of a small design system. The page demonstrates how design tokens flow into real components and serves as a visual contract for the system.

## Font

- **Family:** Roboto (400, 700)
- **Source:** Google Fonts
- **License:** Apache License 2.0
- **Fallback stack:** Roboto → Helvetica Neue → Arial → sans-serif

## File Structure

- `index.html` — markup and all content sections
- `style.css` — design tokens and all component styles
- `README.md` — this file

## How to View

Open `index.html` in any modern browser. No build step required.

## Testing

- **320px viewport:** Page renders without horizontal overflow. Buttons stack full-width. Text remains legible.
- **Wide viewport (1440px):** Text measure holds at 65ch via max-width token. Hierarchy preserved.
- **200% zoom at 320px:** Responsive breakpoints reduce font sizes and padding. No clipping or overflow.
- **Font fallback:** Fallback stack confirmed functional (Helvetica Neue → Arial). Roboto was not loading due to blocked requests; the fallback chain maintained readable hierarchy in both default and blocked states.

## AI Disclosure

This project used AI assistance (ChatGPT) for guidance on HTML/CSS structure, design token organization, responsive breakpoint strategy, and debugging the font fallback test. All code was written and reviewed by the project author.
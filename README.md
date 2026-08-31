# Type Specimen — Compact Type System

## Overview

A tokenized type system using self-hosted Roboto with an Arial fallback stack. Built to stay readable when the preferred font fails, loads slowly, or is unavailable.

## Font Source & Licensing

- Font family: Roboto
- Source: Self-hosted via @font-face in style.css
- Font files:
  - fonts/Roboto-Regular.woff2 (weight 400)
  - fonts/Roboto-Medium.woff2 (weight 500)
  - fonts/Roboto-Bold.woff2 (weight 700)
- License: Apache License 2.0
- License URL: https://www.apache.org/licenses/LICENSE-2.0
- Service requests: None — all fonts served locally from /fonts
- Fallback stack: Roboto, "Helvetica Neue", Arial, sans-serif

## Type Tokens

- --font-body: Roboto, Helvetica Neue, Arial, sans-serif
- --font-display: Roboto, Helvetica Neue, Arial, sans-serif
- --base-size: 1rem
- --body-line-height: 1.6
- --display-line-height: 1.1
- --measure: 65ch

### Type Scale (1.250 ratio)

Default sizes:
- --text-sm: 0.8rem
- --text-md: 1rem
- --text-lg: 1.25rem
- --text-xl: 1.5625rem
- --text-2xl: 3.052rem

At 360px breakpoint, large sizes shrink:
- --text-2xl: 2.5rem
- --text-xl: 1.375rem
- --text-lg: 1.125rem

At 200px breakpoint (200% zoom on 320px):
- --text-2xl: 2rem
- --text-xl: 1.25rem
- --text-md: 0.9rem
- --text-sm: 0.75rem

## Test Record

- 320px (Roboto loaded): No overflow. Buttons stacked full-width. Text legible.
- 320px (Roboto blocked, Arial fallback): h1 heading overflowed the viewport due to Arial's wider character widths. Fixed via media query.
- 1440px wide: Measure held at 65ch. Hierarchy intact. No issues.
- 200% zoom on 320px (effective 160px): 200px breakpoint kicked in. No clipping or overflow.

## Evidence-Based Revision

During the blocked-font test at 320px, the h1 heading (3.052rem) overflowed horizontally when Arial replaced Roboto. Arial's wider character metrics caused the heading to exceed the 320px viewport width.

Fix: Added a @media (max-width: 360px) breakpoint that reduces --text-2xl to 2.5rem and --text-xl to 1.375rem. Also added a @media (max-width: 200px) breakpoint for the 200% zoom scenario.

Verification: Reloaded at 320px with Roboto blocked. Heading now wraps cleanly. No horizontal scroll. Hierarchy preserved.

## File Structure

- index.html
- style.css
- README.md
- fonts/
  - Roboto-Regular.woff2
  - Roboto-Medium.woff2
  - Roboto-Bold.woff2
- screenshots

## AI Disclosure

This project used AI assistance (ChatGPT) for guidance on HTML/CSS structure, design token organization, responsive breakpoint strategy, and documentation. All code was written and reviewed by the project author. The AI provided explanations and suggestions that the author implemented manually.
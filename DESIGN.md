---
version: alpha
name: Markarbeten Göteborg
description: Regional guide for mark- och anläggningsentreprenörer in Göteborg/Västra Götaland (joint ES Sten + MS Entreprenad). Built from the Webraketen Astro starter pinned to its "construction" theme. This repo has no src/styles/global.css yet — these tokens mirror the starter's documented construction theme and become the contract once the site is built.
colors:
  brand: "#D97706"
  brand-dark: "#B45309"
  accent: "#1C1C1E"
  bg: "#FAFAF9"
  surface: "#FFFFFF"
  text: "#111827"
  muted: "#6B7280"
  border: "#E5E7EB"
  success: "#10B981"
typography:
  display:
    fontFamily: "Barlow, sans-serif"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  heading:
    fontFamily: "Barlow, sans-serif"
    fontWeight: 700
    lineHeight: 1.25
    letterSpacing: "-0.01em"
  body:
    fontFamily: "Inter, sans-serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.625
  small:
    fontFamily: "Inter, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
  overline:
    fontFamily: "Inter, sans-serif"
    fontSize: 12px
    fontWeight: 600
    letterSpacing: "0.1em"
rounded:
  sm: 6px
  md: 12px
  lg: 20px
spacing:
  1: 4px
  2: 8px
  3: 12px
  4: 16px
  6: 24px
  8: 32px
  12: 48px
  16: 64px
  24: 96px
components:
  button-primary:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.surface}"
    rounded: "{rounded.md}"
    padding: "12px 24px"
  button-primary-hover:
    backgroundColor: "{colors.brand-dark}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.brand}"
    border: "2px solid {colors.brand}"
    rounded: "{rounded.md}"
    padding: "12px 24px"
  card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.md}"
    border: "1px solid {colors.border}"
    shadow: "0 1px 3px rgb(0 0 0 / 0.08), 0 1px 2px rgb(0 0 0 / 0.06)"
    padding: "{spacing.6}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    border: "1px solid {colors.border}"
    rounded: "{rounded.sm}"
    padding: "12px 16px"
---

# Markarbeten Göteborg — Design System

Design contract for the joint regional guide to markarbeten in Göteborg/Västra Götaland
(ES Sten och Anläggning + MS Entreprenad). The token block above is the source of truth for
*intent*; once the site ships, `src/styles/global.css` (`@theme` block) becomes the source of
truth in code — change one, change the other in the same commit.

## Overview

A solid, industrial identity for a groundwork/landscaping (mark- och anläggning) guide:
amber brand, near-black accent, condensed Barlow headings, neutral warm-gray background. The
feeling is grounded, trustworthy, no-nonsense — built to convey craft (stensättning,
dränering, plattläggning) and 20+ års erfarenhet, not flash.

This repository currently holds only documentation; there is no `src/` or `global.css` yet.
These tokens mirror the **construction** theme of the shared Webraketen Astro/Tailwind starter
that the fleet is built from. When the site is implemented, pin this theme via
`data-theme="construction"` (or inline the values) and reconcile the `@theme` block back to
this file.

## Design Principles

1. **Solid over slick.** Whitespace, legible type, and proof (F-skatt, försäkring,
   kollektivavtal, fast pris) carry the page. No gradients fighting for attention.
2. **One brand color, used decisively.** `brand` amber for primary actions and key accents;
   `accent` near-black for contrast moments and footer surfaces only.
3. **Soft, not sharp.** Rounded corners (`rounded.md` for cards) and gentle shadows — solid,
   not hard-edged brutalism.
4. **Mobile-first.** Most traffic is phones searching a local trade. Tap targets ≥44px,
   single column by default, content before chrome.

## Color

| Token | Value | Use |
|------|-------|-----|
| `brand` | `#D97706` | Primary buttons, links, active states, focus ring |
| `brand-dark` | `#B45309` | Hover/pressed state for brand surfaces |
| `accent` | `#1C1C1E` | Near-black accent — footer background, high-contrast blocks |
| `bg` | `#FAFAF9` | Page background — a warm neutral, never pure white |
| `surface` | `#FFFFFF` | Cards, inputs, raised surfaces |
| `text` | `#111827` | Body and headings |
| `muted` | `#6B7280` | Secondary text, captions, placeholders |
| `border` | `#E5E7EB` | Hairline dividers and input borders |
| `success` | `#10B981` | Confirmation states, checkmarks |

Body text on `bg`/`surface` clears WCAG AA. White on `brand` is reserved for buttons and large
UI; for small text on amber prefer `text` or darken to `brand-dark`.

## Typography

- **Display / headings:** `Barlow` — condensed, sturdy, slightly tight tracking; reads as
  industrial without being severe. `h1–h4` use it via the base layer.
- **Body:** `Inter` — neutral, legible at small sizes.

Scale follows Tailwind defaults. Reach for the named roles: `display` for hero h1
(`text-4xl`→`text-7xl`, `font-extrabold`), `heading` for section h2/h3
(`text-2xl`→`text-4xl`, `font-bold`), `body` for paragraphs (`leading-relaxed`), `small` for
labels/meta, `overline` for `uppercase tracking-widest` eyebrow labels.

## Spacing & Layout

Spacing uses the Tailwind 4px scale (shared across all starter themes — only brand colors and
fonts swap per theme). Section rhythm is generous: standard sections `py-20 lg:py-28`; card
interiors use `spacing.6` (`lg:p-8`). Container is `max-w-6xl mx-auto px-4 sm:px-6 lg:px-8`;
prose narrows to ~`max-w-3xl`. Single column on mobile, 2–3 columns from `sm:`/`md:` up.

## Components

- **button-primary** — `brand` fill, white text, `rounded.md`, darkens to `brand-dark` on hover.
- **button-secondary** — white fill, `brand` text + 2px `brand` border; hover adds a `brand/5` wash.
- **card** — white surface, `rounded.md`, hairline `border`, resting shadow
  `0 1px 3px rgb(0 0 0 / 0.08)` lifting to `0 4px 16px rgb(0 0 0 / 0.12)` on hover.
- **input** — white surface, `border` outline, `rounded.sm`; focus shows the 2px brand ring.

## Accessibility

- Focus is always visible: a global double ring — `0 0 0 2px var(--color-surface), 0 0 0 4px
  var(--color-brand)` — that reads on any background.
- A skip link appears on focus (`bg-brand text-white`).
- Tap targets ≥44px; body text ≥16px; never rely on color alone to convey state.
- Full `prefers-reduced-motion` support.

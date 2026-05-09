---
version: alpha
name: AI Learning Roadmap
description: A clean, editorial roadmap for AI learning — monochrome foundation with stage-color accents, strong typographic hierarchy, and responsive layout that accommodates both Chinese and English text without breaking.

colors:
  bg: "#fafafa"
  surface: "#ffffff"
  surface-alt: "#f5f5f5"
  hover: "#f0f0f0"
  border: "#e5e5e5"
  border-hi: "#d4d4d4"
  ink: "#0a0a0a"
  ink-sec: "#525252"
  ink-muted: "#737373"
  accent: "#111111"
  accent-hover: "#333333"
  s1: "#15803d"
  s1-bg: "#f0fdf4"
  s1-br: "#bbf7d0"
  s2: "#a16207"
  s2-bg: "#fefce8"
  s2-br: "#fef08a"
  s3: "#7e22ce"
  s3-bg: "#faf5ff"
  s3-br: "#e9d5ff"
  s4: "#b91c1c"
  s4-bg: "#fef2f2"
  s4-br: "#fecaca"

typography:
  h1:
    fontFamily: Inter, sans-serif
    fontSize: "clamp(1.75rem, 4vw, 2.25rem)"
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: "-0.035em"
  h2:
    fontFamily: Inter, sans-serif
    fontSize: 1.25rem
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "-0.02em"
  body:
    fontFamily: Inter, sans-serif
    fontSize: 0.9375rem
    lineHeight: 1.6
    fontWeight: 400
  caption:
    fontFamily: Inter, sans-serif
    fontSize: 0.75rem
    lineHeight: 1.5
    fontWeight: 500
  overline:
    fontFamily: Inter, sans-serif
    fontSize: 0.75rem
    fontWeight: 600
    letterSpacing: "0.08em"
  mono:
    fontFamily: JetBrains Mono, monospace
    fontSize: 0.6875rem
    fontWeight: 500

spacing:
  xs: "0.25rem"
  sm: "0.5rem"
  md: "0.75rem"
  base: "1rem"
  lg: "1.25rem"
  xl: "1.5rem"
  xxl: "2rem"
  page: "2.5rem"

rounded:
  sm: 6px
  md: 8px
  lg: 12px
  full: 9999px

components:
  icon-btn:
    width: 34px
    height: 34px
    borderRadius: "{rounded.md}"
    backgroundColor: transparent
    textColor: "{colors.ink-sec}"
  icon-btn-hover:
    backgroundColor: "{colors.surface-alt}"
    textColor: "{colors.ink}"
  tag:
    borderRadius: "{rounded.sm}"
    padding: "1px 7px"
    backgroundColor: "{colors.surface-alt}"
    textColor: "{colors.ink-sec}"
  badge:
    borderRadius: "{rounded.full}"
    padding: "2px 10px"
    backgroundColor: "{colors.s1-bg}"
    textColor: "{colors.s1}"
  card:
    borderRadius: "{rounded.lg}"
    padding: "1.5rem"
    backgroundColor: "{colors.surface}"
  star-btn:
    borderRadius: "{rounded.md}"
    padding: "0.5rem 1rem"
    backgroundColor: "{colors.accent}"
    textColor: "{colors.bg}"
---

## Overview

Monochrome-first editorial layout for an AI learning roadmap. The ink-on-paper
aesthetic uses a single black accent for all interactive surfaces — theme toggle,
language switch, share buttons, and progress tracking. Stage colors (green, amber,
purple, red) are reserved exclusively for the timeline dots, section badges, and
completion indicators. This creates visual hierarchy without competing palettes.

**Core principle:** Typography does the heavy lifting. Boxes, icons, and color are
secondary. English and Chinese text must both fit cleanly — use `overflow-wrap:
break-word` on skill descriptions and generous grid minimum widths.

## Colors

- **bg (#fafafa):** Warm off-white page background. Softens the harshness of pure
  white without looking dirty.
- **surface (#ffffff):** Card and control bar background. Creates depth through
  contrast with the page.
- **ink (#0a0a0a):** Near-black for primary text. Softer than pure #000000.
- **ink-sec (#525252):** Secondary text for subtitles, descriptions, and muted labels.
- **ink-muted (#737373):** Tertiary text for timestamps, overlines, and meta info.
- **accent (#111111):** The sole interaction color. Used for all buttons, links, and
  progress fill in light mode. In dark mode, it inverts to #fafafa.
- **Stage colors (s1-s4):** Semantic color coding for the four learning stages.
  Green (beginner) → Amber (intermediate) → Purple (advanced) → Red (specialized).
  Only appear as small dots, badges, and completion chip accents.

## Typography

Inter for all UI text — its large x-height and neutral personality work well for
both dense technical content (skill names, code tags) and editorial prose
(descriptions, resource names). JetBrains Mono exclusively for technology tag pills
(`Python 3`, `sklearn`, `PyTorch`).

**Hierarchy:** overline → h1 title → h2 stage titles → body descriptions →
caption meta labels. No bold text below the stage title level — weight is reserved
for skill names and section headers.

## Layout

**Max width: 72rem** — wide enough for comfortable 3-column skill grids, narrow
enough to keep text lines readable.

**Timeline pattern:** A vertical line with stage dots, each stage containing a
card with a skills grid. The card grid uses `auto-fill, minmax(230px, 1fr)` so
it naturally adjusts from 3 → 2 → 1 columns as viewport shrinks.

**Controls bar:** Flex layout with legend on the left and icon buttons on the
right. Wraps to stacked rows on mobile (< 640px).

**Dark mode:** Full token swap via `[data-theme="dark"]`. Surface inverts to
#0a0a0a with #141414 cards. Accent inverts to #fafafa.

## Components

**icon-btn:** 34×34 square with 1px border. No background in default state.
Hover adds subtle surface-alt fill. Houses theme toggle (sun/moon SVG), language
toggle (EN/中文 text label), and share buttons (X/copy/GitHub SVGs).

**tag:** Mono font, 11px, with surface-alt background and thin border. Used for
technology keywords inside skill cards. Wraps naturally with `flex-wrap`.

**badge:** Pill-shaped section label at the top of each stage card. Filled with
the stage's color (e.g., green for beginner).

**card:** The main stage container with lg border-radius and 24px padding.
Contains the stage header (badge, title, subtitle, time) and a skills grid below.

**star-btn:** Solid accent fill button in the footer linking to GitHub. The only
filled button on the page — highest visual emphasis after the title.

## Do's and Don'ts

- **Do** use typography for hierarchy — size, weight, and letter-spacing before
  adding borders or backgrounds.
- **Do** let the skills grid reflow naturally. Don't force a fixed column count.
- **Don't** use stage colors outside of timeline dots, badges, and progress chips.
- **Don't** add decorative illustrations or emoji. The content is technical — the
  design should respect that.
- **Don't** use gradients or glassmorphism. Flat surfaces with 1px borders only.
- **Do** ensure English text fits in all containers. Use `overflow-wrap: break-word`
  on descriptions and generous `minmax(230px)` in grids.

---
name: accessibility-checker
description: "Audit a web page, component or design for accessibility against WCAG 2.2 AA \u2014 keyboard use, screen readers, contrast, forms, media and motion \u2014 and give concrete code fixes. Use when the user asks for an accessibility (a11y) review, WCAG compliance, or screen-reader support."
---

# Accessibility Checker

## When to use
- "Is this accessible?", "check WCAG compliance", "make this work with a screen reader / keyboard".

## Process
1. **Get the real thing**: URL, HTML/JSX, or design file. Automated tools (axe, Lighthouse) catch only part of the issues — combine with manual checks.
2. **Keyboard pass**: Tab through everything. Is every control reachable and operable? Is focus visible and in a logical order? Can you escape dialogs and menus? Any keyboard traps?
3. **Screen reader pass** (VoiceOver, NVDA): are headings, landmarks, labels, and state changes announced sensibly?
4. **Check the criteria below** and record each issue with its WCAG reference.
5. **Fix**: give the corrected code for each issue.

## Checklist (WCAG 2.2 AA)
- **Structure**: one `h1`, ordered headings, landmarks (`header`, `nav`, `main`, `footer`), correct `lang`.
- **Semantics**: native elements first (`button`, `a`, `label`, `select`); ARIA only to fill gaps, and with correct roles and states (`aria-expanded`, `aria-current`).
- **Names**: every control has an accessible name; icon buttons have `aria-label`; images have meaningful `alt` (or `alt=""` if decorative).
- **Contrast**: text ≥ 4.5:1 (large text ≥ 3:1); UI components and focus indicators ≥ 3:1.
- **Forms**: visible labels tied to inputs, instructions before fields, errors in text next to the field and announced, no color-only error states.
- **Target size**: at least 24×24 CSS px (WCAG 2.2), ideally 44×44 on touch.
- **Motion and time**: respects `prefers-reduced-motion`; no auto-playing media with sound; time limits can be extended.
- **Media**: captions for video, transcripts for audio.
- **Zoom/reflow**: usable at 200% zoom and 320px width without horizontal scrolling.

## Output format
| Severity | Issue | Where | WCAG | Fix |
|---|---|---|---|---|
| 🔴 Blocker | Icon button has no name | header search | 4.1.2 | `<button aria-label="Search">` |

Then the corrected code snippets, and what to verify manually.

## Rules
- Do not claim full compliance from an automated scan alone.
- Prefer fixing the HTML over adding ARIA.

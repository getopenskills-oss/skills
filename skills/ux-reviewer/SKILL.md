---
name: ux-reviewer
description: "Review a screen, flow, or prototype for usability and accessibility problems and return prioritized, specific fixes. Use when the user shares a UI (screenshot, URL, Figma, or code) and asks for UX feedback, a design critique, or why users struggle."
---

# UX Reviewer

## When to use
- "Review this screen/flow", "what's wrong with this UI?", "why aren't users converting?".

## Process
1. **Understand the goal**: who the user is, what task this screen serves, and what success looks like (sign-up, purchase, finding information).
2. **Walk the main task step by step** as a first-time user. Note every moment of hesitation, confusion, or extra work.
3. **Check against heuristics**:
   - Clarity: is the purpose and primary action obvious within 5 seconds?
   - Hierarchy: does visual weight match importance? Exactly one primary button per view.
   - Feedback: loading, success, empty and error states exist and explain what to do next.
   - Forms: labels (not placeholder-only), sensible defaults, inline validation, errors next to the field.
   - Consistency: the same thing looks and behaves the same everywhere.
   - Copy: plain words, specific button labels ("Save changes", not "Submit").
   - Mobile: touch targets ≥ 44px, no horizontal scroll, thumb-reachable primary actions.
4. **Check accessibility (WCAG 2.2 AA)**: text contrast ≥ 4.5:1, visible focus, full keyboard use, alt text, form labels, color not the only signal, respects reduced motion.

## Output format
```
## Summary
Overall verdict and the single most important fix.

## Issues
### 🔴 Blocks the task
- Where — what happens — why it hurts — specific fix
### 🟡 Slows users down
### 🔵 Polish

## What works well
```

## Rules
- Be specific: "the 'Continue' button is below the fold on 375px screens" beats "improve the layout".
- Tie each issue to user impact, and suggest a concrete fix.
- Separate evidence (what you observed) from opinion (taste).
- Recommend testing with 3–5 real users for anything uncertain.

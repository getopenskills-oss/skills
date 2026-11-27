---
name: refactoring-guide
description: "Plan and carry out safe refactorings in small, behavior-preserving steps backed by tests: find the real pain, choose the refactoring, change, verify. Use when code is hard to change, duplicated, too long, or the user asks to clean up or refactor."
---

# Refactoring Guide

## When to use
- "Clean this up", "this file is a mess", "refactor before adding feature X".
- Repeated bugs in the same area, or a change that should be small keeps getting big.

## Principles
- Refactoring changes structure, **not behavior**. Never mix a refactor and a behavior change in one commit.
- Work in **small steps**, each leaving the code working and the tests green.
- Refactor toward the change you need next — not toward abstract perfection.

## Process
1. **Name the pain** concretely: "adding a payment method means editing 6 files", "this 400-line function has 9 flags".
2. **Secure behavior with tests** first. If coverage is missing, add characterization tests that pin down current behavior (even odd behavior).
3. **Pick refactorings** that address the pain:
   - long function → extract function, replace temp with query;
   - duplication → extract shared function/module (only after the third copy, and only if they change for the same reason);
   - long parameter lists / flag arguments → introduce parameter object, split into separate functions;
   - nested conditionals → guard clauses, replace conditional with polymorphism or a lookup table;
   - unclear names → rename (cheapest, highest value);
   - god object → move function/field toward the data it uses.
4. **Apply one step at a time**; run tests after each; commit often with `refactor:` messages.
5. **Stop** when the next feature is easy to add. Note remaining debt instead of gold-plating.

## Rules
- Use automated IDE/language-server refactorings (rename, extract, move) where available — they are safer than manual edits.
- Keep public APIs stable, or deprecate them with a migration path.
- Do not reformat whole files in the same change; it hides the real diff.
- Large refactors: propose a plan with checkpoints before starting.

## Output
The plan (pain → steps), the diffs in small commits, and test results after each step.

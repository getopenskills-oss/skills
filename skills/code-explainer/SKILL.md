---
name: code-explainer
description: "Explain unfamiliar code clearly \u2014 what it does, how data flows through it, why it is written that way, and what to watch out for \u2014 at the reader's level. Use when the user asks what some code does, how a codebase works, or to walk through a function."
---

# Code Explainer

## When to use
- "What does this do?", "explain this file/function/regex/SQL", "how does this codebase work?"
- Onboarding to a new repository.

## Process
1. **Ask or infer the reader's level** (new to programming, new to this language, experienced but new to this codebase) and adapt vocabulary.
2. **Read before explaining.** Follow the call path: where is this called from, what does it call, what data goes in and out. For a codebase, start at entry points (main, routes, handlers, CLI commands) and the main data models.
3. **Explain top-down**:
   - one-sentence purpose,
   - inputs → steps → outputs,
   - the important details (edge cases, side effects, error handling, performance),
   - why it may be written this way (constraints, history, trade-offs) — clearly marked as inference.
4. **Point out risks**: bugs, surprising behavior, security concerns — briefly and separately.

## Techniques
- Walk through a concrete example input step by step.
- Use a small diagram (Mermaid sequence or flowchart) for multi-component flows.
- Quote short snippets with file and line references instead of pasting whole files.
- Define jargon the first time it appears.

## Rules
- Never guess what code does when you can read it; say "I could not find where X is defined" if needed.
- Separate what the code *does* from what it was probably *meant* to do.
- Keep it as short as the question allows; offer to go deeper.

## Output format
```
## In one sentence
## How it works
1. …
## Key details
## Watch out for
```

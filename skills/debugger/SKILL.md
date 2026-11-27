---
name: debugger
description: "Find the root cause of a bug systematically: reproduce it, form hypotheses, test them with evidence, then fix and verify. Use when something is broken, a test fails, or the user reports an error or unexpected behavior."
---

# Debugger

## When to use
- An error, stack trace, failing test, crash, or "it doesn't work".
- Behavior differs between environments, or started after a change.

## Process
1. **Reproduce.** Get the exact command, input, and output. If you cannot reproduce it, say so and collect more information (logs, versions, environment) before changing code.
2. **Read the error carefully.** The first error in the log is usually the real one; later ones are often consequences.
3. **Narrow the search.**
   - What changed? `git log`, `git diff`, dependency updates, config, data.
   - Bisect: `git bisect`, or comment out halves until the failure moves.
   - Make the failing case as small as possible.
4. **Form hypotheses and test each one** with a single targeted experiment: a log line, an assertion, a debugger breakpoint, a minimal script. Write down what each result rules in or out.
5. **Fix the root cause**, not the symptom. Ask "why?" until you reach something that is actually wrong (a wrong assumption, a missing check, a race), not just where it crashed.
6. **Verify**: the original reproduction now passes, add a regression test, and run the surrounding test suite.

## Rules
- Change one thing at a time.
- Do not guess-and-patch (adding try/except, null checks, retries or sleeps) to make an error disappear without understanding it.
- Remove temporary debug logging before finishing.
- If the fix is risky or the root cause is outside the code (data, infra, third party), explain and propose options instead of forcing a change.

## Output format
```
## Problem
What fails, how to reproduce.

## Root cause
What is actually wrong and why, with the evidence.

## Fix
What changed and why it addresses the cause.

## Verification
Commands run and results; regression test added.
```

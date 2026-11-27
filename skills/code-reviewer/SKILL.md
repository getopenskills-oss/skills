---
name: code-reviewer
description: Review a code diff or file for bugs, security issues, performance problems, and readability, and return prioritized, actionable findings. Use when the user asks for a code review, PR review, or "check my code".
---

# Code Reviewer

## When to use
- The user asks to review a diff, pull request, file, or function.
- The user asks "is this correct?", "any bugs?", or "can this be improved?".

## Process
1. **Understand intent.** Read the PR description, commit message, or ask what the change is meant to do.
2. **Read the whole change** before commenting, including tests.
3. **Trace the risky paths**: error handling, null/empty inputs, concurrency, boundaries (off-by-one, limits), and anything touching auth, money, or user data.
4. **Check each finding** — be able to describe concrete input that triggers it. Drop anything you cannot justify.

## What to look for (in priority order)
1. **Correctness** — logic errors, unhandled cases, broken contracts.
2. **Security** — injection, missing auth checks, secrets in code, unsafe deserialization, XSS.
3. **Data safety** — migrations, irreversible deletes, race conditions.
4. **Performance** — N+1 queries, unbounded loops or memory, missing indexes.
5. **Maintainability** — unclear names, duplication, dead code, missing tests for new behavior.

## Output format
```
## Summary
One paragraph: what the change does and overall verdict.

## Findings
### 🔴 Must fix
- `path/file.ts:42` — Problem. Why it matters. Suggested fix.
### 🟡 Should fix
### 🔵 Nit
```

## Rules
- Point to exact lines. Suggest a fix, not just a complaint.
- Do not pad the review with style nits when there are real bugs.
- If the change looks good, say so plainly.

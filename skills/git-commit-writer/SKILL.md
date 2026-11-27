---
name: git-commit-writer
description: "Write clear git commit messages from a diff or a description of the change, following Conventional Commits. Use when the user asks for a commit message, to commit changes, or to clean up commit history wording."
---

# Git Commit Writer

## When to use
- The user asks for a commit message, or asks you to commit staged changes.
- The user pastes a diff and asks "what should I call this?".

## Process
1. **Read the actual change.** Run `git diff --staged` (or `git diff` if nothing is staged). Never describe a change you have not seen.
2. **Find the one reason** the change exists. If the diff mixes unrelated changes (a fix plus a refactor plus a dependency bump), suggest splitting it and say how.
3. **Pick the type**: `feat` (new behavior for users), `fix` (bug fix), `refactor` (no behavior change), `perf`, `docs`, `test`, `build`, `ci`, `chore`, `style`.
4. **Pick a scope** only if the project already uses scopes (check `git log --oneline -20`). Match the existing style.
5. **Write the message.**

## Format
```
<type>(<scope>): <summary in imperative mood, ≤ 72 chars, no period>

<body: why the change was needed and what it changes, wrapped at 72 chars>

<footer: BREAKING CHANGE: …, Fixes #123, Co-authored-by: …>
```

## Rules
- Summary in the imperative: "add", "fix", "remove" — not "added" or "adds".
- Say *why* in the body; the diff already shows *what*.
- Mark breaking changes with `!` after the type (`feat(api)!: …`) **and** a `BREAKING CHANGE:` footer explaining the migration.
- Do not invent issue numbers, co-authors, or ticket IDs.
- Skip the body for trivial changes (typos, formatting).

## Example
```
fix(auth): refresh expired session before retrying the request

Requests made right after a session expired failed with 401 because the
retry reused the old token. Refresh the token once and retry; give up
after a second 401 so a revoked session still signs the user out.

Fixes #412
```

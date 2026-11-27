---
name: changelog-writer
description: "Write user-facing release notes and CHANGELOG entries from commits, merged pull requests, or a diff between versions, grouped by impact. Use when the user prepares a release, asks for release notes, or wants to update CHANGELOG.md."
---

# Changelog Writer

## When to use
- Preparing a release; "write release notes", "update the CHANGELOG".

## Process
1. **Collect the changes since the last release**: `git log <last-tag>..HEAD --oneline`, merged PR titles and descriptions, or the issue tracker.
2. **Drop internal noise**: refactors, CI, formatting, dependency bumps with no user impact (unless security-related).
3. **Translate each change into user impact** — what users can now do, or what is fixed — in plain language.
4. **Group** under: Breaking changes, Added, Changed, Fixed, Security, Deprecated, Removed.
5. **Add upgrade instructions** for every breaking change.

## Format (Keep a Changelog)
```
## [1.4.0] - 2026-11-27

### ⚠️ Breaking changes
- `config.timeout` is now in seconds instead of milliseconds. Divide existing values by 1000.

### Added
- Export reports as CSV (#231).

### Fixed
- Dates no longer shift by one day for users west of UTC (#240).

### Security
- Updated `libfoo` to 2.3.1 to fix CVE-2026-1234.
```

## Rules
- Write for users, not for the team: "Search now finds partial words", not "refactor tokenizer".
- Lead with what matters most to users; breaking changes always first.
- Reference PRs or issues when the project does; never invent numbers or credit.
- Use the version scheme the project already uses (check existing tags); suggest semver bumps: breaking → major, feature → minor, fix → patch.
- Keep each entry to one line where possible.

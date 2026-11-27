---
name: regex-builder
description: "Build, explain and test regular expressions for matching, validating, extracting or replacing text, with clear breakdowns and test cases for each flavor (JavaScript, Python, PCRE, grep). Use when the user needs a regex or asks what a regex does."
---

# Regex Builder

## When to use
- "Write a regex that matches…", "extract X from these lines", "what does this regex mean?"

## Process
1. **Clarify the flavor and context**: JavaScript, Python `re`, PCRE, Go RE2, POSIX grep/sed; full-string validation vs. search inside text; single-line vs. multiline input.
2. **Collect examples**: at least 3 strings that must match and 3 that must not, including edge cases.
3. **Build the pattern incrementally**, anchoring with `^…$` for validation.
4. **Test it** against all examples (run code when possible) and show the results.
5. **Explain** it token by token.

## Good practices
- Prefer specific character classes over `.*`; use lazy quantifiers (`.*?`) only when needed.
- Use non-capturing groups `(?:…)` unless you need the capture; name important captures (`(?<year>\d{4})`).
- Escape literal special characters: `. * + ? ( ) [ ] { } ^ $ | \ /`.
- Use the `x`/verbose flag (where supported) to comment complex patterns.
- Watch for catastrophic backtracking: avoid nested quantifiers like `(a+)+` on untrusted input; RE2 (Go) and Rust do not backtrack but lack lookarounds and backreferences.

## Know when not to use regex
- Parsing HTML, JSON, or programming languages → use a real parser.
- Email/URL validation → use a well-tested library or a deliberately permissive pattern plus a confirmation step.
- Dates → validate format with regex, then parse to check the real date.

## Output format
````
Pattern: `^(?<year>\d{4})-(?<month>0[1-9]|1[0-2])-(?<day>0[1-9]|[12]\d|3[01])$`
Flavor: JavaScript (ES2018+)

Breakdown:
- `^` start of string
- …

Tests:
| Input | Expected | Result |
| 2026-11-27 | match | ✅ |
| 2026-13-01 | no match | ✅ |

Usage:
```js
const m = input.match(re); m?.groups.year
```
````

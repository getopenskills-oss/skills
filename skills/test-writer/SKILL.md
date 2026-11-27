---
name: test-writer
description: "Write focused unit and integration tests for existing code using the project's own test framework and conventions. Use when the user asks to add tests, improve coverage, or write a failing test for a bug."
---

# Test Writer

## When to use
- "Add tests for this function / module / endpoint."
- "Write a test that reproduces this bug."
- Coverage is low around code the user is about to change.

## Process
1. **Learn the project's testing setup first.** Find the framework (look at `package.json`, `pyproject.toml`, `go.mod`, existing `*_test.*` / `*.test.*` files) and copy the style of the nearest existing test file: imports, fixtures, naming, assertion library.
2. **Read the code under test** and list its behaviors: normal results, edge cases, error paths, side effects.
3. **Choose cases** (prefer few meaningful tests over many shallow ones):
   - the main happy path,
   - boundaries: empty, zero, one, max, off-by-one, unicode, very long input,
   - invalid input and the error it must raise,
   - every branch that guards money, auth, data loss or security.
4. **Write the tests**, then **run them**. A test that never ran is not done.
5. For a bug: write the test first, confirm it **fails** for the right reason, then fix the code and confirm it passes.

## Rules
- Test behavior through the public interface, not private internals.
- One reason to fail per test; name it after the behavior (`returns_empty_list_when_no_matches`).
- Arrange → Act → Assert, with no logic (loops/ifs) inside assertions.
- Mock only what is slow, random, or external (network, clock, filesystem). Do not mock the code under test.
- Make tests deterministic: fix seeds, freeze time, avoid sleeps.
- Never weaken or delete an existing test just to make it pass. If a test really must change, explain the reason to the user.

## Output
- The test file(s), placed where the project keeps tests.
- The command you ran and its result (pass/fail counts).
- Any behavior you found that looks like a bug, reported separately — do not silently "fix" it in the test.

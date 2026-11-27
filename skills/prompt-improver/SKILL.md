---
name: prompt-improver
description: "Rewrite a prompt for an AI model so it is clear, specific and reliable: role, task, context, constraints, output format, and examples. Use when the user's prompt gives inconsistent or poor results, or they ask to write or improve a system prompt."
---

# Prompt Improver

## When to use
- "Improve this prompt", "write a system prompt for…", "the model keeps doing X".

## Process
1. **Understand the job**: what input the prompt receives, what a perfect output looks like, and how outputs currently fail. Ask for 2–3 real examples of bad outputs if available.
2. **Diagnose** the original prompt: vague task, missing context, conflicting instructions, no output format, rules buried at the end, or examples that bias the model.
3. **Rewrite** with this structure (omit what does not apply):
   - **Context**: who the output is for and why.
   - **Task**: one clear instruction; say what to do, not only what to avoid.
   - **Inputs**: clearly delimited (e.g. XML tags `<document>…</document>`).
   - **Constraints**: length, tone, must/must-not, how to handle missing information ("say you don't know").
   - **Output format**: exact structure, or a schema for JSON.
   - **Examples**: 1–3 diverse ones when format or style matters.
4. **Test** the new prompt on the real examples, including edge cases, and compare against the old one.

## Rules
- Prefer explaining the reason behind a rule; models generalize from reasons better than from ALL-CAPS commands.
- Remove contradictions and duplicated instructions.
- Keep it as short as possible while still specific.
- Ask for step-by-step reasoning only when the task needs it, and separate reasoning from the final answer.
- Never claim a prompt is "guaranteed" to work — show the test results.

## Output format
1. **Diagnosis** — what was wrong (bullets).
2. **Improved prompt** — in a code block, ready to paste.
3. **What changed and why** — short.
4. **How to test** — inputs to try.

---
name: meeting-notes
description: Turn a meeting transcript or rough notes into a concise summary with decisions, action items (owner and due date), and open questions. Use when the user shares a transcript, recording notes, or asks to summarize a meeting.
---

# Meeting Notes

## When to use
- The user pastes a transcript, chat log, or rough notes from a meeting.
- The user asks "what did we decide?" or "summarize this call".

## Process
1. Identify the meeting title, date, and attendees (if present).
2. Read the full transcript once before writing anything.
3. Extract **decisions** — things the group agreed on, not just discussed.
4. Extract **action items** — each needs an owner and, if mentioned, a due date. If the owner is unclear, write `Owner: unassigned`.
5. Extract **open questions** — raised but not resolved.
6. Write a short summary of the discussion for people who were not there.

## Output format
```
# <Meeting title> — <date>
**Attendees:** …

## Summary
3–5 sentences.

## Decisions
- …

## Action items
| # | Task | Owner | Due |
|---|------|-------|-----|

## Open questions
- …
```

## Rules
- Do not attribute statements or tasks to someone unless the transcript supports it.
- Do not invent due dates.
- Keep the user's language; keep names exactly as written.

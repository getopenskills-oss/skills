---
name: document-summarizer
description: "Summarize long documents, reports, papers, contracts or threads into the format the reader needs \u2014 TL;DR, key points, decisions, numbers, and open questions \u2014 with references back to the source. Use when the user asks to summarize, condense, or get the key points of a text."
---

# Document Summarizer

## When to use
- "Summarize this", "TL;DR", "what are the key points?", "what do I need to know from this report?"

## Process
1. **Ask (or infer) the purpose**: deciding something, briefing a boss, studying, reviewing a contract. The purpose decides what to keep.
2. **Read the whole document** before writing. Note the structure, the main claim, the evidence, and any numbers, dates, obligations or decisions.
3. **Write the summary** at the requested length (default: about 10% of the original, max one page).
4. **Check faithfulness**: every statement in the summary must be supported by the document. Keep the author's uncertainty ("may", "preliminary") — do not upgrade it into certainty.

## Output format
```
## TL;DR
2–3 sentences.

## Key points
- Point (section / page reference)

## Numbers and dates
- …

## Decisions, obligations, or action items
- Who — what — by when

## Open questions / caveats
- What the document does not answer, or where it is weak
```
Adapt the sections to the document type: for research papers include method and limitations; for contracts include parties, term, payment, termination, liability and unusual clauses; for meeting threads include decisions and owners.

## Rules
- Do not add facts, opinions, or conclusions that are not in the source; label any of your own commentary separately.
- Quote exact wording for anything legally or financially important.
- If the document is incomplete or unreadable in parts, say which parts.
- For contracts and legal or medical documents, add a note that the summary is not professional advice.

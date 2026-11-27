---
name: deep-research
description: Research a question across many sources and deliver a structured, cited report. Use when the user asks to research, investigate, compare options, or analyze a topic in depth.
---

# Deep Research

## When to use
- The user asks to "research", "investigate", "look into", or "compare" something.
- The answer needs more than one source, or the facts may have changed recently.

## Process
1. **Clarify the question.** Restate it in one sentence. If scope, timeframe, or audience is ambiguous and it changes the answer, ask one short question first.
2. **Break it down.** Split the question into 3–6 sub-questions that together answer it.
3. **Search widely.** For each sub-question, consult several independent sources. Prefer primary sources (official docs, papers, filings, datasets) over summaries.
4. **Cross-check.** A claim that matters needs two independent sources. Note where sources disagree and why.
5. **Track dates.** Record the publication date of every source; flag anything that may be outdated.
6. **Synthesize.** Answer the question — do not just list what each source said.

## Output format
```
# <Title>

## TL;DR
3–5 bullet points with the direct answer.

## Findings
### <Sub-question 1>
Narrative answer with inline citations [1][2].

## Disagreements & uncertainty
Where sources conflict, and how confident you are.

## Sources
[1] Title — Publisher, date. URL
```

## Rules
- Never invent a source, quote, or statistic. If you could not verify it, say so.
- Separate facts from your own interpretation.
- Keep quotes short; paraphrase instead.

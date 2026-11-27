---
name: user-interview-synthesis
description: "Turn user interview notes or transcripts into evidence-backed insights: themes, pains, jobs-to-be-done, quotes, and recommendations with how strongly the evidence supports each. Use when the user has customer or user interviews to analyze, or asks what users really need."
---

# User Interview Synthesis

## When to use
- After customer discovery or usability interviews: "what did we learn?", "synthesize these notes".

## Process
1. **Gather the raw material** — notes or transcripts, plus who each participant is (segment, role, usage level). Keep participants anonymous in the output (P1, P2…).
2. **Extract observations** per interview: what they did, said, felt, and the workaround they use. Separate *behavior* ("exports to Excel every Friday") from *opinion* ("I'd love dark mode").
3. **Cluster** observations into themes (affinity mapping). A theme needs evidence from several participants.
4. **Frame insights**: "*Segment* struggles to *do job* because *reason*, so they *workaround*." Include the jobs-to-be-done and the trigger moments.
5. **Rate evidence strength**: how many participants, which segments, behavior vs. stated opinion.
6. **Recommend** what to build, test, or research next.

## Rules
- Quote participants verbatim for every key insight; never invent or "clean up" quotes so they mean something else.
- Note contradictions and outliers instead of hiding them.
- Five interviews show patterns, not percentages — avoid "60% of users".
- Feature requests are clues to underlying problems; report the problem first.
- Flag leading questions or biased samples if you notice them in the transcripts.

## Output format
```
## Summary
3–5 most important insights in one paragraph.

## Insights
### 1. Insight statement
- Evidence: P1, P3, P4 (behavior) · P2 (opinion)
- Quotes: "…" — P3
- Implication: …

## Jobs to be done
## Open questions
## Recommended next steps
```

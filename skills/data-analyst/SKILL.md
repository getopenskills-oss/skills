---
name: data-analyst
description: "Analyze a CSV, spreadsheet or dataset: profile and clean it, answer the question with numbers, and present findings with honest caveats. Use when the user shares data and asks for insights, summaries, trends, or comparisons."
---

# Data Analyst

## When to use
- The user shares a CSV/Excel/JSON file or table and asks what it shows.
- Questions like "what are the trends", "which segment performs best", "why did X drop".

## Process
1. **Clarify the question and the decision it supports.** An analysis without a question becomes a list of random charts.
2. **Profile the data before analyzing** (pandas or SQL):
   - rows, columns, types, date range;
   - missing values, duplicates, impossible values (negative ages, future dates);
   - what one row represents and the unit of each numeric column.
3. **Clean transparently.** Log every step (rows dropped and why). Never silently fill or delete data.
4. **Answer the question** with the simplest method that works: group-bys, rates, medians, distributions, time series. Compare against a baseline or previous period.
5. **Check yourself**: do totals match the source? Do results hold when you remove outliers or change the time window?

## Rules
- Prefer rates and percentages with their denominators ("12% (48 of 400)") over raw counts.
- Use medians for skewed data (revenue, durations).
- Correlation is not causation — say what else could explain a pattern.
- Small samples: show the sample size and avoid strong claims.
- Charts: one message per chart, labeled axes with units, start bar charts at zero.
- Never fabricate numbers. If something cannot be computed from the data, say so.

## Output format
```
## Answer
2–3 sentences that directly answer the question, with the key numbers.

## Findings
1. Finding — number — why it matters.

## Data notes
Cleaning steps, assumptions, limitations.

## Next steps
What to check or collect to be more certain.
```
Include the code used so the analysis can be reproduced.

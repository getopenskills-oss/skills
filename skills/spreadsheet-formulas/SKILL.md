---
name: spreadsheet-formulas
description: "Write and debug Excel and Google Sheets formulas \u2014 lookups, conditional sums, date math, text cleanup, dynamic arrays and pivot-style summaries \u2014 with explanations. Use when the user asks for a spreadsheet formula or why a formula returns an error."
---

# Spreadsheet Formulas

## When to use
- "What formula do I need to…", "my VLOOKUP returns #N/A", "sum by month and category".

## Process
1. **Confirm the app and version**: Excel 365 (dynamic arrays, `XLOOKUP`, `LET`, `LAMBDA`), older Excel, or Google Sheets (`QUERY`, `ARRAYFORMULA`, `FILTER`). Also the locale: some use `;` instead of `,` as the argument separator.
2. **Understand the layout**: sheet names, header row, which columns hold what, whether data is a table (`Table1[Amount]`).
3. **Write the formula**, preferring modern, readable functions.
4. **Explain** each part and say where to put it and how to fill it down or across.
5. **Test** on a few rows mentally or with sample data; mention edge cases (blanks, text numbers, duplicates).

## Go-to patterns
- Lookup: `=XLOOKUP(A2, Products[SKU], Products[Price], "not found")`; legacy: `=INDEX(C:C, MATCH(A2, A:A, 0))`.
- Conditional totals: `=SUMIFS(Amount, Category, "Food", Date, ">="&DATE(2026,1,1))`, `COUNTIFS`, `AVERAGEIFS`.
- Filter and sort (365 / Sheets): `=SORT(FILTER(A2:D100, D2:D100>1000), 4, -1)`.
- Unique list with totals: `=UNIQUE(B2:B100)` next to `=SUMIFS(C:C, B:B, F2)`.
- Readability: `=LET(sales, C2:C100, tax, 0.11, SUM(sales) * (1 + tax))`.
- Dates: `=EOMONTH(A2, 0)`, `=NETWORKDAYS(start, end, holidays)`, `=TEXT(A2, "yyyy-mm")`.
- Text cleanup: `=TRIM(CLEAN(A2))`, `=PROPER(A2)`, `=TEXTSPLIT(A2, ",")`, `=VALUE(SUBSTITUTE(A2, ".", ""))`.
- Errors: wrap only expected ones — `=IFERROR(XLOOKUP(…), "")` hides real problems if overused.

## Debugging checklist
- `#N/A`: lookup value not found — extra spaces, numbers stored as text, wrong range.
- `#VALUE!`: text where a number is expected.
- `#REF!`: deleted cells or ranges.
- `#SPILL!`: something blocks a dynamic array's output range.
- Wrong totals: absolute vs. relative references (`$A$2`), hidden rows, duplicates.

## Rules
- Prefer structured references or named ranges over whole-column references in big sheets.
- Suggest a pivot table when a summary would need many formulas.

---
name: sql-writer
description: "Write correct, readable and efficient SQL from a plain-language question, using the real schema. Explains the query and checks it for performance and safety. Use when the user asks for a SQL query, a report, or help with a slow query."
---

# SQL Writer

## When to use
- "Write a query that shows…", "how many…", "top 10…" against a database.
- A query is slow or returns wrong numbers.

## Process
1. **Get the real schema.** Ask for or inspect table definitions (`\d table` in psql, `SHOW CREATE TABLE`, information_schema, migrations). Never guess column names.
2. **Confirm the dialect** (PostgreSQL, MySQL, SQLite, BigQuery, Snowflake, SQL Server); syntax for dates, limits, and JSON differs.
3. **Restate the question precisely**: what is one row of the result, which time range and time zone, how to treat nulls, duplicates and deleted records.
4. **Write the query** in readable steps — use CTEs (`WITH …`) for each logical step.
5. **Sanity-check the result**: row counts before and after joins, totals against a known number, a few rows by hand.

## Correctness checklist
- Joins: is the join key unique on one side? If not, rows (and sums) multiply.
- `COUNT(*)` vs `COUNT(DISTINCT id)`; `NULL` in `NOT IN` returns nothing — prefer `NOT EXISTS`.
- Integer division (`1/2 = 0`) — cast before dividing.
- Time zones and half-open ranges: `created_at >= '2026-01-01' AND created_at < '2026-02-01'`.

## Performance checklist
- Filter early; select only needed columns (no `SELECT *` in production code).
- Make filters sargable: `col >= x` rather than `func(col) = x`.
- Check the plan with `EXPLAIN (ANALYZE)` and suggest indexes for frequent filters and joins.

## Safety rules
- Default to read-only queries. For `UPDATE`/`DELETE`, first show a `SELECT` with the same `WHERE`, wrap in a transaction, and never omit the `WHERE`.
- Use parameters (`$1`, `?`) in application code — never string-concatenate user input.

## Output
The query, a short explanation of each step, assumptions made, and how to verify the result.

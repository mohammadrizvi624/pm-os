---
name: sql-query
description: "Translate a business question into an optimized SQL query against a described schema — BigQuery, PostgreSQL, MySQL, Snowflake, and others — with an explanation and a way to validate it. Use when writing SQL, pulling a data report, or turning a metric question into a query."
---
# SQL query

Turns a plain-language data question into a correct, readable SQL query for the user's warehouse, with the logic explained so they can trust and adapt it.

## Inputs
- The question and the schema (uploaded SQL/DDL, docs, or a described set of tables/columns/relationships). Read attached files first. Confirm the **SQL dialect** (BigQuery / PostgreSQL / MySQL / Snowflake / SQL Server) and any filters, grain, or time range.

## Load company context
Read `./company-context/07-tools-stack.md` (warehouse/dialect and known tables) where relevant.

## Method
1. Map the question to the schema: tables, join keys, the grain of the answer, and the time window.
2. Write efficient, commented SQL in the confirmed dialect; prefer clear CTEs over nested subqueries.
3. Note performance considerations for large data (partition/date filters, indexes, avoiding needless scans); offer an alternative approach if relevant.
4. Explain the query in plain English and say how to **validate** it (a row-count or spot-check), since a query that runs isn't necessarily correct.

## Output
- The query (commented), a plain-English explanation, performance notes, and a validation check. Save to `./outputs/` if substantial; offer a test-data script on request.

## Avoid
- Guessing column/table names — ask or state the assumption when the schema is unclear.
- Returning a query with no explanation or validation step.

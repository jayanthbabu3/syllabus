# SQL Syllabus

A complete, structured learning path for SQL — from your first `SELECT` to writing production-grade queries with joins, transactions, schema design, indexing, and analytical patterns.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 8-12 Weeks](https://img.shields.io/badge/Duration-8--12%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![SQL: ANSI + PostgreSQL](https://img.shields.io/badge/SQL-ANSI%20%2B%20PostgreSQL-336791)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started & Relational Thinking](#phase-1-getting-started--relational-thinking)
- [Phase 2: SELECT, Filtering & Sorting](#phase-2-select-filtering--sorting)
- [Phase 3: Expressions, Functions & NULL Handling](#phase-3-expressions-functions--null-handling)
- [Phase 4: Aggregation & Grouping](#phase-4-aggregation--grouping)
- [Phase 5: Joins & Set Operations](#phase-5-joins--set-operations)
- [Phase 6: Subqueries, CTEs & Window Functions](#phase-6-subqueries-ctes--window-functions)
- [Phase 7: Schema Design, DDL & Constraints](#phase-7-schema-design-ddl--constraints)
- [Phase 8: INSERT, UPDATE, DELETE & Transactions](#phase-8-insert-update-delete--transactions)
- [Phase 9: Indexes, Query Plans & Performance](#phase-9-indexes-query-plans--performance)
- [Phase 10: Advanced SQL & Real-World Analytics](#phase-10-advanced-sql--real-world-analytics)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> SQL is not a general-purpose programming language in the same way as Python or JavaScript. It is a **declarative language** for working with relational data. This syllabus teaches ANSI-style SQL first, using PostgreSQL-like examples when dialect details matter.

- No prior programming experience required
- A database to practice with ([PostgreSQL](https://www.postgresql.org/download/) recommended)
- A GUI client like [DBeaver](https://dbeaver.io/) or `psql` / `mysql` command line access
- Patience for thinking carefully about data shape and query intent

---

## Phase 1: Getting Started & Relational Thinking

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Learn what a relational database is and how SQL fits into it.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is SQL | A language for defining, querying, and manipulating relational data |
| 2 | Tables, Rows, Columns | The core mental model of relational databases |
| 3 | Primary Keys | Unique row identity and why it matters |
| 4 | Relationships | One-to-one, one-to-many, many-to-many |
| 5 | Database vs Schema vs Table | How data is organized |
| 6 | SQL Dialects | ANSI SQL vs PostgreSQL, MySQL, SQLite, SQL Server differences |
| 7 | Practice Environment | Connecting to a database and running your first query |

> [!TIP]
> SQL becomes easier when you think in sets of rows, not step-by-step loops. The database is good at operating on collections all at once.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Connect to a database and run a simple query
- [ ] Explain table, row, column, and primary key
- [ ] Describe the difference between SQL dialects at a high level

</details>

---

## Phase 2: SELECT, Filtering & Sorting

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Read data correctly before trying to design or optimize anything.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `SELECT` Basics | Choosing columns and understanding result sets |
| 2 | `WHERE` | Filtering rows with exact matches and conditions |
| 3 | Comparison Operators | `=`, `<>`, `<`, `>`, `<=`, `>=` |
| 4 | Logical Operators | `AND`, `OR`, `NOT` and grouping conditions |
| 5 | Pattern Matching | `LIKE`, wildcards, and text filters |
| 6 | `ORDER BY` | Sorting ascending, descending, multi-column |
| 7 | `LIMIT` / `OFFSET` | Restricting output and simple pagination |
| 8 | Aliases | Cleaner output and more readable queries |

> [!IMPORTANT]
> `SELECT *` is fine for exploration, but it is a bad habit in production code. Ask for the columns you actually need.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Filter rows using `WHERE`, `AND`, and `OR`
- [ ] Sort and limit results predictably
- [ ] Explain why explicit column lists are better than `SELECT *`

</details>

---

## Phase 3: Expressions, Functions & NULL Handling

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how SQL transforms and computes values.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Arithmetic Expressions | Derived columns and numeric calculations |
| 2 | String Functions | Concatenation, trimming, casing, substring operations |
| 3 | Date/Time Functions | Filtering and transforming temporal data |
| 4 | `CASE` Expressions | Conditional logic inside queries |
| 5 | `NULL` Semantics | Why `NULL` is not the same as zero or an empty string |
| 6 | `COALESCE` | Replacing nulls intentionally |
| 7 | Type Casting | Explicit conversion between data types |
| 8 | Boolean Logic Pitfalls | Three-valued logic and unexpected query behavior |

> [!CAUTION]
> `NULL = NULL` is not true in SQL. Use `IS NULL` and `IS NOT NULL` when testing null values.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `CASE` to create derived output
- [ ] Handle missing values with `COALESCE`
- [ ] Explain why `NULL` behaves differently from normal values

</details>

---

## Phase 4: Aggregation & Grouping

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Summarize data accurately and avoid classic grouping mistakes.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Aggregate Functions | `COUNT`, `SUM`, `AVG`, `MIN`, `MAX` |
| 2 | `GROUP BY` | Turning raw rows into summary tables |
| 3 | `HAVING` | Filtering after aggregation |
| 4 | Distinct Counts | `COUNT(DISTINCT ...)` and uniqueness questions |
| 5 | Grouping by Multiple Columns | Dimensional summaries and rollups of meaning |
| 6 | Aggregate Null Behavior | How missing values affect summary functions |
| 7 | Common Grouping Errors | Mixing non-grouped columns improperly |
| 8 | Reporting Queries | Building totals, category summaries, and dashboards |

> [!IMPORTANT]
> Learn the logical order of query processing. `WHERE` filters rows before grouping; `HAVING` filters grouped results after aggregation.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Summarize data with `GROUP BY` and aggregates
- [ ] Explain the difference between `WHERE` and `HAVING`
- [ ] Write a query that groups by more than one dimension

</details>

---

## Phase 5: Joins & Set Operations

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn to combine related tables without creating incorrect results.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Inner Joins | Matching related rows across tables |
| 2 | Left / Right Joins | Keeping unmatched rows from one side |
| 3 | Full Outer Join | Combining both sides including non-matches |
| 4 | Self Joins | Relating a table to itself |
| 5 | Join Conditions | Using keys correctly to avoid accidental cross joins |
| 6 | Many-to-Many Relationships | Junction tables and linking entities |
| 7 | `UNION`, `UNION ALL`, `INTERSECT`, `EXCEPT` | Combining result sets |
| 8 | Duplicate Explosion | Why bad joins produce the wrong counts and totals |

> [!WARNING]
> Most SQL bugs in reporting come from joins that multiply rows unexpectedly. Always understand the cardinality of each relationship before aggregating.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write inner and left joins confidently
- [ ] Explain when a junction table is needed
- [ ] Diagnose a duplicate-row problem caused by a join

</details>

---

## Phase 6: Subqueries, CTEs & Window Functions

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Move from basic retrieval to analytical SQL.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Scalar Subqueries | Using one query inside another expression |
| 2 | Correlated Subqueries | Row-by-row dependent logic and when to avoid it |
| 3 | `EXISTS` / `NOT EXISTS` | Efficient presence checks |
| 4 | Common Table Expressions | `WITH` clauses for readable multi-step queries |
| 5 | Recursive CTEs | Hierarchies and graph-like traversal |
| 6 | Window Functions | `ROW_NUMBER`, `RANK`, running totals, partitions |
| 7 | Partitioning Concepts | `OVER (PARTITION BY ...)` and ordered calculations |
| 8 | Query Readability | Breaking complex logic into understandable pieces |

> [!TIP]
> Window functions are one of the biggest jumps in SQL skill. They let you analyze rows relative to other rows without collapsing everything into one aggregate.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use a CTE to simplify a complex query
- [ ] Write a running total with a window function
- [ ] Explain the difference between aggregation and window functions

</details>

---

## Phase 7: Schema Design, DDL & Constraints

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn how good data models prevent bad data and simplify future queries.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `CREATE TABLE` | Defining columns and data types |
| 2 | Primary Keys | Natural vs surrogate keys |
| 3 | Foreign Keys | Enforcing relationships between tables |
| 4 | Constraints | `NOT NULL`, `UNIQUE`, `CHECK`, defaults |
| 5 | Normalization | 1NF, 2NF, 3NF and practical tradeoffs |
| 6 | Schema Evolution | `ALTER TABLE`, migrations, backward-compatible changes |
| 7 | Views | Reusable query layers and access simplification |
| 8 | Naming Conventions | Designing schemas other humans can understand |

> [!IMPORTANT]
> A good schema is defensive programming for data. Constraints catch problems at the database boundary instead of after bad data spreads.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a normalized schema with keys and constraints
- [ ] Explain why foreign keys matter
- [ ] Evolve a schema without breaking existing data

</details>

---

## Phase 8: INSERT, UPDATE, DELETE & Transactions

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Safely change data without corrupting it.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `INSERT` | Creating rows safely and intentionally |
| 2 | `UPDATE` | Modifying only the rows you mean to touch |
| 3 | `DELETE` | Removing data carefully and reversibly where possible |
| 4 | `RETURNING` / Output Features | Seeing changed data immediately in supporting dialects |
| 5 | Transactions | `BEGIN`, `COMMIT`, `ROLLBACK` and atomic changes |
| 6 | Isolation Concepts | Dirty reads, lost updates, concurrency basics |
| 7 | Upserts | `INSERT ... ON CONFLICT` or dialect equivalents |
| 8 | Bulk Loads | Importing data and validating it during ingest |

> [!CAUTION]
> `UPDATE` or `DELETE` without a `WHERE` clause is one of the most expensive mistakes in SQL. Slow down before you run write queries.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Insert, update, and delete rows correctly
- [ ] Use a transaction for a multi-step operation
- [ ] Explain what rollback protects you from

</details>

---

## Phase 9: Indexes, Query Plans & Performance

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn why some queries are instant and others are painfully slow.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Index Basics | How indexes speed lookups and what they cost |
| 2 | B-tree Thinking | The common default index and common query shapes it helps |
| 3 | Composite Indexes | Multi-column access patterns and order matters |
| 4 | Query Plans | `EXPLAIN` / `EXPLAIN ANALYZE` and reading execution strategies |
| 5 | Full Table Scans vs Index Scans | When each happens and why |
| 6 | Sorting & Grouping Costs | Temporary sorts, memory, and large intermediate results |
| 7 | Query Rewrites | Making SQL more sargable and planner-friendly |
| 8 | Pragmatic Optimization | Fix schema, indexes, and query design before scaling hardware |

> [!TIP]
> Performance work should start with actual plans and timings, not guesses. Databases are optimized systems; intuition is often wrong.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add an index and measure the effect
- [ ] Read a basic query plan
- [ ] Identify one non-obvious cause of slow SQL

</details>

---

## Phase 10: Advanced SQL & Real-World Analytics

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Apply SQL to realistic product, reporting, and data workflows.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Analytical Patterns | Cohorts, retention, funnels, period-over-period comparisons |
| 2 | Deduplication | Canonical row selection with windows and ranking |
| 3 | Data Quality Checks | Finding anomalies, missing links, and constraint violations |
| 4 | Views & Materialized Views | Reusable query layers and performance tradeoffs |
| 5 | Access Control Concepts | Roles, permissions, and principle of least privilege |
| 6 | Partitioning Concepts | Large-table maintenance and time-based data organization |
| 7 | ETL-Friendly SQL | Cleaning, staging, and shaping raw data |
| 8 | SQL in Real Systems | App backends, BI dashboards, warehousing, and reporting jobs |

> [!TIP]
> Advanced SQL is less about obscure syntax and more about clarity: correct grain, correct joins, correct business definitions, and correct performance tradeoffs.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a multi-step analytical query with CTEs and windows
- [ ] Explain the "grain" of a result set
- [ ] Create a reusable reporting view or materialized view

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `=` with `NULL` | It does not behave like ordinary values | Use `IS NULL` / `IS NOT NULL` |
| 2 | Joining without understanding cardinality | Produces duplicate rows and incorrect totals | Check one-to-many vs one-to-one before aggregating |
| 3 | Using `SELECT *` in real code | Pulls unnecessary data and breaks easily as schemas change | Select explicit columns |
| 4 | Forgetting a `WHERE` on `UPDATE` / `DELETE` | Can modify or remove all rows | Preview with `SELECT` first, then write the change |
| 5 | Mixing grouped and non-grouped columns carelessly | Either errors out or expresses the wrong question | Match every selected non-aggregate column to the grouping |
| 6 | Assuming all dialects behave the same | Syntax and functions differ across systems | Learn the target database's dialect |
| 7 | Ignoring indexes | Large queries become slow at scale | Add indexes based on actual query patterns |
| 8 | Writing giant unreadable one-liners | Hard to verify and maintain | Use aliases, formatting, and CTEs |
| 9 | Treating the database like a spreadsheet | Weak schema design and poor constraints follow | Model relationships and constraints intentionally |
| 10 | Optimizing before measuring | Wastes time and may make queries worse | Use query plans and timing first |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is SQL used for?**
   - SQL is used to define, query, and modify data in relational databases.

2. **What is the difference between `WHERE` and `HAVING`?**
   - `WHERE` filters rows before grouping. `HAVING` filters groups after aggregation.

3. **What is a primary key?**
   - A column or set of columns that uniquely identifies each row in a table.

4. **What is the difference between `INNER JOIN` and `LEFT JOIN`?**
   - `INNER JOIN` returns only matching rows. `LEFT JOIN` keeps all rows from the left table even when no match exists on the right.

5. **Why is `NULL` special in SQL?**
   - `NULL` means missing or unknown, and it participates in SQL's three-valued logic instead of ordinary true/false comparisons.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What does normalization achieve?**
   - It reduces redundancy and update anomalies by structuring related data into well-defined tables.

2. **What is a window function?**
   - A function that computes values across a related set of rows without collapsing them into one grouped row.

3. **How do transactions help?**
   - They make multi-step changes atomic so either all changes succeed or none do.

4. **What is the difference between a subquery and a CTE?**
   - Both build on other queries, but CTEs often improve readability by naming intermediate steps explicitly.

5. **How would you diagnose a slow query?**
   - Inspect the execution plan, understand the row counts, review indexes, and confirm the query matches the intended data access pattern.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How do bad joins distort aggregate metrics?**
   - If one row on one side matches many rows on the other, counts and sums can multiply unless you aggregate at the correct grain.

2. **When would you use a materialized view?**
   - When a complex query is expensive and the result can be refreshed periodically rather than computed on every request.

3. **What makes a query "sargable"?**
   - The optimizer can use indexes effectively because predicates are written in a form compatible with indexed access, instead of wrapping indexed columns in functions or non-searchable expressions.

4. **How do indexes improve speed but hurt writes?**
   - Indexes speed reads by adding lookup structures, but inserts, updates, and deletes must also maintain those structures.

5. **How do you keep SQL maintainable in a codebase?**
   - Make query intent explicit, keep result grain clear, document assumptions, format consistently, and encapsulate repeated logic responsibly.

</details>

---

## Practice Projects

### Project 1: Query Playground
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A small practice database and a library of queries for filters, sorting, expressions, and null handling.

**Skills practiced:** `SELECT`, `WHERE`, expressions, aliases, data exploration.

---

### Project 2: Reporting Dashboard Queries
![Phase 4-6](https://img.shields.io/badge/After-Phase%204--6-yellow)

**What you'll build:** A set of business-style reports: top customers, monthly revenue, active users, running totals.

**Skills practiced:** Aggregates, joins, CTEs, window functions.

---

### Project 3: Relational Schema for an App
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** A schema for an e-commerce, school, or booking system with keys, constraints, inserts, and transactions.

**Skills practiced:** DDL, normalization, constraints, writes, transactional thinking.

---

### Project 4: Query Optimization Case Study
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** Take a slow query, inspect its plan, add indexes or rewrite it, and measure the improvement.

**Skills practiced:** `EXPLAIN`, indexing, performance reasoning.

---

### Project 5: Analytics Workbook
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A real-world analytics pack with cohort, funnel, retention, and anomaly-detection SQL.

**Skills practiced:** Everything from all phases — your SQL graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Strong official introduction to relational databases and SQL |
| [PostgreSQL: The SQL Language](https://www.postgresql.org/docs/current/sql.html) | Comprehensive official SQL reference and learning path |
| [MySQL Tutorial](https://dev.mysql.com/doc/refman/8.4/en/tutorial.html) | Official tutorial from the MySQL ecosystem |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [SQLBolt](https://sqlbolt.com/) | Interactive SQL lessons with immediate practice |
| [SQLZoo](https://sqlzoo.net/) | Huge range of guided SQL exercises and quizzes |
| [Mode SQL Tutorial](https://mode.com/sql-tutorial/) | Data-analysis-oriented SQL learning path |
| [HackerRank — SQL](https://www.hackerrank.com/domains/sql) | Structured challenge practice |

### Practice & Interview Prep

| Resource | Why Use It |
|----------|------------|
| [LeetCode Database Problems](https://leetcode.com/problemset/database/) | Good for interview-style SQL problem solving |
| [StrataScratch](https://www.stratascratch.com/) | Real interview-style data questions |

### Tools & Clients

| Tool | Why You Need It |
|------|----------------|
| [DBeaver](https://dbeaver.io/) | Popular universal database client |
| [pgAdmin](https://www.pgadmin.org/) | PostgreSQL GUI administration and querying |
| [PostgreSQL Downloads](https://www.postgresql.org/download/) | Official PostgreSQL installation page |
| [MySQL Shell / Tools](https://dev.mysql.com/downloads/) | Official MySQL tooling and downloads |

### Further Reading

| Resource | Format |
|----------|--------|
| [SQLZoo Reference](https://sqlzoo.net/wiki/SQL_Tutorial) | Step-by-step topic reference and practice |
| [PostgreSQL Window Functions](https://www.postgresql.org/docs/current/tutorial-window.html) | Focused official guide on a high-value advanced topic |

---

[Back to Main Syllabus](../README.md)

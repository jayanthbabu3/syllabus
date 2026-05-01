# SQL Syllabus

A complete, structured learning path for SQL — your one-stop guide from your very first `SELECT` to writing production-grade queries with joins, window functions, transactions, indexes, and analytical patterns. This is the language that runs the world's data: every backend job, every analytics dashboard, every ML feature store, every AI RAG pipeline. Learn it once, use it everywhere — for the rest of your career.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 15 Phases](https://img.shields.io/badge/Topics-15%20Phases-orange)
![PostgreSQL: 16+](https://img.shields.io/badge/PostgreSQL-16%2B-336791)

---

## Table of Contents

- [What is SQL?](#what-is-sql)
- [Why Learn SQL in 2026?](#why-learn-sql-in-2026)
- [How SQL Works](#how-sql-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Querying Basics](#phase-2-querying-basics)
- [Phase 3: Filtering & Operators](#phase-3-filtering--operators)
- [Phase 4: Joins](#phase-4-joins)
- [Phase 5: Aggregations & Grouping](#phase-5-aggregations--grouping)
- [Phase 6: Subqueries & CTEs](#phase-6-subqueries--ctes)
- [Phase 7: Window Functions](#phase-7-window-functions)
- [Phase 8: Data Modification](#phase-8-data-modification)
- [Phase 9: Schema Design & DDL](#phase-9-schema-design--ddl)
- [Phase 10: Indexes & Performance](#phase-10-indexes--performance)
- [Phase 11: Transactions & Concurrency](#phase-11-transactions--concurrency)
- [Phase 12: Advanced Postgres Features](#phase-12-advanced-postgres-features)
- [Phase 13: Modern SQL — Vectors, JSON, Time-Series & AI](#phase-13-modern-sql--vectors-json-time-series--ai)
- [Phase 14: The Database Ecosystem](#phase-14-the-database-ecosystem)
- [Phase 15: What's Next? (Specializations & Deploy)](#phase-15-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is SQL?

**SQL (Structured Query Language) is the standard, declarative language for working with relational databases.** It is how you ask a database for data ("show me every order placed last month"), how you change data ("mark this order shipped"), how you shape the database itself ("create a `users` table with these columns"), and how you control who is allowed to do any of that. Learn SQL once and you can talk to **PostgreSQL**, **MySQL**, **SQLite**, **SQL Server**, **Oracle**, **Snowflake**, **BigQuery**, **DuckDB**, **CockroachDB** — practically every serious data system on the planet.

SQL grew out of **Edgar F. Codd's 1970 paper** "A Relational Model of Data for Large Shared Data Banks" while he was at IBM. Codd's idea was radical at the time: store data as plain rows in plain tables, link tables by values (not pointers), and let users describe *what* they want — not *how* to get it. In **1974**, two IBM researchers, **Donald Chamberlin** and **Raymond Boyce**, designed a language to query Codd's relational model. They called it **SEQUEL** — Structured English Query Language. A trademark dispute later forced the name change to **SQL**. By **1986** SQL was an ANSI standard, and by the 1990s every database vendor on Earth had a SQL dialect. It is, by a wide margin, the most successful and longest-lived programming language in history.

In simple words:

- A **relational database** is a collection of **tables**. Each table is a grid: **columns** (typed fields) and **rows** (records).
- SQL is the language you use to **read** (`SELECT`), **change** (`INSERT`, `UPDATE`, `DELETE`), **define** (`CREATE`, `ALTER`, `DROP`), and **control** (`GRANT`, `REVOKE`) that data.
- SQL is **declarative** — you say what result you want; the database figures out how to fetch it efficiently.
- The same query, with tiny dialect tweaks, works across dozens of database engines.

### A Brief History

| Year | Milestone | What Changed |
|------|-----------|--------------|
| 1970 | Codd's relational model | E. F. Codd publishes the paper that founds the relational era. |
| 1974 | SEQUEL prototype | Chamberlin & Boyce build the first SQL-like language at IBM. |
| 1979 | First commercial SQL DB | Oracle ships the first commercial SQL relational database. |
| 1986 | ANSI SQL-86 | SQL becomes a US (ANSI) and international (ISO) standard. |
| 1992 | SQL-92 | Major revision — JOIN syntax, transactions, integrity constraints. The "modern" baseline. |
| 1995 | MySQL released | Open-source, web-friendly. Fuels the LAMP stack and most of the early web. |
| 1996 | PostgreSQL 6.0 | The descendant of Berkeley's POSTGRES becomes "PostgreSQL." Open source, standards-loving. |
| 2000 | SQLite released | Tiny, embedded, public-domain SQL. Now in every phone and browser on Earth. |
| 2003 | SQL:2003 | Window functions and `WITH` (CTE) standardized. Modern analytical SQL is born. |
| 2016 | SQL:2016 | JSON support, row pattern matching. SQL adapts to semi-structured data. |
| 2023 | SQL:2023 | Property graph queries, more JSON, multidimensional arrays. |
| 2024 | PostgreSQL 17 / pgvector everywhere | Postgres is now the default open-source database. pgvector turns it into a vector DB. |
| 2026 | The "Postgres-for-everything" era | OLTP, analytics, search, vectors, graphs — all on Postgres + extensions. |

> [!IMPORTANT]
> Every database engine has its own **dialect**. ~80% of SQL is identical everywhere; the other 20% (date functions, string syntax, upserts, JSON) varies. This syllabus defaults to **PostgreSQL 16+** — the modern open-source standard — and calls out MySQL/SQLite/SQL Server differences where they matter.

### What Makes a Relational Database

- **Tables** with strict columns and types — no surprises in your data.
- **Primary keys** that uniquely identify each row.
- **Foreign keys** that enforce relationships between tables.
- **Constraints** (`NOT NULL`, `UNIQUE`, `CHECK`) that the database itself enforces — your data stays correct even when buggy code tries to break it.
- **Transactions** with **ACID** guarantees — atomic, consistent, isolated, durable. The database does not lose your money.
- **A query optimizer** that turns your declarative SQL into the fastest physical plan it can find.
- **Indexes** that make billion-row queries return in milliseconds.

### The Big Five (and a few more)

| Database | License | Best For | Notes |
|----------|---------|----------|-------|
| **[PostgreSQL](https://www.postgresql.org/)** | Open source (PostgreSQL License) | Default new-project pick in 2026. OLTP, analytics, JSON, vectors, GIS | The "Swiss Army knife" of databases. Extensible, standards-loving. |
| **[MySQL](https://www.mysql.com/)** | Open source (GPL) | Classic web stack (LAMP), WordPress, large user bases | Owned by Oracle. MariaDB is the community fork. |
| **[SQLite](https://sqlite.org/)** | Public domain | Mobile apps, browsers, desktop apps, tests, prototypes | Single file, zero config. The most-deployed database in the world. |
| **[SQL Server](https://www.microsoft.com/en-us/sql-server)** | Commercial / Express free | Microsoft / .NET shops, enterprise BI | T-SQL dialect. Tight Azure integration. |
| **[Oracle Database](https://www.oracle.com/database/)** | Commercial | Banks, telcos, governments, anywhere very-old & very-rich | PL/SQL dialect. Still huge in finance. |
| **[MariaDB](https://mariadb.org/)** | Open source (GPL) | MySQL replacement | Drop-in fork of MySQL with an independent roadmap. |
| **[CockroachDB](https://www.cockroachlabs.com/) / [YugabyteDB](https://www.yugabyte.com/)** | Open source / commercial | Globally distributed Postgres-compatible | Spanner-style consistency at scale. |
| **[DuckDB](https://duckdb.org/)** | MIT | Analytics on local files (CSV / Parquet) | "SQLite for analytics." Embedded OLAP. |

---

## Why Learn SQL in 2026?

| Reason | What It Means |
|--------|---------------|
| **Every backend job needs it** | Whether you write Python, Java, Node, Go, Rust or .NET, your service eventually talks to a database. SQL is the lingua franca. |
| **#1 skill in data analysis** | Tableau, Power BI, Looker, Metabase, Mode, Hex — every analytics tool sits on top of SQL. Analysts who know SQL out-earn those who don't. |
| **AI / RAG runs on databases** | Modern LLM apps store embeddings in **pgvector** (Postgres) or vector DBs that all speak SQL-flavored APIs. Knowing SQL is a prerequisite for production AI. |
| **ML feature stores** | Feast, Tecton, Hopsworks — feature engineering for ML lives in SQL. Most production ML pipelines are 80% SQL. |
| **Cross-cutting forever skill** | Languages come and go. Frameworks come and go. SQL has lasted **50 years** and isn't going anywhere. Learn it once, use it always. |
| **Top of every tech-skills survey** | Stack Overflow's most-used database technology, year after year. Listed on more job postings than any single programming language. |
| **Salary impact** | Backend devs who can write fast queries and design schemas earn 10–25% more than those who can't. Data engineers and DBAs sit firmly in six-figure territory. |
| **Beginner-accessible** | A 10-line SQL query can do the work of 200 lines of Python. SQL pays off faster than almost any other technical skill. |

---

## How SQL Works

Understanding what happens when you press "Run" on a query makes everything easier. SQL is **declarative** — you describe the *result*, not the recipe. The database engine reads your text, plans an efficient way to fetch the data, executes the plan, and returns rows.

```
   ┌─────────────────────────────┐
   │  You write SQL              │  SELECT name FROM users WHERE id = 42;
   └────────────┬────────────────┘
                │
                ▼
   ┌─────────────────────────────┐
   │  Parser                     │  Lex + parse → abstract syntax tree
   │  (validates syntax & names) │  Catches "FORM" instead of "FROM"
   └────────────┬────────────────┘
                ▼
   ┌─────────────────────────────┐
   │  Planner / Optimizer        │  Considers many physical plans:
   │  (cost-based)               │   - seq scan vs index scan
   │                             │   - hash join vs merge join vs nested loop
   │                             │  Picks lowest estimated cost
   └────────────┬────────────────┘
                ▼
   ┌─────────────────────────────┐
   │  Execution Engine           │  Reads pages from disk / cache
   │                             │  Walks indexes, joins rows, filters
   └────────────┬────────────────┘
                ▼
   ┌─────────────────────────────┐
   │  Result Set                 │  Rows returned to your client
   └─────────────────────────────┘
```

**The core ideas:**

- **Declarative.** You write *what* you want; the optimizer decides *how*. Two equivalent queries can run in 10ms or 10s — the optimizer's choices and your indexes decide.
- **The optimizer.** A piece of software that turns your SQL into a *query plan* using statistics it keeps about your data. `EXPLAIN ANALYZE` lets you see the plan it picked. Reading plans is a senior-level superpower.
- **Indexes** are the database's "shortcut maps" — sorted, compact data structures that let the engine skip 99% of the rows. The right index turns minutes into milliseconds.
- **Transactions** group statements into atomic units. Either all succeed and persist, or none do. **ACID** = Atomic, Consistent, Isolated, Durable.
- **Concurrency** is solved by isolation levels and **MVCC** (multi-version concurrency control in Postgres). Many readers never block writers, and vice versa.

> [!TIP]
> Two queries that return the same rows can have wildly different performance. Always ask: "Is there an index that supports this `WHERE`?" and "Did the planner actually use it?" Use `EXPLAIN ANALYZE` to find out.

---

## Pick Your Path

SQL is enormous — but most people don't need every phase equally. Pick the track that matches your goal. Each one tells you what to focus on, what to skip, and what to do next.

### Track 1 — Backend Engineer (8–12 weeks)
**Goal:** ship REST/GraphQL APIs whose database layer is fast and correct.

Do every phase, with extra time on **Joins**, **Indexes & Performance**, **Transactions**, and **Schema Design**. Default to PostgreSQL. Pair this syllabus with the [Python Syllabus](python.md) (or your language of choice) and the [Docker Syllabus](docker.md). Build the production REST API project end-to-end with proper migrations.

### Track 2 — Data Analyst (6–10 weeks)
**Goal:** get hired writing SQL against a data warehouse.

Cover Phases 1–7 deeply (querying, joins, aggregations, CTEs, **window functions**). Skip transaction details and DBA-heavy material. Live in **window functions** — they are 50% of every analyst interview. Build the Analytics Dashboard project. Pair with a BI tool (Metabase, Looker, or Tableau) and learn dbt.

### Track 3 — Data Engineer (10–14 weeks)
**Goal:** build pipelines, models, and warehouses.

Do every phase, plus **a lot** of Phase 14 (warehouses: Snowflake, BigQuery, DuckDB, dbt). Pair with [Python](python.md), Docker, Airflow / Prefect / Dagster, and Spark or DuckDB. Build the ETL Pipeline project.

### Track 4 — Database Administrator (DBA) (12–16 weeks)
**Goal:** operate, tune, and secure databases in production.

Do every phase, deeply. Live in **Indexes & Performance**, **Transactions & Concurrency**, **Advanced Postgres Features**, and the operational tools (pgBadger, pg_stat_statements, backups, replication). Pair with Linux command line, monitoring (Datadog/Grafana), and an HA setup (Patroni, replication).

### Track 5 — Interview Prep (3–5 weeks)
**Goal:** you already know SQL and have an interview coming up.

Drill: **Joins** (inner / left / self), **Window Functions** (the second-highest-salary classic), **Aggregations**, **Indexes**, **EXPLAIN**, **ACID** + **isolation levels**. Re-read [Common Mistakes](#common-mistakes) and the [Interview Questions](#interview-questions). Solve 1–2 [LeetCode SQL](https://leetcode.com/studyplan/top-sql-50/) or [DataLemur](https://datalemur.com/) problems per day.

### Track 6 — Modernize From MySQL to Postgres (4–6 weeks)
**Goal:** you know MySQL and want to be fluent in PostgreSQL.

Skim Phases 1–5 (most of it transfers). Focus on the differences: `LIMIT/OFFSET` vs window-based pagination, Postgres `RETURNING`, `ON CONFLICT`, **JSONB**, **arrays**, **CTEs / recursive CTEs**, **window functions** (Postgres has had them forever; MySQL only since 8.0), generated columns, partial indexes, **MVCC**. Read **Phase 12** carefully — it is where Postgres pulls ahead.

> [!TIP]
> Whichever track you pick, **Phase 4 (Joins)**, **Phase 7 (Window Functions)**, and **Phase 10 (Indexes)** are the three phases every track depends on. Read them carefully and practice them until they are muscle memory.

---

## Prerequisites

> [!NOTE]
> SQL requires **zero programming experience**. It is a declarative language for data — closer to a powerful spreadsheet formula than to a "real" programming language. If you can read English and reason about rows and columns, you can learn SQL.

- A computer (Windows, Mac, or Linux)
- A terminal (Terminal on Mac/Linux, PowerShell or [Windows Terminal](https://aka.ms/terminal) on Windows)
- A database engine — install **[PostgreSQL 16+](https://www.postgresql.org/download/)** (recommended) or [SQLite](https://sqlite.org/download.html) for the absolutely-zero-setup path
- A SQL client — **[DBeaver](https://dbeaver.io/)** (free, all databases), **[TablePlus](https://tableplus.com/)** (gorgeous, free tier), or **[pgAdmin](https://www.pgadmin.org/)** for Postgres
- A [GitHub account](https://github.com/) so every query you write is committed somewhere

---

## How to Use This Syllabus

1. **Don't skip phases.** Each one builds on the last. If joins are shaky, window functions will feel impossible.
2. **Type every query yourself.** Copy-pasting from tutorials gives the illusion of learning. Type each example by hand.
3. **Always have a real database open.** Spin up Postgres locally (or use [Neon](https://neon.tech/) / [Supabase](https://supabase.com/) free tiers) and run every example.
4. **Use `EXPLAIN ANALYZE` early.** Even on simple queries. Reading plans becomes natural only with practice.
5. **Build the project at the end of each phase block** before moving on. Reading is not the same as doing.
6. **Keep a `notes.sql` file.** Paste useful patterns, query templates, and gotchas. Future-you will thank you.
7. **Commit to GitHub** from your first project. Future employers want to see SQL too.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Install a real database, connect to it, and run your first `SELECT`.

**What this phase is about.** Before you can write SQL, you need a database to write *against*. This phase walks you through installing **PostgreSQL** (the modern default), pointing a GUI client at it, loading a sample dataset, and running your first query. We also cover the mental model — tables, rows, columns, schemas — and the difference between a SQL **engine** (Postgres, MySQL...), a SQL **dialect** (each one slightly different), and a SQL **client** (DBeaver, TablePlus, psql).

**Why it matters.** Most beginners flame out here because they pick a "SQL learning website" and never set up a real database. Online sandboxes are great for one-off problems, but you cannot build real instincts (or projects) without a local Postgres you can break and reset. Get this right and the next 14 phases fly.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is a database? | A persistent, queryable store of structured data. Vs files, vs spreadsheets, vs key-value caches |
| 2 | Tables, rows, columns | The relational model in one minute. Each row is a record; each column has a type |
| 3 | Primary key & foreign key (intro) | A unique row identity (`id`) and a reference to another table's id |
| 4 | SQL vs NoSQL | When relational is the right call, when it isn't |
| 5 | Install PostgreSQL | Mac (Homebrew), Windows (installer), Linux (apt), or Docker (`docker run postgres:16`) |
| 6 | Install a GUI: DBeaver / TablePlus | Free, all-databases. Connect with host, port, user, password |
| 7 | Connect with `psql` | The official Postgres CLI: `psql -h localhost -U postgres -d sample` |
| 8 | Load a sample database | The Northwind, Sakila, or Postgres' [`dvdrental`](https://www.postgresqltutorial.com/postgresql-getting-started/postgresql-sample-database/) — practice data we'll use throughout |
| 9 | Your first `SELECT` | `SELECT * FROM customers LIMIT 10;` — the universal "hello world" of SQL |
| 10 | SQL formatting & comments | Uppercase keywords, line breaks before main clauses, `--` and `/* */` comments |
| 11 | Statement terminator (`;`) | Why every statement ends with a semicolon (especially in `psql` / multi-statement scripts) |
| 12 | Case sensitivity | SQL keywords are case-insensitive. Identifiers usually are too — but quoted ones aren't |

> [!TIP]
> The single best beginner setup in 2026 is **Postgres in Docker + DBeaver**. One command spins up the database, one click connects: `docker run --name pg -e POSTGRES_PASSWORD=postgres -p 5432:5432 -d postgres:16`. Then open DBeaver → New Connection → PostgreSQL → host `localhost`, port `5432`, user `postgres`, password `postgres`.

<details>
<summary><strong>Quick Reference: Cloud Postgres in 60 Seconds</strong></summary>

If you'd rather skip local install, two free-tier services give you a real Postgres in under a minute:

- **[Neon](https://neon.tech/)** — serverless Postgres, free tier, branchable databases like Git.
- **[Supabase](https://supabase.com/)** — Postgres + auth + realtime + storage, free tier.

Sign up, copy the connection string, paste it into DBeaver. You're done.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Postgres locally (or use Neon / Supabase) and connect with DBeaver
- [ ] Connect with `psql` from the terminal at least once
- [ ] Load the `dvdrental` (or another sample) database
- [ ] Run `SELECT * FROM customer LIMIT 5;` and read the result
- [ ] Explain the difference between database, schema, and table

</details>

---

## Phase 2: Querying Basics

![Phase](https://img.shields.io/badge/Phase-2%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Master `SELECT`, `FROM`, `WHERE`, `ORDER BY`, and `LIMIT` — 80% of all SQL ever written.

**What this phase is about.** The `SELECT` statement is the heart of SQL. You will type it more than every other keyword combined. This phase teaches the **six core clauses** in their canonical order — `SELECT`, `FROM`, `WHERE`, `GROUP BY`, `ORDER BY`, `LIMIT` — what each one does, and the *logical execution order* (which is not the order you write them in, and confuses every beginner).

**Why it matters.** A senior engineer reads a 100-line query the same way they read a paragraph: they know exactly which clause does what. Internalize the structure here and every later phase becomes faster.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `SELECT` columns | Pick specific columns: `SELECT first_name, last_name FROM customer` |
| 2 | `SELECT *` | Returns all columns. Convenient in the REPL, **avoid in production code** |
| 3 | Column aliases | `SELECT first_name AS fname` — rename in the result. Use double quotes for spaces: `AS "First Name"` |
| 4 | Computed columns | `SELECT price * 1.18 AS price_with_tax` — math, string concat, function calls |
| 5 | `FROM` & table aliases | `FROM customer c` — short alias to reference in joins later |
| 6 | `WHERE` filtering | `WHERE country = 'US'` — predicates, comparison operators |
| 7 | `ORDER BY` | `ORDER BY created_at DESC` — sort ascending (default) or descending |
| 8 | Multi-column `ORDER BY` | `ORDER BY country ASC, total_spent DESC` |
| 9 | `LIMIT` & `OFFSET` | `LIMIT 10 OFFSET 20` — pagination basics |
| 10 | `DISTINCT` | `SELECT DISTINCT country` — unique values only |
| 11 | Logical execution order | The order the engine actually runs clauses: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT |
| 12 | Comments | `-- single line`, `/* multi-line */` |
| 13 | SQL formatting style | Keywords UPPERCASE, identifiers `lower_snake_case`, one clause per line |

> [!IMPORTANT]
> The **logical execution order** of a `SELECT` statement is not the order you write it in:
>
> 1. `FROM` (and `JOIN`s) — pick the source tables
> 2. `WHERE` — filter rows
> 3. `GROUP BY` — bucket rows
> 4. `HAVING` — filter groups
> 5. `SELECT` — choose / compute output columns
> 6. `DISTINCT` — drop duplicates
> 7. `ORDER BY` — sort
> 8. `LIMIT` / `OFFSET` — paginate
>
> This is why you cannot reference a `SELECT` alias in a `WHERE` clause — `WHERE` runs *before* `SELECT`.

```sql
-- Real-world query template you will write thousands of times
SELECT
    customer_id,
    first_name || ' ' || last_name AS full_name,
    email
FROM customer
WHERE active = TRUE
  AND created_at >= '2025-01-01'
ORDER BY created_at DESC
LIMIT 50;
```

<details>
<summary><strong>Quick Reference: SELECT Skeleton</strong></summary>

```sql
SELECT   <columns>           -- what to return
FROM     <table>             -- source
WHERE    <row predicates>    -- filter individual rows
GROUP BY <columns>           -- bucket rows
HAVING   <group predicates>  -- filter groups
ORDER BY <columns>           -- sort the result
LIMIT    <n> OFFSET <m>;     -- paginate
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Run a query with every clause: SELECT, FROM, WHERE, ORDER BY, LIMIT
- [ ] Use a column alias and a table alias correctly
- [ ] Recite the logical execution order of a SELECT
- [ ] Paginate a result with LIMIT + OFFSET
- [ ] Use DISTINCT to find unique values in a column

</details>

---

## Phase 3: Filtering & Operators

![Phase](https://img.shields.io/badge/Phase-3%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Build precise `WHERE` clauses — the workhorse of every real query.

**What this phase is about.** Real queries rarely match a single value. You filter by ranges, lists, patterns, regex, NULLs, dates. This phase covers every operator that appears in a `WHERE` clause: comparison (`=`, `<>`, `<`, `>`), set membership (`IN`, `NOT IN`), ranges (`BETWEEN`), pattern matching (`LIKE`, `ILIKE`), regex (`~`, `SIMILAR TO`), and the famously tricky **NULL handling**.

**Why it matters.** "WHERE the bug lives" is a real saying among DB engineers — most production data bugs are wrong filters. NULL semantics catch every beginner at least once. Master these operators and you'll catch bugs before they ship.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Comparison operators | `=`, `<>` (or `!=`), `<`, `>`, `<=`, `>=` |
| 2 | Logical operators | `AND`, `OR`, `NOT`. Operator precedence: `AND` binds tighter than `OR` |
| 3 | Parentheses for clarity | `(A AND B) OR C` vs `A AND (B OR C)` — never trust precedence, parenthesize |
| 4 | `IN` / `NOT IN` | `WHERE country IN ('US', 'IN', 'UK')` — set membership |
| 5 | `BETWEEN` | `WHERE age BETWEEN 18 AND 65` — inclusive on both ends |
| 6 | `LIKE` patterns | `%` (any chars), `_` (single char). `WHERE email LIKE '%@gmail.com'` |
| 7 | `ILIKE` (Postgres) | Case-insensitive `LIKE`. MySQL has `LIKE` case-insensitive by default; SQL Server uses collation |
| 8 | Regex with `~`, `~*`, `!~` (Postgres) | `WHERE phone ~ '^\+1' ` — POSIX regex. Faster than `SIMILAR TO` |
| 9 | `SIMILAR TO` | The SQL standard's regex-lite. Most engines support it |
| 10 | `IS NULL` / `IS NOT NULL` | `NULL` is not a value; you cannot compare with `=`. **Trips up every beginner** |
| 11 | `IS DISTINCT FROM` | NULL-safe equality. `a IS DISTINCT FROM b` returns `TRUE` if values differ, including when one is NULL |
| 12 | `COALESCE` & `NULLIF` | `COALESCE(nickname, name, 'guest')` returns the first non-NULL. `NULLIF(a, b)` → NULL if equal |
| 13 | `CASE WHEN ... THEN ... ELSE` | SQL's if/else. Returns a value: `CASE WHEN amount > 100 THEN 'big' ELSE 'small' END` |
| 14 | Boolean columns | `WHERE active` is shorter than `WHERE active = TRUE` — and clearer |
| 15 | Date filtering | `WHERE created_at >= '2025-01-01'` — ISO-8601 strings work everywhere |
| 16 | `EXTRACT` & date parts | `EXTRACT(YEAR FROM created_at)`, `date_trunc('month', created_at)` |

> [!CAUTION]
> **NULL is not equal to anything — not even another NULL.** This is the #1 SQL gotcha. `SELECT NULL = NULL` returns NULL (not TRUE), and `SELECT NULL <> NULL` also returns NULL. So `WHERE deleted_at = NULL` returns no rows even when NULLs exist — you must write `WHERE deleted_at IS NULL` (or `IS NOT NULL`).

```sql
-- The NULL trap, demonstrated
SELECT NULL = NULL;            -- NULL (not TRUE!)
SELECT NULL <> NULL;           -- NULL

-- Wrong: returns NO rows even when there are NULLs
SELECT * FROM users WHERE deleted_at = NULL;

-- Right
SELECT * FROM users WHERE deleted_at IS NULL;
```

```sql
-- Putting it all together: filter messy real-world data
SELECT id, email, signed_up_at, country, plan
FROM users
WHERE active = TRUE
  AND email ILIKE '%@gmail.com'
  AND country IN ('US', 'CA', 'UK')
  AND signed_up_at BETWEEN '2025-01-01' AND '2025-12-31'
  AND (plan = 'pro' OR plan = 'enterprise')
  AND deleted_at IS NULL
ORDER BY signed_up_at DESC;
```

<details>
<summary><strong>Quick Reference: NULL Cheat Sheet</strong></summary>

```sql
-- Test for NULL
WHERE col IS NULL
WHERE col IS NOT NULL

-- Three-valued logic
TRUE  AND NULL = NULL
FALSE AND NULL = FALSE      -- short-circuit
TRUE  OR  NULL = TRUE
FALSE OR  NULL = NULL

-- COALESCE: first non-NULL
COALESCE(nickname, full_name, 'Guest')

-- NULLIF: NULL when values match
NULLIF(score, 0)            -- NULL when score = 0 (avoid divide-by-zero)

-- NULL-safe equality (Postgres)
WHERE a IS DISTINCT FROM b  -- TRUE if different (treats NULLs)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write WHERE clauses combining `AND`/`OR` with parentheses
- [ ] Use `IN`, `BETWEEN`, `LIKE`, `ILIKE`, regex correctly
- [ ] Filter for and against NULLs without the `=` mistake
- [ ] Use `COALESCE` to provide fallback values
- [ ] Use `CASE WHEN` to return categorized output

</details>

---

## Phase 4: Joins

![Phase](https://img.shields.io/badge/Phase-4%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Combine rows from multiple tables — the most-tested SQL skill in interviews.

**What this phase is about.** Real systems split data across tables: `users`, `orders`, `products`, `categories`, `addresses`. To answer "list every user with their last order's total," you `JOIN`. This phase covers all six join types — **INNER**, **LEFT**, **RIGHT**, **FULL OUTER**, **CROSS**, and **SELF** — the difference between **`ON` and `USING`**, and how to spot the classic mistakes (cartesian explosions, lost rows, NULL pitfalls).

**Why it matters.** Joins are the #1 topic in SQL interviews. They're also the #1 source of subtle bugs: a missing condition can return millions of accidental rows; a `LEFT` instead of `INNER` can silently include or exclude data. Internalize the join model and 90% of "weird query results" disappear.

### 4.1 — The Six Join Types (Visual)

```
   Table A          Table B            INNER JOIN          LEFT JOIN
   ┌───────┐        ┌───────┐         ┌───────┐           ┌───────┐
   │   a   │        │       │         │       │           │   a   │
   │   ┌───┼──┐  ┌──┼───┐   │         │   ┌───┐           │   ┌───┐
   │   │ a&b  │  │ a&b  │   │   ──>   │   │a&b│   ──>     │   │a&b│
   │   └───┼──┘  └──┼───┘   │         │   └───┘           │   └───┘
   │       │        │   b   │         │       │           │       │
   └───────┘        └───────┘         └───────┘           └───────┘
   only matches in BOTH                only the overlap   all of A + matches from B

   RIGHT JOIN              FULL OUTER JOIN              CROSS JOIN
   ┌───────┐               ┌───────┐                    every row in A
   │       │               │   a   │                     paired with
   │   ┌───┐               │   ┌───┐                    every row in B
   │   │a&b│               │   │a&b│
   │   └───┘               │   └───┘                    A: 100 rows
   │   b   │               │   b   │                    B: 200 rows
   └───────┘               └───────┘                    => 20,000 rows
   matches from A + all of B          everything from both
```

### 4.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `INNER JOIN` | Returns only matched rows. The default — `JOIN` alone means `INNER JOIN` |
| 2 | `LEFT JOIN` (LEFT OUTER) | All rows from the left + matches from the right; NULLs where no match |
| 3 | `RIGHT JOIN` (RIGHT OUTER) | Mirror of LEFT. Rare in practice — flip the table order and use LEFT |
| 4 | `FULL OUTER JOIN` | All rows from both sides, NULLs where no match. Useful for set comparisons |
| 5 | `CROSS JOIN` | Cartesian product — every row of A paired with every row of B. Used for grids and date series |
| 6 | `SELF JOIN` | A table joined to itself (e.g. employees with managers — both rows live in the same table) |
| 7 | `ON` vs `USING` | `ON a.user_id = b.user_id` (explicit) vs `USING (user_id)` (when columns match by name) |
| 8 | `NATURAL JOIN` | Joins by every same-named column. **Avoid** — schema changes silently break it |
| 9 | Multi-table joins | Chain joins to combine 3+ tables. Order doesn't matter logically; it matters for readability |
| 10 | Filtering vs joining | A filter in `ON` runs *during* the join; in `WHERE` it runs *after* — and that matters for OUTER joins |
| 11 | The cartesian explosion | A missing `ON` clause silently multiplies rows. The most expensive bug in junior SQL |
| 12 | Joins with non-equality (`>`, `<`, `BETWEEN`) | Range joins — pricing tiers, time windows |
| 13 | Anti-join with `LEFT JOIN ... WHERE b.id IS NULL` | "Find users with no orders" — the canonical anti-join pattern |
| 14 | `EXISTS` / `NOT EXISTS` | Often a clearer (and faster) alternative to `IN` / `NOT IN` for "does any row exist" |

```sql
-- Get every customer and (if they have one) their most recent order amount
SELECT
    c.customer_id,
    c.first_name,
    c.last_name,
    o.order_id,
    o.total
FROM customer c
LEFT JOIN order o
  ON o.customer_id = c.customer_id
ORDER BY c.customer_id;

-- Self-join: every employee with their manager's name
SELECT
    e.first_name AS employee,
    m.first_name AS manager
FROM employee e
LEFT JOIN employee m
  ON e.manager_id = m.employee_id;

-- Anti-join: customers who have never placed an order
SELECT c.*
FROM customer c
LEFT JOIN order o ON o.customer_id = c.customer_id
WHERE o.order_id IS NULL;
```

> [!IMPORTANT]
> The difference between **`ON` and `WHERE` for OUTER joins** is the most common mistake. A predicate inside `ON` runs *during* the join and preserves NULL right-side rows; the same predicate in `WHERE` runs *after* the join and silently turns a `LEFT JOIN` into an `INNER JOIN` by dropping the NULL right-side rows. See the example below.

```sql
-- LEFT JOIN keeps all customers; the filter runs DURING the join
SELECT c.*, o.*
FROM customer c
LEFT JOIN order o
  ON o.customer_id = c.customer_id
 AND o.created_at >= '2025-01-01';

-- This SAME-LOOKING query silently turns LEFT into INNER!
-- The WHERE drops customers whose joined o.created_at is NULL.
SELECT c.*, o.*
FROM customer c
LEFT JOIN order o ON o.customer_id = c.customer_id
WHERE o.created_at >= '2025-01-01';
```

<details>
<summary><strong>Quick Reference: ON vs USING</strong></summary>

```sql
-- ON: most flexible, allows expressions
SELECT *
FROM users u
JOIN orders o ON o.user_id = u.id;

-- USING: shorthand when columns share a name (collapses the duplicate column)
SELECT *
FROM users u
JOIN orders o USING (user_id);

-- Multi-column USING
SELECT *
FROM events a
JOIN events b USING (user_id, session_id);
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write INNER, LEFT, FULL OUTER, CROSS, and SELF joins from scratch
- [ ] Predict which rows survive an INNER vs LEFT join with NULLs in the right table
- [ ] Spot a cartesian explosion in a query and fix it
- [ ] Use the `LEFT JOIN ... WHERE x IS NULL` anti-join pattern
- [ ] Convert `IN (SELECT ...)` to `EXISTS (SELECT 1 ...)` and back

</details>

---

## Phase 5: Aggregations & Grouping

![Phase](https://img.shields.io/badge/Phase-5%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Reduce many rows to summary numbers — the language of dashboards and reports.

**What this phase is about.** Aggregation is how SQL turns "every order ever" into "monthly revenue per country." You group rows with `GROUP BY`, summarize them with **aggregate functions** (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`), and filter the resulting groups with `HAVING`. Modern SQL adds `FILTER` for conditional aggregates, `DISTINCT` inside aggregates, and grouping sets / `ROLLUP` / `CUBE` for multi-level summaries.

**Why it matters.** Every analytics dashboard, every business KPI, every "how many users signed up last week" question is an aggregation. They're also a heavy interview topic: `GROUP BY` rules trip up most candidates. Master these and you can answer any "tell me about my data" question in 5 minutes.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `COUNT(*)`, `COUNT(col)`, `COUNT(DISTINCT col)` | Subtle: `COUNT(col)` ignores NULLs; `COUNT(*)` doesn't |
| 2 | `SUM`, `AVG` | Aggregate math. Beware: `SUM` of an empty set is NULL, `COUNT` is 0 |
| 3 | `MIN`, `MAX` | Smallest/largest values. Work on numbers, dates, and strings (lexicographic) |
| 4 | `GROUP BY` | Bucket rows by one or more columns, then aggregate within each bucket |
| 5 | The `GROUP BY` rule | Every column in `SELECT` must either be in `GROUP BY` or inside an aggregate |
| 6 | `HAVING` vs `WHERE` | `WHERE` filters rows before grouping; `HAVING` filters groups after |
| 7 | `FILTER (WHERE ...)` | Conditional aggregate: `COUNT(*) FILTER (WHERE active)` |
| 8 | `DISTINCT` inside aggregates | `COUNT(DISTINCT user_id)` — common analytics pattern |
| 9 | `STRING_AGG` / `ARRAY_AGG` | Concatenate values per group: `STRING_AGG(name, ', ')`. MySQL: `GROUP_CONCAT` |
| 10 | `GROUPING SETS`, `ROLLUP`, `CUBE` | Multi-level summaries in a single query — by country, by region, and grand total |
| 11 | Statistical aggregates | `STDDEV`, `VARIANCE`, `PERCENTILE_CONT`, `PERCENTILE_DISC` |
| 12 | Aggregates with no `GROUP BY` | `SELECT COUNT(*) FROM users` — single-row summary over the whole table |
| 13 | `ORDER BY` aggregate | `ORDER BY SUM(total) DESC` — sort by an aggregate, often paired with a `LIMIT` |
| 14 | NULL behavior in aggregates | All aggregates **except `COUNT(*)`** ignore NULLs |

```sql
-- Monthly revenue and order count by country, only countries with > 100 orders
SELECT
    country,
    DATE_TRUNC('month', created_at) AS month,
    COUNT(*)                          AS orders,
    COUNT(DISTINCT user_id)           AS unique_buyers,
    SUM(total)                        AS revenue,
    AVG(total)                        AS avg_order_value,
    COUNT(*) FILTER (WHERE total > 100) AS big_orders,
    PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY total) AS median_order
FROM orders
WHERE created_at >= '2025-01-01'
GROUP BY country, DATE_TRUNC('month', created_at)
HAVING COUNT(*) > 100
ORDER BY revenue DESC;
```

> [!TIP]
> **Postgres-specific niceties** for analytics:
> - `FILTER (WHERE ...)` is cleaner than `SUM(CASE WHEN ... THEN ... ELSE 0 END)` — both work everywhere, but `FILTER` is the modern way.
> - `PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY x)` for true median.
> - `BOOL_AND` / `BOOL_OR` to aggregate booleans.

<details>
<summary><strong>Quick Reference: GROUP BY Rules</strong></summary>

```sql
-- LEGAL: every non-aggregate is in GROUP BY
SELECT country, COUNT(*) FROM users GROUP BY country;

-- ILLEGAL in standard SQL (and in Postgres): name not in GROUP BY
SELECT country, name, COUNT(*) FROM users GROUP BY country;

-- LEGAL: name is functionally dependent on the grouping key
-- (Postgres allows when grouping by primary key; MySQL allows everything by default — usually a bug)
SELECT u.id, u.name, COUNT(o.id)
FROM users u
LEFT JOIN orders o ON o.user_id = u.id
GROUP BY u.id;
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Compute COUNT, SUM, AVG, MIN, MAX with and without GROUP BY
- [ ] Explain the difference between WHERE and HAVING in plain English
- [ ] Use `FILTER (WHERE ...)` for conditional counts
- [ ] Compute `COUNT(DISTINCT user_id)` per day
- [ ] Use `STRING_AGG` (or `GROUP_CONCAT`) to make a comma-separated list per group

</details>

---

## Phase 6: Subqueries & CTEs

![Phase](https://img.shields.io/badge/Phase-6%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Compose queries from smaller queries — and finally write SQL you can read.

**What this phase is about.** Real questions are layered: "Show me customers whose orders this year are bigger than their lifetime average." Three queries in one. SQL gives you three composition tools: **scalar subqueries** (one value), **derived tables** (a query in the `FROM`), and **Common Table Expressions** (CTEs) — the modern, named, top-to-bottom way to build complex queries. Plus **recursive CTEs** for hierarchies and graphs.

**Why it matters.** A 200-line query without CTEs is unreadable; the same logic with CTEs is a sequence of named, self-explaining steps. Senior engineers reach for CTEs constantly. Recursive CTEs handle org charts, category trees, friend-of-a-friend graphs — without them you'd write a loop in application code (slow, brittle).

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Scalar subqueries | `WHERE total > (SELECT AVG(total) FROM orders)` — one value used in an expression |
| 2 | Single-row vs multi-row subqueries | `=` for single, `IN`/`ANY`/`ALL` for multiple |
| 3 | `IN` / `NOT IN` subqueries | `WHERE user_id IN (SELECT id FROM users WHERE active)` — beware NULLs in `NOT IN` |
| 4 | `EXISTS` / `NOT EXISTS` | NULL-safe alternative to `IN` — and usually the optimizer's preferred form |
| 5 | Correlated subqueries | The inner query references the outer row. Powerful but slow if naive |
| 6 | Derived tables (subquery in `FROM`) | `FROM (SELECT ...) sub` — a temporary table for one query |
| 7 | CTE basics: `WITH` | `WITH active_users AS (SELECT ...) SELECT ... FROM active_users` |
| 8 | Multiple CTEs | Chain: `WITH a AS (...), b AS (... FROM a) SELECT ...` |
| 9 | CTE vs subquery | CTEs are named, reusable, top-to-bottom. Better readability; same performance in modern Postgres |
| 10 | Recursive CTEs | `WITH RECURSIVE tree AS (... UNION ALL ...) SELECT ...` — walk hierarchies and graphs |
| 11 | `ANY` / `ALL` | `> ANY (SELECT ...)` (greater than at least one), `> ALL` (greater than every) |
| 12 | Materialized vs inlined CTEs | Postgres 12+ inlines CTEs for the optimizer (use `WITH ... AS MATERIALIZED` to force materialization) |
| 13 | LATERAL joins | A subquery in the `FROM` that can reference columns from earlier tables. "For each row, run this query" |

```sql
-- CTE pipeline: top 10 customers by spend, with their last order date
WITH customer_spend AS (
    SELECT customer_id, SUM(total) AS total_spent
    FROM orders
    WHERE created_at >= '2025-01-01'
    GROUP BY customer_id
),
last_order AS (
    SELECT customer_id, MAX(created_at) AS last_order_at
    FROM orders
    GROUP BY customer_id
)
SELECT
    c.customer_id,
    c.first_name,
    c.last_name,
    s.total_spent,
    l.last_order_at
FROM customer c
JOIN customer_spend s USING (customer_id)
JOIN last_order   l USING (customer_id)
ORDER BY s.total_spent DESC
LIMIT 10;

-- Recursive CTE: walk a category tree
WITH RECURSIVE tree AS (
    -- Anchor: root categories
    SELECT id, name, parent_id, 1 AS depth
    FROM category
    WHERE parent_id IS NULL

    UNION ALL

    -- Recursive step: children of categories already in `tree`
    SELECT c.id, c.name, c.parent_id, t.depth + 1
    FROM category c
    JOIN tree t ON c.parent_id = t.id
)
SELECT * FROM tree ORDER BY depth, name;
```

> [!TIP]
> **CTEs are the readability superpower of modern SQL.** Postgres 12+ inlines them by default, so they're as fast as subqueries — there's no longer a performance reason to avoid them. Use CTEs to make every step of your logic named and easy to read.

<details>
<summary><strong>Quick Reference: When to Use Each Form</strong></summary>

| Pattern | When |
|---------|------|
| **Scalar subquery** | One value used in `SELECT` or `WHERE` |
| **`IN (SELECT ...)`** | Membership; safe when no NULLs |
| **`EXISTS (SELECT 1 ...)`** | Existence check; NULL-safe; usually the fastest |
| **Derived table** | One-off intermediate result you don't reuse |
| **CTE** | Multi-step pipeline, recursive queries, or anything you want to name |
| **`LATERAL`** | "For each row of A, run a parameterized query against B" — top-N per group, JSON aggregations |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Rewrite a nested subquery as a CTE
- [ ] Use `EXISTS` and explain why it can be safer than `NOT IN`
- [ ] Write a 3-step CTE pipeline solving a real analytical question
- [ ] Walk a category / org-chart tree with a recursive CTE
- [ ] Use `LATERAL` to grab the top-3 orders per customer

</details>

---

## Phase 7: Window Functions

![Phase](https://img.shields.io/badge/Phase-7%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> The single most-asked SQL interview topic — and the most useful tool you've never heard of.

**What this phase is about.** Window functions compute per-row values that depend on a *window* of other rows — without collapsing the result like `GROUP BY` does. They unlock **ranking** (1st, 2nd, 3rd customer by spend), **running totals**, **moving averages**, **lag/lead** (compare a row to the previous one), and **top-N-per-group** problems. Postgres, MySQL 8+, SQL Server, Oracle, SQLite 3.25+, BigQuery, and Snowflake all support them.

**Why it matters.** Window functions show up in roughly half of all senior SQL interviews. The classic "second-highest salary" problem, the "top 3 orders per customer," the "running total of revenue," the "month-over-month growth" — all window functions, and all unsolvable cleanly without them. Master them and senior interviewers will smile.

### 7.1 — The Mental Model

```
                       OVER (
                          PARTITION BY  group_column   -- buckets the rows
                          ORDER BY      sort_column    -- orders within bucket
                          ROWS BETWEEN ...             -- frame: which rows count?
                       )
```

Every window function is `function_name(args) OVER ( ... )`. The `OVER` clause defines the *window*: which rows the function looks at for each output row.

### 7.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is a window? | Per-row computation over a "window" of other rows. Doesn't collapse rows like `GROUP BY` |
| 2 | `OVER ()` (whole table) | Most basic — every row sees every other row |
| 3 | `PARTITION BY` | Like a `GROUP BY` for the window — the function resets per partition |
| 4 | `ORDER BY` inside `OVER` | Within each partition, define an order. Required for ranking and offset functions |
| 5 | `ROW_NUMBER()` | 1, 2, 3 per partition — unique even on ties |
| 6 | `RANK()` | 1, 2, 2, 4 — ties get the same rank, next rank skips |
| 7 | `DENSE_RANK()` | 1, 2, 2, 3 — no skips |
| 8 | `NTILE(n)` | Quartiles, deciles — bucket rows into N equal groups |
| 9 | `LAG()` / `LEAD()` | Reach into the previous / next row. "Compared to last week..." |
| 10 | `FIRST_VALUE()` / `LAST_VALUE()` / `NTH_VALUE()` | First, last, or nth row in the window |
| 11 | Aggregates as window functions | `SUM(x) OVER (...)`, `AVG(x) OVER (...)` — running totals & moving averages |
| 12 | Window frames (`ROWS` / `RANGE`) | `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW` — running. `ROWS BETWEEN 6 PRECEDING AND CURRENT ROW` — 7-day moving avg |
| 13 | Top-N per group | `ROW_NUMBER() OVER (PARTITION BY ... ORDER BY ...)` then filter `= 1` (or `<= N`) |
| 14 | The "second-highest" problem | The interview classic — solved with `DENSE_RANK()` or window subquery |

```sql
-- Top 3 orders per customer (the classic)
SELECT *
FROM (
    SELECT
        o.*,
        ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY total DESC) AS rn
    FROM orders o
) ranked
WHERE rn <= 3;

-- Running daily revenue
SELECT
    order_date,
    daily_total,
    SUM(daily_total) OVER (ORDER BY order_date
                           ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS running_total
FROM (
    SELECT DATE(created_at) AS order_date, SUM(total) AS daily_total
    FROM orders
    GROUP BY DATE(created_at)
) d
ORDER BY order_date;

-- 7-day moving average revenue
SELECT
    order_date,
    daily_total,
    AVG(daily_total) OVER (ORDER BY order_date
                           ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) AS moving_avg_7d
FROM daily_revenue;

-- Compared-to-yesterday with LAG
SELECT
    order_date,
    daily_total,
    daily_total - LAG(daily_total) OVER (ORDER BY order_date) AS day_over_day_change
FROM daily_revenue;

-- The famous "second-highest salary" problem
SELECT DISTINCT salary
FROM (
    SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS r
    FROM employees
) s
WHERE r = 2;
```

> [!IMPORTANT]
> The difference between `ROW_NUMBER`, `RANK`, and `DENSE_RANK` is a guaranteed interview question:
>
> | Score | `ROW_NUMBER` | `RANK` | `DENSE_RANK` |
> |-------|:------------:|:------:|:------------:|
> | 100   | 1            | 1      | 1            |
> | 95    | 2            | 2      | 2            |
> | 95    | 3            | 2      | 2            |
> | 80    | 4            | 4      | 3            |

<details>
<summary><strong>Quick Reference: Useful Frames</strong></summary>

```sql
-- Running total
SUM(x) OVER (ORDER BY t
             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)

-- 7-day moving average (current + 6 previous rows)
AVG(x) OVER (ORDER BY t
             ROWS BETWEEN 6 PRECEDING AND CURRENT ROW)

-- Compare to all values in the same partition
x - AVG(x) OVER (PARTITION BY country)

-- Default frame for ORDER BY: RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
-- Default frame without ORDER BY:  the whole partition
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the difference between `ROW_NUMBER`, `RANK`, and `DENSE_RANK`
- [ ] Write a top-N-per-group query using `ROW_NUMBER`
- [ ] Compute a running total and a 7-day moving average
- [ ] Use `LAG` to compute day-over-day change
- [ ] Solve the "second-highest salary" problem two different ways

</details>

---

## Phase 8: Data Modification

![Phase](https://img.shields.io/badge/Phase-8%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Change data safely — `INSERT`, `UPDATE`, `DELETE`, and the modern upsert pattern.

**What this phase is about.** Querying is half the job; changing data is the other half. This phase covers the three classic DML statements (`INSERT`, `UPDATE`, `DELETE`), Postgres' powerful **`RETURNING`** clause, the **upsert** pattern (`INSERT ... ON CONFLICT`), the SQL standard `MERGE` statement, and bulk operations. We also re-emphasize the **single most dangerous SQL fact**: `UPDATE` and `DELETE` without a `WHERE` clause hit every row.

**Why it matters.** Data modification is where bugs cost real money. A wrong `UPDATE` corrupts production. A missed `WHERE` deletes the customer table. Master the safe patterns — `BEGIN`/`COMMIT`/`ROLLBACK`, `RETURNING` to verify, idempotent upserts — and you can ship changes confidently.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `INSERT INTO ... VALUES` | Single-row insert: `INSERT INTO users (name, email) VALUES ('Alice', 'a@x.com')` |
| 2 | Bulk `INSERT` | Multiple rows in one statement: `VALUES (...), (...), (...)` |
| 3 | `INSERT ... SELECT` | Insert from another query — the SQL way to copy/transform data |
| 4 | `INSERT ... RETURNING` (Postgres) | Get the inserted row(s) back — IDs, timestamps, computed columns |
| 5 | `UPDATE ... SET` | `UPDATE users SET email = 'new@x.com' WHERE id = 1` |
| 6 | `UPDATE ... FROM` | Update a row using values joined from another table |
| 7 | `DELETE FROM ... WHERE` | Remove rows. Always have a `WHERE`. Always |
| 8 | `TRUNCATE` | `TRUNCATE TABLE users` — empty the table fast. Bypasses triggers, can't be filtered |
| 9 | `INSERT ... ON CONFLICT` (Postgres upsert) | "Insert or update" — the modern idempotent pattern |
| 10 | `INSERT ... ON DUPLICATE KEY UPDATE` (MySQL) | MySQL's upsert — slightly different syntax |
| 11 | SQL standard `MERGE` | Postgres 15+ ships `MERGE`. Useful but `ON CONFLICT` is more concise for simple upserts |
| 12 | `RETURNING` for `UPDATE` / `DELETE` | Postgres returns the affected rows — perfect for audit logs and one-step optimistic operations |
| 13 | Soft delete pattern | `UPDATE ... SET deleted_at = NOW()` — rows stay in the table; queries filter on `deleted_at IS NULL` |
| 14 | Bulk operations safety | Always wrap multi-row updates in a transaction; review with `SELECT` first |

```sql
-- Idempotent upsert: insert if new, update if exists
INSERT INTO users (id, email, name)
VALUES (1, 'alice@example.com', 'Alice')
ON CONFLICT (id)
DO UPDATE SET email = EXCLUDED.email,
              name  = EXCLUDED.name,
              updated_at = NOW()
RETURNING *;

-- Update with a join (Postgres syntax)
UPDATE orders o
SET status = 'shipped'
FROM shipments s
WHERE o.id = s.order_id
  AND s.shipped_at IS NOT NULL;

-- Soft delete + return the old state for an audit log
UPDATE users
SET deleted_at = NOW()
WHERE id = 42
RETURNING *;
```

> [!CAUTION]
> **The single most dangerous SQL.** Every senior engineer has done this once — make sure you only do it once. `UPDATE users SET status = 'cancelled';` (no `WHERE`) updates *every* user. `DELETE FROM orders;` (no `WHERE`) deletes *every* order. **Always** preview a destructive change with `SELECT` first. **Always** wrap it in a transaction so you can `ROLLBACK` if something looks off.

```sql
-- The dangerous shapes — never run these without a WHERE
UPDATE users SET status = 'cancelled';   -- updates EVERY user
DELETE FROM orders;                      -- deletes EVERY order

-- The safe pattern: preview, then change, inside a transaction
BEGIN;
SELECT count(*) FROM orders WHERE created_at < '2020-01-01'; -- looks right? continue.
DELETE       FROM orders WHERE created_at < '2020-01-01';
-- COMMIT;    -- only if happy
-- ROLLBACK;  -- otherwise
```

<details>
<summary><strong>Quick Reference: Postgres Upsert vs MySQL vs MERGE</strong></summary>

```sql
-- Postgres
INSERT INTO users (id, email) VALUES (1, 'a@x.com')
ON CONFLICT (id) DO UPDATE SET email = EXCLUDED.email;

-- MySQL
INSERT INTO users (id, email) VALUES (1, 'a@x.com')
ON DUPLICATE KEY UPDATE email = VALUES(email);

-- SQL standard MERGE (Postgres 15+, SQL Server, Oracle)
MERGE INTO users u
USING (VALUES (1, 'a@x.com')) AS s(id, email)
ON u.id = s.id
WHEN MATCHED THEN UPDATE SET email = s.email
WHEN NOT MATCHED THEN INSERT (id, email) VALUES (s.id, s.email);
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Insert single rows, bulk rows, and rows from a SELECT
- [ ] Use `RETURNING` to verify what was changed
- [ ] Write an idempotent upsert with `ON CONFLICT`
- [ ] Update one table from a join with another table
- [ ] Wrap a destructive change in `BEGIN ... ROLLBACK` and prove it can be undone

</details>

---

## Phase 9: Schema Design & DDL

![Phase](https://img.shields.io/badge/Phase-9%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Design a schema that the database itself enforces — no bad data, no surprises.

**What this phase is about.** Up to here you've been *querying* a schema someone else built. This phase teaches you to **build** one. Pick the right column types (`INT` vs `BIGINT`, `TEXT` vs `VARCHAR`, `TIMESTAMP` vs `TIMESTAMPTZ`, `JSONB`), add the right **constraints** (`NOT NULL`, `UNIQUE`, `CHECK`, `FOREIGN KEY`), and structure your tables according to the **normalization** rules — and know when to break them.

**Why it matters.** Schema design is the highest-leverage decision in a project. A great schema makes queries simple, fast, and safe; a bad one means custom application code, brittle data, and slow queries forever. Most production data quality issues trace back to a missing constraint that the schema *should* have enforced.

### 9.1 — The Most-Used Column Types

| Type | Use For |
|------|---------|
| `INT` / `INTEGER` | Whole numbers up to ~2 billion |
| `BIGINT` | Whole numbers beyond 2B (IDs, counters) — default for new IDs in 2026 |
| `SMALLINT` | Whole numbers up to ~32K (tiny enums, small counts) |
| `NUMERIC(p, s)` / `DECIMAL` | Exact decimals — **money**, anything where rounding hurts |
| `REAL` / `DOUBLE PRECISION` | Float — measurements, science. Don't use for money |
| `BOOLEAN` | `TRUE` / `FALSE` |
| `TEXT` | Variable-length string. Postgres' default — no length limit |
| `VARCHAR(n)` | String with max length. Use when you genuinely need the limit |
| `CHAR(n)` | Fixed-length, padded. Avoid in modern code |
| `DATE` | Calendar date, no time |
| `TIMESTAMP` | Date + time, no timezone |
| `TIMESTAMPTZ` | Date + time with timezone — **use this for everything by default** |
| `INTERVAL` | A duration (`'1 day 2 hours'`) |
| `UUID` | 128-bit globally unique IDs — `gen_random_uuid()` in Postgres |
| `JSON` / `JSONB` | Semi-structured data. **Use `JSONB`** — binary, indexable |
| `BYTEA` | Raw bytes |
| `TEXT[]`, `INT[]` | Native arrays (Postgres) |
| `ENUM` | Custom enumerated type — use carefully (changes are awkward) |

### 9.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `CREATE TABLE` | Define columns, types, defaults, and constraints |
| 2 | Picking ID strategy | `BIGSERIAL` (auto-increment), `UUID` (`gen_random_uuid()`), or composite keys |
| 3 | `NOT NULL` | The most underused constraint. Default *most* columns to `NOT NULL` |
| 4 | `UNIQUE` | One value per column (or column combo). Backed by an index |
| 5 | `CHECK` constraints | `CHECK (price >= 0)`, `CHECK (status IN ('active','disabled'))` |
| 6 | `PRIMARY KEY` | Unique + NOT NULL + the table's natural identity |
| 7 | `FOREIGN KEY` | `REFERENCES users(id)` — points to a row in another table |
| 8 | `ON DELETE` / `ON UPDATE` | `CASCADE`, `SET NULL`, `RESTRICT`, `NO ACTION` — what happens to children |
| 9 | `DEFAULT` | `created_at TIMESTAMPTZ NOT NULL DEFAULT NOW()` |
| 10 | `ALTER TABLE` | Add/drop/rename columns, add constraints, change types |
| 11 | `DROP TABLE` | Permanent. `DROP TABLE ... CASCADE` removes dependent objects |
| 12 | Naming conventions | `snake_case`, plural table names (`users`), `created_at` not `creation_dt`, `*_id` for FKs |
| 13 | Normalization 1NF / 2NF / 3NF | Eliminate repeating groups, partial dependencies, transitive dependencies |
| 14 | When to denormalize | Read-heavy reporting, computed totals, JSONB blobs for flexible attributes |
| 15 | Generated columns | `total NUMERIC GENERATED ALWAYS AS (price * quantity) STORED` |
| 16 | Schemas (logical grouping) | `CREATE SCHEMA reporting;` — namespace tables by domain |
| 17 | Migrations as code | Use Flyway / Liquibase / Atlas / Alembic — never hand-edit a production schema |

```sql
-- A real schema you'd actually ship
CREATE TABLE users (
    id           BIGSERIAL    PRIMARY KEY,
    email        TEXT         NOT NULL UNIQUE,
    name         TEXT         NOT NULL,
    plan         TEXT         NOT NULL DEFAULT 'free'
                              CHECK (plan IN ('free', 'pro', 'enterprise')),
    metadata     JSONB        NOT NULL DEFAULT '{}'::jsonb,
    created_at   TIMESTAMPTZ  NOT NULL DEFAULT NOW(),
    updated_at   TIMESTAMPTZ  NOT NULL DEFAULT NOW(),
    deleted_at   TIMESTAMPTZ
);

CREATE TABLE orders (
    id           BIGSERIAL    PRIMARY KEY,
    user_id      BIGINT       NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    total_cents  BIGINT       NOT NULL CHECK (total_cents >= 0),
    status       TEXT         NOT NULL DEFAULT 'pending'
                              CHECK (status IN ('pending','paid','shipped','cancelled')),
    created_at   TIMESTAMPTZ  NOT NULL DEFAULT NOW()
);

CREATE INDEX idx_orders_user_id ON orders (user_id);
CREATE INDEX idx_orders_created_at ON orders (created_at DESC);
```

> [!IMPORTANT]
> **Six rules that will save you a year of pain:**
>
> 1. Default columns to `NOT NULL` — only allow NULL when "no value" is a real, distinct state.
> 2. Use `BIGINT` for IDs, not `INT`. Twos-billion seems like a lot until it isn't.
> 3. Store money as `NUMERIC` (or as integer cents) — never `FLOAT`.
> 4. Use `TIMESTAMPTZ` everywhere — never `TIMESTAMP` (no zone) for events.
> 5. Always have `created_at` and `updated_at` on every table.
> 6. Migrations as code — never hand-edit production with `ALTER TABLE`.

<details>
<summary><strong>Quick Reference: Normalization in 30 Seconds</strong></summary>

| Form | Rule | Smell |
|------|------|-------|
| **1NF** | Every column holds a single value | A `tags` column with `'red,blue,green'` |
| **2NF** | No partial dependency on a composite key | Order-line table that stores customer name (depends only on order_id) |
| **3NF** | No transitive dependency | `employees` table with `department_name` (it depends on `department_id`, not on the employee) |

Most application schemas live at **3NF for OLTP** and **denormalized for reporting / analytics**.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Pick the right type (`BIGINT`, `NUMERIC`, `TIMESTAMPTZ`, `JSONB`) for each column
- [ ] Add `NOT NULL`, `UNIQUE`, `CHECK`, and `FOREIGN KEY` constraints to a real schema
- [ ] Choose between `BIGSERIAL` and `UUID` for primary keys
- [ ] Apply 3NF to an obvious denormalization
- [ ] Generate a column with `GENERATED ALWAYS AS ... STORED`
- [ ] Run a schema change as a migration (Flyway, Atlas, or Alembic)

</details>

---

## Phase 10: Indexes & Performance

![Phase](https://img.shields.io/badge/Phase-10%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 9-12 Hours](https://img.shields.io/badge/Time-9--12%20Hours-yellow)

> Make billion-row queries return in milliseconds — the highest-leverage SQL skill.

**What this phase is about.** A query without an index walks every row in the table. A query *with* an index walks the tree of an index — `O(log n)` vs `O(n)`. This phase covers **B-tree** (the default), **hash**, **GIN** (for JSONB / arrays / full-text), **BRIN** (huge time-series tables), **partial** and **covering** indexes, and the single most important diagnostic tool in SQL: **`EXPLAIN ANALYZE`**.

**Why it matters.** "The query is slow" is the most common production issue you'll be paged for. 90% of the time the cause is a missing or wrong index. Reading query plans is what separates engineers who *guess* at performance from engineers who fix it. Every senior interview asks about indexes, query plans, and `EXPLAIN`.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What an index is | A separate, sorted data structure that points back at rows. Trades disk + write cost for read speed |
| 2 | B-tree (default) | Fits 99% of cases. Supports `=`, `<`, `>`, range scans, `ORDER BY` |
| 3 | Hash | Equality only, very fast for `=`. Postgres now WAL-logs them; mostly use B-tree anyway |
| 4 | GIN | "Generalized Inverted Index" — for `JSONB`, arrays, full-text search. Multiple values per row |
| 5 | GiST | "Generalized Search Tree" — geometry, ranges, full-text |
| 6 | BRIN | "Block Range INdex" — tiny indexes for huge naturally-ordered tables (logs, time-series) |
| 7 | Composite (multi-column) indexes | `CREATE INDEX ON orders (user_id, created_at DESC)` — order matters! |
| 8 | The leftmost-prefix rule | A composite index `(a, b, c)` helps `WHERE a=...`, `WHERE a=... AND b=...`, but not `WHERE b=...` alone |
| 9 | Unique indexes | Backing for `UNIQUE` constraints — also speeds up lookups |
| 10 | Partial indexes | `CREATE INDEX ... WHERE active = TRUE` — index only the rows you query |
| 11 | Covering / `INCLUDE` columns | `INCLUDE (col)` — store extra columns in the index leaf so the query never touches the table |
| 12 | Expression indexes | `CREATE INDEX ON users (LOWER(email))` — index on a function or expression |
| 13 | Index-only scans | The optimizer answers a query *purely* from the index — fastest case |
| 14 | `EXPLAIN` | Estimated plan — what the optimizer *thinks* will happen |
| 15 | `EXPLAIN ANALYZE` | Actually runs the query and shows real timings |
| 16 | `EXPLAIN (ANALYZE, BUFFERS)` | Adds I/O statistics — see what hit cache vs disk |
| 17 | Reading scan types | Seq Scan, Index Scan, Index-Only Scan, Bitmap Heap Scan, Nested Loop, Hash Join, Merge Join |
| 18 | Statistics & `ANALYZE` | The optimizer uses table stats; out-of-date stats = bad plans. `ANALYZE table_name` |
| 19 | When NOT to add an index | Tiny tables, write-heavy hot columns, low-selectivity columns — indexes have a real cost |
| 20 | Slow query log / `pg_stat_statements` | Find your worst queries automatically |

```sql
-- Add the right indexes for a real query
CREATE INDEX idx_orders_user_created
    ON orders (user_id, created_at DESC);

CREATE INDEX idx_orders_active_pending
    ON orders (created_at)
    WHERE status = 'pending';                -- partial index

CREATE INDEX idx_users_email_lower
    ON users (LOWER(email));                 -- expression index

-- Diagnose a slow query
EXPLAIN (ANALYZE, BUFFERS)
SELECT *
FROM orders
WHERE user_id = 42
  AND created_at >= NOW() - INTERVAL '30 days'
ORDER BY created_at DESC
LIMIT 10;
```

> [!IMPORTANT]
> **A 60-second indexing checklist for every slow query:**
>
> 1. Run `EXPLAIN ANALYZE`. Is it a `Seq Scan` of a big table? Probably need an index.
> 2. Look at the `WHERE` columns. Do they have indexes? In the right *order* (most-selective first)?
> 3. Look at the `ORDER BY`. Is the index sorted the same way? `(user_id ASC, created_at DESC)`?
> 4. Big result set? Add `LIMIT` and look for `Index Scan ... Heap Fetches: 0` (index-only scan).
> 5. Multiple `WHERE` columns? Consider a composite index. **Order matters.**
> 6. Does the column have very few distinct values? (`status`, `country`) → consider a *partial* index.

<details>
<summary><strong>Quick Reference: Reading EXPLAIN</strong></summary>

```
                                                              QUERY PLAN
─────────────────────────────────────────────────────────────────────────────
Index Scan using idx_orders_user_created on orders  (cost=0.42..8.45 rows=10)
  Index Cond: (user_id = 42)
  Filter: (created_at >= now() - '30 days'::interval)
  Rows Removed by Filter: 5
Planning Time: 0.123 ms
Execution Time: 0.521 ms
```

Key numbers:
- **cost** — optimizer's estimate (low number = first to start, high = total).
- **rows** — estimated rows. If wildly off vs actual rows, run `ANALYZE`.
- **Execution Time** — the only number that matters in production.
- Bad smells: `Seq Scan` on big tables, `Rows Removed by Filter` very high, `Sort` with high `external merge` (sorting on disk).

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read an `EXPLAIN ANALYZE` plan and identify each scan / join type
- [ ] Add a B-tree index that turns a Seq Scan into an Index Scan
- [ ] Add a composite index in the right column order
- [ ] Add a partial index that beats a full index on the same column
- [ ] Add a GIN index on a JSONB column for fast key lookups
- [ ] Use `pg_stat_statements` to find the worst queries on a real database

</details>

---

## Phase 11: Transactions & Concurrency

![Phase](https://img.shields.io/badge/Phase-11%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> ACID, isolation levels, locks, deadlocks — the rules that keep money safe.

**What this phase is about.** Multiple clients hit your database at the same time. Without coordination, two simultaneous "withdraw $100" calls can both succeed against the same $100 balance. Transactions and isolation levels solve this. This phase covers **ACID** in detail, the four **isolation levels** of the SQL standard, **MVCC** (how Postgres implements them without read locks), explicit **row-level locks**, **deadlocks**, and **`SAVEPOINT`s** for partial rollbacks.

**Why it matters.** Concurrency bugs are the worst kind — they pass tests, work in dev, and corrupt production at 3am on a Saturday. Master isolation levels, know when `READ COMMITTED` is enough vs when you need `SERIALIZABLE` or `SELECT ... FOR UPDATE`, and you become the engineer the team trusts with money-touching code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is a transaction? | A unit of work — all or nothing. `BEGIN ... COMMIT` (or `ROLLBACK`) |
| 2 | ACID: Atomicity | All statements succeed, or none persist |
| 3 | ACID: Consistency | Constraints hold before and after; the database moves between valid states |
| 4 | ACID: Isolation | Concurrent transactions appear to run in some serial order |
| 5 | ACID: Durability | Committed data survives crashes (write-ahead log → disk) |
| 6 | The four isolation levels | `READ UNCOMMITTED` → `READ COMMITTED` → `REPEATABLE READ` → `SERIALIZABLE` |
| 7 | Anomalies | Dirty read, non-repeatable read, phantom read, write skew |
| 8 | Postgres defaults | `READ COMMITTED` by default. Snapshot-based — readers don't block writers |
| 9 | MVCC | Multi-version concurrency control — every row has multiple versions; readers see a snapshot |
| 10 | `SELECT ... FOR UPDATE` | Lock the row(s) for the rest of the transaction. The serializability hammer |
| 11 | `SELECT ... FOR SHARE` | Shared lock — others can read but not update |
| 12 | `SKIP LOCKED` & `NOWAIT` | "Skip rows already locked" — the queue-table pattern. "Fail fast" — don't wait |
| 13 | Deadlocks | Two transactions wait for each other's locks. Postgres detects and aborts one. Order locks consistently to avoid |
| 14 | `SAVEPOINT` & `ROLLBACK TO` | Nested partial rollbacks within a transaction |
| 15 | Long-running transactions | Hold row visibility, bloat the table — bad in production. Keep transactions short |
| 16 | Optimistic vs pessimistic locking | Optimistic: a `version` column + retry on conflict. Pessimistic: `FOR UPDATE` row lock |
| 17 | Read replicas | Reads on replicas, writes on primary. Watch for replication lag |

```sql
-- Money transfer — the canonical "I really need a transaction" example
BEGIN;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

-- Either both run, or neither does
COMMIT;

-- Pessimistic locking: prevent two concurrent updates of the same row
BEGIN;
SELECT * FROM accounts WHERE id = 1 FOR UPDATE;
-- ... now no other transaction can update this row until we commit ...
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
COMMIT;

-- Job-queue pattern: skip rows other workers are already processing
BEGIN;
SELECT *
FROM jobs
WHERE status = 'queued'
ORDER BY created_at
LIMIT 1
FOR UPDATE SKIP LOCKED;     -- the magic — Postgres' job-queue superpower
-- ... process the job ...
UPDATE jobs SET status = 'done' WHERE id = $1;
COMMIT;
```

> [!IMPORTANT]
> **The four isolation levels — what each one prevents:**
>
> | Level | Dirty Read | Non-repeatable Read | Phantom Read | Write Skew |
> |-------|:----------:|:--------------------:|:------------:|:----------:|
> | READ UNCOMMITTED   | Possible | Possible | Possible | Possible |
> | READ COMMITTED     | No       | Possible | Possible | Possible |
> | REPEATABLE READ    | No       | No       | Possible*| Possible |
> | SERIALIZABLE       | No       | No       | No       | No       |
>
> *Postgres' `REPEATABLE READ` actually prevents phantom reads using snapshot isolation — a happy historical accident.

<details>
<summary><strong>Quick Reference: Set Isolation Level</strong></summary>

```sql
-- For a single transaction
BEGIN;
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
-- ... your statements ...
COMMIT;

-- Or per session
SET SESSION CHARACTERISTICS AS TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Wrap a multi-statement change in a transaction and roll it back
- [ ] Explain ACID in your own words to a non-engineer
- [ ] List the four isolation levels and which anomalies each prevents
- [ ] Use `SELECT ... FOR UPDATE` to prevent a lost update
- [ ] Implement a job queue with `FOR UPDATE SKIP LOCKED`
- [ ] Reproduce a deadlock between two psql sessions, then watch Postgres abort one

</details>

---

## Phase 12: Advanced Postgres Features

![Phase](https://img.shields.io/badge/Phase-12%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Why Postgres is the most-loved database in 2026 — the features that pull it ahead.

**What this phase is about.** Postgres is *not* "just MySQL with a different syntax." It ships an enormous set of features that other open-source databases either don't have or only fake. **JSONB** with proper indexing, native **arrays**, **full-text search**, **generated columns**, **materialized views**, **triggers**, **stored procedures** in PL/pgSQL (or Python, or JavaScript), **`LISTEN`/`NOTIFY`** for pub/sub, and the famously vibrant **extension** ecosystem (pgvector, PostGIS, TimescaleDB, pg_partman). This phase is your tour.

**Why it matters.** Postgres has won the open-source database war. Knowing these features lets you replace whole categories of infrastructure (a Redis pub/sub here, an Elasticsearch instance there, a vector DB elsewhere) with a single Postgres instance. Less infra = fewer bugs = faster startup.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `JSONB` storage | Binary, indexable JSON. Use `JSONB` over `JSON` 99% of the time |
| 2 | `JSONB` operators | `->`, `->>`, `#>`, `#>>`, `@>`, `?` — extract, contains, key-exists |
| 3 | `JSONB` indexing | GIN indexes on whole columns or specific paths |
| 4 | JSON path queries | SQL/JSON path: `jsonb_path_query(data, '$.users[*].email')` |
| 5 | Arrays | `INT[]`, `TEXT[]` — native arrays. `ANY`/`ALL`/`@>`/`&&` operators |
| 6 | Full-text search | `tsvector`, `tsquery`, `to_tsvector('english', content) @@ to_tsquery('postgres')` |
| 7 | Trigram (`pg_trgm`) | Fuzzy matching, "similar to" queries, fast `LIKE '%foo%'` searches |
| 8 | Generated columns | `total NUMERIC GENERATED ALWAYS AS (price * qty) STORED` — computed on insert |
| 9 | Views | `CREATE VIEW active_users AS SELECT ...` — saved query, runs each time |
| 10 | Materialized views | Cached query results — `REFRESH MATERIALIZED VIEW` |
| 11 | Triggers | Run a function on `BEFORE`/`AFTER` `INSERT`/`UPDATE`/`DELETE`. Audit logs, last-modified, denormalization |
| 12 | Stored procedures & functions | `CREATE FUNCTION ... LANGUAGE plpgsql` — encapsulate logic in the DB |
| 13 | Multiple PL languages | PL/pgSQL, PL/Python (`plpython3u`), PL/JavaScript (`plv8`), PL/Rust |
| 14 | `LISTEN` / `NOTIFY` | Lightweight pub/sub built into Postgres — no Redis needed for many use cases |
| 15 | Common Table Expressions (recap) | Recursive CTEs for graphs, trees, "find all dependencies of X" |
| 16 | Range types | `int4range`, `tstzrange` — represent intervals natively, with operators |
| 17 | Custom types & domains | `CREATE TYPE`, `CREATE DOMAIN` — strongly-typed reusable definitions |
| 18 | Partitioning | Native table partitioning by range, list, or hash. For huge tables |
| 19 | Logical replication | Stream changes from one Postgres to another (or to Kafka) |
| 20 | Foreign Data Wrappers | Query other databases (MySQL, Mongo, files) **as if they were Postgres tables** |
| 21 | Extensions | `CREATE EXTENSION pgvector;` — add new features with one command |

```sql
-- JSONB: store flexible attributes, query them, index them
ALTER TABLE products ADD COLUMN attrs JSONB NOT NULL DEFAULT '{}'::jsonb;

UPDATE products SET attrs = '{"color":"red","size":"M","tags":["sale","new"]}'::jsonb
WHERE id = 1;

-- Find products with color=red, anywhere in attrs
SELECT * FROM products WHERE attrs @> '{"color":"red"}';

-- Index it
CREATE INDEX idx_products_attrs ON products USING GIN (attrs);

-- Full-text search
CREATE INDEX idx_articles_fts ON articles
    USING GIN (to_tsvector('english', title || ' ' || body));

SELECT *
FROM articles
WHERE to_tsvector('english', title || ' ' || body)
      @@ websearch_to_tsquery('english', 'postgres performance');

-- Materialized view for a slow analytics query
CREATE MATERIALIZED VIEW monthly_revenue AS
SELECT date_trunc('month', created_at) AS month,
       country,
       SUM(total) AS revenue
FROM orders
GROUP BY 1, 2;

CREATE INDEX ON monthly_revenue (month, country);
REFRESH MATERIALIZED VIEW CONCURRENTLY monthly_revenue;

-- Trigger: keep updated_at fresh
CREATE OR REPLACE FUNCTION set_updated_at() RETURNS TRIGGER AS $$
BEGIN
    NEW.updated_at = NOW();
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER users_updated_at
    BEFORE UPDATE ON users
    FOR EACH ROW EXECUTE FUNCTION set_updated_at();

-- Pub/sub: listen for events, no Redis needed
LISTEN order_placed;
NOTIFY order_placed, '{"order_id": 42}';
```

> [!TIP]
> **A practical "replace this infra with Postgres" cheat sheet:**
>
> | You think you need... | Postgres can do it with... |
> |-----------------------|----------------------------|
> | Redis pub/sub          | `LISTEN` / `NOTIFY` |
> | Redis cache (small)    | `UNLOGGED TABLE` + GIN/JSONB |
> | Job queue              | `SELECT ... FOR UPDATE SKIP LOCKED` |
> | Elasticsearch          | Full-text search + `pg_trgm` |
> | A vector database      | `pgvector` extension |
> | A time-series database | `TimescaleDB` extension |
> | Mongo for flexible data| `JSONB` columns |
> | A graph database (sometimes) | Recursive CTEs |

<details>
<summary><strong>Quick Reference: Famous Postgres Extensions</strong></summary>

| Extension | What It Does |
|-----------|--------------|
| **pgvector** | Vector similarity search — embeddings for AI / RAG |
| **PostGIS** | Geospatial — points, polygons, distance, R-tree indexes |
| **TimescaleDB** | Time-series — automatic partitioning, continuous aggregates |
| **pg_partman** | Automated partition creation for huge tables |
| **pg_stat_statements** | Tracks slowest queries — every production DB enables this |
| **pgcrypto** | `gen_random_uuid()`, hashes, encryption |
| **pg_trgm** | Trigram similarity — fast `LIKE '%foo%'`, fuzzy match |
| **citext** | Case-insensitive text type |
| **uuid-ossp** | Older UUID functions (use `pgcrypto` in modern Postgres) |
| **hstore** | Older key-value type (use `JSONB` instead) |
| **pg_cron** | Cron-style scheduled jobs inside Postgres |
| **postgres_fdw** | Query other Postgres databases as foreign tables |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Store and query data in a `JSONB` column with `@>` and GIN index
- [ ] Build a full-text search across two columns
- [ ] Create a generated column that computes `total = price * qty`
- [ ] Create a materialized view and refresh it
- [ ] Write a `BEFORE UPDATE` trigger that maintains `updated_at`
- [ ] Use `LISTEN` / `NOTIFY` for a tiny pub/sub demo
- [ ] Install and use **one** Postgres extension (pgvector, PostGIS, or pg_trgm)

</details>

---

## Phase 13: Modern SQL — Vectors, JSON, Time-Series & AI

![Phase](https://img.shields.io/badge/Phase-13%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Postgres for AI / RAG, modern JSON paths, time-series, and partitioning.

**What this phase is about.** SQL has quietly become *the* default for new AI features. **pgvector** turns Postgres into a vector database. **JSON path** queries (SQL/JSON, SQL:2016+) make Postgres a first-class document store. **TimescaleDB** turns Postgres into a time-series database. **Native partitioning** handles billion-row tables. This phase shows you the modern SQL features that didn't exist 10 years ago — and that today's hireable engineers are expected to know.

**Why it matters.** Two years ago, building an AI app meant Postgres + Pinecone + Elasticsearch + a queue. In 2026, the same app is just **Postgres** + your application code. Knowing this stack lets you ship AI features in days, not months — and means you don't need to spin up four separate services to get there.

### 13.1 — pgvector: Postgres as a Vector Database

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is a vector / embedding? | A list of floats representing meaning. From text, images, audio. Output of OpenAI's `text-embedding-3-small`, Voyage AI, Cohere, etc. |
| 2 | The `vector` type | `CREATE EXTENSION vector;` adds a `vector(1536)` type |
| 3 | Distance operators | `<->` (L2), `<=>` (cosine), `<#>` (negative inner product) |
| 4 | Approximate Nearest Neighbor (ANN) indexes | `IVFFlat`, `HNSW` — sub-linear similarity search at scale |
| 5 | Hybrid search | Combine vector search + full-text search with weights |
| 6 | RAG pipeline in SQL | Embed → store → query → top-K → feed into LLM context |

```sql
-- Turn your Postgres into a vector database
CREATE EXTENSION IF NOT EXISTS vector;

CREATE TABLE documents (
    id          BIGSERIAL PRIMARY KEY,
    content     TEXT       NOT NULL,
    embedding   vector(1536) NOT NULL,         -- OpenAI text-embedding-3-small dimensions
    created_at  TIMESTAMPTZ NOT NULL DEFAULT NOW()
);

-- HNSW index for fast similarity search at scale
CREATE INDEX ON documents
    USING hnsw (embedding vector_cosine_ops)
    WITH (m = 16, ef_construction = 64);

-- Find the 5 most similar docs to a query embedding
SELECT id, content, 1 - (embedding <=> $1) AS similarity
FROM documents
ORDER BY embedding <=> $1
LIMIT 5;
```

### 13.2 — Modern JSON Path

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 7 | `jsonb_path_query` | SQL standard JSON path expressions |
| 8 | `@?` and `@@` operators | Test paths against JSONB values |
| 9 | Path filters & predicates | `$.users[*] ? (@.age > 30).name` |

```sql
-- Get every email in a nested JSONB structure
SELECT id, jsonb_path_query(profile, '$.users[*].email') AS email
FROM accounts;
```

### 13.3 — Time-Series with TimescaleDB

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 10 | Hypertables | TimescaleDB auto-partitions by time chunks |
| 11 | Continuous aggregates | Materialized views that incrementally refresh |
| 12 | Retention policies | Automatic drop of old chunks |
| 13 | Compression | Column-store compression on cold chunks |

```sql
-- TimescaleDB hypertable
CREATE TABLE metrics (
    time        TIMESTAMPTZ NOT NULL,
    device_id   BIGINT NOT NULL,
    cpu         REAL,
    memory      REAL
);
SELECT create_hypertable('metrics', 'time');

-- A continuous aggregate that auto-refreshes
CREATE MATERIALIZED VIEW metrics_hourly
WITH (timescaledb.continuous) AS
SELECT time_bucket('1 hour', time) AS bucket,
       device_id,
       AVG(cpu) AS avg_cpu,
       MAX(cpu) AS max_cpu
FROM metrics
GROUP BY 1, 2;
```

### 13.4 — Native Partitioning

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 14 | Why partition? | Smaller indexes per partition, fast deletes (drop a partition), better cache locality |
| 15 | `PARTITION BY RANGE` / `LIST` / `HASH` | Partition by month, by tenant, by hash bucket |
| 16 | Partition pruning | Optimizer skips partitions whose range can't match |
| 17 | When to partition | Tables ≥ 100M rows, or naturally time-bounded data |

```sql
-- Range-partitioned events table
CREATE TABLE events (
    id          BIGSERIAL,
    occurred_at TIMESTAMPTZ NOT NULL,
    payload     JSONB,
    PRIMARY KEY (id, occurred_at)
) PARTITION BY RANGE (occurred_at);

CREATE TABLE events_2025_01 PARTITION OF events
    FOR VALUES FROM ('2025-01-01') TO ('2025-02-01');
CREATE TABLE events_2025_02 PARTITION OF events
    FOR VALUES FROM ('2025-02-01') TO ('2025-03-01');
-- Drop a month in milliseconds:  DROP TABLE events_2025_01;
```

> [!TIP]
> The 2026 default architecture for a startup that needs AI:
>
> 1. Postgres on Neon, Supabase, or AlloyDB.
> 2. `pgvector` for embeddings.
> 3. Native JSONB for flexible doc storage.
> 4. Native partitioning for events / logs.
> 5. `LISTEN`/`NOTIFY` for cheap real-time fanout.
>
> One database, four problems solved.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install pgvector and store embeddings from OpenAI / Voyage AI
- [ ] Build a tiny RAG: embed → search top-5 → send to Claude as context
- [ ] Query nested JSON with `jsonb_path_query`
- [ ] Set up a TimescaleDB hypertable + continuous aggregate
- [ ] Create a range-partitioned table by month and prove pruning with `EXPLAIN`

</details>

---

## Phase 14: The Database Ecosystem

![Phase](https://img.shields.io/badge/Phase-14%2F15-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The single biggest reason SQL is unkillable — its ecosystem.

**What this phase is about.** Knowing SQL is one half of the job; knowing the **ecosystem around it** is the other. ORMs, migrations, GUIs, performance tools, hosted Postgres, NoSQL alternatives, search engines, time-series, vector databases, data warehouses, analytics tools — every team uses some combination of these. This phase is a **map**: a categorized directory of every tool you'll meet on the job, with one-line descriptions so you know which is which.

**Why it matters.** When a job description lists "Postgres, Drizzle, Prisma, Flyway, Kysely, dbt, BigQuery, Snowflake, pgvector, Datadog DB monitoring, Hibernate" you should *know what every one of those is* without Googling. This phase is your dictionary.

### 14.1 — Relational Databases

| Database | License | What It's Best At |
|----------|---------|-------------------|
| **[PostgreSQL](https://www.postgresql.org/)** | Open source | The 2026 default — extensible, standards-loving, batteries included |
| **[MySQL](https://www.mysql.com/)** | Open source | The classic web database. Largest install base. WordPress and friends |
| **[MariaDB](https://mariadb.org/)** | Open source | Community-driven MySQL fork — drop-in compatible |
| **[SQLite](https://sqlite.org/)** | Public domain | Embedded, single-file. Phones, browsers, tests, Git's GUIs |
| **[SQL Server](https://www.microsoft.com/en-us/sql-server)** | Commercial | Microsoft / .NET / Azure shops. T-SQL dialect, fantastic tooling |
| **[Oracle Database](https://www.oracle.com/database/)** | Commercial | Banks, telcos, governments. PL/SQL. Still huge in finance |
| **[CockroachDB](https://www.cockroachlabs.com/)** | Open source / commercial | Postgres-wire-compatible distributed SQL |
| **[YugabyteDB](https://www.yugabyte.com/)** | Open source / commercial | Distributed Postgres alternative |
| **[Google Spanner](https://cloud.google.com/spanner)** | Commercial | Globally distributed strongly-consistent SQL |
| **[TiDB](https://www.pingcap.com/tidb/)** | Open source | MySQL-compatible HTAP database |
| **[Vitess](https://vitess.io/)** | Open source | MySQL sharding / scaling layer (used by YouTube, Slack) |

### 14.2 — Cloud / Hosted Postgres

| Service | Niche |
|---------|-------|
| **[Neon](https://neon.tech/)** | Serverless Postgres. Branchable databases like Git. The 2026 favorite for new projects |
| **[Supabase](https://supabase.com/)** | Postgres + auth + realtime + storage + edge functions. Open-source Firebase |
| **[PlanetScale](https://planetscale.com/)** | Originally MySQL/Vitess, now also Postgres. Branching, no-downtime migrations |
| **[Turso](https://turso.tech/)** | Edge SQLite — replicated SQLite at the edge |
| **[Amazon RDS](https://aws.amazon.com/rds/)** | Managed Postgres / MySQL / SQL Server / Oracle on AWS |
| **[Amazon Aurora](https://aws.amazon.com/rds/aurora/)** | AWS-native Postgres / MySQL with cloud-scale storage |
| **[AlloyDB](https://cloud.google.com/alloydb)** | Google Cloud's Postgres-compatible analytical OLTP |
| **[Cloud SQL](https://cloud.google.com/sql)** | GCP's managed Postgres / MySQL / SQL Server |
| **[Azure Database for PostgreSQL](https://azure.microsoft.com/en-us/products/postgresql)** | Azure's managed Postgres (single-server and Flexible Server) |
| **[Crunchy Bridge](https://www.crunchydata.com/products/crunchy-bridge/)** | Pure managed Postgres |
| **[Tembo](https://tembo.io/)** | Postgres "stacks" with extensions pre-installed |
| **[Vercel Postgres](https://vercel.com/storage/postgres) / [Vercel Marketplace](https://vercel.com/marketplace)** | Postgres provisioned via Neon and friends inside Vercel |
| **[Fly.io Managed Postgres](https://fly.io/docs/postgres/)** | Postgres on Fly's edge platform |

### 14.3 — ORMs & Query Builders (by language)

#### TypeScript / JavaScript

| Library | What It Is |
|---------|-----------|
| **[Drizzle](https://orm.drizzle.team/)** | Modern, type-safe SQL-first ORM. The 2026 favorite for TS |
| **[Prisma](https://www.prisma.io/)** | Schema-first ORM with great DX, generates a typed client |
| **[Kysely](https://kysely.dev/)** | Type-safe SQL query builder. SQL you can read, types you trust |
| **[TypeORM](https://typeorm.io/)** | Decorator-style classic ORM (the "Hibernate of TS") |
| **[Sequelize](https://sequelize.org/)** | The classic Node ORM (older but still common) |
| **[MikroORM](https://mikro-orm.io/)** | Data Mapper / Identity Map. Heavier, ergonomic |
| **[Knex](http://knexjs.org/)** | Query builder underneath many ORMs |
| **[postgres.js](https://github.com/porsager/postgres)** | Tiny, fast Postgres client — basis of Drizzle and many tools |
| **[node-postgres (`pg`)](https://node-postgres.com/)** | The classic Postgres driver |

#### Python

| Library | What It Is |
|---------|-----------|
| **[SQLAlchemy 2.0](https://www.sqlalchemy.org/)** | The dominant Python ORM. Async + sync, Core or ORM |
| **[SQLModel](https://sqlmodel.tiangolo.com/)** | FastAPI-flavored wrapper over SQLAlchemy + Pydantic |
| **[Django ORM](https://docs.djangoproject.com/en/stable/topics/db/)** | Bundled with Django. Active-record-ish |
| **[Tortoise ORM](https://tortoise.github.io/)** | Async ORM inspired by Django |
| **[Peewee](http://docs.peewee-orm.com/)** | Tiny, expressive ORM |
| **[asyncpg](https://magicstack.github.io/asyncpg/)** | The fastest Postgres driver for asyncio |
| **[psycopg 3](https://www.psycopg.org/)** | The classic / current Postgres driver for Python |

#### Java / Kotlin

| Library | What It Is |
|---------|-----------|
| **[Hibernate](https://hibernate.org/) / JPA** | The dominant Java ORM |
| **[Spring Data JPA](https://spring.io/projects/spring-data-jpa)** | Repository abstractions over Hibernate |
| **[jOOQ](https://www.jooq.org/)** | Type-safe SQL DSL, code-generated from your schema |
| **[MyBatis](https://mybatis.org/)** | SQL-mapper — write SQL, map results |
| **[Exposed](https://github.com/JetBrains/Exposed)** | Kotlin SQL framework by JetBrains |
| **[HikariCP](https://github.com/brettwooldridge/HikariCP)** | The connection pool everyone uses |

#### Other Languages

| Language | Library | What It Is |
|----------|---------|-----------|
| Ruby | **[ActiveRecord (Rails)](https://guides.rubyonrails.org/active_record_basics.html)** | The classic ORM. Convention over configuration |
| Ruby | **[Sequel](https://sequel.jeremyevans.net/)** | Mature alternative to ActiveRecord |
| Go | **[GORM](https://gorm.io/)** | The most popular Go ORM |
| Go | **[sqlc](https://sqlc.dev/)** | Generate type-safe Go from raw SQL |
| Go | **[ent](https://entgo.io/)** | Facebook's entity framework for Go |
| Rust | **[Diesel](https://diesel.rs/)** | Type-safe ORM with compile-time checks |
| Rust | **[sqlx](https://github.com/launchbadge/sqlx)** | Async, compile-time-checked SQL |
| Rust | **[SeaORM](https://www.sea-ql.org/SeaORM/)** | Async dynamic ORM |
| .NET | **[Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/)** | The dominant .NET ORM |
| .NET | **[Dapper](https://github.com/DapperLib/Dapper)** | "Micro-ORM" — fast and minimal |
| PHP | **[Eloquent (Laravel)](https://laravel.com/docs/eloquent)** | ActiveRecord-style ORM |
| PHP | **[Doctrine](https://www.doctrine-project.org/)** | Data Mapper-style ORM |

### 14.4 — Migrations

| Tool | Best For |
|------|---------|
| **[Flyway](https://flywaydb.org/)** | Java/JVM-flavored. Versioned SQL migrations. Industry standard for Spring apps |
| **[Liquibase](https://www.liquibase.org/)** | XML/YAML/JSON-based migrations. Strong rollback support |
| **[Alembic](https://alembic.sqlalchemy.org/)** | The Python migration tool. SQLAlchemy's companion |
| **[Atlas](https://atlasgo.io/)** | Modern declarative schema-as-code. Multi-language |
| **[sqlx-cli](https://github.com/launchbadge/sqlx)** | Rust-flavored, lightweight |
| **[Drizzle Kit](https://orm.drizzle.team/kit-docs/overview)** | Drizzle's migration generator |
| **[Prisma Migrate](https://www.prisma.io/docs/concepts/components/prisma-migrate)** | Prisma's migration system |
| **[Diesel migrations](https://diesel.rs/guides/getting-started/)** | Rails-style migrations for Rust + Diesel |
| **[Rails migrations](https://guides.rubyonrails.org/active_record_migrations.html)** | The original "DSL migration" |
| **[Goose](https://github.com/pressly/goose)** | Lightweight Go migrations |
| **[Knex migrations](http://knexjs.org/guide/migrations.html)** | Migrations for Knex / many JS ORMs |
| **[Laravel Migrations](https://laravel.com/docs/migrations)** | PHP migrations baked into Laravel |

### 14.5 — GUI Clients

| Tool | License | Notes |
|------|---------|-------|
| **[DBeaver](https://dbeaver.io/)** | Open source / Pro | Every database. Free version is fine. Industry default |
| **[TablePlus](https://tableplus.com/)** | Free tier / paid | Beautiful native app. Free tier limited but usable |
| **[DataGrip](https://www.jetbrains.com/datagrip/)** | Commercial | JetBrains' DB IDE. Best query refactoring on the planet |
| **[pgAdmin](https://www.pgadmin.org/)** | Open source | The official Postgres GUI |
| **[Postico 2](https://eggerapps.at/postico2/)** | Paid (Mac) | Mac-native, gorgeous Postgres client |
| **[Beekeeper Studio](https://www.beekeeperstudio.io/)** | Open source / paid | Modern, multi-database |
| **[HeidiSQL](https://www.heidisql.com/)** | Free | Lightweight Windows-first MySQL/Postgres client |
| **[psql](https://www.postgresql.org/docs/current/app-psql.html)** | Built in | The terminal, always with you |
| **[mycli](https://www.mycli.net/) / [pgcli](https://www.pgcli.com/)** | Open source | CLI clients with autocomplete and syntax highlighting |
| **[Outerbase](https://www.outerbase.com/)** | Cloud | Web-based DB GUI with AI assistance |

### 14.6 — Performance & Observability

| Tool | What It Does |
|------|--------------|
| **[pg_stat_statements](https://www.postgresql.org/docs/current/pgstatstatements.html)** | Built-in slow-query tracking — every production Postgres turns this on |
| **[pgBadger](https://pgbadger.darold.net/)** | Parses Postgres logs into rich HTML reports |
| **[pganalyze](https://pganalyze.com/)** | SaaS Postgres performance dashboard |
| **[EverSQL](https://www.eversql.com/)** | AI query optimizer — suggests rewrites and indexes |
| **[Datadog Database Monitoring](https://www.datadoghq.com/product/database-monitoring/)** | Per-query performance, locks, plan changes |
| **[New Relic Database](https://newrelic.com/platform/database-monitoring)** | Database APM |
| **[Percona Monitoring & Management](https://www.percona.com/software/database-tools/percona-monitoring-and-management)** | Open-source monitoring suite |
| **[explain.depesz.com](https://explain.depesz.com/)** | Paste an EXPLAIN, get a colored visualization |
| **[explain.dalibo.com](https://explain.dalibo.com/)** | Alternative EXPLAIN visualizer |
| **[pghero](https://github.com/ankane/pghero)** | Self-hosted Postgres dashboard |

### 14.7 — Backups, Replication & HA

| Tool | What It Does |
|------|--------------|
| **[pg_dump / pg_restore](https://www.postgresql.org/docs/current/app-pgdump.html)** | Built-in logical backups |
| **[pgBackRest](https://pgbackrest.org/)** | Production-grade physical backups + PITR |
| **[Barman](https://pgbarman.org/)** | Postgres backup manager |
| **[WAL-G](https://github.com/wal-g/wal-g)** | Continuous archival to S3 / GCS |
| **[Patroni](https://patroni.readthedocs.io/)** | High-availability Postgres orchestration |
| **[repmgr](https://repmgr.org/)** | Replication management |
| **[pgpool-II](https://www.pgpool.net/)** | Connection pooling + failover |
| **[PgBouncer](https://www.pgbouncer.org/)** | Lightweight Postgres connection pooler |

### 14.8 — NoSQL Alternatives

| Database | Use Case |
|----------|----------|
| **[MongoDB](https://www.mongodb.com/)** | Document store. JSON-native, flexible schemas |
| **[DynamoDB](https://aws.amazon.com/dynamodb/)** | AWS' managed key-value / document store. Predictable latency at scale |
| **[Cassandra](https://cassandra.apache.org/) / [ScyllaDB](https://www.scylladb.com/)** | Wide-column, write-heavy, horizontally scalable |
| **[Redis](https://redis.io/)** | In-memory key-value, pub/sub, queues, caches |
| **[KeyDB](https://keydb.dev/) / [Dragonfly](https://www.dragonflydb.io/)** | Faster, drop-in Redis alternatives |
| **[Couchbase](https://www.couchbase.com/)** | Document + key-value at scale |
| **[Firestore](https://firebase.google.com/products/firestore)** | Google's hosted document DB with realtime |
| **[FoundationDB](https://www.foundationdb.org/)** | Distributed transactional KV (Apple) |
| **[etcd](https://etcd.io/)** | Distributed KV used by Kubernetes |

### 14.9 — Search Engines

| Engine | What It Does |
|--------|--------------|
| **[Elasticsearch](https://www.elastic.co/elasticsearch/)** | The classic search engine — full-text, analytics |
| **[OpenSearch](https://opensearch.org/)** | AWS' open-source ES fork |
| **[Apache Solr](https://solr.apache.org/)** | The original Lucene-based search engine |
| **[Typesense](https://typesense.org/)** | Lightweight, easy-to-host search |
| **[Meilisearch](https://www.meilisearch.com/)** | Fast, dev-friendly search engine |
| **[Algolia](https://www.algolia.com/)** | Hosted search (commercial). Top-tier UX |

### 14.10 — Time-Series Databases

| Database | What It's Best At |
|----------|-------------------|
| **[TimescaleDB](https://www.timescale.com/)** | Postgres-extension time-series — full SQL, hypertables |
| **[InfluxDB](https://www.influxdata.com/)** | The original time-series DB. Flux query language |
| **[ClickHouse](https://clickhouse.com/)** | Column-store OLAP, mind-bendingly fast on analytics |
| **[QuestDB](https://questdb.io/)** | High-throughput time-series with SQL |
| **[VictoriaMetrics](https://victoriametrics.com/)** | Prometheus-compatible long-term storage |
| **[Prometheus](https://prometheus.io/)** | Metrics + alerting |

### 14.11 — Vector Databases (the AI / RAG layer)

| Database | What It Is |
|----------|-----------|
| **[pgvector](https://github.com/pgvector/pgvector)** | Postgres extension. The default in 2026 — Postgres + vectors in one DB |
| **[Pinecone](https://www.pinecone.io/)** | Hosted vector DB. Great DX, premium price |
| **[Weaviate](https://weaviate.io/)** | Open source / hosted, schema + vectors |
| **[Qdrant](https://qdrant.tech/)** | Rust-built, fast, easy self-host |
| **[Chroma](https://www.trychroma.com/)** | The "SQLite of vector DBs" — embedded, simple |
| **[Milvus](https://milvus.io/) / [Zilliz Cloud](https://zilliz.com/)** | Mature open-source vector DB at scale |
| **[LanceDB](https://lancedb.com/)** | Embedded vector DB on top of Apache Arrow |
| **[Vespa](https://vespa.ai/)** | Yahoo-built search + vector engine |

### 14.12 — Data Warehouses

| Warehouse | What It Is |
|-----------|-----------|
| **[Snowflake](https://www.snowflake.com/)** | Cloud-native data warehouse. The gold standard for analytics |
| **[BigQuery](https://cloud.google.com/bigquery)** | Google's serverless warehouse. Petabytes, SQL-first |
| **[Databricks](https://www.databricks.com/) / Delta Lake** | Lakehouse — warehouse on top of object storage |
| **[Amazon Redshift](https://aws.amazon.com/redshift/)** | AWS' classic warehouse |
| **[Microsoft Fabric / Synapse](https://learn.microsoft.com/en-us/fabric/)** | Azure analytics platform |
| **[ClickHouse](https://clickhouse.com/)** | Columnar OLAP, often used as a warehouse |
| **[DuckDB](https://duckdb.org/)** | "SQLite for analytics." Embedded OLAP — runs in your laptop / your app |
| **[Motherduck](https://motherduck.com/)** | DuckDB-as-a-service |
| **[StarRocks](https://www.starrocks.io/) / [Apache Doris](https://doris.apache.org/)** | Open-source MPP analytics DBs |

### 14.13 — Analytics, Modeling & BI

| Tool | What It Does |
|------|--------------|
| **[dbt](https://www.getdbt.com/)** | The de facto data transformation tool — write your warehouse logic as SQL + Jinja |
| **[Metabase](https://www.metabase.com/)** | Open-source BI dashboards |
| **[Superset](https://superset.apache.org/)** | Apache's open-source BI |
| **[Looker](https://www.looker.com/)** | Google's enterprise BI |
| **[Tableau](https://www.tableau.com/)** | The classic enterprise BI tool |
| **[Power BI](https://powerbi.microsoft.com/)** | Microsoft's BI platform |
| **[Mode](https://mode.com/)** | SQL + notebooks for analytics teams |
| **[Hex](https://hex.tech/)** | Data + SQL + Python notebooks |
| **[Lightdash](https://www.lightdash.com/)** | Open-source dbt-native BI |
| **[Sigma](https://www.sigmacomputing.com/)** | Spreadsheet-style BI on the warehouse |
| **[Cube](https://cube.dev/)** | Headless BI — semantic layer over warehouses |

### 14.14 — Pipeline / ETL

| Tool | What It Does |
|------|--------------|
| **[Apache Airflow](https://airflow.apache.org/)** | The classic Python DAG scheduler |
| **[Prefect](https://www.prefect.io/)** | Modern Pythonic workflow engine |
| **[Dagster](https://dagster.io/)** | Software-defined assets, modern data DAGs |
| **[Mage](https://www.mage.ai/)** | Notebook-flavored ETL |
| **[Fivetran](https://www.fivetran.com/)** | Hosted EL connectors |
| **[Airbyte](https://airbyte.com/)** | Open-source data integration |
| **[Apache Kafka](https://kafka.apache.org/)** | Event streaming — often the backbone of streaming ETL |
| **[Apache Spark](https://spark.apache.org/)** | Distributed batch + stream processing |
| **[Apache Flink](https://flink.apache.org/)** | Stateful stream processing |

> [!IMPORTANT]
> You don't learn all of these. You **recognize** all of these (so you can read job descriptions). You **deeply learn** maybe 5–8 — the ones your team uses + the foundational set: Postgres, an ORM in your language, a migration tool, a GUI client, `pg_stat_statements`, and pgvector or dbt depending on your track.

---

## Phase 15: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-15%2F15-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You've finished the language. Now pick a specialization and ship real things.

**What this phase is about.** SQL is rarely the *only* skill on a job description — it's the *cross-cutting* skill that pairs with everything else. This phase is a map: pick the track that excites you most, then go deep. Whatever you pick, you'll need a **programming language** (Python or Node are the easiest pairings), **Docker**, and basic **cloud** skills. Those three travel with you for the rest of your career.

### 15.1 — Pick a Specialization

| Track | What You Build | Key Tools Beyond SQL |
|-------|----------------|----------------------|
| **Backend / API Engineer** | REST/GraphQL APIs powered by a relational DB | [Python](python.md) / [Java](java.md) / [Node](javascript.md), an ORM, [Docker](docker.md), Redis |
| **Data Engineer** | Pipelines, warehouses, ETL/ELT | [Python](python.md), Airflow / Prefect / Dagster, Spark, dbt, Snowflake / BigQuery / DuckDB |
| **Data Analyst** | Dashboards, KPIs, ad-hoc analysis | dbt, Metabase / Looker / Tableau, Excel / Sheets, Python or R for stats |
| **Database Administrator (DBA)** | Operate, tune, secure databases | Linux, Bash, monitoring stacks, backup tools, replication / HA |
| **AI / LLM Engineer** | LLM apps, agents, RAG | Python, [Anthropic](https://docs.anthropic.com/) / [OpenAI](https://platform.openai.com/) SDKs, pgvector, LangChain / LlamaIndex |
| **ML Engineer** | Train + deploy models with feature stores | Python, scikit-learn, PyTorch, MLflow, Feast / Tecton |
| **Embedded SQL** | Apps with embedded SQLite (mobile, desktop) | Swift / Kotlin / Rust / C++, SQLite |
| **Search Engineer** | Full-text + vector + hybrid search | Postgres + pg_trgm + pgvector, Elasticsearch / OpenSearch / Typesense |
| **Game Backend** | Persistent worlds, leaderboards | Postgres, Redis, a backend language |

### 15.2 — Required Cross-Cutting Skills

| Skill | Why It Matters |
|-------|----------------|
| **A programming language** | Apps talk to databases; pick [Python](python.md), [Node](javascript.md), [Java](java.md), Go, or Rust |
| **[Git](git.md)** | Every team. Every project. Non-negotiable |
| **[Docker](docker.md)** | Spin up Postgres, MySQL, Redis in seconds. Required for modern dev loops |
| **CI/CD** (GitHub Actions) | Run migrations + tests automatically on every push |
| **Cloud basics** (AWS / GCP / Azure / Vercel) | Where your DB actually lives in production |
| **Linux command line** | Every server runs Linux. `cd`, `ssh`, `tail`, `grep`, `cron` |

### 15.3 — Where to Run Your Database

| Target | Tool |
|--------|------|
| Tiny project / prototype | [SQLite](https://sqlite.org/) (single file) or [DuckDB](https://duckdb.org/) for analytics |
| Modern startup default | [Neon](https://neon.tech/) or [Supabase](https://supabase.com/) (free tiers) |
| Cloud-managed Postgres | [AWS RDS](https://aws.amazon.com/rds/) / [Aurora](https://aws.amazon.com/rds/aurora/), [GCP AlloyDB](https://cloud.google.com/alloydb) / Cloud SQL, [Azure Database for PostgreSQL](https://azure.microsoft.com/en-us/products/postgresql) |
| Serverless / branchable | [Neon](https://neon.tech/), [PlanetScale](https://planetscale.com/) |
| Edge SQL | [Turso](https://turso.tech/) (replicated SQLite) |
| Self-hosted | Docker + [PgBouncer](https://www.pgbouncer.org/) + [pgBackRest](https://pgbackrest.org/) + [Patroni](https://patroni.readthedocs.io/) |
| Globally distributed | [CockroachDB](https://www.cockroachlabs.com/), [YugabyteDB](https://www.yugabyte.com/), [Spanner](https://cloud.google.com/spanner) |
| Data warehouse | [Snowflake](https://www.snowflake.com/), [BigQuery](https://cloud.google.com/bigquery), [Databricks](https://www.databricks.com/), [DuckDB](https://duckdb.org/) |

### 15.4 — Suggested Order After This Syllabus

```
Pick a specialization → Pair language (Python/Node/Java) → Docker → A real project →
                                                                     Deploy → Repeat
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | `SELECT *` in production queries | Returns extra columns, breaks when schema changes, blocks index-only scans | List columns explicitly |
| 2 | `UPDATE` / `DELETE` without `WHERE` | Hits every row in the table | Always preview with `SELECT` first; wrap in a transaction |
| 3 | Comparing with `= NULL` | NULL is not equal to anything; the predicate is always NULL (≈ false) | Use `IS NULL` / `IS NOT NULL` |
| 4 | `NOT IN (subquery)` with NULLs | A single NULL in the subquery makes the whole predicate NULL (returns no rows) | Use `NOT EXISTS (SELECT 1 ...)` |
| 5 | Missing index on a foreign key | Joins and `ON DELETE` cascades become full scans | Add an index on every FK column |
| 6 | Wrong column order in composite index | Index doesn't help queries that don't filter the leading column | Lead with the most-selective / always-filtered column |
| 7 | Storing money as `FLOAT` / `DOUBLE` | Floating-point rounding errors on cents | `NUMERIC` or integer cents |
| 8 | Storing timestamps as `TIMESTAMP` (no zone) | Timezone bugs on global apps | `TIMESTAMPTZ` everywhere |
| 9 | No `created_at` / `updated_at` | You'll wish you had them in week 2 | Add them on every table by default |
| 10 | No transactions for multi-statement changes | A crash in the middle leaves data half-written | `BEGIN ... COMMIT` |
| 11 | Long-running transactions | Block VACUUM, hold row locks, balloon table size | Keep transactions short — open, change, commit |
| 12 | `UNION` when you don't need uniqueness | Forces an expensive sort + dedup | `UNION ALL` is much faster — use it unless you really need DISTINCT |
| 13 | Misuse of `GROUP BY` (selecting non-grouped columns) | Standard error or, worse, MySQL silently picks an arbitrary value | Group by every non-aggregate column you select |
| 14 | Hand-editing production schemas | No history, no rollback, drift | Migrations as code (Flyway, Liquibase, Alembic, Atlas, Drizzle Kit) |
| 15 | Hard-coded LIMIT/OFFSET pagination at scale | OFFSET 10000 scans 10000 rows | Keyset pagination: `WHERE id > last_seen_id ORDER BY id LIMIT 50` |
| 16 | Trusting the optimizer to be magic | Stats can drift; plans can flip overnight | Run `ANALYZE` after big changes; set up `pg_stat_statements` |
| 17 | Ignoring `EXPLAIN ANALYZE` | "It works on my dev DB" — until prod has 100M rows | Read plans for every slow query; learn the scan types |
| 18 | One mega-query for everything | Unreadable, untestable, hard to optimize | Break into named CTEs; or compose in application code |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What's the difference between `WHERE` and `HAVING`?**
   - `WHERE` filters rows *before* grouping. `HAVING` filters groups *after* grouping. You can't use an aggregate (`COUNT`, `SUM`) in `WHERE`; you can in `HAVING`.

2. **What's the difference between `INNER JOIN` and `LEFT JOIN`?**
   - `INNER JOIN` returns only rows that match in both tables. `LEFT JOIN` returns all rows from the left table, plus matches from the right (with NULLs where there's no match).

3. **Explain primary key vs foreign key.**
   - Primary key uniquely identifies a row in a table (e.g. `users.id`). Foreign key is a column in one table that points to a primary key in another (`orders.user_id` → `users.id`). The database enforces the link.

4. **What is `NULL` in SQL?**
   - "Unknown" or "missing." It's not a value, so `= NULL` doesn't work — use `IS NULL`. Most operators with NULL return NULL (three-valued logic).

5. **What does `DISTINCT` do?**
   - Removes duplicate rows from a result set. `SELECT DISTINCT country FROM users` returns each country once.

6. **What's the difference between `DELETE` and `TRUNCATE`?**
   - `DELETE` removes rows by predicate, fires triggers, can be rolled back, and is logged per-row. `TRUNCATE` empties a whole table fast (no `WHERE`), bypasses row-level triggers, and resets sequences. `TRUNCATE` is much faster for "empty this table."

7. **What does `GROUP BY` do?**
   - Buckets rows that share the same value(s) for the grouping columns, then runs aggregates per bucket. `SELECT country, COUNT(*) FROM users GROUP BY country` returns one row per country with its user count.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **How do you find the second-highest salary?**
   - Window function (cleanest): `SELECT DISTINCT salary FROM (SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) r FROM employees) s WHERE r = 2`. Or `SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees)`. Or `LIMIT 1 OFFSET 1` after `ORDER BY salary DESC` (only correct without ties).

2. **What's a CTE and when would you use one?**
   - Common Table Expression — `WITH name AS (SELECT ...)` defines a named, reusable subquery you can reference later. Use them to break complex queries into readable steps and for recursive queries (trees, graphs).

3. **Explain `INNER`, `LEFT`, `RIGHT`, `FULL` joins.**
   - `INNER`: only matched rows. `LEFT`: all from left + matches from right. `RIGHT`: all from right + matches from left. `FULL`: everything from both sides; NULLs where no match.

4. **What does `EXISTS` do? When is it better than `IN`?**
   - `EXISTS (SELECT 1 ...)` returns true if the subquery returns any row. It's NULL-safe (unlike `NOT IN` with NULLs) and the optimizer often prefers it for "does any row exist" semantics.

5. **What is an index, and what's the cost of adding one?**
   - A separate sorted data structure that speeds up reads matching its columns. Costs: extra disk space, slower writes (every insert/update/delete must update the index), and a maintenance burden. Add indexes for queries you actually run; don't index every column.

6. **What's the difference between a clustered and a non-clustered index?**
   - Clustered = the table's rows are physically stored in index order (one per table; SQL Server / MySQL InnoDB primary key). Non-clustered = a separate structure that points back to the table. Postgres has no clustered index — every index is non-clustered. (`CLUSTER` reorders the heap one-time.)

7. **Explain ACID.**
   - Atomicity: all-or-nothing. Consistency: the database moves from one valid state to another, constraints respected. Isolation: concurrent transactions appear to run in some serial order. Durability: once committed, data survives crashes.

8. **What's a window function? Give an example.**
   - A function that computes per-row values over a window of related rows, without collapsing the result like `GROUP BY`. Example: `RANK() OVER (PARTITION BY department ORDER BY salary DESC)` — rank within each department.

9. **`UNION` vs `UNION ALL` — which is faster?**
   - `UNION ALL` is faster — it concatenates result sets without deduplication. `UNION` adds a sort/hash to remove duplicates. Use `UNION ALL` unless you specifically need uniqueness.

10. **What does `EXPLAIN ANALYZE` do?**
    - `EXPLAIN` shows the query plan the optimizer chose. `EXPLAIN ANALYZE` actually executes the query and reports real times and row counts per node. Essential for diagnosing slow queries.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **List the four isolation levels and what each prevents.**
   - `READ UNCOMMITTED` — allows dirty reads, non-repeatable reads, phantoms.
   - `READ COMMITTED` — prevents dirty reads (Postgres default).
   - `REPEATABLE READ` — also prevents non-repeatable reads. In Postgres, also prevents phantom reads via snapshot isolation.
   - `SERIALIZABLE` — prevents all anomalies; transactions appear fully serial. May abort with serialization errors that the app must retry.

2. **Explain MVCC.**
   - Multi-Version Concurrency Control. Each row has multiple versions tagged with transaction IDs. Readers see a consistent snapshot of the database as of their transaction's start; writers create new versions. No read locks. Postgres's `VACUUM` cleans up obsolete versions.

3. **When would you denormalize? Give a concrete example.**
   - Read-heavy workloads where joins dominate cost. Example: an analytics events table where you store `country_name` directly instead of `country_id`, accepting that updating a country name requires touching many rows. Denormalize only after measuring.

4. **What's the difference between a B-tree, GIN, and BRIN index? When to use each?**
   - B-tree: sorted tree, ideal for `=`, ranges, `ORDER BY`. The default. GIN: inverted index, one row → many keys. Best for arrays, JSONB, full-text. BRIN: stores per-block-range summaries, tiny on disk. Best for huge naturally-ordered tables (logs, time series).

5. **How do you handle a deadlock?**
   - The DB detects the cycle and aborts one transaction. Mitigations: (1) always acquire locks in the same order across transactions, (2) keep transactions short, (3) catch deadlock errors in app code and retry, (4) use lower isolation level if business logic permits.

6. **Explain N+1 queries from the database's perspective.**
   - Application-side anti-pattern: fetch N parents in 1 query, then issue 1 follow-up query per parent (= N more queries). The fix is one query with a join, or batched fetches grouped by ID. ORMs like SQLAlchemy / Hibernate / Drizzle have eager loading helpers.

7. **What does a query plan look like, and how do you read it?**
   - A tree of operators — Seq Scan, Index Scan, Hash Join, Merge Join, Nested Loop, Sort, Aggregate. Each node has estimated cost, estimated rows, and (with `ANALYZE`) actual rows + time. You read top-down, but execution is bottom-up: leaf nodes feed parents. Look for: Seq Scans on big tables, large `Rows Removed by Filter`, `Sort` spilling to disk.

8. **What is `SELECT ... FOR UPDATE SKIP LOCKED` good for?**
   - Implementing a job queue. Workers atomically pick a row and lock it; concurrent workers see *only the unlocked rows*, eliminating contention. Combined with `LIMIT 1`, this is the canonical Postgres "give me the next job" pattern.

9. **Explain partitioning and when it helps.**
   - Splitting a logical table into many physical sub-tables by range / list / hash. Helps when: (1) tables are huge (≥100M rows), (2) most queries naturally filter by the partition key (e.g. by month), (3) you need cheap "drop old data" via `DROP TABLE partition_x`. Smaller per-partition indexes also improve cache locality.

10. **Walk me through a RAG pipeline that uses Postgres.**
    - Ingest: chunk documents, embed each chunk with an embeddings model (OpenAI / Voyage / Cohere). Store: `INSERT INTO documents (content, embedding) VALUES ($1, $2)` with `vector(1536)`. Index: `CREATE INDEX ... USING hnsw (embedding vector_cosine_ops)`. Query: embed the user question, run `SELECT ... ORDER BY embedding <=> $query_embedding LIMIT k`. Construct: feed top-K chunks as context to Claude / GPT. Optionally combine with a full-text predicate for hybrid search.

11. **How do you do safe schema migrations in production?**
    - Tools: Flyway / Liquibase / Atlas / Alembic / Drizzle Kit — every change is a versioned, code-reviewed file. Patterns: avoid blocking locks (use `CREATE INDEX CONCURRENTLY`), do `ALTER TABLE` in steps (add nullable → backfill → make NOT NULL), always have a forward + rollback plan, run on a staging copy first, monitor during deploy.

12. **What's the difference between a view and a materialized view?**
    - View: a saved query — runs every time you select from it. Always fresh, no extra storage. Materialized view: stores the result like a real table, refreshed manually (or via TimescaleDB continuous aggregates). Trades freshness for speed.

</details>

---

## Practice Projects

You don't truly know SQL until you've shipped real projects against real data. Each project below builds skills from multiple phases and produces something you can put on your portfolio. **Do them in order — each is harder than the last.**

> [!TIP]
> Push every project to GitHub with a proper README, the schema (`schema.sql`), and a "questions answered" section showing the queries you wrote. A junior portfolio with 5 polished SQL projects beats a CS degree with no projects.

### Project 1: Library Database (Pure SQL Schema + Queries)
![Phase 1-5](https://img.shields.io/badge/After-Phase%201--5-green)

**What you'll build:** Design a small library database (books, authors, members, loans). Write the schema with proper types, primary keys, foreign keys, and `NOT NULL` constraints. Seed it with realistic data. Answer 15+ business questions in SQL: "most-loaned book this month," "members with overdue loans," "top 5 authors by total checkouts."

**Skills practiced:** DDL, types, constraints, `INSERT`, `SELECT`, `WHERE`, `JOIN`, `GROUP BY`, `ORDER BY`, `LIMIT`.

**Stretch:** Add `JSONB` for book metadata. Add a `genre` enum. Add a check constraint that prevents lending the same copy twice simultaneously.

---

### Project 2: E-Commerce Analytics Queries
![Phase 5-7](https://img.shields.io/badge/After-Phase%205--7-yellow)

**What you'll build:** Use a public e-commerce dataset (Olist, Northwind, or generate one with [Mockaroo](https://www.mockaroo.com/)). Write a `analytics.sql` file containing 25+ queries: monthly revenue by country, top-N products per category, repeat customers, churn cohort, basket analysis (items often bought together), running totals, month-over-month growth.

**Skills practiced:** Joins, aggregations, CTEs, window functions, `LAG`/`LEAD`, ranking, date functions.

**Stretch:** Build a Metabase / Superset dashboard on top. Schedule a `pg_dump` nightly backup.

---

### Project 3: SQL-Backed Task Manager API
![Phase 8-10](https://img.shields.io/badge/After-Phase%208--10-yellow)

**What you'll build:** A real REST API for a task manager. Choose any backend language ([Python](python.md) FastAPI, [Node](javascript.md) Express, [Java](java.md) Spring). Schema: `users`, `projects`, `tasks` with proper FKs and indexes. Endpoints: signup, login, CRUD on tasks, list-by-project, search. All migrations via Alembic / Flyway / Drizzle Kit. JWT auth.

**Skills practiced:** Schema design, indexes, transactions, migrations, ORM or raw SQL, parameterized queries (no SQL injection!), `EXPLAIN` to verify queries hit indexes.

**Stretch:** Deploy to Vercel / Fly.io / Railway with a managed Postgres (Neon / Supabase). Add `pg_stat_statements` and screenshot your slowest query.

---

### Project 4: Database Performance Tuning Lab
![Phase 10](https://img.shields.io/badge/After-Phase%2010-yellow)

**What you'll build:** Take an existing slow database (or generate one with 10M+ fake rows). Identify the 5 slowest queries with `pg_stat_statements`. For each: capture the `EXPLAIN ANALYZE` plan, identify the bottleneck (sequential scan, missing index, bad statistics, etc.), add the right index or rewrite the query, capture the *new* plan and timing. Document the before/after in a Markdown report.

**Skills practiced:** `EXPLAIN ANALYZE`, B-tree / partial / covering indexes, query rewriting, statistics, `pg_stat_statements`.

**Stretch:** Set up `pgBadger` and produce a weekly performance report. Add a CI test that runs `EXPLAIN` and fails if any critical query goes back to a Seq Scan.

---

### Project 5: Real-Time Analytics with Window Functions
![Phase 7](https://img.shields.io/badge/After-Phase%207-red)

**What you'll build:** Pick a real public dataset (NYC Taxi, Stack Overflow, GitHub events). Load 100M+ rows into Postgres or DuckDB. Write 10 advanced analytical queries using window functions: per-user time-since-last-event, sessionization, retention cohorts, percentile-based outlier detection, top-N-per-group, moving averages, leaderboards.

**Skills practiced:** Window functions, `PARTITION BY`, frames, `LAG`/`LEAD`, percentiles, large-data tactics, partitioning, materialized views.

**Stretch:** Migrate the same queries to BigQuery or Snowflake free tier. Compare execution times. Add dbt models.

---

### Project 6: ETL Pipeline (CSV → Postgres → Warehouse)
![Phase 8-12](https://img.shields.io/badge/After-Phase%208--12-red)

**What you'll build:** Build a daily pipeline. Step 1: download a public CSV / API every night. Step 2: load into a staging Postgres schema with idempotent upserts (`ON CONFLICT`). Step 3: dbt models transform staging → mart (a star schema). Step 4: a Metabase dashboard visualizes the mart. Schedule via GitHub Actions / Airflow / Prefect.

**Skills practiced:** Idempotent inserts, transactions, dbt, schema design (fact/dim tables), scheduling, error handling, monitoring.

**Stretch:** Add data-quality tests with dbt. Push the warehouse copy to BigQuery / Snowflake / DuckDB.

---

### Project 7: Multi-Tenant SaaS Schema (Production-Style)
![Phase 9-12](https://img.shields.io/badge/After-Phase%209--12-red)

**What you'll build:** Design a multi-tenant database for a SaaS app (think: a Linear / Notion clone). Pick a strategy (shared schema with `tenant_id`, schema-per-tenant, or DB-per-tenant) and justify it. Add Row Level Security (RLS) so a tenant cannot see another tenant's rows even if the app has a bug. Migrations, seed data, and a real test suite.

**Skills practiced:** Advanced schema design, tenancy, indexes with `tenant_id` leading, RLS policies, migrations, testing.

**Stretch:** Add audit logging via triggers. Add per-tenant rate limiting in SQL.

---

### Project 8: AI / RAG Capstone with Postgres + pgvector
![Phase 13](https://img.shields.io/badge/After-Phase%2013-red)

**What you'll build:** Your graduation project. A web app where users upload PDFs / paste URLs / ask questions about their own documents. Pipeline: chunk → embed (with [OpenAI](https://platform.openai.com/) or [Voyage AI](https://www.voyageai.com/)) → store in Postgres with `pgvector` and an HNSW index → at query time, embed the question, retrieve top-K chunks using cosine distance, send to **Claude** ([Anthropic SDK](https://docs.anthropic.com/en/api/client-sdks)) with **streaming**. Add **hybrid search** — combine vector similarity with full-text search and weight them. Backend in your favorite language, simple frontend, deployed to Neon / Supabase + Vercel / Fly.io. End-to-end tests.

**Skills practiced:** Everything — schema design, indexes, vectors, full-text search, transactions, performance, EXPLAIN, hybrid retrieval, deployment. **This is portfolio gold for any 2026 interview.**

**Stretch:** Add re-ranking with a cross-encoder. Add per-user document scoping with RLS. Add an LLM-driven SQL agent that answers natural-language analytics questions over the user's data ("show me my top 5 documents by view count").

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [PostgreSQL Documentation](https://www.postgresql.org/docs/current/) | The gold standard of database documentation. Long, thorough, beautifully written |
| [PostgreSQL Tutorial (postgresqltutorial.com)](https://www.postgresqltutorial.com/) | Friendly, example-driven tutorials for every Postgres feature |
| [MySQL Reference Manual](https://dev.mysql.com/doc/refman/) | Comprehensive MySQL docs |
| [SQLite Documentation](https://sqlite.org/docs.html) | Surprisingly readable; small enough to read end-to-end |
| [SQL Server Docs](https://learn.microsoft.com/en-us/sql/sql-server/) | Microsoft's docs for T-SQL and SQL Server |
| [Oracle SQL Reference](https://docs.oracle.com/en/database/oracle/oracle-database/) | Comprehensive Oracle / PL-SQL docs |
| [Modern SQL (modern-sql.com)](https://modern-sql.com/) | What every database supports of the modern SQL standard |
| [Use The Index, Luke](https://use-the-index-luke.com/) | The free online textbook on indexes and performance |

### Books

| Book | Why Read |
|------|---------|
| [SQL for Smarties (Joe Celko)](https://www.elsevier.com/books/joe-celkos-sql-for-smarties/celko/978-0-12-800761-7) | Deep, opinionated SQL idioms from a 40-year veteran |
| [Designing Data-Intensive Applications (Martin Kleppmann)](https://dataintensive.net/) | Required reading for anyone building backend systems. Storage engines, replication, transactions, distributed data |
| [The Art of PostgreSQL (Dimitri Fontaine)](https://theartofpostgresql.com/) | The book to read after this syllabus. Teaches you to think Postgres-natively |
| [PostgreSQL: Up and Running (Regina Obe & Leo Hsu)](https://www.oreilly.com/library/view/postgresql-up-and/9781492092346/) | Practical, recipe-based intro |
| [Database Internals (Alex Petrov)](https://www.databass.dev/) | The book on how databases actually work under the hood |
| [SQL Performance Explained (Markus Winand)](https://sql-performance-explained.com/) | The companion book to Use The Index, Luke |
| [Learning SQL (Alan Beaulieu, O'Reilly)](https://www.oreilly.com/library/view/learning-sql-3rd/9781492057604/) | Friendly third-edition refresher of SQL fundamentals |
| [SQL Antipatterns (Bill Karwin)](https://pragprog.com/titles/bksap1/sql-antipatterns-volume-1/) | What *not* to do — and why |
| [High Performance MySQL (Schwartz, Zaitsev, Tkachenko)](https://www.oreilly.com/library/view/high-performance-mysql/9781492080503/) | The reference for tuning MySQL |

### Free Courses

| Course | What Makes It Special |
|--------|----------------------|
| [Stanford — Databases (DB5 series)](https://www.edx.org/learn/databases/stanford-university-databases-relational-databases-and-sql) | The classic Stanford course — relational model, SQL, indexing, transactions |
| [CMU 15-445 / 15-645 (Andy Pavlo)](https://15445.courses.cs.cmu.edu/) | Intro / Advanced Database Systems. The legendary university lecture series, on YouTube and free |
| [SQLBolt](https://sqlbolt.com/) | Bite-sized free interactive lessons |
| [Mode SQL Tutorial](https://mode.com/sql-tutorial/) | Practical analyst-flavored SQL — from joins through window functions |
| [Khan Academy — Intro to SQL](https://www.khanacademy.org/computing/computer-programming/sql) | Friendly free intro for total beginners |
| [Codecademy — Learn SQL](https://www.codecademy.com/learn/learn-sql) | In-browser interactive SQL course |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Hussein Nasser](https://www.youtube.com/@hnasr) | The best database YouTuber. Internals, indexes, transactions, scaling |
| [Database Star (Ben Brumm)](https://www.youtube.com/@DatabaseStar) | Clear, structured tutorials for SQL beginners and intermediates |
| [Andy Pavlo (CMU lectures)](https://www.youtube.com/@CMUDatabaseGroup) | Full database systems courses, free, world-class |
| [Fireship — SQL in 100 seconds](https://www.youtube.com/watch?v=zsjvFFKOm3c) | The lightning-fast intro |
| [TechWorld with Nana — SQL Tutorial](https://www.youtube.com/@TechWorldwithNana) | Crisp tutorials including DBs in Docker |
| [Bryan Cantrill — Postgres Internals](https://www.youtube.com/results?search_query=bryan+cantrill+postgres) | Deep, advanced, occasionally hilarious |
| [Crunchy Data YouTube](https://www.youtube.com/@CrunchyData) | Postgres tips and feature deep dives |

### Practice / Challenges

| Site | What It Offers |
|------|----------------|
| [LeetCode SQL](https://leetcode.com/studyplan/top-sql-50/) | Curated 50-problem SQL study plan; the standard interview prep |
| [HackerRank SQL](https://www.hackerrank.com/domains/sql) | Structured challenges from easy to advanced |
| [PgExercises](https://pgexercises.com/) | Free interactive Postgres exercises with a sample club database |
| [SQLZoo](https://sqlzoo.net/) | Long-running interactive SQL tutorial |
| [DataLemur](https://datalemur.com/) | SQL interview questions from real companies (Meta, Amazon, etc.) |
| [StrataScratch](https://www.stratascratch.com/) | Real-data SQL interview questions |
| [SQLPad / SQLBolt](https://sqlbolt.com/) | Beginner-friendly browser-based exercises |
| [Mode Practice (Mode Analytics)](https://mode.com/sql-tutorial/sql-business-analytics-training/) | Real-world analyst questions over Mode's playgrounds |
| [Advent of SQL](https://adventofsql.com/) | Yearly December puzzle series in pure SQL |

### Tools You Should Try

| Tool | Why You Need It |
|------|-----------------|
| [DBeaver](https://dbeaver.io/) | Free, all-databases GUI |
| [TablePlus](https://tableplus.com/) | Beautiful native client (Mac/Win/Linux) |
| [DataGrip](https://www.jetbrains.com/datagrip/) | The premium IDE for SQL |
| [pgcli](https://www.pgcli.com/) / [mycli](https://www.mycli.net/) | Modern CLI clients with autocomplete |
| [Postgres Docker image](https://hub.docker.com/_/postgres) | One command to spin up a Postgres for testing |
| [DuckDB CLI](https://duckdb.org/docs/api/cli) | "SQLite for analytics" — incredible for ad-hoc CSV/Parquet queries |
| [pgvector](https://github.com/pgvector/pgvector) | Vector similarity search for AI |
| [explain.depesz.com](https://explain.depesz.com/) | Visualize EXPLAIN plans |
| [pg_stat_statements](https://www.postgresql.org/docs/current/pgstatstatements.html) | Built-in slow-query log |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [SQL Cheat Sheet (SQLTutorial)](https://www.sqltutorial.org/sql-cheat-sheet/) | One-page PDF — every clause and operator |
| [PostgreSQL Cheat Sheet (PostgreSQL Tutorial)](https://www.postgresqltutorial.com/postgresql-cheat-sheet/) | Postgres-specific reference |
| [Use The Index, Luke — PDF Cheat Sheet](https://use-the-index-luke.com/sql/where-clause/cheat-sheet) | Index-tuning quick reference |
| [JOOQ SQL Style Guide](https://www.jooq.org/doc/latest/manual/sql-building/sql-style-guide/) | Opinionated, clean SQL formatting rules |
| [Markus Winand's "modern SQL" talks](https://modern-sql.com/slides) | Slide decks on lesser-known modern SQL features |
| [Postgres Wiki — Cheat Sheet](https://wiki.postgresql.org/wiki/Cheatsheet) | Community-maintained Postgres reference |

### Newsletters & Podcasts

| Resource | Format |
|----------|--------|
| [Postgres Weekly](https://postgresweekly.com/) | The weekly Postgres newsletter |
| [DB Weekly](https://dbweekly.com/) | News across all databases |
| [Crunchy Data Blog](https://www.crunchydata.com/blog) | Postgres tips, deep dives, news |
| [Citus Data Blog](https://www.citusdata.com/blog/) | Postgres scaling and internals |
| [Use The Index, Luke! Newsletter](https://use-the-index-luke.com/) | Index tuning insights from Markus Winand |
| [Database Engineering Podcast](https://www.dataengineeringpodcast.com/) | Long-form interviews with DB engineers |
| [Postgres FM](https://postgres.fm/) | Twice-weekly Postgres podcast |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — SQL](https://roadmap.sh/sql) | Interactive SQL learning path with progress tracking |
| [roadmap.sh — PostgreSQL DBA](https://roadmap.sh/postgresql-dba) | The full DBA roadmap |
| [roadmap.sh — Data Engineer](https://roadmap.sh/data-engineer) | SQL-heavy data engineering roadmap |
| [roadmap.sh — AI Engineer](https://roadmap.sh/ai-engineer) | The 2026 must-have for the AI specialization (includes vector DBs) |

---

[Back to Main Syllabus](../README.md)

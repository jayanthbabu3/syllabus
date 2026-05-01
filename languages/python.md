# Python Syllabus

A complete, structured learning path for Python — your one-stop guide from your first `print("hello")` to building web APIs, automation scripts, data pipelines, machine learning models, and AI agents. Whether you have never written code before, or you already use Python at work and want to fill the gaps, this syllabus walks you through every concept in the right order, explains *why* each matters, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-20 Weeks](https://img.shields.io/badge/Duration-14--20%20Weeks-blue)
![Topics: 15 Phases](https://img.shields.io/badge/Topics-15%20Phases-orange)
![Python: 3.13+](https://img.shields.io/badge/Python-3.13%2B-3776AB)

---

## Table of Contents

- [What is Python?](#what-is-python)
- [Why Learn Python in 2026?](#why-learn-python-in-2026)
- [How Python Runs](#how-python-runs)
- [Who This Syllabus Is For](#who-this-syllabus-is-for)
- [Learning Paths](#learning-paths)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Data Types & Type Conversion](#phase-2-data-types--type-conversion)
- [Phase 3: Operators & Control Flow](#phase-3-operators--control-flow)
- [Phase 4: Functions & Modules](#phase-4-functions--modules)
- [Phase 5: Data Structures](#phase-5-data-structures)
- [Phase 6: Strings & Regular Expressions](#phase-6-strings--regular-expressions)
- [Phase 7: File I/O & Error Handling](#phase-7-file-io--error-handling)
- [Phase 8: Object-Oriented Programming](#phase-8-object-oriented-programming)
- [Phase 9: Advanced Python](#phase-9-advanced-python)
- [Phase 10: Concurrency, Parallelism & Async](#phase-10-concurrency-parallelism--async)
- [Phase 11: Standard Library Deep Dive](#phase-11-standard-library-deep-dive)
- [Phase 12: Testing, Tooling & Modern Project Setup](#phase-12-testing-tooling--modern-project-setup)
- [Phase 13: Web Development & APIs](#phase-13-web-development--apis)
- [Phase 14: Data Science, ML & AI](#phase-14-data-science-ml--ai)
- [Phase 15: What's Next? (Specializations & Deploy)](#phase-15-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is Python?

**Python is a high-level, general-purpose programming language famous for being readable, beginner-friendly, and ridiculously versatile.** A web server, a data-analysis notebook, an AI agent, a Raspberry Pi robot, a desktop GUI, a script that renames 10,000 files, the system that lands a SpaceX rocket — all written in the same language, with the same syntax, by people of every skill level.

Created by **Guido van Rossum** in 1991 and named after *Monty Python's Flying Circus* (not the snake), Python was designed around one philosophy: **code is read more often than it is written**. Run `import this` in any Python REPL and you'll see The Zen of Python — 19 aphorisms like "Readability counts", "Explicit is better than implicit", "There should be one — and preferably only one — obvious way to do it."

In simple words:

- Python looks almost like English (`if score > 50: print("pass")`).
- No semicolons, no curly braces — **indentation defines structure**.
- One language, dozens of careers — web dev, data science, ML/AI, DevOps, security, scripting, scientific computing.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 1991 | Python 0.9 | First public release by Guido van Rossum at CWI (Netherlands). |
| 2000 | Python 2.0 | List comprehensions, garbage collection, Unicode. The version most early adopters learned. |
| 2008 | Python 3.0 | Major rewrite — backward incompatible. Print became a function, `str` became Unicode by default. |
| 2020 | Python 2 EOL | Python 2 retired. Everyone is on Python 3 now. |
| 2024 | Python 3.13 | Free-threaded build (no-GIL preview!), JIT preview, better error messages. |
| 2025 | Python 3.14 | Continued no-GIL work, PEP 750 (template strings), faster startup. |

> [!IMPORTANT]
> "Python" today means **Python 3** (3.13+ in 2026). Anyone teaching you Python 2 is teaching you a retired language. Always start a new project with the latest stable Python.

### What Makes Python Special

- **Indentation is the syntax.** No `{}`, no `;` — whitespace is meaningful. Forces consistent style across teams.
- **"Batteries included" standard library.** HTTP, JSON, regex, dates, math, threading, sockets — all in the box.
- **The world's biggest scientific & ML ecosystem.** NumPy, Pandas, scikit-learn, PyTorch, TensorFlow, Jupyter — Python is *the* default for data work.
- **Glue language.** Wraps C, C++, Rust, Fortran libraries. Python is fast at being slow at the right things.
- **Most-taught first language on Earth.** Used in nearly every CS curriculum, every coding bootcamp, every "intro to AI" course.

---

## Why Learn Python in 2026?

| Reason | What It Means |
|--------|---------------|
| **#1 language for AI / ML** | Every major LLM library (OpenAI, Anthropic, LangChain, LlamaIndex, PyTorch, TensorFlow, HuggingFace) is Python-first. Want to build with AI? Learn Python. |
| **#1 language for data science** | NumPy, Pandas, Polars, Matplotlib, Jupyter, scikit-learn, statsmodels — the entire data ecosystem. |
| **Top 2 most popular language** | Tied with JavaScript at the very top of TIOBE, GitHub, StackOverflow rankings, year after year. |
| **Backend web development** | Django (Instagram, Pinterest), FastAPI (modern APIs), Flask (micro-services). |
| **DevOps & automation** | Ansible, SaltStack, internal tooling at almost every tech company. Replace bash with Python and your scripts become readable. |
| **Scripting & glue** | Rename files, scrape sites, talk to APIs, generate reports. Python is the duct tape of modern computing. |
| **Pays well** | Average Python dev salary in 2026: **$110k–$200k** (US, with ML uplift), **₹10L–₹50L** (India). |
| **Beginner-friendliest mainstream language** | If you've never coded, Python lets you build *useful* programs in days, not months. |

---

## How Python Runs

Understanding what happens when you type `python script.py` makes the rest of the syllabus easier.

```
   ┌─────────────────────────┐
   │   You write Python      │  script.py — human-readable text
   └────────────┬────────────┘
                │ python script.py
                ▼
   ┌─────────────────────────┐
   │   Compile to bytecode   │  .pyc files in __pycache__
   │   (CPython compiler)    │  Platform-independent instructions
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │   Python Virtual        │  Reads bytecode and executes it
   │   Machine (PVM)         │  one operation at a time
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │   OS / hardware         │  Output to console, files, network
   └─────────────────────────┘
```

**Key implementations:**

| Implementation | What It Is |
|----------------|-----------|
| **CPython** (default) | The reference implementation, written in C. When people say "Python" they usually mean CPython. |
| **PyPy** | A faster Python with a JIT compiler. 4–10× faster on pure-Python code. Great for hot loops. |
| **MicroPython** | Tiny Python for microcontrollers (ESP32, Pico). Runs on devices with kilobytes of RAM. |
| **Pyodide** | CPython compiled to WebAssembly. Runs Python *in the browser*. |
| **Free-threaded CPython** (3.13+) | Experimental no-GIL build — true parallel threads. |

> [!TIP]
> Python is **interpreted, dynamically typed, garbage-collected**. That means you don't compile before running, you don't declare types, and you don't manually free memory. The price you pay is speed — Python is roughly 50–100× slower than C for tight loops. For 99% of work, you don't notice. For the 1% that matters, you call into C/Rust libraries (NumPy, Polars) or use PyPy.

---

## Who This Syllabus Is For

| You Are | What You Get |
|---------|--------------|
| **Absolute beginner** — never coded before | Start at Phase 1. Each concept is explained from scratch. Python is *the* best first language. |
| **Coming from another language** (JS / Java / C++) | Skim Phase 1–4, focus on Phase 5 (Pythonic data structures), Phase 8 (OOP differs), Phase 9 (decorators/generators are unique), Phase 10 (the GIL). |
| **Self-taught dev with gaps** | Use [Common Mistakes](#common-mistakes) as a self-audit, then re-do the failing phase. |
| **Bootcamp grad / Junior dev** | Phases 9, 10, 12 are usually weak spots. Then pick a specialization (Phase 13 web, Phase 14 data/ML). |
| **Aspiring data scientist** | Phases 1–9 fast → **Phase 14** is your home. Pair with a math/stats course. |
| **Aspiring ML / AI engineer** | Phases 1–10 → **Phase 14** (PyTorch + LLM SDKs). Build the AI capstone project. |
| **Backend / Web dev moving to Python** | Phases 1–9 → **Phase 13** (FastAPI + SQLAlchemy). |
| **DevOps / automation** | Phases 1–7 → Phase 11 (stdlib) + Phase 12 (tooling). Skip data/web phases. |
| **Mid / Senior dev preparing for interviews** | Phase 9 + Phase 10 + [Interview Questions](#interview-questions). |

---

## Learning Paths

Pick the path that matches your goal. Each path tells you which phases to do, in what order, and roughly how long it takes.

### Path A — Zero to First Job (16–20 weeks)
Fresher with no coding background, target: junior backend / data role.

```
Phase 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9 → 12 → 13 → 15
```
- Build Practice Projects 1, 2, 3, 5.
- After Phase 9, start your specialization (web or data).
- Push every project to GitHub with a README.

### Path B — Data Scientist Track (12–16 weeks)
Goal: get hired analyzing data, building models.

```
Phase 1 → 2 → 3 → 5 → 6 → 7 → 8 → 9 → 11 → 14 → 15 (data specialization)
```
- Skip Phase 13 (web). Focus all project effort on Phase 14.
- Pair with a math/stats course (linear algebra, probability, statistics).
- Build Project 6 (Data Analysis Notebook) and Project 7 (ML Trainer).

### Path C — AI / LLM Engineer (10–14 weeks, post-Python basics)
Already know Python basics, want to build with LLMs.

```
Phase 9 → 10 (async!) → 12 → 13 (FastAPI) → 14 (LLM SDKs + RAG) → Project 8 (AI capstone)
```
- Master `async`/`await` — every LLM SDK is async-first.
- Learn one LLM provider deeply ([Anthropic](https://docs.anthropic.com/) or [OpenAI](https://platform.openai.com/docs/)).
- Build Project 8 (AI Chatbot with RAG) — most hireable demo in 2026.

### Path D — Backend / API Engineer (12–16 weeks)
Goal: ship production REST/GraphQL APIs with Python.

```
All phases 1–13 → Project 5 (FastAPI + auth + DB) → Phase 15 (deployment)
```
- Master FastAPI + SQLAlchemy + Alembic + Pydantic.
- Pair with the [SQL Syllabus](sql.md) and [Docker Syllabus](docker.md).

### Path E — DevOps / Automation (6–10 weeks)
Replace bash with Python.

```
Phase 1 → 2 → 3 → 4 → 5 → 7 → 11 → 12
```
- Focus on `pathlib`, `subprocess`, `argparse`/`typer`, `paramiko`, logging.
- Skip Phases 8–10 unless your team uses them.

---

## Prerequisites

> [!NOTE]
> Python requires **zero programming experience**. It's one of the best first languages — readable syntax, gentle learning curve, used everywhere.

- A computer (Windows, Mac, or Linux)
- A terminal (Terminal on Mac/Linux, PowerShell or [Windows Terminal](https://aka.ms/terminal) on Windows)
- A code editor — [VS Code](https://code.visualstudio.com/) recommended (free, best Python support via the Python extension)
- Comfort with running commands — `cd`, `ls`, `python script.py`
- A [GitHub account](https://github.com/) to store your code from day one

---

## How to Use This Syllabus

1. **Don't skip phases.** Each one builds on the last. If Phase 5 (data structures) is shaky, Phase 9 (advanced) will feel impossible.
2. **Type the code yourself.** Copy-pasting from tutorials gives the illusion of learning. Type every example by hand.
3. **Use the REPL constantly.** Anytime you wonder "what does X do?", open `python` in a terminal and try it. Faster than Googling.
4. **Always use a virtual environment.** `python -m venv .venv` per project. Never install packages globally.
5. **Build the project at the end of each phase block** before moving on. Reading is not the same as doing.
6. **Use type hints from day one.** They make every editor smarter and catch bugs you'd otherwise hit at runtime.
7. **Commit to GitHub** from your first project. Future you (and future employers) will thank you.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write your first Python program and understand the basics.

**What this phase is about.** Before you can write Python, you need to install it, know how to run a script vs use the interactive REPL, and understand the very smallest unit of a program — a variable. This phase covers installation (the right way — including `pyenv` and `uv` for managing Python versions), your first `print()`, comments, and Python's most beloved feature: **f-strings** for clean string formatting.

**Why it matters.** Every line of Python builds on the muscle memory you develop in this phase. Skipping installation hygiene (no virtual env, wrong Python version) causes 80% of beginner pain in later phases. Get this right and the rest flies.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Python | High-level, interpreted language. Used for web, data, AI, automation, scripting — everywhere |
| 2 | Installation | Install Python 3.13+. Verify with `python --version`. Why you should use `pyenv` (or `uv`) instead of system Python |
| 3 | The Python Interpreter | REPL mode (`python` in terminal) for quick experiments vs script mode (`python app.py`) for real programs |
| 4 | VS Code Setup | Install the Python extension, Pylance, the Black formatter. Configure auto-format on save |
| 5 | Variables & Naming | `name = "Alice"` — no type declaration needed. PEP 8 conventions: `snake_case`, `CONSTANTS`, `_private` |
| 6 | Basic Output: `print()` | `print()`, `sep=`, `end=`, printing multiple values |
| 7 | Basic Input: `input()` | `input("Name: ")` — always returns a string. Convert with `int()`, `float()` |
| 8 | f-strings | `f"Hello, {name}!"` — modern string formatting, expressions, formatting specs (`{x:.2f}`) |
| 9 | Comments & Docstrings | `#` for single-line, `"""triple-quoted"""` for module/function/class docstrings |
| 10 | The Zen of Python | `import this` — Python's philosophy in 19 lines |
| 11 | Running Python Files | `python script.py`, shebangs, making scripts executable on Mac/Linux |

> [!TIP]
> **f-strings** (Python 3.6+) are the standard for string formatting in 2026 — they're the most readable and the fastest:
> ```python
> name = "Alice"
> age = 30
> print(f"Hello, {name}! You are {age} years old.")
> # f-strings can contain any expression
> print(f"Next year you'll be {age + 1}")
> # Format specs: 2 decimal places, comma thousands, percent
> print(f"Pi is {3.14159:.2f}, sales {1_000_000:,}, tax {0.08:.0%}")
> ```

<details>
<summary><strong>Quick Reference: PEP 8 Naming</strong></summary>

| Item | Convention | Example |
|------|-----------|---------|
| Variables, functions | `snake_case` | `user_name`, `calculate_tax()` |
| Classes | `PascalCase` | `UserAccount`, `HTTPClient` |
| Constants | `SCREAMING_SNAKE_CASE` | `MAX_RETRIES`, `API_KEY` |
| "Private" | `_leading_underscore` | `_internal_helper` |
| "Strongly private" | `__double_leading` | `__name_mangled` (rare) |
| Modules / files | `snake_case.py` | `user_service.py` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Python and run `python --version` successfully
- [ ] Run a script from the terminal and from the REPL
- [ ] Declare variables of different types and use f-strings with format specs
- [ ] Set up VS Code with the Python extension and auto-format on save

</details>

---

## Phase 2: Data Types & Type Conversion

![Phase](https://img.shields.io/badge/Phase-2%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Master Python's built-in types — they show up in every line you'll ever write.

**What this phase is about.** Every value in Python belongs to a **type**. The built-in types come in two categories: **scalars** (`int`, `float`, `complex`, `bool`, `str`, `bytes`, `None`) and **collections** (`list`, `tuple`, `set`, `dict`, `frozenset`). The most important distinction is **mutable vs immutable** — mutable objects (lists, dicts, sets) can be changed in place; immutable objects (strings, tuples, numbers) can't. This phase also covers conversions, the `type()`/`isinstance()` checks, and Python's **type hint system** that makes editors and team-mates smarter.

**Why it matters.** A surprising amount of Python "weirdness" — `a = b = []; a.append(1)` and now `b == [1]`, `True + True == 2`, `0.1 + 0.2 != 0.3`, `"" == False` is `False` (no, Python isn't JS) — all comes from type behavior. Get the model right and the language stops surprising you.

### 2.1 — Python's Built-in Types

| Type | Mutable? | Example | Used For |
|------|:--------:|---------|----------|
| `int` | No | `42`, `-7`, `1_000_000` | Whole numbers (arbitrary precision!) |
| `float` | No | `3.14`, `1e-3` | Decimals (IEEE 754 double) |
| `complex` | No | `2+3j` | Complex numbers |
| `bool` | No | `True`, `False` | Booleans (subtype of `int`) |
| `str` | No | `"hello"`, `'a'`, `"""multi"""` | Text (Unicode by default) |
| `bytes` | No | `b"hello"` | Raw binary data |
| `None` | No | `None` | Absence of a value |
| `list` | **Yes** | `[1, 2, 3]` | Ordered, changeable sequence |
| `tuple` | No | `(1, 2, 3)` | Ordered, fixed sequence |
| `set` | **Yes** | `{1, 2, 3}` | Unique, unordered values |
| `frozenset` | No | `frozenset({1,2})` | Immutable set (hashable) |
| `dict` | **Yes** | `{"a": 1}` | Key-value pairs |

### 2.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Numbers | `int` (arbitrary precision!), `float` (IEEE 754), `complex`. Operators: `+ - * / // % **` |
| 2 | Number Precision | Why `0.1 + 0.2 != 0.3` (IEEE 754). Use `decimal.Decimal` for money, `fractions.Fraction` for exact ratios |
| 3 | Booleans | `True`/`False`. Booleans are integers (`True + True == 2`). Truthy/falsy values |
| 4 | Strings | `str`, immutability, escape sequences, raw strings (`r"..."`), bytes (`b"..."`), encoding (UTF-8) |
| 5 | The Falsy Values | `False`, `0`, `0.0`, `""`, `[]`, `{}`, `()`, `set()`, `None` — and why they matter for `if` |
| 6 | `None` | Python's "no value." `None` is unique — always compare with `is`, not `==` |
| 7 | Type Checking | `type(x)`, `isinstance(x, int)`, `isinstance(x, (int, float))`. When to use which |
| 8 | Type Conversion | `int("42")`, `str(42)`, `float("3.14")`, `bool(0)`, `list("abc")` → `['a','b','c']` |
| 9 | Mutable vs Immutable | The single most important Python concept. Why `a = b = []` is a footgun |
| 10 | Variables Are References | All variables are *references* to objects. Assignment binds names; it doesn't copy |
| 11 | `id()` and `is` | Every object has a unique `id()`. `is` compares identity, `==` compares value |
| 12 | Type Hints (Intro) | `name: str = "Alice"`, `age: int = 30`, `items: list[int] = []`. Documentation + tooling, not enforced |
| 13 | Big Integers | Python `int` has no overflow — `2 ** 1000` works fine. Unique to Python in mainstream langs |

### 2.3 — Mutable vs Immutable: The Mental Model

```python
# IMMUTABLE — assignment creates a new object
a = "hello"
b = a            # b points to same string
a = a + " world" # a now points to a NEW string
print(b)         # "hello"  (unchanged)

# MUTABLE — methods modify the same object
x = [1, 2, 3]
y = x            # y points to SAME list
x.append(4)
print(y)         # [1, 2, 3, 4]  (changed!)

# To get a real copy:
y = x.copy()         # shallow copy
y = list(x)          # also shallow
import copy
y = copy.deepcopy(x) # deep copy (recursive)
```

> [!IMPORTANT]
> The **#1 bug for new Python developers** is mutating an object they thought they had copied. If you write `b = a` for a list/dict/set and modify one, both change — they're the same object. Always copy explicitly with `.copy()` or `copy.deepcopy()`.

### 2.4 — Type Conversion Cheatsheet

```python
int("42")        # 42
int("0xff", 16)  # 255 (hex)
int(3.7)         # 3 (truncates, doesn't round)
float("3.14")    # 3.14
str(42)          # "42"
bool(0)          # False
bool("")         # False
bool([])         # False
bool("False")    # True (non-empty string!)
list("abc")      # ['a', 'b', 'c']
list(range(3))   # [0, 1, 2]
tuple([1,2,3])   # (1, 2, 3)
set([1,1,2])     # {1, 2}
dict([("a",1)])  # {"a": 1}
```

<details>
<summary><strong>Quick Reference: Falsy Values</strong></summary>

```python
# Falsy — evaluate to False in `if`/`while`
False
None
0           # int
0.0         # float
0j          # complex
""          # empty string
[]          # empty list
()          # empty tuple
{}          # empty dict
set()       # empty set
range(0)    # empty range

# Everything else is truthy
"0"         # non-empty string → True
"False"     # non-empty string → True
[0]         # non-empty list  → True
```

</details>

<details>
<summary><strong>Quick Reference: Number Gotchas</strong></summary>

```python
0.1 + 0.2 == 0.3                # False — IEEE 754 floats
0.1 + 0.2                       # 0.30000000000000004
round(0.1 + 0.2, 1) == 0.3      # True

# Use Decimal for money:
from decimal import Decimal
Decimal("0.1") + Decimal("0.2") # Decimal('0.3')

# Big integers — no overflow
2 ** 1000  # giant number, no error

# Booleans are ints
True + True       # 2
sum([True, False, True])  # 2
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] List the 12 built-in types and which are mutable
- [ ] List the 9 falsy values from memory
- [ ] Explain the difference between `==` and `is`
- [ ] Predict the output of `a = b = []; a.append(1); print(b)`
- [ ] Convert between `int`, `str`, `float`, `list`, `set`, `dict`
- [ ] Use `Decimal` for exact decimal arithmetic

</details>

---

## Phase 3: Operators & Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions and repeat actions.

**What this phase is about.** Programs do two things: **make decisions** (if score > 50, pass; else fail) and **repeat work** (for every order, calculate tax). Python's control-flow constructs are tight and readable — `if/elif/else`, `for`, `while`, plus two superpowers: **comprehensions** (a one-line way to build lists/dicts/sets) and **structural pattern matching** (`match`/`case`, like a `switch` on steroids — Python 3.10+).

**Why it matters.** Comprehensions are *the* Pythonic idiom — using them instead of explicit loops marks you as someone who reads Pythonic code. `match/case` is the newest big addition to the language and increasingly common in interview questions. Master both here.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `elif` / `else` | Conditional branching: `if age >= 18:` — the colon and indentation are mandatory |
| 2 | Comparison Operators | `==`, `!=`, `<`, `>`, `<=`, `>=`. Chained: `0 < x < 10` (yes, that works!) |
| 3 | Logical Operators | `and`, `or`, `not` — short-circuit evaluation |
| 4 | Identity vs Equality | `is` (same object) vs `==` (same value). Use `is None`, never `== None` |
| 5 | Membership Operators | `in`, `not in` — works on lists, strings, dicts (checks keys), sets |
| 6 | Ternary Expression | `result = "pass" if score >= 50 else "fail"` |
| 7 | `for` Loops | `for item in iterable:` — iterate over lists, strings, ranges, dicts, files |
| 8 | `while` Loops | `while condition:` — repeat until condition is false. Avoid infinite loops |
| 9 | `break`, `continue`, `else` on loops | `break` exits, `continue` skips, `else` runs only if no break (rare but useful) |
| 10 | `range()` | `range(10)`, `range(1, 11)`, `range(0, 20, 2)` — generate number sequences |
| 11 | `enumerate()` & `zip()` | Loop with index (`enumerate`) or pair two iterables (`zip`) |
| 12 | List Comprehensions | `[x*2 for x in range(10) if x % 2 == 0]` — Pythonic list building |
| 13 | Dict & Set Comprehensions | `{k: v for k, v in items}`, `{x for x in items}` |
| 14 | Generator Expressions | `(x*2 for x in range(10))` — like list comp but lazy, memory-efficient |
| 15 | `match` / `case` (3.10+) | Structural pattern matching with destructuring — far beyond a switch statement |
| 16 | Walrus Operator (`:=`) | Assign-while-testing: `if (n := len(data)) > 10:` |

> [!IMPORTANT]
> **Indentation is not optional in Python** — it defines code blocks. Use 4 spaces (not tabs). Mixed indentation = `IndentationError`:
> ```python
> if True:
>     print("Indented with 4 spaces")
>     if True:
>         print("Nested — 8 spaces")
> ```

<details>
<summary><strong>Quick Reference: `match` / `case` (Python 3.10+)</strong></summary>

```python
def http_error(status):
    match status:
        case 200 | 201 | 204:
            return "OK"
        case 301 | 302:
            return "Redirect"
        case 400:
            return "Bad request"
        case 404:
            return "Not found"
        case 500 | 502 | 503:
            return "Server error"
        case _:                    # default
            return "Unknown"

# Destructuring — match's real superpower
match point:
    case (0, 0):              return "origin"
    case (x, 0):              return f"x-axis at {x}"
    case (0, y):              return f"y-axis at {y}"
    case (x, y):              return f"point ({x}, {y})"
    case _:                   return "not a point"
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a program using `if/elif/else` with chained comparisons
- [ ] Loop with `enumerate()` and `zip()` instead of `range(len(...))`
- [ ] Convert a `for` loop into an equivalent list comprehension
- [ ] Use `match`/`case` to destructure a tuple or dict
- [ ] Use the walrus operator (`:=`) in an `if` or `while` condition

</details>

---

## Phase 4: Functions & Modules

![Phase](https://img.shields.io/badge/Phase-4%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Write reusable code with functions, organize it into modules and packages.

**What this phase is about.** Functions are reusable units of behavior — *take inputs, return an output*. Python takes them seriously: functions are **first-class objects** (you can pass them around, store them, return them), they support default + keyword + variadic arguments (`*args`, `**kwargs`), and they document themselves with **type hints** + **docstrings**. Modules and packages are how you split a big program across many files. Virtual environments are how you keep each project's dependencies separate — non-negotiable in real Python work.

**Why it matters.** Every Python codebase you'll ever join is a graph of functions calling functions across modules. Master the function model + project structure here, and joining a new codebase becomes painless.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Defining Functions | `def greet(name):` — functions are defined with `def`, return `None` by default |
| 2 | Parameters & Arguments | Positional, keyword, default arguments: `def greet(name, greeting="Hello"):` |
| 3 | `*args` & `**kwargs` | `*args` collects variable positional args as a tuple. `**kwargs` collects keyword args as a dict |
| 4 | Positional-Only & Keyword-Only | `/` (must be positional) and `*` (must be keyword) markers in the signature |
| 5 | Lambda Functions | `lambda x: x * 2` — anonymous one-liner functions. Use with `map()`, `filter()`, `sorted(key=)` |
| 6 | Scope (LEGB Rule) | Local → Enclosing → Global → Built-in. Variables defined in functions are local by default |
| 7 | `global` & `nonlocal` | Modify outer-scope variables (rare — usually a code smell) |
| 8 | Closures | A function returning a function that remembers the outer scope's variables |
| 9 | Type Hints | `def add(x: int, y: int) -> int:` — document types. Not enforced at runtime, but `mypy` checks them |
| 10 | Docstrings | `"""Compute the tax for an order."""` — the first string in a function. Used by `help()` and IDEs |
| 11 | Modules | `import os`, `from pathlib import Path`, `import json as j` — organize code into reusable files |
| 12 | Packages | A folder with an `__init__.py` is a package. `from mypackage.utils import helper` |
| 13 | `__name__ == "__main__"` | Guard that prevents code from running when the file is imported as a module |
| 14 | pip & PyPI | `pip install requests` — the package installer. Browse [pypi.org](https://pypi.org/) for libraries |
| 15 | Virtual Environments | `python -m venv .venv`, `source .venv/bin/activate` — isolate each project's deps |
| 16 | `uv` (modern alternative) | A 10–100× faster Python package manager (Rust-based). Drop-in replacement for pip + venv |
| 17 | `requirements.txt` | `pip freeze > requirements.txt` — record exact versions for reproducible installs |

> [!TIP]
> Always create a **virtual environment** for each project. It isolates dependencies so projects don't conflict:
> ```bash
> python -m venv .venv          # Create virtual environment
> source .venv/bin/activate     # Activate (Mac/Linux)
> .venv\Scripts\activate        # Activate (Windows)
> pip install requests          # Install packages inside venv
> pip freeze > requirements.txt # Save dependencies
> ```
> Or with [`uv`](https://docs.astral.sh/uv/) — much faster and the new default in 2026:
> ```bash
> uv venv && source .venv/bin/activate
> uv pip install requests
> ```

<details>
<summary><strong>Quick Reference: Function Signatures</strong></summary>

```python
def fancy(
    pos_only,           # positional-only (must come first)
    /,
    pos_or_kw,          # can be either (default category)
    *args,              # variadic positional
    kw_only,            # keyword-only (after *)
    **kwargs            # variadic keyword
) -> str:
    """Demo of every parameter kind."""
    ...
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with default parameters and `*args`/`**kwargs`
- [ ] Use type hints and docstrings on every function you write
- [ ] Create a multi-module project with `__init__.py`
- [ ] Set up a virtual environment and install a package with both `pip` and `uv`
- [ ] Add and use `if __name__ == "__main__":` correctly

</details>

---

## Phase 5: Data Structures

![Phase](https://img.shields.io/badge/Phase-5%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master Python's built-in data structures — they're incredibly powerful and chosen on purpose.

**What this phase is about.** Real data is rarely a single value — it's a *list of users*, a *user profile* with name + email + age, a *set of unique tags*, a *cart of {item: quantity}*. Python's four core collections — **list, tuple, set, dict** — cover almost every shape of data. This phase teaches the methods you'll use thousands of times, slicing (Python's most-loved feature), unpacking (`a, *b = ...`), and the **time complexity** of each operation (so you don't make `O(n²)` mistakes).

**Why it matters.** "Which data structure should I use?" is one of the highest-leverage questions in programming. Wrong choice = slow code, ugly code, buggy code. Right choice = clean, fast, idiomatic Python. Interview questions are 80% data-structure questions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Lists | Mutable sequences: `[1, 2, 3]`. Methods: `.append()`, `.extend()`, `.insert()`, `.pop()`, `.sort()`, `.reverse()`, `.count()`, `.index()` |
| 2 | List Time Complexity | `append`: O(1), `pop()`: O(1), `insert(0, x)`: O(n), `in`: O(n), `sort`: O(n log n) |
| 3 | Tuples | Immutable sequences: `(1, 2, 3)`. Unpacking: `x, y = (1, 2)`. Use for fixed collections and dict keys |
| 4 | Sets | Unordered, no duplicates: `{1, 2, 3}`. Operations: `union (\|)`, `intersection (&)`, `difference (-)`, `symmetric (^)`. O(1) `in` check |
| 5 | Frozensets | Immutable sets — hashable, can be used as dict keys / set elements |
| 6 | Dictionaries | Key-value pairs: `{"name": "Alice"}`. Access with `[]` or `.get()`. Iterate `.keys()`, `.values()`, `.items()`. Insertion-ordered since 3.7 |
| 7 | Dict Methods | `.update()`, `.setdefault()`, `.pop()`, dict union: `a \| b` (Python 3.9+), `\|=` for in-place |
| 8 | Strings as Sequences | Strings behave like immutable sequences: indexing, slicing, `len`, `in` all work |
| 9 | Slicing | `seq[start:stop:step]`. Negative indices: `seq[-1]`. Reverse: `seq[::-1]`. Every other: `seq[::2]` |
| 10 | Unpacking | `a, b = [1, 2]`, `first, *rest = [1, 2, 3, 4]` (rest = `[2,3,4]`), `*a, last = [1,2,3]` |
| 11 | Dict / List Comprehensions (Recap) | Build new collections in one line — see Phase 3 |
| 12 | Nested Structures | Lists of dicts (`users[0]["name"]`), dicts of lists, dict of dicts. Real-world data shapes |
| 13 | `sorted()` and `key=` | `sorted(users, key=lambda u: u["age"])`, `sorted(..., reverse=True)`, `sorted(..., key=str.lower)` |
| 14 | `min()`, `max()`, `sum()` | Reductions over iterables. With `key=` for custom comparisons |
| 15 | Iteration Helpers | `any()`, `all()`, `len()`, `reversed()`, `enumerate()`, `zip()` |
| 16 | Choosing the Right Structure | Decision tree: ordered? unique? key-based? mutable? |

> [!IMPORTANT]
> **When to use which data structure:**
> - **List** → ordered collection that changes: `[item1, item2]`. Default choice for sequences.
> - **Tuple** → ordered collection that *never* changes: `(x, y)`. Returns from functions, dict keys.
> - **Set** → unique items, fast `in` lookup: `{item1, item2}`. Deduplication, membership tests.
> - **Dict** → key-value pairs, fast lookup by key: `{"key": "value"}`. JSON, configs, indexes.

<details>
<summary><strong>Quick Reference: Operation Time Complexity</strong></summary>

| Operation | List | Tuple | Set | Dict |
|-----------|:----:|:-----:|:---:|:----:|
| Lookup `seq[i]` / `d[k]` | O(1) | O(1) | — | O(1) avg |
| `x in seq` | O(n) | O(n) | **O(1)** | **O(1)** |
| `append` / `add` | O(1) amort | — | O(1) avg | O(1) avg |
| `insert(0, x)` | O(n) | — | — | — |
| Iterate | O(n) | O(n) | O(n) | O(n) |
| Sort | O(n log n) | — | — | — |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use all 4 core data structures and explain when to use each
- [ ] Slice a list and string with negative indices and steps
- [ ] Use unpacking to swap variables: `a, b = b, a`
- [ ] Sort a list of dicts by a specific key
- [ ] Use sets to find duplicates / common elements between two lists in O(n)

</details>

---

## Phase 6: Strings & Regular Expressions

![Phase](https://img.shields.io/badge/Phase-6%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Master text — slicing, searching, formatting, and pattern matching.

**What this phase is about.** Most data on the web — names, emails, URLs, error logs, file paths — is text. Python's `str` type ships with a rich set of methods, supports full Unicode out of the box, and pairs naturally with the `re` module for **regular expressions** (a pattern-matching mini-language used in nearly every other language and tool too).

**Why it matters.** Form validation, log scraping, data cleaning, file renaming, web scraping — all powered by string methods + regex. Regex is intimidating at first but pays back forever; the same syntax works in Python, JavaScript, Java, Go, `grep`, and VS Code search.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | String Basics | Literals (`"..."`, `'...'`, `'''multi'''`), Unicode by default, immutability |
| 2 | String Methods | `.upper()`, `.lower()`, `.title()`, `.strip()`, `.split()`, `.join()`, `.replace()`, `.startswith()`, `.endswith()` |
| 3 | Searching | `.find()`, `.rfind()`, `.index()`, `in`, `.count()` |
| 4 | Slicing & Indexing | `s[i]`, `s[start:stop:step]`, `s[::-1]` (reverse) |
| 5 | f-strings (Advanced) | Format specs (`{x:>10}`, `{x:.2%}`), nested expressions, `{x=}` (debug repr in 3.8+) |
| 6 | `format()` & `%` | Older formatting styles you'll see in legacy code |
| 7 | String Encoding | `.encode("utf-8")`, `.decode()`, the `bytes` ↔ `str` boundary |
| 8 | Raw Strings | `r"\n is not a newline"` — disable escape processing. Mandatory for regex patterns |
| 9 | Regex Introduction | `re.search`, `re.match`, `re.findall`, `re.sub`, compiled patterns |
| 10 | Character Classes | `\d`, `\w`, `\s`, `.`, negations (`\D`, `\W`, `\S`), custom `[a-z]` |
| 11 | Quantifiers | `*`, `+`, `?`, `{n,m}`, greedy vs lazy (`*?`, `+?`) |
| 12 | Anchors & Boundaries | `^`, `$`, `\b`, `\B`, multiline mode |
| 13 | Groups | Capturing `(...)`, non-capturing `(?:...)`, named `(?P<name>...)` |
| 14 | Lookahead & Lookbehind | `(?=...)`, `(?!...)`, `(?<=...)`, `(?<!...)` |
| 15 | Regex Flags | `re.IGNORECASE`, `re.MULTILINE`, `re.DOTALL`, `re.VERBOSE` |

> [!TIP]
> Use [Regex101](https://regex101.com/) (pick "Python" flavor) to build and test regex patterns. It explains every character of your pattern step-by-step.

<details>
<summary><strong>Quick Reference: Common Regex Patterns</strong></summary>

```python
import re

# Email (basic — for production use a library)
EMAIL = r"^[\w.+-]+@[\w-]+\.[\w.-]+$"
re.match(EMAIL, "user@example.com")     # match object

# Phone (10 digits)
PHONE = r"^\d{10}$"

# Strong password (8+ chars, upper, lower, digit, symbol)
STRONG = r"^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[^\w\s]).{8,}$"

# Find all hashtags
re.findall(r"#\w+", "Loving #python and #fastapi")  # ['#python', '#fastapi']

# Replace
re.sub(r"\s+", " ", "too    many   spaces")  # 'too many spaces'

# Named groups
m = re.match(r"(?P<area>\d{3})-(?P<num>\d{7})", "555-1234567")
m.group("area")  # '555'
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use 10+ string methods correctly without checking the docs
- [ ] Format numbers with f-string format specs (decimals, percent, width)
- [ ] Validate an email and a phone number with regex
- [ ] Extract all URLs from a paragraph using `re.findall`
- [ ] Use `re.sub` to clean / normalize messy text

</details>

---

## Phase 7: File I/O & Error Handling

![Phase](https://img.shields.io/badge/Phase-7%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Read/write files and handle errors gracefully.

**What this phase is about.** Real programs talk to the disk — they read CSVs, write logs, save user data. They also fail — files don't exist, networks drop, users type weird input. This phase teaches *file I/O the right way* (always with `with`, prefer `pathlib` over `os.path`) and *error handling the right way* (catch specific exceptions, never bare `except`, raise meaningful errors).

**Why it matters.** Resource leaks (unclosed files, sockets, db connections) and unhandled exceptions are two of the top causes of production bugs. Master both here and your programs become predictable and debuggable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Reading Files | `with open("file.txt") as f:` — `f.read()`, `f.readlines()`, iterate with `for line in f:` (memory-friendly) |
| 2 | Writing Files | `open("file.txt", "w")` overwrites, `"a"` appends. `.write()`, `.writelines()` |
| 3 | File Modes | `r`, `w`, `a`, `x` (exclusive create), `b` (binary), `t` (text), `+` (read+write) |
| 4 | Encoding | Always pass `encoding="utf-8"` explicitly. Why default encoding is platform-dependent and dangerous |
| 5 | `pathlib` (modern way) | `Path("dir") / "file.txt"`, `.read_text()`, `.write_text()`, `.exists()`, `.glob()` |
| 6 | Working with JSON | `json.load(f)` / `json.dump(data, f)` — read/write JSON files |
| 7 | Working with CSV | `csv.reader`, `csv.DictReader`, `csv.DictWriter` |
| 8 | Context Managers | `with` statement auto-cleans up. Build your own with `__enter__`/`__exit__` or `@contextmanager` |
| 9 | `try` / `except` / `else` / `finally` | Catch errors: `try: risky() except ValueError as e: handle(e)`. `else` runs if no exception. `finally` always runs |
| 10 | Common Exceptions | `ValueError`, `TypeError`, `KeyError`, `IndexError`, `FileNotFoundError`, `ZeroDivisionError`, `AttributeError` |
| 11 | Raising Exceptions | `raise ValueError("Invalid input")` — fail fast when preconditions aren't met |
| 12 | Custom Exceptions | `class ValidationError(Exception): pass` — domain-specific error types |
| 13 | Exception Chaining | `raise NewError("...") from original_error` — preserve the original cause |
| 14 | Logging | `import logging` — `.info()`, `.warning()`, `.error()`. Use instead of `print()` in production |
| 15 | EAFP vs LBYL | "Easier to Ask Forgiveness than Permission" — Python prefers `try/except` over pre-checks |

> [!CAUTION]
> **Never write a bare `except:`** — it swallows all errors, including `KeyboardInterrupt` and `SystemExit`:
> ```python
> # WRONG — hides all errors including Ctrl+C
> try: risky()
> except: pass
>
> # RIGHT — catch specific exceptions, log them
> try: risky()
> except ValueError as e:
>     logging.error(f"Validation failed: {e}")
>     raise  # re-raise if you can't recover
> ```

<details>
<summary><strong>Quick Reference: pathlib (use it instead of os.path)</strong></summary>

```python
from pathlib import Path

config = Path("config") / "settings.json"  # OS-safe path joining
config.exists()                            # True/False
config.is_file()                           # True/False
config.parent                              # Path("config")
config.stem                                # "settings" (no extension)
config.suffix                              # ".json"
config.read_text(encoding="utf-8")         # whole file as str
config.write_text("hello", encoding="utf-8")
for py in Path("src").rglob("*.py"):       # recursive glob
    print(py)
Path("data").mkdir(parents=True, exist_ok=True)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write text and JSON files using `with` and `pathlib`
- [ ] Handle exceptions for specific error types (no bare `except`)
- [ ] Create a custom exception class
- [ ] Set up `logging` instead of `print` for a small script
- [ ] Build a custom context manager with `@contextmanager`

</details>

---

## Phase 8: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-8%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Model real-world entities with classes.

**What this phase is about.** Functions take inputs and return outputs. Classes bundle **data + behavior** together — a `User` knows its `name`, `email`, and how to `send_welcome_email()`. Python's OOP is flexible: full inheritance, multiple inheritance, abstract classes, *duck typing* ("if it walks like a duck..."), `@dataclass` for boilerplate-free data classes, and `@property` for computed attributes that look like fields.

**Why it matters.** Almost every web framework (Django, FastAPI, Flask), every ORM (SQLAlchemy), every test framework defines classes you inherit from or instantiate. You can't read modern Python code without OOP fluency. Even if you prefer functional style, OOP literacy is non-negotiable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | `class User:` + `def __init__(self, name):` — blueprints for objects |
| 2 | Attributes & Methods | Instance attributes (`self.name`), methods take `self` as first parameter |
| 3 | Class vs Instance Attributes | `class_var` (shared) vs `self.instance_var` (per-instance) |
| 4 | Inheritance | `class Admin(User):` inherits all User methods. `super().__init__()` calls the parent constructor |
| 5 | Multiple Inheritance & MRO | Multiple parents + Python's C3 linearization. Check with `Class.__mro__` |
| 6 | Encapsulation | `_private` (convention), `__name_mangled` (rarely used). Python is "consenting adults" |
| 7 | `@property` | Computed attributes with getter/setter syntax: `user.full_name` not `user.get_full_name()` |
| 8 | Polymorphism & Duck Typing | Different classes with the same method name are interchangeable. "If it has `.read()` we treat it as a file." |
| 9 | Magic / Dunder Methods | `__str__`, `__repr__`, `__eq__`, `__hash__`, `__len__`, `__iter__`, `__add__`, `__call__` |
| 10 | `@staticmethod` & `@classmethod` | Static: no `self`. Classmethod: takes `cls`, alternative constructors (`User.from_dict(...)`) |
| 11 | `@dataclass` | Auto-generates `__init__`, `__repr__`, `__eq__`. Less boilerplate for data-holding classes |
| 12 | `Enum` | `class Color(Enum): RED = 1` — proper named constants |
| 13 | Abstract Classes | `from abc import ABC, abstractmethod` — define interfaces subclasses must implement |
| 14 | `Protocol` (Structural Typing) | `typing.Protocol` — duck typing with type-checking support |
| 15 | Composition over Inheritance | When to compose objects vs inherit from them. Industry-favored design |
| 16 | `__slots__` | Memory optimization for classes with millions of instances |

> [!TIP]
> Use `@dataclass` for classes that primarily hold data — it saves massive boilerplate:
> ```python
> from dataclasses import dataclass, field
>
> @dataclass(frozen=True)   # frozen=True → immutable
> class User:
>     name: str
>     email: str
>     age: int = 0
>     tags: list[str] = field(default_factory=list)
>
> u = User("Alice", "a@x.com", 30)
> print(u)  # User(name='Alice', email='a@x.com', age=30, tags=[])
> ```

<details>
<summary><strong>Quick Reference: Common Magic Methods</strong></summary>

| Method | Purpose | Example |
|--------|---------|---------|
| `__init__` | Constructor | `User("Alice")` |
| `__repr__` | Developer string | `repr(user)` → `User(name='Alice')` |
| `__str__` | User-friendly string | `str(user)` → `Alice` |
| `__eq__` | Equality | `u1 == u2` |
| `__hash__` | Hash for sets/dicts | needed if `__eq__` defined |
| `__len__` | `len(obj)` | `len(my_collection)` |
| `__iter__` / `__next__` | Iteration protocol | `for x in obj:` |
| `__getitem__` | Indexing | `obj[key]` |
| `__contains__` | `in` operator | `x in obj` |
| `__call__` | Make instance callable | `obj()` |
| `__enter__` / `__exit__` | Context manager | `with obj as ...` |
| `__add__`, `__sub__`, ... | Operator overloading | `a + b` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with `__init__`, methods, and inheritance
- [ ] Implement `__str__`, `__repr__`, and `__eq__` magic methods
- [ ] Refactor a class to use `@dataclass`
- [ ] Use `@property` to add a computed attribute
- [ ] Define an abstract base class with `abc.ABC`

</details>

---

## Phase 9: Advanced Python

![Phase](https://img.shields.io/badge/Phase-9%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Master the features that separate juniors from seniors.

**What this phase is about.** This is the "why" phase. Why does `@app.route("/")` work? Why can `for line in file` process a 100GB file in 10MB of RAM? Why are `with` blocks so clean? You'll learn **decorators** (functions that wrap functions), **generators & iterators** (lazy sequences), **context managers** (resource cleanup), the **type hint system** (with Pydantic & Protocols), **descriptors** (the magic behind `@property`), and a peek at **metaclasses** (the magic behind ORMs).

**Why it matters.** Frameworks come and go — but generators and decorators are forever. Once you internalize these, you can read *any* Python codebase, contribute to popular libraries, and ace any senior interview.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Decorators | `@decorator` wraps functions — add logging, timing, auth, retries without modifying the original |
| 2 | Decorator Factories | `@retry(times=3)` — decorators that take arguments |
| 3 | `functools.wraps` | Preserve `__name__` and `__doc__` of the wrapped function |
| 4 | Generators | `yield` instead of `return` — produce values lazily, one at a time. Memory-efficient |
| 5 | Generator Expressions | `(x*2 for x in range(10))` — like list comp but lazy |
| 6 | Iterators | `__iter__()` + `__next__()` protocol — make any object iterable with `for x in obj:` |
| 7 | `itertools` Recipes | `chain`, `cycle`, `islice`, `groupby`, `combinations`, `permutations` |
| 8 | Context Managers | `with` blocks. Build your own with `__enter__`/`__exit__` or `@contextmanager` |
| 9 | `match` / `case` (Recap) | Structural pattern matching with destructuring (Python 3.10+) |
| 10 | Walrus Operator (`:=`) | Assign-while-testing for cleaner code |
| 11 | Type Hints (Deep) | `Optional`, `Union` (3.10+: `int \| None`), generics, `TypeVar`, `Callable`, `Literal`, `TypedDict` |
| 12 | `Protocol` (Structural Subtyping) | Duck typing with type-checker support |
| 13 | Pydantic | Runtime data validation backed by type hints — the basis of FastAPI, used everywhere in 2026 |
| 14 | Descriptors | The protocol behind `@property`, `@classmethod`. Power tool for ORMs |
| 15 | Metaclasses | "Classes whose instances are classes." How Django's ORM works. Rarely needed — but iconic |
| 16 | `__slots__` | Skip `__dict__`, save memory and CPU on classes with millions of instances |

> [!TIP]
> **Generators** are perfect for processing large files — they use almost no memory:
> ```python
> def read_large_file(path):
>     with open(path) as f:
>         for line in f:
>             yield line.strip()  # one line at a time
>
> # Process a 10GB file without loading it all into memory
> for line in read_large_file("huge.csv"):
>     process(line)
> ```

<details>
<summary><strong>Quick Reference: A Useful Decorator</strong></summary>

```python
import functools, time, logging

def timed(fn):
    @functools.wraps(fn)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        try:
            return fn(*args, **kwargs)
        finally:
            elapsed = time.perf_counter() - start
            logging.info(f"{fn.__name__} took {elapsed:.3f}s")
    return wrapper

@timed
def slow():
    time.sleep(1)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a decorator that logs function calls and timing
- [ ] Write a decorator factory that retries N times
- [ ] Create a generator that yields Fibonacci numbers infinitely
- [ ] Build a custom context manager with `@contextmanager`
- [ ] Define a Pydantic model for an API request and validate input
- [ ] Use `Protocol` for structural subtyping

</details>

---

## Phase 10: Concurrency, Parallelism & Async

![Phase](https://img.shields.io/badge/Phase-10%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Run things at the same time — without melting your CPU.

**What this phase is about.** Python has **three distinct concurrency models** and beginners constantly pick the wrong one. **Threading** for I/O-bound work (network, disk). **Multiprocessing** for CPU-bound work (math, image processing). **Asyncio** for high-throughput I/O (thousands of HTTP requests, WebSocket servers). Plus the famous **GIL (Global Interpreter Lock)** — and the new **free-threaded build** (Python 3.13+) that finally removes it.

**Why it matters.** Modern Python — FastAPI, every LLM SDK (`openai`, `anthropic`), `httpx`, `asyncpg`, every WebSocket server — is **async-first**. If you can't read `async def` and `await`, you can't work with the modern Python ecosystem. Most senior interview questions touch on the GIL or asyncio.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Concurrency vs Parallelism | Concurrency = handling many at once. Parallelism = doing many at once. Different problems |
| 2 | The GIL | Why CPython's Global Interpreter Lock means threads don't help CPU-bound code |
| 3 | Free-Threaded Python (3.13+) | The new no-GIL build — true parallel threads. Experimental, growing fast |
| 4 | Threading | `threading.Thread`, `Thread.start()`, `.join()`. Best for I/O-bound work |
| 5 | Thread Synchronization | `Lock`, `RLock`, `Semaphore`, `Event`, `Queue` — coordinate threads safely |
| 6 | `concurrent.futures.ThreadPoolExecutor` | The clean way to run many threads with `submit()` and `map()` |
| 7 | Multiprocessing | `multiprocessing.Process` — separate Python processes, true parallelism |
| 8 | `concurrent.futures.ProcessPoolExecutor` | Clean parallelism for CPU-bound work |
| 9 | When Threads vs Processes vs Async | Decision tree: I/O-bound? CPU-bound? Many tiny I/O ops? |
| 10 | Async Basics | `async def`, `await`, the event loop. Coroutines, not threads |
| 11 | `asyncio.run()` | Entry point: run a top-level async function |
| 12 | `asyncio.gather()` | Run many awaitables concurrently and collect results |
| 13 | `asyncio.create_task()` | Fire-and-forget background tasks |
| 14 | Async Iteration | `async for`, `async with`, async generators |
| 15 | `httpx`, `aiohttp` | Async HTTP clients — make 1000 requests in the time `requests` makes 10 |
| 16 | `asyncio.Queue`, `Lock`, `Semaphore` | Async-safe coordination primitives |
| 17 | `asyncio.timeout()` | Cancel an awaitable after N seconds (Python 3.11+) |
| 18 | `subprocess` | Run external programs (`ls`, `git`, `ffmpeg`) from Python |

> [!IMPORTANT]
> **The decision tree:**
> - **I/O-bound, few tasks** → `threading` or `concurrent.futures.ThreadPoolExecutor`.
> - **I/O-bound, thousands of tasks** → `asyncio` + `httpx`. Way more efficient than threads.
> - **CPU-bound** → `multiprocessing` or `ProcessPoolExecutor`. Threads can't help (GIL).
> - **Mixed** → asyncio with `loop.run_in_executor()` to push CPU-bound work to a process pool.

<details>
<summary><strong>Quick Reference: 1000 HTTP Requests, Three Ways</strong></summary>

```python
import time, requests, httpx, asyncio
from concurrent.futures import ThreadPoolExecutor

URLS = [f"https://httpbin.org/delay/1?id={i}" for i in range(50)]

# 1. Sequential — slow
def sync_run():
    return [requests.get(u).status_code for u in URLS]
# ~50 seconds

# 2. Threads — much better for I/O
def threaded_run():
    with ThreadPoolExecutor(max_workers=20) as pool:
        return list(pool.map(lambda u: requests.get(u).status_code, URLS))
# ~3 seconds

# 3. Async — best for high-throughput I/O
async def async_run():
    async with httpx.AsyncClient() as client:
        return await asyncio.gather(*(client.get(u) for u in URLS))
# ~1.5 seconds
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the GIL and which workloads it hurts
- [ ] Pick the right tool: threading vs multiprocessing vs asyncio for a given task
- [ ] Write an async function that fetches 100 URLs concurrently with `httpx` + `asyncio.gather`
- [ ] Use `ThreadPoolExecutor` to parallelize I/O work
- [ ] Use `ProcessPoolExecutor` to parallelize a CPU-bound function
- [ ] Run a shell command from Python with `subprocess.run`

</details>

---

## Phase 11: Standard Library Deep Dive

![Phase](https://img.shields.io/badge/Phase-11%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Python's "batteries included" — the most useful built-in modules.

**What this phase is about.** Python ships with 200+ modules in its standard library. You don't need to know all of them, but the ~15 in this phase appear in nearly every codebase. `pathlib` and `json` you'll use daily. `datetime` is famously tricky and worth a deep dive. `collections` and `itertools` are filled with hidden gems that turn 20-line loops into 1-line beauties. `argparse` and `logging` turn scripts into professional CLI tools.

**Why it matters.** "Batteries included" is Python's superpower. Knowing the standard library means *not* installing a third-party package for every task — which means less bloat, fewer security surfaces, and faster onboarding for the next dev who reads your code.

| # | Module | What You'll Learn |
|:-:|--------|-------------------|
| 1 | `pathlib` | Modern paths: `Path("dir") / "file"`, `.read_text()`, `.glob()`, `.rglob()` |
| 2 | `json` | `loads`/`dumps` (strings), `load`/`dump` (files). `indent=2` for pretty output |
| 3 | `datetime` | `datetime.now()`, `timedelta`, `strftime` (format), `strptime` (parse), timezones with `zoneinfo` |
| 4 | `zoneinfo` | Modern timezone handling (Python 3.9+). Replaces `pytz` |
| 5 | `re` | Regex (covered in Phase 6) |
| 6 | `collections` | `Counter` (frequencies), `defaultdict`, `namedtuple`, `deque` (fast append/pop both ends), `OrderedDict`, `ChainMap` |
| 7 | `itertools` | `chain`, `product`, `combinations`, `permutations`, `cycle`, `groupby`, `islice`, `accumulate` |
| 8 | `functools` | `@lru_cache` / `@cache` (memoization), `@wraps`, `reduce`, `partial`, `cached_property`, `singledispatch` |
| 9 | `os` | `os.environ` (env vars), `os.cpu_count()`, `os.makedirs()` |
| 10 | `sys` | `sys.argv` (CLI args), `sys.exit(code)`, `sys.path`, `sys.stderr` |
| 11 | `subprocess` | Run external commands: `subprocess.run(["git", "status"], capture_output=True)` |
| 12 | `argparse` | Build proper CLIs with `--help`, types, defaults, subcommands |
| 13 | `logging` | Real logging — levels, handlers, formatters. Replaces `print` in production |
| 14 | `csv` | Read/write CSV files — `DictReader`, `DictWriter` |
| 15 | `sqlite3` | Built-in SQL database — perfect for prototypes and small apps |
| 16 | `urllib` | URL parsing/joining (`urllib.parse`), simple HTTP (use `requests`/`httpx` for real work) |
| 17 | `http.server` | One-line HTTP server: `python -m http.server 8000` — useful for testing |
| 18 | `unittest.mock` | `Mock`, `patch` — fake APIs and dependencies in tests |
| 19 | `dataclasses` | `@dataclass` (covered in Phase 8) |
| 20 | `typing` | The whole type-hint system |
| 21 | `concurrent.futures` | Thread / process pools (covered in Phase 10) |
| 22 | `asyncio` | Async I/O (covered in Phase 10) |

> [!TIP]
> Use `pathlib.Path` instead of `os.path` — it's more readable, modern, and Pythonic. Most new code in 2026 uses `pathlib` exclusively.

<details>
<summary><strong>Quick Reference: collections power</strong></summary>

```python
from collections import Counter, defaultdict, deque

# Counter — frequencies in one line
Counter("hello world").most_common(3)  # [('l', 3), ('o', 2), (' ', 1)]

# defaultdict — no more `if key not in d`
groups = defaultdict(list)
for word in ["apple", "ant", "banana", "berry"]:
    groups[word[0]].append(word)
# {'a': ['apple', 'ant'], 'b': ['banana', 'berry']}

# deque — O(1) append/pop on both ends (queue or stack)
queue = deque(["a", "b", "c"])
queue.append("d")       # right
queue.appendleft("z")   # left
queue.popleft()         # 'z'
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Parse and create JSON with the `json` module
- [ ] Use `pathlib` for all file path operations (no `os.path`)
- [ ] Format and parse dates with `datetime` and timezones with `zoneinfo`
- [ ] Use `Counter`, `defaultdict`, `deque` correctly
- [ ] Build a CLI with `argparse` (positional + optional args + subcommands)
- [ ] Configure `logging` with levels and a file handler

</details>

---

## Phase 12: Testing, Tooling & Modern Project Setup

![Phase](https://img.shields.io/badge/Phase-12%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write tests, set up a professional project, ship code your team trusts.

**What this phase is about.** Writing code is half the job — proving it works (tests), keeping it consistent (formatter, linter), and packaging it for distribution (modern `pyproject.toml`). This phase covers **pytest** (the de facto test runner), **mocking**, **coverage**, **type checking** with **mypy** / **pyright**, the modern toolchain (**ruff**, **black**, **uv**, **poetry**), and what a 2026 Python project layout looks like.

**Why it matters.** Tested + linted + typed code is shippable. Untested code is a coin flip. Companies hiring above junior level expect tests as a default. Setting up a project right once — `pyproject.toml`, `pytest`, `ruff`, `pre-commit`, CI — and you can spin up a new project in 5 minutes for the rest of your career.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Test? | Confidence to refactor, prevention of regressions, executable documentation |
| 2 | The Testing Pyramid | Unit tests (fast, many) → Integration → End-to-end (slow, few) |
| 3 | pytest Basics | `pip install pytest`, `def test_x(): assert ...`, `pytest -v` |
| 4 | Fixtures | `@pytest.fixture` — reusable setup/teardown for tests |
| 5 | Parametrize | `@pytest.mark.parametrize` — run one test against many inputs |
| 6 | Mocking | `unittest.mock.Mock`, `patch` — fake APIs, databases, time |
| 7 | Test Coverage | `pip install coverage` → `coverage run -m pytest` → `coverage report` |
| 8 | Async Tests | `pytest-asyncio` for testing `async def` functions |
| 9 | TDD Basics | Red → Green → Refactor: write failing test, write minimal code, clean up |
| 10 | PEP 8 | Python's style guide: 4-space indent, `snake_case`, max 79 chars (88 for Black) |
| 11 | **ruff** (modern linter + formatter) | 100× faster than flake8/isort/black combined. The 2026 default |
| 12 | **black** (formatter, alternative) | Opinionated formatter. "Any color you like, as long as it's black." |
| 13 | **mypy** / **pyright** | Static type checking. Run as part of CI |
| 14 | **uv** / **poetry** / **pdm** | Modern dependency managers replacing `pip + venv` |
| 15 | `pyproject.toml` | The single source of truth — replaces `setup.py`, `setup.cfg`, `requirements.txt` |
| 16 | Project Structure | `src/`, `tests/`, `pyproject.toml`, `.python-version`, `README.md` |
| 17 | pre-commit | Auto-run linters/formatters on `git commit` |
| 18 | GitHub Actions for Python | CI: test, lint, type-check, publish on every push |
| 19 | Publishing to PyPI | Build with `uv build` / `poetry build`, upload with `twine` or `uv publish` |

> [!TIP]
> Use `pytest` (not `unittest`) for new projects — it's simpler and more powerful. Use `ruff` (not `flake8`/`isort`/`black`) — it's faster and replaces all of them.
> ```python
> # test_math.py
> import pytest
>
> @pytest.mark.parametrize("a,b,want", [(1,1,2), (2,3,5), (-1,1,0)])
> def test_add(a, b, want):
>     assert add(a, b) == want
>
> @pytest.fixture
> def sample_users():
>     return [{"name": "Alice"}, {"name": "Bob"}]
>
> def test_count(sample_users):
>     assert len(sample_users) == 2
> ```

<details>
<summary><strong>Quick Reference: Modern Project Skeleton</strong></summary>

```
my-project/
├── pyproject.toml          # Single config file
├── README.md
├── .python-version         # 3.13
├── .gitignore
├── .pre-commit-config.yaml
├── src/
│   └── my_project/
│       ├── __init__.py
│       └── core.py
└── tests/
    ├── __init__.py
    └── test_core.py
```

```toml
# pyproject.toml
[project]
name = "my-project"
version = "0.1.0"
requires-python = ">=3.13"
dependencies = ["httpx", "pydantic"]

[project.optional-dependencies]
dev = ["pytest", "ruff", "mypy"]

[tool.ruff]
line-length = 100

[tool.pytest.ini_options]
addopts = "-v --cov=src"
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 10+ tests with pytest including fixtures and parametrize
- [ ] Achieve 80%+ test coverage on a project
- [ ] Set up `ruff` and `mypy` in `pyproject.toml`
- [ ] Add a `pre-commit` config that auto-runs ruff on commit
- [ ] Add GitHub Actions CI to run tests on every push
- [ ] Build and publish a tiny package to TestPyPI

</details>

---

## Phase 13: Web Development & APIs

![Phase](https://img.shields.io/badge/Phase-13%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Build web applications and consume / create REST APIs.

**What this phase is about.** Python's three big web frameworks: **FastAPI** (modern async APIs, type-hint-driven, auto-generated docs — the 2026 default for new projects), **Django** (the heavyweight, batteries-included web framework — Instagram, Pinterest, Mozilla), and **Flask** (the original micro-framework — small, flexible). This phase covers HTTP fundamentals, building REST APIs, talking to databases with SQLAlchemy + Alembic, authentication with JWT, and web scraping with `requests` + BeautifulSoup.

**Why it matters.** "Backend Python developer" is one of the highest-paying junior roles in every market. FastAPI in particular is the framework powering most new Python startups in 2026 — fluency = employability.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | HTTP Basics | Request/response cycle, methods (GET, POST, PUT, PATCH, DELETE), status codes (2xx/3xx/4xx/5xx), headers |
| 2 | URLs, Query, Body | Path params, query strings, JSON body, form data, file uploads |
| 3 | `requests` | The classic sync HTTP client: `get`, `post`, `.json()`, `.raise_for_status()` |
| 4 | `httpx` | Modern HTTP client — sync **and** async API. The 2026 default |
| 5 | FastAPI | `@app.get`, `@app.post`, automatic OpenAPI docs at `/docs`, type-hint-driven validation |
| 6 | Pydantic Models | Define request/response schemas; validate at the boundary; auto-generate JSON schema |
| 7 | Async Endpoints | `async def` endpoints, awaiting database / external APIs |
| 8 | Dependency Injection | `Depends()` — auth, db sessions, shared state. FastAPI's killer feature |
| 9 | Authentication | OAuth2 password flow, JWT tokens, password hashing with `passlib[bcrypt]` |
| 10 | CORS, Rate Limiting, Middleware | Cross-origin, throttling, custom request hooks |
| 11 | SQLAlchemy 2.0 | Modern Pythonic ORM: declarative models, async session, type-safe queries |
| 12 | Alembic | Database migrations: `alembic revision --autogenerate`, `alembic upgrade head` |
| 13 | Async DBs | `asyncpg` (Postgres), `aiosqlite`, `motor` (MongoDB) |
| 14 | Django (overview) | When to pick Django: admin panel, ORM, auth, forms — all included |
| 15 | Flask (overview) | When to pick Flask: tiny, flexible, no opinions |
| 16 | Templates | Jinja2 — used by Flask, FastAPI, Django (Django uses its own variant) |
| 17 | Web Scraping | `BeautifulSoup`, `lxml`, `Playwright` for JavaScript-heavy sites |
| 18 | Background Jobs | `Celery`, `Dramatiq`, `RQ`, `arq` (async-native) — long-running tasks |
| 19 | Testing FastAPI | `TestClient`, `httpx.AsyncClient`, fixture-driven DB setup |

> [!TIP]
> **FastAPI** auto-generates interactive Swagger docs from your type hints. Visit `http://localhost:8000/docs` after starting the server:
> ```python
> from fastapi import FastAPI
> from pydantic import BaseModel
>
> app = FastAPI(title="Tasks API")
>
> class Task(BaseModel):
>     title: str
>     done: bool = False
>
> @app.post("/tasks", status_code=201)
> async def create_task(task: Task) -> dict:
>     return {"id": 1, **task.model_dump()}
> ```

<details>
<summary><strong>Quick Reference: Pick a Framework</strong></summary>

| Framework | Best For | Trade-offs |
|-----------|----------|-----------|
| **FastAPI** | Modern async APIs, type-driven, auto docs | Less batteries — no built-in admin / forms |
| **Django** | Full-stack web apps, admin panel needed | Heavier, opinionated, sync-first (async exists but partial) |
| **Flask** | Tiny services, custom architecture | You assemble the pieces yourself (auth, ORM, etc.) |
| **Litestar** | FastAPI-like with more batteries | Newer, smaller community |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data from a public API with `httpx` (sync and async)
- [ ] Build a CRUD REST API with FastAPI + Pydantic
- [ ] Connect FastAPI to a SQLite (or Postgres) DB with SQLAlchemy 2.0
- [ ] Add JWT auth with hashed passwords
- [ ] Write Alembic migrations for a schema change
- [ ] Scrape a website with BeautifulSoup
- [ ] Test a FastAPI endpoint with `TestClient`

</details>

---

## Phase 14: Data Science, ML & AI

![Phase](https://img.shields.io/badge/Phase-14%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 12-20 Hours](https://img.shields.io/badge/Time-12--20%20Hours-yellow)

> The single biggest reason Python is the most popular language in 2026.

**What this phase is about.** Python is the lingua franca of data and AI. This phase tours the libraries that power 99% of the field: **NumPy** (fast numerical arrays), **Pandas** (the spreadsheet superpower), **Matplotlib** / **Plotly** (visualization), **Jupyter** (the interactive notebook), **scikit-learn** (classical machine learning — regression, classification, clustering), **PyTorch** (deep learning — neural nets, transformers), and the **LLM SDKs** ([`anthropic`](https://docs.anthropic.com/), [`openai`](https://platform.openai.com/docs/), [`langchain`](https://www.langchain.com/), [`llamaindex`](https://www.llamaindex.ai/)) that let you build agents and RAG apps in Python.

**Why it matters.** In 2026, "Python developer + ML/AI" is the single highest-paid combination on the planet. Even backend engineers are expected to plug LLMs into their apps. Even data analysts are expected to write Python for non-trivial work. This phase is your entry to the most explosive part of the industry.

### 14.1 — The Data Stack

| # | Library | What You'll Learn |
|:-:|---------|-------------------|
| 1 | **Jupyter** | Interactive notebooks — code + output + plots in one document. Run with `jupyter lab` |
| 2 | **NumPy** | N-dimensional arrays. Vectorized math 100× faster than Python loops. The foundation of everything below |
| 3 | NumPy Indexing | Slicing, fancy indexing, boolean masks, broadcasting |
| 4 | **Pandas** | DataFrames (think: code-driven Excel). `read_csv`, `read_parquet`, `merge`, `groupby`, `pivot` |
| 5 | Pandas Cleaning | Missing values (`fillna`, `dropna`), types, duplicates, outliers |
| 6 | Pandas Group / Aggregate | `df.groupby("country").sum()`, `df.pivot_table(...)`, window functions |
| 7 | **Polars** (modern alternative) | Rust-powered, often 10× faster than Pandas. Lazy queries. The 2026 rising star |
| 8 | **Matplotlib** | The classic plotting library. Bar, line, scatter, histogram |
| 9 | **Seaborn** | Statistical plotting — beautiful defaults on top of Matplotlib |
| 10 | **Plotly** | Interactive plots that work in browsers and notebooks |

### 14.2 — Machine Learning

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 11 | ML Concepts | Supervised vs unsupervised, training/validation/test split, overfitting, metrics |
| 12 | **scikit-learn** | The classical-ML powerhouse. `LogisticRegression`, `RandomForest`, `KMeans`, pipelines |
| 13 | Feature Engineering | Scaling, encoding categoricals, dealing with text, dates, missing values |
| 14 | Train / Eval / Predict | `model.fit(X, y)`, `model.predict(X)`, `model.score(X, y)`, cross-validation |
| 15 | Model Persistence | `joblib.dump` / `joblib.load` to save trained models |
| 16 | **XGBoost** / **LightGBM** | Gradient boosting — the algorithms that win Kaggle competitions |

### 14.3 — Deep Learning

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 17 | **PyTorch** | The dominant deep-learning framework. Tensors, autograd, `nn.Module`, training loops |
| 18 | **HuggingFace Transformers** | Pre-trained models — BERT, GPT, Llama. `from transformers import pipeline` |
| 19 | Fine-tuning | Adapt a pre-trained model to your task. PEFT, LoRA |
| 20 | Inference / Serving | `transformers`, `vllm`, ONNX, TorchServe |

### 14.4 — Building with LLMs (the 2026 must-have)

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 21 | LLM SDKs | `anthropic` (Claude), `openai` (GPT) — both async-first, both nearly identical APIs |
| 22 | Streaming | `stream=True` — token-by-token response (ChatGPT-style UI) |
| 23 | Tool Use / Function Calling | Let an LLM call your Python functions to fetch data or take actions |
| 24 | Prompt Caching | Cache long system prompts — 90% cost reduction on Claude/OpenAI |
| 25 | Embeddings | Convert text → vector. The basis of similarity search and RAG |
| 26 | Vector Databases | `chromadb`, `pgvector`, `weaviate`, `qdrant` — store + search embeddings |
| 27 | RAG (Retrieval-Augmented Generation) | Embed docs → search → inject context into the LLM prompt |
| 28 | **LangChain** / **LlamaIndex** | Frameworks for agents, chains, RAG pipelines |
| 29 | LLM Evals | How to test that your AI app actually works. Faithfulness, relevance, regression sets |
| 30 | Production Concerns | Cost tracking, rate limiting, fallbacks, prompt injection defenses |

> [!TIP]
> The Anthropic Python SDK starter ([docs](https://docs.anthropic.com/en/api/client-sdks)):
> ```python
> from anthropic import Anthropic
>
> client = Anthropic()  # reads ANTHROPIC_API_KEY from env
>
> response = client.messages.create(
>     model="claude-opus-4-7",
>     max_tokens=1024,
>     messages=[{"role": "user", "content": "Explain decorators in 3 lines."}],
> )
> print(response.content[0].text)
> ```

<details>
<summary><strong>Quick Reference: Pandas in 30 Seconds</strong></summary>

```python
import pandas as pd

df = pd.read_csv("sales.csv")
df.head()                              # first 5 rows
df.info()                              # types + non-null counts
df.describe()                          # summary stats
df["price"].mean()                     # column aggregate
df[df["country"] == "IN"]              # filter rows
df.groupby("country")["price"].sum()   # group + aggregate
df.merge(other, on="id", how="left")   # SQL-like join
df.to_parquet("out.parquet")           # save (parquet is faster than CSV)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use Jupyter or VS Code notebooks comfortably
- [ ] Load a CSV with Pandas, clean it (missing values, types, duplicates)
- [ ] Create at least 3 different plots with Matplotlib or Seaborn
- [ ] Train a scikit-learn model (e.g. logistic regression) end-to-end
- [ ] Save and load a trained model with `joblib`
- [ ] Call Claude (or GPT) with the official SDK from Python
- [ ] Build a tiny RAG: embed a few docs, search by query, feed to the LLM

</details>

---

## Phase 15: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-15%2F15-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You've finished the language. Now pick a specialization and ship real things.

**What this phase is about.** Python opens more doors than almost any other language. This phase is a map: pick the track that excites you most, then go deep. Whatever you pick, you'll need **deployment** skills (Docker, cloud), **databases** (SQL), and **Git**. Those three travel with you for the rest of your career.

### 15.1 — Pick a Specialization

| Track | What You Build | Key Tools |
|-------|---------------|-----------|
| **Backend / API** | REST/GraphQL APIs, microservices | FastAPI, SQLAlchemy, Postgres, Redis, Docker |
| **Data Science / Analytics** | Reports, dashboards, insights | Pandas, Polars, Plotly, Jupyter, dbt, DuckDB |
| **ML Engineer** | Train + deploy models | scikit-learn, PyTorch, MLflow, BentoML |
| **AI / LLM Engineer** | LLM apps, agents, RAG, copilots | Claude/OpenAI SDKs, LangChain, LlamaIndex, vector DBs |
| **DevOps / Platform** | CI/CD, infra-as-code, automation | Ansible, Terraform, Kubernetes, GitHub Actions |
| **Security** | Pentest tools, exploit dev | Scapy, requests, burp, paramiko |
| **Data Engineer** | Pipelines, ETL/ELT, warehouses | Airflow, Prefect, Dagster, Spark, Kafka |
| **Game Dev** | 2D/3D games | Pygame, Panda3D, Godot's Python bindings |
| **Embedded / IoT** | Microcontrollers, sensors | MicroPython, CircuitPython, Raspberry Pi |
| **Desktop GUIs** | Cross-platform apps | PyQt, Tkinter, Kivy, Flet |
| **Scientific** | Research code, simulations | NumPy, SciPy, SymPy, JAX |

### 15.2 — Required Cross-cutting Skills

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Every team. Every project. Non-negotiable. |
| **[SQL](sql.md)** | Every backend. Every data role. Pair with the SQL Syllabus. |
| **[Docker](docker.md)** | Package your app once, run anywhere. The deployment standard. |
| **CI/CD** (GitHub Actions) | Auto-test and auto-deploy on every push |
| **Cloud basics** (AWS / GCP / Azure / Vercel) | Where your code actually lives in production |
| **Linux command line** | Every server runs Linux. `cd`, `ssh`, `tail`, `grep`, `cron` |

### 15.3 — Deploy Your Python Code

| Target | Tool |
|--------|------|
| Static analysis script | [GitHub Actions cron](https://docs.github.com/en/actions) |
| Web API | [Vercel](https://vercel.com/) (Python on Fluid Compute), [Railway](https://railway.app/), [Fly.io](https://fly.io/), [Render](https://render.com/) |
| Container | [Docker](docker.md) → [AWS ECS](https://aws.amazon.com/ecs/) / [GCP Cloud Run](https://cloud.google.com/run) |
| Notebook / dashboard | [Streamlit](https://streamlit.io/) Cloud, [Hugging Face Spaces](https://huggingface.co/spaces) |
| Long-running ML inference | [Modal](https://modal.com/), [BentoML](https://www.bentoml.com/), [Banana](https://www.banana.dev/) |
| Serverless function | [AWS Lambda](https://aws.amazon.com/lambda/), [Vercel Functions](https://vercel.com/docs/functions), [Cloudflare Workers](https://workers.cloudflare.com/) (via Pyodide) |

### 15.4 — Suggested Order After This Syllabus

```
Pick a specialization → Git → SQL → Docker → Build & deploy a real project → Repeat
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Mutable default arguments | `def f(items=[]):` reuses the same list across calls — items accumulate | Use `None`: `def f(items=None): items = items or []` |
| 2 | Modifying list while iterating | `for item in lst: lst.remove(item)` skips elements | Iterate a copy: `for item in lst[:]` or use a comprehension |
| 3 | Bare `except:` | Catches everything including `KeyboardInterrupt` — hides real bugs | Catch specific: `except ValueError as e:` |
| 4 | Not closing files | File handles leak without explicit close | Always use `with open(...) as f:` |
| 5 | Global variables | Hard to track, test, debug | Pass data via parameters and return values |
| 6 | No `__name__ == "__main__"` guard | Code runs when imported as a module | Add: `if __name__ == "__main__": main()` |
| 7 | `is` vs `==` confusion | `[] == []` is `True`, `[] is []` is `False` | Use `==` for values, `is` only for `None` (and other singletons) |
| 8 | No virtual environment | Package conflicts between projects | Always: `python -m venv .venv` (or `uv venv`) per project |
| 9 | Using `print()` for debugging | Hard to find/remove, no log levels, clutters output | Use `logging` module with proper levels |
| 10 | Ignoring type hints | No IDE autocomplete, no static checking, harder to read | Add type hints: `def greet(name: str) -> str:` |
| 11 | Iterating with `range(len(...))` | Anti-pattern, harder to read, easy to off-by-one | Use `for i, item in enumerate(items):` |
| 12 | `dict[key]` when key may not exist | `KeyError` crash | Use `dict.get(key, default)` |
| 13 | Confusing shallow vs deep copy | Mutating nested objects in a "copy" mutates the original | Use `copy.deepcopy()` for nested mutable structures |
| 14 | Storing API keys in code | Leaked on every push to GitHub | Use env vars + `python-dotenv`, never commit `.env` |
| 15 | Threading CPU-bound work | The GIL means threads don't help — code stays slow | Use `multiprocessing` or `ProcessPoolExecutor` |
| 16 | Mixing tabs and spaces | `IndentationError` and silent bugs | Configure editor to insert 4 spaces (never tabs) |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What's the difference between lists and tuples?**
   - Lists are **mutable** (`append`, `remove`), tuples are **immutable**. Lists `[]`, tuples `()`. Use tuples for fixed collections, dict keys, and when you want to prevent modification.

2. **List the 9 falsy values in Python.**
   - `False`, `None`, `0`, `0.0`, `""`, `[]`, `()`, `{}`, `set()`. Everything else is truthy.

3. **What does `*args` and `**kwargs` mean?**
   - `*args` collects variable positional arguments into a tuple. `**kwargs` collects keyword arguments into a dict. Used for flexible function signatures.

4. **What is a lambda function?**
   - Anonymous one-expression function: `lambda x: x * 2`. Useful with `sorted(key=)`, `map`, `filter`. Limited to one expression — for anything bigger, use `def`.

5. **How do you read a file in Python?**
   - `with open("file.txt", encoding="utf-8") as f: content = f.read()`. Always `with` for auto-close. Or `Path("file.txt").read_text(encoding="utf-8")`.

6. **What is a dictionary?**
   - Key-value data structure: `{"name": "Alice"}`. O(1) average lookup. Methods: `.keys()`, `.values()`, `.items()`, `.get()`, `.pop()`. Insertion-ordered since Python 3.7.

7. **Difference between `is` and `==`?**
   - `==` compares **values**. `is` compares **identity** (same object in memory). Use `is` only for `None`, `True`, `False`. Use `==` for everything else.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain list comprehensions with an example.**
   - Concise list construction: `[x*2 for x in range(5)]` = `[0, 2, 4, 6, 8]`. With filter: `[x for x in range(10) if x % 2 == 0]`. More Pythonic and slightly faster than equivalent `for` loops.

2. **What are decorators?**
   - Functions that wrap other functions. `@decorator` applied above a function definition. Add behavior (logging, timing, auth) without modifying the original. Use `@functools.wraps(fn)` to preserve metadata.

3. **What is a generator and when would you use one?**
   - Function with `yield` instead of `return`. Produces values lazily — doesn't store all values in memory. Use for: large datasets, infinite sequences, streaming. Iterate with `for`, advance with `next()`.

4. **Explain shallow vs deep copy.**
   - `copy.copy()` duplicates the outer object but shares references to nested objects. `copy.deepcopy()` recursively copies everything. Matters when nested data is mutable.

5. **How do you handle exceptions properly?**
   - Catch specific exceptions: `except ValueError as e:`. Use `finally` for cleanup. Raise custom exceptions for domain errors. Never use bare `except:`. Log instead of silently passing.

6. **What is `@dataclass` and why use it?**
   - Decorator that auto-generates `__init__`, `__repr__`, `__eq__` for data-holding classes. Saves boilerplate. Use `@dataclass(frozen=True)` for immutable.

7. **Explain context managers and `with`.**
   - Objects with `__enter__` / `__exit__` methods. Guaranteed cleanup even if an exception happens. `with open(...) as f:` is the canonical example. Build your own with `@contextlib.contextmanager`.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How does Python's GIL affect multithreading?**
   - The Global Interpreter Lock prevents multiple threads from executing Python bytecode simultaneously. Threading helps **I/O-bound** tasks (GIL is released during I/O) but not **CPU-bound** tasks. Use `multiprocessing` for CPU-bound work — each process has its own GIL. Python 3.13 ships an experimental free-threaded build that removes the GIL.

2. **What is duck typing?**
   - "If it walks like a duck and quacks like a duck, it's a duck." Python checks what an object can DO, not what it IS. Any object with `__len__` works with `len()`. Enables polymorphism without explicit inheritance. Pair with `typing.Protocol` for type-checked duck typing.

3. **Explain metaclasses.**
   - Classes whose instances are classes. `class Meta(type):` controls class creation — modify or validate class definitions. Used in frameworks (Django models, SQLAlchemy declarative). "If you wonder if you need a metaclass, you don't" — the 99% rule.

4. **How do you handle circular imports?**
   - Module A imports B, B imports A → `ImportError`. Solutions: (1) extract shared code to a third module, (2) import inside functions (lazy), (3) use `if TYPE_CHECKING:` from `typing` for type-hint-only imports.

5. **What is the MRO (Method Resolution Order)?**
   - The order Python searches for methods in inheritance: child → parents (left to right) → grandparents. Uses C3 linearization. Inspect with `Class.__mro__`. Critical for multiple inheritance (the diamond problem).

6. **Explain `async def`, `await`, and the event loop.**
   - `async def` declares a coroutine — it returns a coroutine object, not a value. `await` suspends the coroutine and yields control to the event loop, which can run other coroutines while waiting. The event loop schedules and runs them all on a single thread. Massive efficiency win for I/O-bound work.

7. **How does `@property` work? What's a descriptor?**
   - `@property` turns a method into a read-only attribute. Under the hood it's a **descriptor** — a class with `__get__` / `__set__` / `__delete__`. The descriptor protocol is what lets `obj.attr` invoke a function. Same machinery powers `@classmethod`, `@staticmethod`, and ORM fields.

8. **Why is `0.1 + 0.2 != 0.3`?**
   - Floats are IEEE 754 doubles — most decimal fractions can't be represented exactly in binary. Use `decimal.Decimal` for exact decimal arithmetic (money), `fractions.Fraction` for exact ratios, or compare with a tolerance: `math.isclose(a, b)`.

</details>

---

## Practice Projects

You don't truly know Python until you've shipped real projects. Each project below builds skills from multiple phases and produces something you can put on your portfolio. **Do them in order — each is harder than the last.**

> [!TIP]
> Push every project to GitHub with a proper README, screenshots, and (where it makes sense) a deployed live demo. A junior portfolio with 5 polished, deployed projects beats a CS degree with no projects.

### Project 1: Personal Finance CLI
![Phase 1-7](https://img.shields.io/badge/After-Phase%201--7-green)

**What you'll build:** A command-line app to record income/expenses, categorize them, calculate totals, filter by date range, and persist to a JSON file. CLI built with `argparse` (or `typer`). Add a "monthly report" subcommand.

**Skills practiced:** Variables, types, control flow, functions, data structures, file I/O, JSON, exception handling, `argparse`.

**Stretch:** Export to CSV. Add SQLite as alternative storage. Show a simple ASCII bar chart in the report.

---

### Project 2: Quiz Engine with OOP
![Phase 8](https://img.shields.io/badge/After-Phase%208-green)

**What you'll build:** Object-oriented quiz system: `Question` (abstract), `MultipleChoice`, `TrueFalse`, `ShortAnswer`. A `Quiz` class loads questions from a JSON file, runs the quiz, scores it, saves results. Use `@dataclass`, `@property`, abstract base classes.

**Skills practiced:** Classes, inheritance, magic methods, dataclasses, ABCs, error handling.

**Stretch:** Difficulty levels, timed mode, leaderboard saved across runs.

---

### Project 3: Web Scraper + Data Cleaner
![Phase 9-11](https://img.shields.io/badge/After-Phase%209--11-yellow)

**What you'll build:** Scrape a website (e.g. [Hacker News](https://news.ycombinator.com/), product listings, weather pages), clean the data, save to CSV + Parquet, generate a simple report (counts, top items). Use `httpx` + BeautifulSoup. Make the scraper polite (rate limit, user-agent).

**Skills practiced:** Decorators, generators, `httpx`, BeautifulSoup, `pathlib`, `collections.Counter`, logging, robust error handling.

**Stretch:** Schedule with `cron`. Push results to Google Sheets via API. Send an email digest.

---

### Project 4: Async URL Fetcher / Site Health Checker
![Phase 10](https://img.shields.io/badge/After-Phase%2010-yellow)

**What you'll build:** Given a list of URLs, fetch all of them concurrently with `asyncio` + `httpx`, measure response times, detect down sites, retry with exponential backoff, output a JSON + Markdown report. Compare runtimes against a sequential `requests`-based version.

**Skills practiced:** `async`/`await`, `asyncio.gather`, `asyncio.Semaphore`, `AsyncClient`, retry decorator, timing, structured logging.

**Stretch:** Web UI with FastAPI to trigger checks. Alert via Slack / email when a site is down.

---

### Project 5: Production-Style REST API (FastAPI + SQLAlchemy + Auth)
![Phase 12-13](https://img.shields.io/badge/After-Phase%2012--13-red)

**What you'll build:** A complete CRUD API for a task manager with: JWT auth (signup, login, refresh), role-based access, SQLite (with Alembic migrations), Pydantic request/response models, full pytest suite (80%+ coverage), `pyproject.toml`, ruff + mypy, GitHub Actions CI, deployed to Vercel / Railway / Fly.io with a public URL.

**Skills practiced:** FastAPI, Pydantic, SQLAlchemy 2.0, Alembic, JWT auth, password hashing, dependency injection, pytest, CI/CD, deployment.

**Stretch:** Switch SQLite → Postgres. Add background tasks (`arq`). Rate limiting. Dockerize.

---

### Project 6: Data Analysis Notebook (Pandas + Visualization)
![Phase 14](https://img.shields.io/badge/After-Phase%2014-red)

**What you'll build:** A Jupyter notebook that loads a real public dataset (e.g. [Kaggle Titanic](https://www.kaggle.com/c/titanic), NYC Taxi, World Bank). Clean it (missing values, types, duplicates), explore it (groupby, pivot tables, summary stats), visualize it (5+ chart types with Matplotlib/Seaborn/Plotly), write a one-page Markdown story of your findings.

**Skills practiced:** Pandas, NumPy, Matplotlib/Seaborn/Plotly, Jupyter, data storytelling.

**Stretch:** Publish on Kaggle / GitHub Pages. Reproduce as a Streamlit dashboard.

---

### Project 7: ML Model Trainer & Predictor
![Phase 14](https://img.shields.io/badge/After-Phase%2014-red)

**What you'll build:** Pick a tabular ML problem (Titanic survival, house prices, churn). Build a complete pipeline: `pandas` for data prep, `scikit-learn` `Pipeline` + `ColumnTransformer`, train a baseline (LogReg) + an XGBoost model, cross-validate, save the best model with `joblib`. Wrap it in a FastAPI endpoint that returns predictions.

**Skills practiced:** scikit-learn, pandas, feature engineering, model evaluation, model persistence, FastAPI integration.

**Stretch:** Hyperparameter search with `Optuna`. Model versioning with MLflow. Deploy to Hugging Face Spaces.

---

### Project 8: AI Chatbot with RAG (Capstone)
![Phase 14](https://img.shields.io/badge/After-Phase%2014-red)

**What you'll build:** Your graduation project. A web app where users upload PDFs / paste URLs / ask questions about your documentation. Pipeline: chunk docs → embed with `text-embedding-3` (OpenAI) or Voyage AI → store in `chromadb` / `pgvector` → at query time, embed the question, retrieve top-K chunks, send to **Claude** (via the [`anthropic`](https://docs.anthropic.com/en/api/client-sdks) SDK) with **streaming** response. FastAPI backend, simple HTML/HTMX frontend, deployed to a real cloud, end-to-end tests with `pytest-asyncio`. Use **prompt caching** for the system prompt.

**Skills practiced:** Everything from all 15 phases — async, type hints, FastAPI, embeddings, vector DBs, LLM SDKs, streaming, RAG, prompt engineering, deployment. **This is portfolio gold for any 2026 interview.**

**Stretch:** Tool use (LLM calls your search function). Multi-turn memory. Eval suite that scores your bot's answers.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [docs.python.org](https://docs.python.org/3/) | Official Python documentation — every module, function, feature |
| [Python Tutorial (official)](https://docs.python.org/3/tutorial/) | The official tutorial. Authoritative, thorough |
| [Real Python](https://realpython.com/) | Best tutorial site for Python. Deep, well-written articles on every topic |
| [PEP Index](https://peps.python.org/) | Every Python Enhancement Proposal — read PEP 8 (style), PEP 20 (Zen), PEP 484 (type hints) |

### Books (Free or Online)

| Book | Why Read |
|------|---------|
| [Automate the Boring Stuff](https://automatetheboringstuff.com/) | Free book — learn Python by automating real tasks (files, web, Excel) |
| [Think Python (Allen Downey)](https://greenteapress.com/wp/think-python-3rd-edition/) | Free, beautifully written intro to programming with Python |
| [Fluent Python (Luciano Ramalho)](https://www.fluentpython.com/) | The book every Python dev reads at year 2. Deep, idiomatic, advanced |
| [Python Crash Course (Eric Matthes)](https://nostarch.com/python-crash-course-3rd-edition) | Best beginner book with projects |
| [The Hitchhiker's Guide to Python](https://docs.python-guide.org/) | Free online — opinionated best-practices for tooling, structure, deployment |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Scientific Computing with Python](https://www.freecodecamp.org/learn/scientific-computing-with-python/) | Free certification with 5 projects |
| [Codecademy — Learn Python 3](https://www.codecademy.com/learn/learn-python-3) | In-browser coding with instant feedback |
| [Exercism — Python Track](https://exercism.org/tracks/python) | 140+ exercises with free mentor feedback |
| [HackerRank — Python](https://www.hackerrank.com/domains/python) | Structured challenges from easy to hard |
| [LeetCode (Python)](https://leetcode.com/) | Interview prep — pick any problem, choose Python |
| [Kaggle Learn](https://www.kaggle.com/learn) | Free hands-on micro-courses on Pandas, ML, deep learning |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Corey Schafer](https://www.youtube.com/@coreyms) | The best Python educator on YouTube. Full tutorials on OOP, decorators, generators, async |
| [ArjanCodes](https://www.youtube.com/@ArjanCodes) | Advanced Python patterns, clean code, design patterns |
| [Tech with Tim](https://www.youtube.com/@TechWithTim) | Beginner-friendly, project-based Python tutorials |
| [mCoding](https://www.youtube.com/@mCoding) | Deep, often surprising Python internals |
| [Fireship — Python in 100 Seconds](https://www.youtube.com/watch?v=x7X9w_GIm1s) | Quick visual overview |
| [freeCodeCamp — Full Python Course](https://www.youtube.com/@freecodecamp) | 4+ hour comprehensive course |

### Podcasts & Newsletters

| Resource | Format |
|----------|--------|
| [Talk Python To Me](https://talkpython.fm/) | Weekly Python interviews — frameworks, libraries, careers |
| [Python Bytes](https://pythonbytes.fm/) | 30-min weekly news roundup |
| [Real Python Podcast](https://realpython.com/podcasts/rpp/) | Weekly conversations + tutorials |
| [PyCoder's Weekly](https://pycoders.com/) | Weekly newsletter — best Python articles, jobs, releases |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Python](https://roadmap.sh/python) | Interactive learning path with progress tracking |
| [roadmap.sh — AI Engineer](https://roadmap.sh/ai-engineer) | The 2026 must-have roadmap for the AI specialization |
| [roadmap.sh — Data Analyst](https://roadmap.sh/data-analyst) | Pandas, SQL, viz, statistics |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Python Extension (Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-python.python) | Essential — debugging, IntelliSense, testing |
| [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance) | Fast type checking and IntelliSense |
| [Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff) | Lint + format — replaces flake8/isort/black, 100× faster |
| [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter) | Auto-format on save (alternative to ruff format) |
| [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) | Notebooks inside VS Code |
| [autoDocstring](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring) | Generate docstring templates with `"""` + Tab |
| [uv](https://docs.astral.sh/uv/) | The 2026 package manager — replaces pip + venv + pip-tools, 10–100× faster |
| [pyenv](https://github.com/pyenv/pyenv) | Manage multiple Python versions on one machine |

### Online Playgrounds

| Playground | Best For |
|-----------|---------|
| [Replit](https://replit.com/) | Full IDE in browser, run Python instantly |
| [Google Colab](https://colab.research.google.com/) | Free Jupyter notebooks with GPUs/TPUs — perfect for ML |
| [Kaggle Notebooks](https://www.kaggle.com/code) | Free Jupyter + datasets + GPUs for ML |
| [Pyodide REPL](https://pyodide.org/en/stable/console.html) | Python running in your browser via WebAssembly |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [Python Cheat Sheet (Comprehensive)](https://www.pythoncheatsheet.org/) | Interactive, searchable — covers every Python topic |
| [Real Python Cheat Sheets](https://realpython.com/python-cheat-sheet/) | PDF downloads for specific topics |
| [Pandas Cheat Sheet (official)](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf) | Print and tape to your wall |
| [scikit-learn Algorithm Map](https://scikit-learn.org/stable/machine_learning_map.html) | Pick the right ML algorithm visually |

### AI / LLM SDK Docs

| Resource | What It Is |
|----------|-----------|
| [Anthropic Python SDK](https://docs.anthropic.com/en/api/client-sdks) | Official Claude SDK — the reference for AI work in Python |
| [OpenAI Python SDK](https://github.com/openai/openai-python) | Official OpenAI/GPT SDK |
| [LangChain Python](https://python.langchain.com/) | Framework for chains, agents, RAG |
| [LlamaIndex](https://docs.llamaindex.ai/) | Data framework for LLM apps and RAG |
| [Hugging Face Transformers](https://huggingface.co/docs/transformers) | Pre-trained models, fine-tuning, inference |

---

[Back to Main Syllabus](../README.md)

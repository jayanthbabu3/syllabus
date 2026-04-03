# Python Syllabus

A complete, structured learning path for Python — from your first `print()` to building web APIs, automating tasks, and writing production-ready code.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Python: 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Control Flow](#phase-2-control-flow)
- [Phase 3: Functions & Modules](#phase-3-functions--modules)
- [Phase 4: Data Structures](#phase-4-data-structures)
- [Phase 5: Object-Oriented Programming](#phase-5-object-oriented-programming)
- [Phase 6: File I/O & Error Handling](#phase-6-file-io--error-handling)
- [Phase 7: Advanced Python](#phase-7-advanced-python)
- [Phase 8: Standard Library](#phase-8-standard-library)
- [Phase 9: Web Development & APIs](#phase-9-web-development--apis)
- [Phase 10: Testing & Best Practices](#phase-10-testing--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Python requires **zero programming experience**. It's one of the best first languages — readable syntax, gentle learning curve, and used everywhere (web, data science, AI, automation).

- A computer (Windows, Mac, or Linux)
- A text editor ([VS Code](https://code.visualstudio.com/) recommended)
- Willingness to practice daily

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write your first Python program and understand the basics.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Python | High-level, interpreted language. Used for web, data science, AI, automation, scripting — everywhere |
| 2 | Installation | Install Python 3.10+, verify with `python --version`, set up VS Code with the Python extension |
| 3 | Python Interpreter | REPL mode (`python` in terminal) for quick experiments vs script mode (`python app.py`) for real programs |
| 4 | Variables & Naming | `name = "Alice"` — no type declaration needed. Use `snake_case` naming convention |
| 5 | Basic Data Types | `str`, `int`, `float`, `bool`, `None` — check with `type()`, convert with `int()`, `str()`, `float()` |
| 6 | Input & Output | `print()` for output with f-strings: `f"Hello {name}"`. `input()` for user input (always returns a string) |
| 7 | Comments | `#` for single-line. `"""Docstrings"""` for multi-line documentation |
| 8 | The Zen of Python | `import this` — Python's philosophy: readability counts, explicit is better than implicit |

> [!TIP]
> Use **f-strings** (Python 3.6+) for string formatting — they're the most readable and performant option:
> ```python
> name = "Alice"
> age = 30
> print(f"Hello, {name}! You are {age} years old.")
> # f-strings can contain any expression
> print(f"Next year you'll be {age + 1}")
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Python and run a script from the terminal
- [ ] Declare variables of different types and use f-strings
- [ ] Use the REPL for quick experiments

</details>

---

## Phase 2: Control Flow

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions and repeat actions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `elif` / `else` | Conditional branching: `if age >= 18:` — the colon and indentation are mandatory |
| 2 | Comparison Operators | `==`, `!=`, `<`, `>`, `<=`, `>=` — Python has no loose equality gotchas (unlike JavaScript) |
| 3 | Logical Operators | `and`, `or`, `not` — combine conditions. Short-circuit evaluation |
| 4 | Truthy & Falsy | `0`, `""`, `[]`, `{}`, `None`, `False` are falsy. Everything else is truthy |
| 5 | `for` Loops | `for item in iterable:` — iterate over lists, strings, ranges, dictionaries, files |
| 6 | `while` Loops | `while condition:` — repeat until condition is false. Avoid infinite loops |
| 7 | `break` & `continue` | `break` exits the loop. `continue` skips to the next iteration |
| 8 | `range()` | `range(10)`, `range(1, 11)`, `range(0, 20, 2)` — generate number sequences for loops |
| 9 | List Comprehensions | `[x * 2 for x in range(10) if x % 2 == 0]` — concise, Pythonic way to create lists |
| 10 | Dict Comprehensions | `{k: v for k, v in items}` — build dictionaries in one line |

> [!IMPORTANT]
> **Indentation is not optional in Python** — it defines code blocks. Use 4 spaces (not tabs). Wrong indentation = `IndentationError`:
> ```python
> if True:
>     print("This is indented correctly")  # 4 spaces
>     if True:
>         print("Nested — 8 spaces")
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a program that uses `if/elif/else` with user input
- [ ] Use `for` loops with `range()` and list comprehensions
- [ ] Explain the difference between `break` and `continue`

</details>

---

## Phase 3: Functions & Modules

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable code with functions and organize it into modules.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Defining Functions | `def greet(name):` — functions are defined with `def`, return `None` by default |
| 2 | Parameters & Arguments | Positional, keyword, and default arguments: `def greet(name, greeting="Hello"):` |
| 3 | `*args` & `**kwargs` | `*args` collects variable positional args as a tuple. `**kwargs` collects keyword args as a dict |
| 4 | Lambda Functions | `lambda x: x * 2` — anonymous one-liner functions. Use with `map()`, `filter()`, `sorted()` |
| 5 | Scope (LEGB Rule) | Local → Enclosing → Global → Built-in. Variables defined in functions are local by default |
| 6 | Type Hints | `def add(x: int, y: int) -> int:` — document expected types. Not enforced at runtime |
| 7 | Imports & Modules | `import os`, `from pathlib import Path`, `import json as j` — organize code into reusable files |
| 8 | `__name__ == "__main__"` | Guard that prevents code from running when the file is imported as a module |
| 9 | pip & Virtual Environments | `pip install requests`, `python -m venv venv` — install packages and isolate project dependencies |

> [!TIP]
> Always create a **virtual environment** for each project. It isolates dependencies so projects don't conflict:
> ```bash
> python -m venv venv          # Create virtual environment
> source venv/bin/activate     # Activate (Mac/Linux)
> venv\Scripts\activate        # Activate (Windows)
> pip install requests         # Install packages inside venv
> pip freeze > requirements.txt # Save dependencies
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with default parameters and `*args`/`**kwargs`
- [ ] Create a module and import it from another file
- [ ] Set up a virtual environment and install a package

</details>

---

## Phase 4: Data Structures

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Master Python's built-in data structures — they're incredibly powerful.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Lists | Mutable sequences: `[1, 2, 3]`. Methods: `.append()`, `.extend()`, `.pop()`, `.sort()`, `.reverse()` |
| 2 | Tuples | Immutable sequences: `(1, 2, 3)`. Unpacking: `x, y = (1, 2)`. Use for fixed collections and dict keys |
| 3 | Sets | Unordered, no duplicates: `{1, 2, 3}`. Operations: `union`, `intersection`, `difference`. Fast membership: `in` |
| 4 | Dictionaries | Key-value pairs: `{"name": "Alice"}`. Access with `[]` or `.get()`. Iterate `.keys()`, `.values()`, `.items()` |
| 5 | Strings | Immutable sequences: `.upper()`, `.lower()`, `.split()`, `.join()`, `.replace()`, `.strip()`, slicing |
| 6 | Slicing | `list[start:stop:step]`. Negative indices: `list[-1]`. Reverse: `list[::-1]`. Every other: `list[::2]` |
| 7 | Unpacking | `a, b = [1, 2]`, `first, *rest = [1, 2, 3, 4]` — `rest` gets `[2, 3, 4]` |
| 8 | Nested Structures | Lists of dicts, dicts of lists: `users[0]["name"]`. Build complex data from simple building blocks |

> [!IMPORTANT]
> **When to use which data structure:**
> - **List** → Ordered collection that changes: `[item1, item2]`
> - **Tuple** → Ordered collection that never changes: `(x, y)`
> - **Set** → Unique items, fast lookup: `{item1, item2}`
> - **Dict** → Key-value pairs, fast lookup by key: `{"key": "value"}`

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use all 4 data structures and explain when to use each
- [ ] Slice a list and string with negative indices and steps
- [ ] Use unpacking to swap variables: `a, b = b, a`

</details>

---

## Phase 5: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Model real-world entities with classes.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | `class User:` + `def __init__(self, name):` — create blueprints for objects |
| 2 | Attributes & Methods | Instance attributes (`self.name`), methods take `self` as first parameter |
| 3 | Inheritance | `class Admin(User):` inherits all User methods. `super().__init__()` calls parent constructor |
| 4 | Encapsulation | `_private` (convention), `__mangled` (name mangling). Use `@property` for controlled access |
| 5 | Polymorphism | Different classes respond to the same method name differently. Duck typing: "if it quacks..." |
| 6 | Magic Methods | `__str__()`, `__repr__()`, `__eq__()`, `__len__()`, `__add__()` — customize how objects behave |
| 7 | `@staticmethod` & `@classmethod` | Static: no `self`, utility function. Classmethod: takes `cls`, alternative constructors |
| 8 | Dataclasses | `@dataclass` — auto-generates `__init__`, `__repr__`, `__eq__`. Less boilerplate for data-holding classes |
| 9 | Abstract Classes | `from abc import ABC, abstractmethod` — define interfaces that subclasses must implement |

> [!TIP]
> Use `@dataclass` for classes that primarily hold data — it saves massive boilerplate:
> ```python
> from dataclasses import dataclass
>
> @dataclass
> class User:
>     name: str
>     email: str
>     age: int = 0
>
> # Auto-generates __init__, __repr__, __eq__
> user = User("Alice", "alice@example.com", 30)
> print(user)  # User(name='Alice', email='alice@example.com', age=30)
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with `__init__`, methods, and inheritance
- [ ] Implement `__str__` and `__eq__` magic methods
- [ ] Refactor a class to use `@dataclass`

</details>

---

## Phase 6: File I/O & Error Handling

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Read/write files and handle errors gracefully.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Reading Files | `with open("file.txt") as f:` — `f.read()`, `f.readlines()`, iterate with `for line in f:` |
| 2 | Writing Files | `open("file.txt", "w")` overwrites, `"a"` appends. `.write()`, `.writelines()` |
| 3 | Context Managers | `with` statement auto-closes files. No resource leaks. Implement custom ones with `__enter__`/`__exit__` |
| 4 | `try` / `except` / `finally` | Catch errors without crashing: `try: risky() except ValueError as e: handle(e) finally: cleanup()` |
| 5 | Common Exceptions | `ValueError`, `TypeError`, `KeyError`, `IndexError`, `FileNotFoundError`, `ZeroDivisionError` |
| 6 | Raising Exceptions | `raise ValueError("Invalid input")` — throw errors when preconditions aren't met |
| 7 | Custom Exceptions | `class ValidationError(Exception): pass` — domain-specific error types |
| 8 | Logging | `import logging` — `logging.info()`, `.warning()`, `.error()`. Use instead of `print()` in production |

> [!CAUTION]
> **Never catch bare `except:`** — it swallows all errors, including `KeyboardInterrupt` and `SystemExit`:
> ```python
> # WRONG — hides all errors including Ctrl+C
> try: risky()
> except: pass
>
> # RIGHT — catch specific exceptions
> try: risky()
> except ValueError as e:
>     logging.error(f"Validation failed: {e}")
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write files using `with` context manager
- [ ] Handle exceptions with `try/except` for specific error types
- [ ] Create a custom exception class

</details>

---

## Phase 7: Advanced Python

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master the features that make Python powerful and elegant.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Decorators | `@decorator` wraps functions — add logging, timing, auth without modifying the original function |
| 2 | Generators | `yield` instead of `return` — produce values lazily, one at a time. Memory-efficient for large data |
| 3 | Iterators | `__iter__()` + `__next__()` protocol — make any object iterable with `for x in obj:` |
| 4 | Type Hints | `from typing import Optional, List, Dict` — document types for better IDE support and `mypy` checking |
| 5 | `match` / `case` | Python 3.10+ structural pattern matching — like `switch` but with destructuring superpowers |
| 6 | Walrus Operator | `:=` assigns and returns: `if (n := len(data)) > 10:` — reduces redundant computation |
| 7 | `@property` Decorator | Computed attributes with getter/setter syntax: `user.name` instead of `user.get_name()` |
| 8 | Custom Context Managers | `@contextmanager` from `contextlib` — create `with` blocks for your own resource management |

> [!TIP]
> **Generators** are perfect for processing large files — they use almost no memory:
> ```python
> def read_large_file(path):
>     with open(path) as f:
>         for line in f:
>             yield line.strip()  # yields one line at a time
>
> # Process a 10GB file without loading it all into memory
> for line in read_large_file("huge.csv"):
>     process(line)
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a decorator that logs function calls and execution time
- [ ] Create a generator that yields Fibonacci numbers
- [ ] Use `match`/`case` for pattern matching

</details>

---

## Phase 8: Standard Library

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Python's "batteries included" — powerful built-in modules.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `pathlib` | `Path("dir") / "file.txt"` — modern file path handling. `.exists()`, `.read_text()`, `.glob()` |
| 2 | `json` | `json.loads()` (string → dict), `json.dumps()` (dict → string) — parse and create JSON data |
| 3 | `datetime` | `datetime.now()`, `timedelta`, `strftime()` (format), `strptime()` (parse) — date/time manipulation |
| 4 | `re` (Regex) | `re.search()`, `.findall()`, `.sub()` — pattern matching: `\d+` (digits), `\w+` (words), `.*` (anything) |
| 5 | `collections` | `Counter` (frequency), `defaultdict` (default values), `namedtuple`, `deque` (fast append/pop both ends) |
| 6 | `itertools` | `chain()`, `combinations()`, `permutations()`, `cycle()`, `islice()` — efficient iteration recipes |
| 7 | `functools` | `@lru_cache` (memoization), `@wraps` (decorator metadata), `reduce()`, `partial()` |
| 8 | `os` & `sys` | `os.environ` (env vars), `sys.argv` (CLI args), `os.getcwd()`, `sys.exit()` |
| 9 | `typing` | `Optional`, `Union`, `List`, `Dict`, `Callable`, `Protocol` — comprehensive type hint system |

> [!TIP]
> Use `pathlib.Path` instead of `os.path` — it's more readable and Pythonic:
> ```python
> from pathlib import Path
>
> config = Path("config") / "settings.json"    # OS-safe path joining
> if config.exists():
>     data = json.loads(config.read_text())     # Read file contents
> for py_file in Path("src").glob("**/*.py"):   # Find all Python files
>     print(py_file)
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Parse and create JSON with the `json` module
- [ ] Use `pathlib` for all file path operations
- [ ] Use `@lru_cache` to memoize an expensive function

</details>

---

## Phase 9: Web Development & APIs

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build web applications and consume/create APIs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | HTTP Basics | Request/response cycle, methods (GET, POST, PUT, DELETE), status codes, headers |
| 2 | `requests` Library | `requests.get(url)`, `.json()`, `.post()` with data, headers, error handling with `.raise_for_status()` |
| 3 | Flask Basics | `@app.route("/")` — minimal web framework. Templates with Jinja2, static files, request handling |
| 4 | FastAPI | Modern async framework: type hints = automatic validation + Swagger docs. `@app.get()`, `@app.post()` |
| 5 | REST API Design | Resource URLs, HTTP verbs, status codes, CRUD operations, JSON request/response |
| 6 | Web Scraping | BeautifulSoup: `soup.select("h1")`, `.find()`, `.get_text()` — extract data from web pages |
| 7 | Database Integration | SQLAlchemy (ORM), SQLite for small apps, PostgreSQL for production. Models, queries, migrations |
| 8 | Authentication | JWT tokens, password hashing with `bcrypt`, session management, securing API endpoints |

> [!TIP]
> **FastAPI** auto-generates interactive API documentation from your type hints:
> ```python
> from fastapi import FastAPI
> from pydantic import BaseModel
>
> app = FastAPI()
>
> class User(BaseModel):
>     name: str
>     email: str
>     age: int | None = None
>
> @app.post("/users", status_code=201)
> async def create_user(user: User):
>     return {"message": f"Created {user.name}"}
>
> # Visit http://localhost:8000/docs for auto-generated Swagger UI
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data from a public API with `requests`
- [ ] Build a REST API with FastAPI or Flask
- [ ] Scrape a website with BeautifulSoup

</details>

---

## Phase 10: Testing & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write tests, follow PEP 8, and produce professional-quality code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | pytest | `pip install pytest` — write test functions: `def test_add(): assert add(1, 2) == 3`. Fixtures, parametrize |
| 2 | unittest | Standard library test framework: `TestCase`, `setUp`/`tearDown`, running with `python -m unittest` |
| 3 | Mocking | `unittest.mock.Mock`, `@patch` — fake external dependencies (APIs, databases) in tests |
| 4 | Test Coverage | `coverage run -m pytest` → `coverage report` — measure which code is tested. Aim for 80%+ |
| 5 | PEP 8 | Python's style guide: 4-space indent, `snake_case` for functions, `PascalCase` for classes, max 79 chars |
| 6 | Linters & Formatters | `black` (auto-format), `flake8` (lint), `isort` (sort imports), `mypy` (type checking) |
| 7 | Project Structure | `src/`, `tests/`, `pyproject.toml`, `requirements.txt` — organize code professionally |
| 8 | Virtual Environments | Always use `venv` per project. Never install packages globally. Track deps in `requirements.txt` |

> [!TIP]
> Use `pytest` (not `unittest`) for new projects — it's simpler and more powerful:
> ```python
> # test_math.py
> def test_addition():
>     assert 1 + 1 == 2
>
> def test_string_upper():
>     assert "hello".upper() == "HELLO"
>
> # Run: pytest test_math.py -v
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 10+ tests with pytest and run them
- [ ] Achieve 80%+ test coverage on a project
- [ ] Format code with `black` and lint with `flake8`

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Mutable default arguments | `def func(items=[]):` reuses the same list across calls — items accumulate | Use `None`: `def func(items=None): items = items or []` |
| 2 | Modifying list while iterating | `for item in list: list.remove(item)` skips elements | Iterate a copy: `for item in list[:]` or use comprehension |
| 3 | Bare `except:` | Catches everything including `KeyboardInterrupt` — hides real bugs | Catch specific: `except ValueError as e:` |
| 4 | Not closing files | File handles leak without explicit close | Always use `with open(...) as f:` |
| 5 | Global variables | Hard to track, test, and debug | Pass data via function parameters and return values |
| 6 | No `__name__ == "__main__"` guard | Code runs when imported as a module | Add: `if __name__ == "__main__": main()` |
| 7 | `is` vs `==` confusion | `[] == []` is `True`, `[] is []` is `False` | Use `==` for values, `is` only for `None` |
| 8 | No virtual environment | Package conflicts between projects | Always: `python -m venv venv` per project |
| 9 | Using `print()` for debugging | Hard to find and remove, no log levels, clutters output | Use `logging` module with proper levels |
| 10 | Ignoring type hints | No IDE autocomplete, no static type checking, harder to read | Add type hints: `def greet(name: str) -> str:` |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What's the difference between lists and tuples?**
   - Lists are mutable (`append`, `remove`, etc.), tuples are immutable. Lists use `[]`, tuples use `()`. Use tuples for fixed collections, as dict keys, and when you want to prevent modification.

2. **What does `*args` and `**kwargs` mean?**
   - `*args` collects variable positional arguments into a tuple. `**kwargs` collects keyword arguments into a dictionary. Used to make flexible functions that accept any number of arguments.

3. **What is a lambda function?**
   - Anonymous function: `lambda x: x * 2`. Single expression, no `return` needed. Commonly used with `sorted()`, `map()`, `filter()` for quick transformations.

4. **How do you read a file in Python?**
   - `with open("file.txt") as f: content = f.read()`. Always use `with` for automatic file closing. `f.readlines()` returns a list of lines.

5. **What is a dictionary?**
   - Key-value data structure: `{"name": "Alice", "age": 25}`. O(1) lookup by key. Methods: `.keys()`, `.values()`, `.items()`, `.get()`, `.pop()`.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain list comprehensions with an example.**
   - Concise way to create lists: `[x*2 for x in range(5)]` = `[0, 2, 4, 6, 8]`. With condition: `[x for x in range(10) if x % 2 == 0]`. More Pythonic and faster than equivalent for loops.

2. **What are decorators?**
   - Functions that wrap other functions: `@decorator` applied above a function definition. They add behavior (logging, timing, auth) without modifying the original function. Use `@functools.wraps` to preserve the wrapped function's metadata.

3. **What is a generator and when would you use one?**
   - Function with `yield` instead of `return`. Produces values lazily (one at a time) — doesn't store all values in memory. Use for: large datasets, infinite sequences, streaming data. `next()` gets the next value.

4. **Explain shallow copy vs deep copy.**
   - Shallow copy (`copy.copy()`) duplicates the outer object but shares references to nested objects. Deep copy (`copy.deepcopy()`) recursively copies everything. Matters when nested data is mutable.

5. **How do you handle exceptions properly?**
   - Catch specific exceptions: `except ValueError as e:`. Use `finally` for cleanup. Raise custom exceptions for domain errors. Never use bare `except:`. Log exceptions instead of silently passing.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How does Python's GIL affect multithreading?**
   - The Global Interpreter Lock prevents multiple threads from executing Python bytecode simultaneously. Threading helps I/O-bound tasks (GIL is released during I/O) but not CPU-bound tasks. Use `multiprocessing` for CPU-bound work — each process has its own GIL.

2. **What is duck typing?**
   - "If it walks like a duck and quacks like a duck, it's a duck." Python checks what an object can DO, not what it IS. Any object with `__len__()` can use `len()`. Enables polymorphism without inheritance.

3. **Explain metaclasses.**
   - Classes whose instances are classes. `class Meta(type):` controls class creation — can modify or validate class definitions. Used in frameworks (Django models, SQLAlchemy). "99% of programmers don't need metaclasses."

4. **How do you handle circular imports?**
   - Module A imports B, B imports A → `ImportError`. Solutions: restructure code (extract shared code to third module), import inside functions (lazy import), use `TYPE_CHECKING` from `typing` for type-hint-only imports.

5. **What is the MRO (Method Resolution Order)?**
   - The order Python searches for methods in inheritance: child → parents (left to right) → grandparents. Uses C3 linearization algorithm. Check with `ClassName.__mro__`. Important for multiple inheritance (diamond problem).

</details>

---

## Practice Projects

### Project 1: Personal Finance Tracker
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** CLI app to record income/expenses, categorize transactions, calculate totals, and save to a JSON file.

**Skills practiced:** Variables, loops, functions, lists, dicts, file I/O.

---

### Project 2: Quiz Game with OOP
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** Object-oriented quiz: `Question` class, `Quiz` class, scoring, difficulty levels, loading questions from a file.

**Skills practiced:** Classes, inheritance, file I/O, error handling, dataclasses.

---

### Project 3: Web Scraper & Data Analyzer
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** Scrape data from a website (headlines, prices), save to CSV/JSON, analyze trends with `collections.Counter`.

**Skills practiced:** `requests`, BeautifulSoup, standard library, generators, decorators.

---

### Project 4: REST API with FastAPI
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** A complete CRUD API for a task manager with authentication, database (SQLite), validation, and auto-generated docs.

**Skills practiced:** FastAPI, Pydantic, SQLAlchemy, JWT auth, REST design.

---

### Project 5: Full-Stack Blog
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** Blog with user auth, CRUD posts, comments, Flask/FastAPI backend, 80%+ test coverage, deployed with Docker.

**Skills practiced:** Everything from all phases — your Python graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [docs.python.org](https://docs.python.org/3/) | Official Python documentation — every module, function, and feature |
| [Real Python](https://realpython.com/) | Best tutorial site for Python. Deep, well-written articles on every topic |
| [Python Tutorial (official)](https://docs.python.org/3/tutorial/) | The official tutorial by Python's creator. Authoritative and thorough |
| [Automate the Boring Stuff](https://automatetheboringstuff.com/) | Free book — learn Python by automating real tasks (files, web, Excel) |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Python for Everybody](https://www.freecodecamp.org/learn/scientific-computing-with-python/) | Free certification with 5 projects |
| [Codecademy — Learn Python 3](https://www.codecademy.com/learn/learn-python-3) | In-browser coding with instant feedback |
| [Exercism — Python Track](https://exercism.org/tracks/python) | 130+ exercises with free mentor feedback |
| [HackerRank — Python](https://www.hackerrank.com/domains/python) | Structured challenges from easy to hard |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Corey Schafer](https://www.youtube.com/@coreyms) | The best Python educator on YouTube. Full tutorials on OOP, decorators, generators, async |
| [Tech with Tim](https://www.youtube.com/@TechWithTim) | Beginner-friendly, project-based Python tutorials |
| [freeCodeCamp — Python Full Course](https://www.youtube.com/@freecodecamp) | 4+ hour comprehensive course |
| [Fireship — Python in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview |
| [ArjanCodes](https://www.youtube.com/@ArjanCodes) | Advanced Python patterns, clean code, design patterns |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Python](https://roadmap.sh/python) | Interactive learning path with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Python Extension (Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-python.python) | Essential — debugging, IntelliSense, testing integration |
| [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance) | Fast type checking and IntelliSense |
| [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter) | Auto-format on save. Consistent code style |
| [isort](https://marketplace.visualstudio.com/items?itemName=ms-python.isort) | Auto-sort imports on save |
| [autoDocstring](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring) | Generate docstring templates with `"""` + Tab |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [Python Cheat Sheet (Comprehensive)](https://www.pythoncheatsheet.org/) | Interactive, searchable — covers every Python topic |
| [Real Python Cheat Sheets](https://realpython.com/python-cheat-sheet/) | PDF downloads for specific topics |

---

[Back to Main Syllabus](../README.md)

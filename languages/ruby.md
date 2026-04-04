# Ruby Syllabus

A complete, structured learning path for Ruby — from your first `puts` to building clean applications with gems, testing, metaprogramming, and Ruby on Rails.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Ruby: 4.0+](https://img.shields.io/badge/Ruby-4.0%2B-CC342D)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Syntax, Variables & Control Flow](#phase-2-syntax-variables--control-flow)
- [Phase 3: Methods, Blocks & Iteration](#phase-3-methods-blocks--iteration)
- [Phase 4: Collections & Enumerable](#phase-4-collections--enumerable)
- [Phase 5: Object-Oriented Programming](#phase-5-object-oriented-programming)
- [Phase 6: Files, Gems & Tooling](#phase-6-files-gems--tooling)
- [Phase 7: Exceptions, Testing & Debugging](#phase-7-exceptions-testing--debugging)
- [Phase 8: Advanced Ruby](#phase-8-advanced-ruby)
- [Phase 9: Web Development with Rails](#phase-9-web-development-with-rails)
- [Phase 10: Architecture, Performance & Production Ruby](#phase-10-architecture-performance--production-ruby)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Ruby is beginner-friendly, but if your goal is **Rails development**, basic HTML, CSS, HTTP, and SQL knowledge will help a lot.

- A computer (Windows, macOS, or Linux)
- A code editor ([VS Code](https://code.visualstudio.com/) or RubyMine)
- Willingness to practice in `irb` and on small scripts daily
- Basic command line familiarity is helpful

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Ruby is, install it correctly, and write your first programs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Ruby | A dynamic, object-oriented language focused on programmer happiness and readable code |
| 2 | Installation | Install Ruby with a version manager like `rbenv`, `asdf`, or your OS package manager |
| 3 | `ruby` vs `irb` | `ruby file.rb` runs scripts, `irb` is the interactive REPL for experimentation |
| 4 | Hello World | `puts "Hello, world!"` and how Ruby files are executed |
| 5 | Comments & Style | `#` comments, file naming, and why Ruby favors expressive, readable code |
| 6 | Variables | Local variables, naming conventions, and Ruby's dynamic typing model |
| 7 | Basic I/O | `puts`, `print`, `gets`, `chomp`, and simple user interaction |

> [!TIP]
> Spend real time in `irb`. Ruby becomes much easier once you get comfortable trying expressions, objects, and methods interactively.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Ruby and verify with `ruby --version`
- [ ] Run Ruby in both `irb` and a `.rb` file
- [ ] Read input with `gets.chomp` and print output with `puts`

</details>

---

## Phase 2: Syntax, Variables & Control Flow

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the basic building blocks of Ruby programs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Numbers, Strings, Booleans, `nil` | Ruby's basic value types and how everything is still an object |
| 2 | String Interpolation | `"Hello #{name}"` instead of manual concatenation |
| 3 | Symbols | Lightweight immutable identifiers like `:active` and why Ruby code uses them heavily |
| 4 | Conditionals | `if`, `elsif`, `else`, `unless`, ternary expressions |
| 5 | Comparison & Truthiness | Only `false` and `nil` are falsy in Ruby |
| 6 | Loops | `while`, `until`, `for`, and why iterator methods are usually preferred |
| 7 | Case Statements | `case` for readable multi-branch logic and simple pattern matching |
| 8 | Basic Scope | Local variable visibility and method boundaries |

> [!IMPORTANT]
> Ruby truthiness is simple: only `false` and `nil` are false. `0`, `""`, and `[]` are all truthy.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `if`, `unless`, and `case` correctly
- [ ] Explain the difference between strings and symbols
- [ ] Write a small script with loops and user input

</details>

---

## Phase 3: Methods, Blocks & Iteration

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Ruby gets powerful when you understand methods, blocks, and iterators.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Defining Methods | `def greet(name)` and implicit returns |
| 2 | Parameters | Positional, default, keyword, splat (`*args`), double splat (`**kwargs`) |
| 3 | Blocks | `each do |item| ... end` and `{ |x| ... }` block syntax |
| 4 | Yield | Methods that accept and execute blocks with `yield` |
| 5 | Iterators | `times`, `upto`, `downto`, `each`, `map`, `select`, `reject` |
| 6 | Lambdas & Procs | Callable objects and how they differ from blocks |
| 7 | Method Chaining | Writing clean pipelines like `users.select(...).map(...)` |
| 8 | Predicate & Bang Methods | `empty?`, `include?`, `upcase!` naming conventions |

> [!TIP]
> Idiomatic Ruby replaces many explicit loops with iterator methods. Reach for `each`, `map`, and `select` before `while`.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write methods with default and keyword arguments
- [ ] Use blocks with `each`, `map`, and `select`
- [ ] Explain the difference between a block, a proc, and a lambda

</details>

---

## Phase 4: Collections & Enumerable

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master arrays, hashes, ranges, and the `Enumerable` module.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Arrays | Indexing, slicing, mutation, and common array methods |
| 2 | Hashes | Key-value data structures, symbol keys, defaults, nested hashes |
| 3 | Ranges | `(1..10)` and `(1...10)` plus iteration and membership checks |
| 4 | `Enumerable` | Shared methods like `map`, `find`, `group_by`, `any?`, `all?` |
| 5 | Transformations | Converting and reshaping data with chained methods |
| 6 | Sorting | `sort`, `sort_by`, custom comparators |
| 7 | Sets | Unique collections with `Set` from the standard library |
| 8 | Nested Data | Working with arrays of hashes and real-world data shapes |

> [!IMPORTANT]
> `Enumerable` is one of Ruby's superpowers. Once you understand it, many problems become "transform this collection" instead of "write a big loop."

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use arrays, hashes, and ranges appropriately
- [ ] Solve problems with `Enumerable` instead of manual loops
- [ ] Transform an array of hashes into grouped or filtered output

</details>

---

## Phase 5: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn Ruby's object model and how to design maintainable classes.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | Defining classes, instantiating objects, calling instance methods |
| 2 | `initialize` | Constructor logic and instance variables like `@name` |
| 3 | Getters & Setters | `attr_reader`, `attr_writer`, `attr_accessor` |
| 4 | Inheritance | Reusing behavior with `class Admin < User` |
| 5 | Modules | Mixins for shared behavior and namespacing |
| 6 | Visibility | `public`, `private`, `protected` and responsible encapsulation |
| 7 | Class Methods | `def self.build` and factory-style APIs |
| 8 | Duck Typing | Ruby cares about behavior, not explicit interface declarations |

> [!TIP]
> Prefer composition and small objects over deep inheritance trees. Ruby makes mixins easy, but overusing them still creates complexity.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build classes with constructors and attribute helpers
- [ ] Use modules for shared behavior
- [ ] Explain duck typing with a practical example

</details>

---

## Phase 6: Files, Gems & Tooling

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Move from tiny scripts to real Ruby projects with dependencies and structure.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | File I/O | `File.read`, `File.write`, iterating lines, JSON and CSV basics |
| 2 | Standard Library | `json`, `csv`, `date`, `set`, `pathname` |
| 3 | Gems | Installing packages with `gem install` and understanding the Ruby ecosystem |
| 4 | Bundler | `Gemfile`, `bundle install`, version locking, reproducible environments |
| 5 | Project Structure | Organizing code into `lib/`, `bin/`, and test directories |
| 6 | REPL Tools | `irb`, `pry`, and fast debugging workflows |
| 7 | Formatting & Linting | RuboCop and style enforcement |
| 8 | Documentation | README quality, YARD basics, and self-explanatory APIs |

> [!CAUTION]
> Do not install gems globally and hope for the best. Use Bundler per project so dependencies stay predictable.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write files safely
- [ ] Create a project with a `Gemfile` and install dependencies with Bundler
- [ ] Run RuboCop and fix style issues

</details>

---

## Phase 7: Exceptions, Testing & Debugging

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn how to make Ruby code reliable and maintainable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Exceptions | `begin`, `rescue`, `else`, `ensure`, `raise` |
| 2 | Custom Errors | Domain-specific exception classes and better error messages |
| 3 | Defensive Coding | Validating inputs and failing clearly |
| 4 | Minitest | Ruby's standard testing library and test structure |
| 5 | RSpec | Example-style tests, expectations, and spec-driven workflows |
| 6 | Test Doubles | Mocks, stubs, and when not to overuse them |
| 7 | Debugging | `puts`, `p`, `pp`, breakpoints, `pry`, stack traces |
| 8 | Refactoring | Improving code while keeping tests green |

> [!IMPORTANT]
> Rescue only the exceptions you expect. A broad `rescue` hides bugs and makes debugging much harder.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Raise and rescue exceptions intentionally
- [ ] Write unit tests for a small Ruby project
- [ ] Use a debugger or REPL to inspect runtime state

</details>

---

## Phase 8: Advanced Ruby

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Explore the parts of Ruby that make the language unusually expressive.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Metaprogramming Basics | `send`, `define_method`, `method_missing`, introspection |
| 2 | Reflection | Exploring classes, modules, methods, ancestors, and object state |
| 3 | Pattern Matching | Modern `case ... in` syntax and destructuring |
| 4 | Enumerators | Lazy iteration and advanced traversal patterns |
| 5 | Fibers & Concurrency | Fibers, threads, and when concurrency matters in Ruby |
| 6 | Immutability | Freezing objects and designing safer APIs |
| 7 | Performance Awareness | Measuring hotspots, allocations, and avoiding accidental slowness |
| 8 | Ruby Internals (Intro) | MRI, garbage collection, and what the interpreter is doing for you |

> [!WARNING]
> Metaprogramming is powerful but easy to abuse. Use it to remove repetition, not to make ordinary code mysterious.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use pattern matching on hashes or arrays
- [ ] Explain when metaprogramming is useful and when it is harmful
- [ ] Profile or benchmark a small performance issue

</details>

---

## Phase 9: Web Development with Rails

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Apply Ruby in the ecosystem most people learn it for: Rails.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Rails | Convention over configuration and rapid application development |
| 2 | Rails App Structure | `app/`, `config/`, `db/`, `lib/`, routes, controllers, models, views |
| 3 | MVC | How requests flow through models, views, and controllers |
| 4 | Active Record | Models, migrations, validations, associations, queries |
| 5 | Routing & REST | Resourceful routes and standard CRUD patterns |
| 6 | Forms & Params | Handling user input safely and predictably |
| 7 | Background Jobs & Mailers | Async work and side effects outside request-response cycles |
| 8 | Auth & Authorization | Session-based auth, policies, and common Rails security concerns |

> [!TIP]
> Learn core Ruby before Rails. Rails feels magical when Ruby is weak, but very sensible when Ruby is strong.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a small Rails app with one resource and full CRUD
- [ ] Write migrations, validations, and associations
- [ ] Explain the MVC request lifecycle

</details>

---

## Phase 10: Architecture, Performance & Production Ruby

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Turn working Ruby code into maintainable production software.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Service Objects & POROs | Keeping business logic out of controllers and models |
| 2 | Dependency Boundaries | Designing small, testable objects with clear responsibilities |
| 3 | Caching | Fragment caching, memoization, and avoiding premature optimization |
| 4 | Background Processing | Sidekiq-style job systems and queue-driven workflows |
| 5 | Monitoring & Logging | Useful logs, error reporting, and operational visibility |
| 6 | Security Basics | Secrets, dependency auditing, mass assignment awareness, safe defaults |
| 7 | Deployment | Containers, platform services, CI, and environment-based configuration |
| 8 | Long-Term Maintainability | Refactoring, code review quality, documentation, and upgrade strategy |

> [!TIP]
> Production Ruby is less about clever syntax and more about boring reliability: clear boundaries, good tests, good logging, and predictable deploys.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Refactor a Rails or Ruby project toward smaller service objects
- [ ] Add logging, tests, and dependency auditing
- [ ] Deploy a small Ruby app and document the setup

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using loops where `Enumerable` fits | More code, less clarity, easier to introduce bugs | Prefer `each`, `map`, `select`, `find`, `group_by` |
| 2 | Rescuing all exceptions | Hides real failures and makes debugging painful | Rescue only expected exception classes |
| 3 | Overusing metaprogramming | Clever code becomes unreadable fast | Use explicit methods unless duplication is truly repetitive |
| 4 | Ignoring Bundler | Dependency versions drift across machines | Commit `Gemfile` and `Gemfile.lock` |
| 5 | Deep inheritance hierarchies | Hard to reason about and fragile | Prefer small objects and composition |
| 6 | Confusing strings and symbols | Leads to subtle key-access bugs | Be consistent with key types in hashes |
| 7 | Monkey-patching core classes casually | Can break gems and surprise teammates | Use refinements, helpers, or wrapper objects instead |
| 8 | No tests for business logic | Refactoring becomes risky | Add unit tests around core behavior |
| 9 | Treating Rails as "all of Ruby" | Weak Ruby foundations limit growth | Learn the language before the framework magic |
| 10 | Packing too much into one class | Huge models/controllers become impossible to maintain | Extract responsibilities into modules or service objects |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What makes Ruby different from many other languages?**
   - Ruby is dynamic, object-oriented, and heavily optimized for readability and developer happiness. Everything is an object, and the language leans on expressive methods and blocks.

2. **What's the difference between a string and a symbol?**
   - A string is mutable text data like `"status"`. A symbol is an immutable identifier like `:status`, often used for keys, labels, and method names.

3. **What is a block in Ruby?**
   - A block is a chunk of code passed to a method. It's a core Ruby feature used by iterators like `each`, `map`, and `select`.

4. **What does `attr_accessor` do?**
   - It creates both a getter and setter for an instance variable. `attr_reader` creates only a getter, `attr_writer` only a setter.

5. **What is Bundler used for?**
   - Bundler manages project dependencies through `Gemfile` and locks exact versions with `Gemfile.lock`.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain duck typing in Ruby.**
   - Ruby cares whether an object responds to the methods you need, not whether it comes from a specific class. Behavior matters more than type declarations.

2. **What's the difference between a proc and a lambda?**
   - Both wrap callable code, but lambdas enforce argument count more strictly and return from themselves, while procs are looser and can affect the enclosing method's control flow.

3. **When would you use a module instead of a class?**
   - Use a module for namespacing or mixin behavior that multiple classes should share, not for objects that need instantiation.

4. **What is `Enumerable` and why is it important?**
   - `Enumerable` is a mixin that gives collection-style methods to classes that define `each`. It's central to idiomatic Ruby data processing.

5. **How do you structure business logic in a Rails app?**
   - Keep controllers thin, avoid bloated models, and move reusable domain behavior into POROs, service objects, query objects, or policy objects when appropriate.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How does Ruby method lookup work?**
   - Ruby searches the receiver's class, included modules, superclass chain, and ancestors in order. `ancestors` reveals the lookup chain.

2. **What is metaprogramming, and when is it appropriate?**
   - Writing code that defines or changes code at runtime. It's appropriate when it removes meaningful repetition without hiding important behavior.

3. **What problems can monkey patching cause?**
   - It can change global behavior unexpectedly, break dependencies, and make debugging harder because core classes no longer behave like everyone expects.

4. **How would you improve performance in a Ruby app?**
   - Measure first with profiling, then reduce allocations, optimize queries, cache expensive work, and move heavy tasks off the request path.

5. **How do you design for maintainability in Ruby?**
   - Prefer small objects, explicit names, clear boundaries, isolated side effects, dependable tests, and minimal magic.

</details>

---

## Practice Projects

### Project 1: CLI Habit Tracker
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A command-line tool that records habits, prints summaries, and saves data to a JSON file.

**Skills practiced:** Input/output, methods, blocks, arrays, hashes.

---

### Project 2: Data Cleanup Toolkit
![Phase 4-6](https://img.shields.io/badge/After-Phase%204--6-yellow)

**What you'll build:** A Ruby script that reads CSV data, cleans malformed rows, groups records, and exports a report.

**Skills practiced:** `Enumerable`, file I/O, standard library, gem usage.

---

### Project 3: Object-Oriented Library System
![Phase 5-7](https://img.shields.io/badge/After-Phase%205--7-yellow)

**What you'll build:** Classes for books, users, loans, due dates, and fines with a complete automated test suite.

**Skills practiced:** OOP, modules, exceptions, unit testing.

---

### Project 4: Mini Sinatra or Rails App
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** A CRUD web app for tasks, recipes, or notes with forms, database persistence, and authentication.

**Skills practiced:** MVC, routing, Active Record, REST, validations.

---

### Project 5: Production Rails Platform
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A polished Rails app with background jobs, email, authorization, CI, and deployment.

**Skills practiced:** Everything from all phases — your Ruby graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Ruby Documentation](https://www.ruby-lang.org/en/documentation/) | Official learning hub with docs, guides, and tools |
| [docs.ruby-lang.org](https://docs.ruby-lang.org/en/) | Official API and language documentation |
| [Ruby in Twenty Minutes](https://www.ruby-lang.org/en/documentation/quickstart/) | Fast official intro that gets you using Ruby immediately |
| [Ruby on Rails Guides](https://guides.rubyonrails.org/getting_started.html) | Best official place to start Rails after core Ruby |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Exercism — Ruby Track](https://exercism.org/tracks/ruby) | Practice exercises with mentor feedback |
| [The Odin Project — Ruby Course](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/ruby) | Project-based learning with strong fundamentals |
| [Try Ruby](https://try.ruby-lang.org/) | Tiny browser-based Ruby practice |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [GoRails](https://gorails.com/start) | Practical Ruby and Rails teaching with production context |
| [Drifting Ruby](https://www.driftingruby.com/) | Short focused lessons on real Ruby and Rails problems |
| [freeCodeCamp](https://www.youtube.com/@freecodecamp) | Long-form beginner-friendly programming courses |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Ruby LSP](https://marketplace.visualstudio.com/items?itemName=Shopify.ruby-lsp) | Language server support in VS Code |
| [RuboCop](https://rubocop.org/) | Style enforcement and code quality checks |
| [Bundler](https://bundler.io/) | Dependency management for Ruby projects |
| [Pry](https://pry.github.io/) | Better interactive debugging than plain `irb` |
| [RSpec](https://rspec.info/) | Most widely used Ruby testing framework |

### Cheat Sheets & Further Reading

| Resource | Format |
|----------|--------|
| [ruby-doc.org](https://ruby-doc.org/) | Community API documentation and reference |
| [Ruby Style Guide](https://rubystyle.guide/) | Practical conventions for writing idiomatic Ruby |

---

[Back to Main Syllabus](../README.md)

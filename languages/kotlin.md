# Kotlin Syllabus

A complete, structured learning path for Kotlin — from your first `println()` to building Android, server-side, and multiplatform applications with coroutines, strong typing, and modern architecture.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Kotlin: 2.3+](https://img.shields.io/badge/Kotlin-2.3%2B-7F52FF)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables, Control Flow & Null Safety](#phase-2-variables-control-flow--null-safety)
- [Phase 3: Functions, Collections & Lambdas](#phase-3-functions-collections--lambdas)
- [Phase 4: Classes, Objects & Data Modeling](#phase-4-classes-objects--data-modeling)
- [Phase 5: Generics, Extensions & Functional Patterns](#phase-5-generics-extensions--functional-patterns)
- [Phase 6: Coroutines & Concurrency](#phase-6-coroutines--concurrency)
- [Phase 7: Gradle, Modules & Testing](#phase-7-gradle-modules--testing)
- [Phase 8: Android with Kotlin](#phase-8-android-with-kotlin)
- [Phase 9: Server-Side & Multiplatform Kotlin](#phase-9-server-side--multiplatform-kotlin)
- [Phase 10: Architecture, Performance & Production Kotlin](#phase-10-architecture-performance--production-kotlin)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Kotlin is beginner-friendly, but it is especially productive if you already know basic programming concepts. If your main goal is Android, Android Studio and mobile UI concepts will become important later.

- A computer with IntelliJ IDEA or Android Studio installed
- Basic command line familiarity
- Willingness to practice with console programs before jumping into full apps
- Java knowledge is helpful but not required

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Kotlin is, how it runs, and where it is used.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Kotlin | A concise, statically typed language for JVM, Android, server, web, and native targets |
| 2 | Installation | Kotlin support inside IntelliJ IDEA and Android Studio, plus CLI basics |
| 3 | Kotlin Targets | Kotlin/JVM, Android, Kotlin Multiplatform, Kotlin/JS, Kotlin/Native |
| 4 | First Program | `fun main() { println("Hello") }` and the shape of a Kotlin file |
| 5 | REPL & Playground | Fast experimentation in the browser and locally |
| 6 | Project Setup | Creating a console app and understanding source layout |
| 7 | Kotlin vs Java | Less boilerplate, null safety, extension functions, and interoperability |

> [!TIP]
> Learn Kotlin as Kotlin. If you only translate Java habits into Kotlin syntax, you will miss most of the language's real strengths.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create and run a small Kotlin console app
- [ ] Explain the major platforms Kotlin targets
- [ ] Compare a simple Kotlin example to equivalent Java-style code

</details>

---

## Phase 2: Variables, Control Flow & Null Safety

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn the core syntax and the safety features that define Kotlin.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `val` vs `var` | Immutable-first thinking and when mutation is appropriate |
| 2 | Basic Types | Numbers, strings, booleans, arrays, ranges |
| 3 | String Templates | `"Hello, $name"` and expression embedding |
| 4 | `if` and `when` | Expressions, not just statements |
| 5 | Loops | `for`, ranges, `while`, collection iteration |
| 6 | Nullability | `String` vs `String?` and why Kotlin prevents many NPEs |
| 7 | Safe Calls & Elvis | `?.`, `?:`, `let`, and null-aware programming |
| 8 | Smart Casts | Type checks with `is` and compiler-assisted narrowing |

> [!IMPORTANT]
> Null safety is the feature that changes how you design Kotlin code. Do not treat it as syntax you can ignore with `!!`.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `val` by default and explain why
- [ ] Handle nullable values without `!!`
- [ ] Write code using `when` and smart casts

</details>

---

## Phase 3: Functions, Collections & Lambdas

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build reusable behavior and learn Kotlin's expressive collection APIs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Functions | Parameters, return types, defaults, named arguments |
| 2 | Expression Bodies | Short, readable function syntax |
| 3 | Collections | Lists, sets, maps, mutable vs immutable views |
| 4 | Collection Operations | `map`, `filter`, `flatMap`, `associate`, `groupBy` |
| 5 | Lambdas | Function literals, trailing lambdas, higher-order functions |
| 6 | Scope Functions | `let`, `run`, `apply`, `also`, `with` and when to use each |
| 7 | Destructuring | Pulling values cleanly from pairs, maps, and data classes |
| 8 | Sequences | Lazy transformations for larger pipelines |

> [!TIP]
> Kotlin collection chains are powerful, but clarity matters more than squeezing everything into one line. Prefer readable pipelines over clever ones.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with named and default arguments
- [ ] Transform collections with `map`, `filter`, and `groupBy`
- [ ] Explain the purpose of at least three scope functions

</details>

---

## Phase 4: Classes, Objects & Data Modeling

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Model domain data using Kotlin's concise OOP features.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Constructors | Primary and secondary constructors |
| 2 | Properties | Custom getters/setters, backing fields, visibility |
| 3 | Data Classes | Auto-generated `equals`, `hashCode`, `copy`, `toString` |
| 4 | Objects & Companion Objects | Singletons and factory-like APIs |
| 5 | Inheritance | `open`, `override`, abstract classes |
| 6 | Interfaces | Contracts, multiple inheritance of behavior |
| 7 | Sealed Classes | Modeling restricted state machines and result types |
| 8 | Enums | Enumerated values and enum-specific behavior |

> [!IMPORTANT]
> Kotlin gives you data classes and sealed classes for a reason. Use them instead of defaulting to massive mutable classes with unclear state.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create and use a data class
- [ ] Model a result state with a sealed class
- [ ] Explain when an `object` is better than a class instance

</details>

---

## Phase 5: Generics, Extensions & Functional Patterns

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Learn the abstractions that make Kotlin expressive without losing type safety.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Generics | Reusable typed APIs with constraints |
| 2 | Extension Functions | Adding behavior without modifying original classes |
| 3 | Extension Properties | Lightweight computed APIs on existing types |
| 4 | Reified Type Parameters | Safer generic operations in inline functions |
| 5 | Functional Error Models | `Result`, sealed outcomes, pure transformation pipelines |
| 6 | Immutability Patterns | Safer data flow with copies and immutable collections |
| 7 | DSL Basics | Lambdas with receiver and Kotlin's builder style |
| 8 | Java Interop | Using Java libraries and handling platform types safely |

> [!CAUTION]
> Scope functions and extensions are useful, but overusing them can make code feel like a puzzle. Favor explicitness when behavior is non-trivial.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write an extension function and a generic utility
- [ ] Use a sealed result type instead of throwing for a recoverable failure
- [ ] Explain what makes Kotlin-Java interop powerful and risky

</details>

---

## Phase 6: Coroutines & Concurrency

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn Kotlin's modern concurrency model.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Suspend Functions | `suspend` as the foundation of coroutine-based APIs |
| 2 | Coroutine Builders | `launch`, `async`, `runBlocking` and their roles |
| 3 | Structured Concurrency | Scope ownership, cancellation, parent-child jobs |
| 4 | Dispatchers | `Default`, `IO`, `Main`, confinement, and thread usage |
| 5 | Error Handling | Exception propagation, supervisors, retry patterns |
| 6 | Flow | Asynchronous streams and reactive-style data handling |
| 7 | Shared State | Mutexes, actors, and avoiding race conditions |
| 8 | Testing Coroutines | Deterministic tests for async behavior |

> [!TIP]
> Coroutines are not "lightweight threads you can fire anywhere." Their power comes from structured scopes, cancellation, and explicit lifecycle ownership.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a suspending function and call it correctly
- [ ] Explain structured concurrency in plain language
- [ ] Use `Flow` or coroutine streams in a small example

</details>

---

## Phase 7: Gradle, Modules & Testing

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Organize Kotlin projects as real software, not single files.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Gradle Basics | Build scripts, tasks, dependencies, plugins |
| 2 | Project Structure | Source sets, modules, packages, separation of concerns |
| 3 | Dependency Management | Libraries, version catalogs, update hygiene |
| 4 | Unit Testing | JUnit or Kotlin test frameworks, assertions, fixtures |
| 5 | Mocking & Fakes | Isolating dependencies without overcomplicating tests |
| 6 | Static Analysis | Detekt, ktlint, formatting, and team conventions |
| 7 | Documentation | README quality, package docs, self-explanatory APIs |
| 8 | Build Performance | Avoiding unnecessarily slow Gradle setups |

> [!IMPORTANT]
> If your Kotlin code is growing, modularity and tests matter more than syntax. Small clean modules beat giant "core" packages every time.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a multi-package Kotlin project
- [ ] Add tests and linting to the build
- [ ] Explain how Gradle dependencies are managed

</details>

---

## Phase 8: Android with Kotlin

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Apply Kotlin to the ecosystem where it is most widely used professionally.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Android Project Basics | Activities, composables, resources, app manifest |
| 2 | Jetpack Compose | Declarative UI with Kotlin-first APIs |
| 3 | State & UI Logic | State hoisting, `ViewModel`, lifecycle-aware data flow |
| 4 | Coroutines on Android | `viewModelScope`, main-safety, structured async work |
| 5 | Navigation | Screen transitions, arguments, multi-screen structure |
| 6 | Persistence | Room, DataStore, and local app state |
| 7 | Networking | Retrofit, serialization, repositories, offline thinking |
| 8 | Android Testing | Unit, UI, and instrumentation testing basics |

> [!TIP]
> Treat Android as a separate platform skill layered on top of Kotlin fundamentals. Do not try to learn Kotlin and full Android complexity at the same time on day one.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a small Android app in Kotlin
- [ ] Explain where business logic should live relative to the UI
- [ ] Use coroutines and persistence in a mobile flow

</details>

---

## Phase 9: Server-Side & Multiplatform Kotlin

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> See how Kotlin extends beyond Android into backend and shared-code systems.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Server-Side Kotlin | Ktor, Spring Boot, and JVM backend patterns |
| 2 | HTTP APIs | Routing, serialization, validation, error responses |
| 3 | Database Layers | Exposed, JPA, or SQL-first approaches |
| 4 | Dependency Injection | Constructor injection and wiring app components |
| 5 | Kotlin Multiplatform | Sharing domain logic across Android, iOS, desktop, web |
| 6 | Shared Modules | Deciding what should and should not be shared |
| 7 | Serialization | `kotlinx.serialization` and cross-platform data models |
| 8 | Platform Boundaries | Expect/actual, adapters, and platform-specific APIs |

> [!WARNING]
> Multiplatform works best when you share the right layers. Shared business logic is usually high value; forcing all UI to be shared is often not.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a small backend or API in Kotlin
- [ ] Explain what Kotlin Multiplatform is actually good for
- [ ] Identify a clean boundary for shared business logic

</details>

---

## Phase 10: Architecture, Performance & Production Kotlin

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn how to write Kotlin that survives teams, scale, and time.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Layered Design | Presentation, domain, and data boundaries |
| 2 | Dependency Boundaries | Interfaces, module seams, and testability |
| 3 | Error Strategy | Exceptions vs result types vs domain-specific outcomes |
| 4 | Logging & Observability | Useful diagnostics in apps and services |
| 5 | Performance Awareness | Allocation costs, collection pipelines, blocking vs suspending work |
| 6 | Security Basics | Secret handling, auth boundaries, dependency trust |
| 7 | CI/CD | Linting, testing, builds, release automation |
| 8 | Maintainability | Refactoring, docs, code review quality, upgrade discipline |

> [!TIP]
> Production Kotlin should feel simple. If your codebase depends on language cleverness to be "powerful," it will eventually become expensive to maintain.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Document the architecture of a Kotlin project
- [ ] Add CI checks for formatting, linting, and tests
- [ ] Identify one maintainability improvement in an existing codebase

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `var` everywhere | Makes state harder to reason about | Prefer `val` and explicit mutation points |
| 2 | Reaching for `!!` | Reintroduces null crashes Kotlin is trying to prevent | Use safe calls, guards, or better modeling |
| 3 | Abusing scope functions | Readability drops fast when nesting `let`/`apply` everywhere | Use them only when they clarify intent |
| 4 | Writing Java in Kotlin syntax | Misses Kotlin's expressiveness and safety | Use data classes, sealed classes, extensions, and null safety idiomatically |
| 5 | Launching coroutines without ownership | Leads to leaks, orphaned work, and bad error handling | Use structured scopes tied to lifecycle |
| 6 | Huge Android activities or composables | UI and logic become tangled | Extract state holders, use feature boundaries |
| 7 | Overusing inheritance | Makes behavior rigid and harder to evolve | Prefer composition, interfaces, and sealed modeling |
| 8 | Ignoring Gradle and module hygiene | Build and dependency problems pile up | Keep modules small and builds understandable |
| 9 | No tests for business rules | Refactoring becomes risky | Add fast unit tests around core logic |
| 10 | Treating multiplatform as all-or-nothing | Forces poor abstractions | Share the logic that actually benefits from sharing |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between `val` and `var`?**
   - `val` is read-only after assignment. `var` can be reassigned. Kotlin encourages `val` by default.

2. **What problem does Kotlin null safety solve?**
   - It makes absence explicit in the type system, reducing runtime null pointer errors.

3. **What is a data class in Kotlin?**
   - A concise class intended for holding data, with generated `equals`, `hashCode`, `copy`, and `toString`.

4. **What is a higher-order function?**
   - A function that takes another function as a parameter or returns one. Kotlin uses them heavily in collections and DSLs.

5. **Why is Kotlin popular for Android?**
   - It is concise, safer than Java in many common cases, fully interoperable with Java, and officially supported by Google.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What are scope functions and when do you use them?**
   - They help structure code around an object or computation. Use them when they clarify context, not just to save typing.

2. **How do coroutines differ from threads?**
   - Coroutines are lightweight units of concurrency that can suspend without blocking a thread. Threads are heavier OS-managed execution units.

3. **What is a sealed class useful for?**
   - Modeling a closed set of states or outcomes, often for UI state, result types, and exhaustive `when` handling.

4. **How does Kotlin interoperate with Java?**
   - Kotlin can call Java code directly and vice versa on the JVM, but you must handle platform types and nullability carefully.

5. **Why would you choose an extension function?**
   - To add readable utility behavior to an existing type without subclassing or modifying the original source.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What is structured concurrency?**
   - A model where coroutines are launched inside a scope with a lifecycle, so cancellation, errors, and completion are owned and predictable.

2. **How would you design a scalable Kotlin codebase?**
   - Small modules, explicit boundaries, testable domain logic, conservative use of clever language features, and clear dependency direction.

3. **When should you use exceptions versus result types?**
   - Exceptions fit exceptional failures. Result or sealed outcomes often fit expected business failures or UI state transitions better.

4. **What are platform types in Kotlin?**
   - Types from Java interop whose nullability is unknown to the Kotlin compiler, so you must handle them deliberately to avoid unsafe assumptions.

5. **How do you keep coroutine-based code maintainable?**
   - Tie coroutines to ownership scopes, isolate side effects, use explicit dispatchers, test async behavior, and avoid fire-and-forget patterns.

</details>

---

## Practice Projects

### Project 1: Kotlin Console Toolkit
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A set of small CLI tools such as a task list, grade calculator, or file summary utility.

**Skills practiced:** Syntax, null safety, collections, lambdas, functions.

---

### Project 2: Inventory or Library Domain Model
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A small domain model using data classes, sealed classes, extensions, and tests.

**Skills practiced:** OOP, modeling, generics, functional transformations.

---

### Project 3: Coroutine-Powered Data App
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A program that loads data from multiple sources concurrently and exposes a clean API.

**Skills practiced:** Coroutines, Flow, testing, Gradle project structure.

---

### Project 4: Android or Ktor Application
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** Either an Android app with Compose or a backend API with Ktor and database access.

**Skills practiced:** Platform-specific Kotlin, architecture, persistence, networking.

---

### Project 5: Production Kotlin Platform
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A polished Kotlin app or service with CI, testing, docs, and maintainable module boundaries.

**Skills practiced:** Everything from all phases — your Kotlin graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Get Started with Kotlin](https://kotlinlang.org/docs/getting-started.html) | Official setup and first steps |
| [Kotlin Tour](https://kotlinlang.org/docs/kotlin-tour-welcome.html) | Browser-based guided fundamentals from JetBrains |
| [Kotlin Release History](https://kotlinlang.org/docs/releases.html) | Current language release information |
| [Coroutines Guide](https://kotlinlang.org/docs/coroutines-guide.html) | Official deep dive into coroutine design and usage |
| [Kotlin Multiplatform Overview](https://kotlinlang.org/docs/multiplatform/kmp-overview.html) | Official guide to shared-code architecture |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Kotlin Koans](https://kotlinlang.org/docs/koans.html) | Exercise-driven Kotlin practice |
| [Exercism — Kotlin Track](https://exercism.org/tracks/kotlin) | Many hands-on problems with mentor feedback |
| [Android Basics with Compose](https://developer.android.com/courses/android-basics-compose/course) | Official beginner Android path using Kotlin |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [JetBrains](https://www.youtube.com/@JetBrainsTV) | Official Kotlin ecosystem talks and updates |
| [Philipp Lackner](https://www.youtube.com/@PhilippLackner) | Strong Kotlin and Android architecture content |
| [freeCodeCamp](https://www.youtube.com/@freecodecamp) | Long-form free beginner-friendly courses |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [IntelliJ IDEA](https://www.jetbrains.com/idea/) | Best general-purpose Kotlin IDE |
| [Android Studio](https://developer.android.com/studio) | First-class Kotlin tooling for Android |
| [Detekt](https://detekt.dev/) | Static analysis for Kotlin codebases |
| [ktlint](https://pinterest.github.io/ktlint/latest/) | Formatting and linting conventions |
| [Gradle](https://gradle.org/) | Standard build tool for JVM and Android Kotlin projects |

### Further Reading

| Resource | Format |
|----------|--------|
| [Kotlin on Android](https://developer.android.com/kotlin) | Official Android-specific Kotlin guidance |
| [Ktor Documentation](https://ktor.io/docs/) | Official server-side Kotlin framework docs |

---

[Back to Main Syllabus](../README.md)

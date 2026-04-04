# Swift Syllabus

A complete, structured learning path for Swift — from your first `print()` to building safe, modern apps with SwiftUI, concurrency, networking, and Swift Package Manager.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Swift: 6.2+](https://img.shields.io/badge/Swift-6.2%2B-FA7343)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables, Control Flow & Optionals](#phase-2-variables-control-flow--optionals)
- [Phase 3: Functions, Collections & Closures](#phase-3-functions-collections--closures)
- [Phase 4: Structs, Classes, Enums & Protocols](#phase-4-structs-classes-enums--protocols)
- [Phase 5: Error Handling, Generics & Memory Management](#phase-5-error-handling-generics--memory-management)
- [Phase 6: Concurrency with async/await](#phase-6-concurrency-with-asyncawait)
- [Phase 7: Packages, Modules & Testing](#phase-7-packages-modules--testing)
- [Phase 8: SwiftUI & App Architecture](#phase-8-swiftui--app-architecture)
- [Phase 9: Networking, Persistence & Interop](#phase-9-networking-persistence--interop)
- [Phase 10: Performance, Tooling & Production Swift](#phase-10-performance-tooling--production-swift)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Swift is now a **general-purpose language** that runs on macOS, Linux, and Windows, but if your goal is iOS or macOS apps, you should expect to use **Xcode on macOS**.

- A computer with Swift installed
- A code editor ([Xcode](https://developer.apple.com/xcode/) or [VS Code](https://code.visualstudio.com/))
- Willingness to practice with small command-line tools before jumping into full app development
- Basic programming concepts help, but are not strictly required

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Learn what Swift is, install the toolchain, and run your first code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Swift | A modern, safe, high-performance language for apps, servers, CLI tools, and more |
| 2 | Installation | Install Swift, verify with `swift --version`, and understand platform-specific tooling |
| 3 | Xcode vs SwiftPM | Xcode for Apple app development, Swift Package Manager for packages and CLIs |
| 4 | REPL & Scripts | `swift` REPL, `swift file.swift`, and package-based workflows |
| 5 | Hello World | `print("Hello, world!")` and the shape of a basic Swift program |
| 6 | Playgrounds | Fast experimentation in Playgrounds and Xcode |
| 7 | Build & Run | `swift package init`, `swift run`, `swift build`, and the project layout |

> [!TIP]
> Start with command-line Swift first. It removes UI complexity and makes the language itself much easier to learn.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Swift and verify your toolchain
- [ ] Run a script and a Swift package from the terminal
- [ ] Explain the difference between a Playground, a script, and a package

</details>

---

## Phase 2: Variables, Control Flow & Optionals

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn Swift's core syntax and its strong emphasis on safety.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `let` vs `var` | Constants by default, mutation only when needed |
| 2 | Basic Types | `Int`, `Double`, `String`, `Bool`, tuples, arrays, dictionaries |
| 3 | Type Inference | When Swift infers types and when annotations help |
| 4 | String Interpolation | `\(name)` syntax and expressive string building |
| 5 | Conditionals | `if`, `guard`, `switch`, and pattern matching basics |
| 6 | Loops | `for-in`, `while`, ranges, and collection iteration |
| 7 | Optionals | `String?`, nil handling, unwrapping, and optional chaining |
| 8 | `guard let` and `if let` | Safe extraction of optional values |

> [!IMPORTANT]
> Optionals are a core Swift idea, not an edge case. If you fight them, Swift will feel frustrating. If you learn them early, Swift becomes much safer and clearer.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain `let` vs `var`
- [ ] Unwrap optionals with `if let` and `guard let`
- [ ] Write a small program using `switch`, ranges, and collections

</details>

---

## Phase 3: Functions, Collections & Closures

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build reusable logic and learn the functional side of Swift.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Functions | Parameters, argument labels, return types, default values |
| 2 | Tuples | Returning multiple values cleanly |
| 3 | Arrays, Sets, Dictionaries | Collection types and common operations |
| 4 | Higher-Order Functions | `map`, `filter`, `reduce`, `compactMap`, `sorted` |
| 5 | Closures | Closure syntax, trailing closures, shorthand arguments |
| 6 | Escaping Closures | When a closure outlives the function call |
| 7 | Value Semantics | Why arrays and structs behave predictably in Swift |
| 8 | Extensions | Adding behavior to existing types |

> [!TIP]
> Swift's collection methods and closures are used everywhere, especially in SwiftUI and asynchronous code. Get comfortable reading them now.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with argument labels and return values
- [ ] Transform collections with `map`, `filter`, and `compactMap`
- [ ] Explain what a closure is with a practical example

</details>

---

## Phase 4: Structs, Classes, Enums & Protocols

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn Swift's main modeling tools and when to choose each one.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Structs | Value types, memberwise initializers, immutability |
| 2 | Classes | Reference types, inheritance, identity, deinitializers |
| 3 | Enums | Powerful enums with associated values and exhaustive switching |
| 4 | Protocols | Contracts and protocol-oriented design |
| 5 | Properties | Stored, computed, lazy, property observers |
| 6 | Methods & Mutating Methods | Behavior on value and reference types |
| 7 | Initializers | Designated, convenience, failable initializers |
| 8 | Protocol Extensions | Shared default behavior and expressive APIs |

> [!IMPORTANT]
> In Swift, prefer `struct` by default unless you truly need shared mutable reference semantics.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain `struct` vs `class`
- [ ] Model data with enums and associated values
- [ ] Use protocols and protocol extensions in a small example

</details>

---

## Phase 5: Error Handling, Generics & Memory Management

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Move beyond syntax and start writing robust, reusable Swift.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Throwing Functions | `throws`, `try`, `do-catch`, and custom errors |
| 2 | Result Types | Representing success/failure explicitly |
| 3 | Generics | Reusable functions and generic data structures |
| 4 | Associated Types | Protocols that work across type families |
| 5 | ARC | Automatic Reference Counting and object lifetime |
| 6 | Strong Reference Cycles | `weak`, `unowned`, and closure capture lists |
| 7 | Access Control | `private`, `fileprivate`, `internal`, `public`, `open` |
| 8 | API Design | Clear naming and Swift-style interfaces |

> [!CAUTION]
> Memory bugs in Swift usually come from reference cycles, not manual allocation. Closures that capture `self` are a common place to look.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Throw and catch custom errors
- [ ] Write a generic function or type
- [ ] Detect and fix a retain cycle involving closures

</details>

---

## Phase 6: Concurrency with async/await

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn the modern Swift concurrency model instead of old callback-heavy patterns.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `async` / `await` | Writing asynchronous code that still reads top-to-bottom |
| 2 | `Task` | Launching work and managing task lifetimes |
| 3 | Structured Concurrency | Parent-child task relationships and cancellation |
| 4 | `async let` & Task Groups | Running concurrent work safely |
| 5 | Actors | Protecting mutable state from data races |
| 6 | Main Actor | UI-safe updates and thread correctness |
| 7 | Cancellation | Cooperative cancellation and cleanup |
| 8 | Bridging Old APIs | Moving from callbacks or Combine-style code into async/await |

> [!TIP]
> Prefer structured concurrency over detached background work. It gives you cancellation, ownership, and clearer reasoning.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data with `async` / `await`
- [ ] Explain when to use an actor
- [ ] Handle cancellation in a task cleanly

</details>

---

## Phase 7: Packages, Modules & Testing

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Organize Swift code into reusable modules and verify behavior with tests.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Swift Package Manager | Creating and managing packages with `swift package` |
| 2 | Targets & Modules | Splitting code into boundaries with clear APIs |
| 3 | Dependencies | Adding and updating packages responsibly |
| 4 | XCTest / Swift Testing | Unit tests, async tests, and test structure |
| 5 | Testability | Dependency injection and protocol-driven seams |
| 6 | DocC | Generating developer documentation for packages and frameworks |
| 7 | Linting & Formatting | SwiftFormat, SwiftLint, and consistent code style |
| 8 | Build Configurations | Debug vs release thinking and environment-specific setup |

> [!IMPORTANT]
> Swift Package Manager is part of the normal Swift workflow now, not an optional extra. Learn it early.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a package with a library and executable target
- [ ] Add tests for core logic
- [ ] Add a third-party dependency through SwiftPM

</details>

---

## Phase 8: SwiftUI & App Architecture

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Apply Swift to the UI layer and understand how modern app state flows.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | SwiftUI Basics | Views, modifiers, stacks, lists, navigation |
| 2 | State Management | `@State`, `@Binding`, observable models, unidirectional data flow |
| 3 | View Composition | Breaking UIs into small reusable view units |
| 4 | Forms & Inputs | Text fields, toggles, pickers, validation feedback |
| 5 | Navigation | Stacks, detail flows, and routing state |
| 6 | MVVM / Feature Architecture | Keeping logic out of views |
| 7 | Previews | Fast iteration with live previews |
| 8 | UIKit Interop | Bridging when SwiftUI alone is not enough |

> [!TIP]
> SwiftUI gets much easier when your data flow is simple. Keep state ownership obvious and avoid scattering business logic across views.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a multi-screen SwiftUI app
- [ ] Explain when to use `@State` vs `@Binding`
- [ ] Move non-UI logic out of views

</details>

---

## Phase 9: Networking, Persistence & Interop

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build real applications that talk to APIs, store data, and integrate with other systems.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | URLSession | Network requests, async fetching, and response handling |
| 2 | Codable | JSON encoding and decoding with strongly typed models |
| 3 | Error Surfaces | Network failure states, retries, and user-facing messages |
| 4 | Local Persistence | `UserDefaults`, file storage, SwiftData/Core Data concepts |
| 5 | Image & Data Loading | Async media handling and cache awareness |
| 6 | Interop | Calling C/C++ or platform APIs from Swift |
| 7 | Package-Based Reuse | Sharing networking and domain layers across targets |
| 8 | Offline & Resilience | Designing for sync, cache, and degraded states |

> [!WARNING]
> Do not decode JSON straight into UI code. Keep decoding, networking, and view logic separated or the app becomes difficult to test and evolve.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch and decode JSON from an API
- [ ] Persist app data locally
- [ ] Separate networking logic from the UI layer

</details>

---

## Phase 10: Performance, Tooling & Production Swift

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn what it takes to maintain high-quality Swift code at scale.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Instruments & Profiling | Measuring memory, time, and app responsiveness |
| 2 | Performance Basics | Value semantics, copy behavior, algorithmic costs |
| 3 | Logging & Diagnostics | Useful runtime visibility and crash context |
| 4 | Accessibility | Dynamic type, voice-over basics, semantic UI choices |
| 5 | CI/CD | Tests, package builds, linting, and app pipelines |
| 6 | Release Management | App configuration, signing awareness, environment setups |
| 7 | Dependency Hygiene | Package review, updates, and supply-chain awareness |
| 8 | Long-Term Maintainability | Refactoring, modularization, and documentation habits |

> [!TIP]
> Production Swift is mostly about discipline: clear boundaries, strong typing, concurrency correctness, useful tests, and measured performance.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Profile a performance issue with tools instead of guessing
- [ ] Add tests and linting to a Swift project
- [ ] Document the architecture and module boundaries of an app

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Force-unwrapping everywhere | Crashes the app when values are nil | Use `if let`, `guard let`, or better data modeling |
| 2 | Using classes by default | Unnecessary reference semantics cause complexity | Prefer `struct` unless identity/shared mutability is required |
| 3 | Ignoring retain cycles | Memory leaks often come from captured references | Use `weak` or `unowned` where appropriate |
| 4 | Mixing networking into views | UI becomes hard to test and maintain | Keep IO in services or models |
| 5 | Using old callback patterns only | Misses modern concurrency benefits | Prefer `async` / `await` for new code |
| 6 | Large SwiftUI views with business logic | Hard to reason about and reuse | Extract view models or feature logic |
| 7 | Ignoring error handling | Silent failures create poor user experience | Surface failure states explicitly |
| 8 | Premature optimization | Wastes time and often harms clarity | Measure with Instruments first |
| 9 | Weak understanding of optionals | Leads to noisy or unsafe code | Practice modeling absence intentionally |
| 10 | No tests around core logic | Refactoring becomes risky fast | Add unit tests for domain behavior |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between `let` and `var`?**
   - `let` creates an immutable binding. `var` creates a mutable one. Swift encourages `let` by default.

2. **What is an optional in Swift?**
   - An optional is a value that may either contain a value or be `nil`. It forces you to handle absence explicitly.

3. **What is the difference between a struct and a class?**
   - Structs are value types. Classes are reference types, support inheritance, and participate in ARC differently.

4. **What is a closure?**
   - A closure is a self-contained block of executable code that can be passed around and captured by other code.

5. **What does `Codable` do?**
   - It allows Swift types to encode and decode structured data like JSON in a strongly typed way.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Why does Swift prefer value types?**
   - Value types are easier to reason about, safer with concurrency, and reduce accidental shared mutable state.

2. **How does ARC work?**
   - Automatic Reference Counting tracks strong references to class instances and deallocates them when the count reaches zero.

3. **What problem do actors solve?**
   - Actors protect mutable state from concurrent access and reduce data races in async code.

4. **What is protocol-oriented programming?**
   - Designing systems around capabilities and contracts expressed as protocols, often with default behavior through protocol extensions.

5. **How do you test async Swift code?**
   - Use async test support, await asynchronous calls directly, and control dependencies so tests remain deterministic.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How would you avoid retain cycles in Swift?**
   - Identify strong reference loops, especially around closures and object graphs, then use `weak` or `unowned` captures where ownership permits.

2. **When should you use `async let` vs task groups?**
   - Use `async let` for a fixed small number of concurrent child tasks. Use task groups when the number of child tasks is dynamic or iterative.

3. **How do you structure a scalable SwiftUI application?**
   - Keep views small, isolate state ownership, move business logic out of the UI, and define module boundaries that mirror product features.

4. **What would you profile first in a slow Swift app?**
   - Measure the actual hotspot: rendering work, excessive allocations, expensive decoding, blocking work on the main actor, or algorithmic inefficiency.

5. **How do you make Swift code maintainable over time?**
   - Use strong types, clear names, small modules, tests around business logic, documented architecture, and conservative dependency choices.

</details>

---

## Practice Projects

### Project 1: Swift CLI Utilities
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A set of small command-line programs such as a calculator, habit tracker, or file summarizer.

**Skills practiced:** Syntax, optionals, functions, collections, SwiftPM basics.

---

### Project 2: Data Modeling App
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A small package that models users, tasks, or inventory with structs, protocols, generics, and tests.

**Skills practiced:** Value types, protocols, error handling, memory awareness.

---

### Project 3: Async Weather Client
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A networked command-line or small app that fetches weather or API data concurrently.

**Skills practiced:** `async` / `await`, `URLSession`, decoding, task cancellation, testing.

---

### Project 4: SwiftUI Task Manager
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A SwiftUI app with multiple screens, local persistence, and API-backed sync.

**Skills practiced:** SwiftUI, state management, persistence, networking.

---

### Project 5: Production-Ready App or Package
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A polished app or Swift package with tests, CI, documentation, accessibility, and performance tuning.

**Skills practiced:** Everything from all phases — your Swift graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Swift Documentation](https://www.swift.org/documentation/) | Official entry point to Swift language, libraries, and tooling |
| [The Swift Programming Language](https://www.swift.org/documentation/tspl/) | Authoritative Swift language guide and reference |
| [Getting Started with Swift](https://www.swift.org/getting-started/) | Official setup and first-project guidance |
| [Swift Install](https://www.swift.org/install/) | Current installation instructions for macOS, Linux, and Windows |
| [Apple Developer Swift](https://developer.apple.com/swift/) | Apple platform-specific Swift ecosystem resources |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Swift Playgrounds](https://www.apple.com/swift/playgrounds/) | Great guided entry point, especially for beginners |
| [Hacking with Swift](https://www.hackingwithswift.com/) | Massive project-based Swift and SwiftUI library |
| [Exercism — Swift Track](https://exercism.org/tracks/swift) | Practice problems with mentoring |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [Sean Allen](https://www.youtube.com/@seanallen) | Clear SwiftUI and iOS-focused explanations |
| [CodeWithChris](https://www.youtube.com/@CodeWithChris) | Friendly Swift beginner content |
| [freeCodeCamp](https://www.youtube.com/@freecodecamp) | Long-form free programming courses and walkthroughs |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Xcode](https://developer.apple.com/xcode/) | Primary IDE for Apple-platform Swift development |
| [Swift VS Code Extension](https://marketplace.visualstudio.com/items?itemName=swiftlang.swift-vscode) | Swift language support in VS Code |
| [Swift Package Manager](https://www.swift.org/documentation/package-manager/) | Built-in dependency and package management |
| [SwiftLint](https://github.com/realm/SwiftLint) | Style and convention enforcement |
| [SwiftFormat](https://github.com/nicklockwood/SwiftFormat) | Automatic formatting |

### Cheat Sheets & Further Reading

| Resource | Format |
|----------|--------|
| [Swift API Design Guidelines](https://www.swift.org/documentation/api-design-guidelines/) | Official guidance for writing idiomatic Swift APIs |
| [SwiftLee](https://www.avanderlee.com/swift/) | Strong articles on modern Swift and app architecture |

---

[Back to Main Syllabus](../README.md)

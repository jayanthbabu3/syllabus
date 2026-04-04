# Rust Syllabus

A complete, structured learning path for Rust — from your first program to building safe, concurrent, and blazingly fast systems with ownership, traits, and the Cargo ecosystem.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Rust: 2024 Edition](https://img.shields.io/badge/Rust-2024%20Edition-DEA584)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Types](#phase-2-variables--types)
- [Phase 3: Control Flow & Functions](#phase-3-control-flow--functions)
- [Phase 4: Ownership & Borrowing](#phase-4-ownership--borrowing)
- [Phase 5: Structs & Enums](#phase-5-structs--enums)
- [Phase 6: Error Handling](#phase-6-error-handling)
- [Phase 7: Collections & Iterators](#phase-7-collections--iterators)
- [Phase 8: Traits & Generics](#phase-8-traits--generics)
- [Phase 9: Concurrency](#phase-9-concurrency)
- [Phase 10: Cargo Ecosystem & Testing](#phase-10-cargo-ecosystem--testing)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Rust is a **systems programming language** focused on safety, speed, and concurrency. Prior experience with any programming language (C, C++, Python, JavaScript) helps, but Rust teaches you to think differently about memory.

- Basic programming concepts (variables, loops, functions, conditionals)
- Command line / terminal basics
- Understanding of what a compiler does (source code to binary)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Rust is, install the toolchain, and write your first program.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Rust | A systems language focused on safety, speed, and concurrency. No garbage collector — memory safety is enforced at compile time |
| 2 | Why Rust | Zero-cost abstractions, guaranteed memory safety, fearless concurrency. Used by Mozilla, AWS, Microsoft, Google, Cloudflare |
| 3 | Installation with `rustup` | `rustup` manages Rust versions and toolchains. Install from [rustup.rs](https://rustup.rs). `rustup update`, `rustup show` |
| 4 | Hello World | `fn main() { println!("Hello, world!"); }` — `fn` declares functions, `println!` is a macro (note the `!`), semicolons required |
| 5 | Cargo | Rust's build system and package manager. `cargo new`, `cargo build`, `cargo run`, `cargo check` — you'll use Cargo for everything |
| 6 | Project Structure | `Cargo.toml` (manifest), `src/main.rs` (binary entry), `src/lib.rs` (library entry), `target/` (build output) |
| 7 | Rust Playground | [play.rust-lang.org](https://play.rust-lang.org) — write, compile, and run Rust in the browser. Great for quick experiments |

> [!TIP]
> Use `cargo check` instead of `cargo build` during development — it checks your code for errors without producing a binary, so it's much faster:
> ```bash
> # Fast — just check for errors
> cargo check
>
> # Slower — compiles a debug binary
> cargo build
>
> # Build and run in one step
> cargo run
>
> # Optimized release build
> cargo build --release
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Rust with `rustup` and verify with `rustc --version`
- [ ] Create a new project with `cargo new hello_rust`
- [ ] Build and run it with `cargo run`

</details>

---

## Phase 2: Variables & Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Learn Rust's type system — immutability by default, strong static typing, and type inference.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `let` and `mut` | Variables are **immutable by default**. Use `let mut x = 5;` to make them mutable. Immutability prevents accidental changes |
| 2 | Primitive Types | Integers (`i32`, `u64`), floats (`f32`, `f64`), `bool`, `char` (4 bytes, Unicode). Explicit sizes — no ambiguity |
| 3 | Type Inference | Rust infers types: `let x = 5;` is `i32` by default. Annotate when needed: `let x: u64 = 5;` |
| 4 | Shadowing | Redeclare a variable with `let x = x + 1;` — creates a new variable. Unlike `mut`, shadowing can change the type |
| 5 | Constants | `const MAX_POINTS: u32 = 100_000;` — always typed, always immutable, evaluated at compile time. `_` for readability |
| 6 | Tuples | `let tup: (i32, f64, bool) = (500, 6.4, true);` — fixed-size, mixed types. Destructure: `let (x, y, z) = tup;` Access: `tup.0` |
| 7 | Arrays | `let arr: [i32; 5] = [1, 2, 3, 4, 5];` — fixed-size, same type, stack-allocated. Access: `arr[0]`. Bounds-checked at runtime |

> [!IMPORTANT]
> **Variables are immutable by default in Rust.** This is intentional — it prevents bugs and makes code easier to reason about:
> ```rust
> let x = 5;
> // x = 6;  // ERROR: cannot assign twice to immutable variable
>
> let mut y = 5;
> y = 6;  // OK — y is explicitly mutable
>
> // Shadowing — creates a NEW variable (can even change type)
> let x = "hello";  // x is now a &str, not i32
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare immutable and mutable variables
- [ ] Use shadowing to transform a variable's value and type
- [ ] Create tuples and arrays, and access their elements

</details>

---

## Phase 3: Control Flow & Functions

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Control program flow with conditionals, loops, pattern matching, and functions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if`/`else` | `if condition { } else if { } else { }` — no parentheses needed. `if` is an expression: `let x = if true { 5 } else { 6 };` |
| 2 | `loop` | Infinite loop — `loop { break; }`. Returns a value: `let result = loop { break 42; };`. `continue` skips iterations |
| 3 | `while` | `while condition { }` — standard conditional loop. No `do..while` in Rust |
| 4 | `for` | `for item in collection { }` — iterates over ranges (`0..10`), arrays, vectors. The most common loop in Rust |
| 5 | `match` | Rust's powerful pattern matching: `match value { 1 => "one", 2 => "two", _ => "other" }` — must be exhaustive |
| 6 | Pattern Matching | Destructure in `match`: tuples, enums, ranges (`1..=5`), guards (`x if x > 0`), `if let` for single patterns |
| 7 | Functions | `fn add(a: i32, b: i32) -> i32 { a + b }` — parameter types required, return type after `->`, last expression is returned |
| 8 | Expressions vs Statements | Expressions return values (`5 + 3`, blocks `{}`). Statements don't (`let x = 5;`). No semicolon = return value |

> [!TIP]
> In Rust, almost everything is an expression. The last expression in a block (without a semicolon) is its return value:
> ```rust
> fn classify(n: i32) -> &'static str {
>     // match is an expression — its result is returned
>     match n {
>         n if n < 0 => "negative",
>         0 => "zero",
>         _ => "positive",
>     }
> }
>
> // if is also an expression
> let label = if x > 10 { "big" } else { "small" };
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a function that uses `match` with multiple patterns
- [ ] Use `for` to iterate over a range and an array
- [ ] Understand why `if` and `match` are expressions, not statements

</details>

---

## Phase 4: Ownership & Borrowing

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> The core concept that makes Rust unique — memory safety without a garbage collector.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Ownership Rules | Each value has one owner. When the owner goes out of scope, the value is dropped. Only one owner at a time |
| 2 | Move Semantics | Assigning a `String` to another variable **moves** it — the original is invalidated. `let s2 = s1;` means `s1` is gone |
| 3 | `Clone` and `Copy` | `s1.clone()` creates a deep copy. Primitives (`i32`, `bool`, `f64`) implement `Copy` — they're copied, not moved |
| 4 | Borrowing with `&` | `&x` creates an immutable reference — you can read but not modify. Multiple immutable references allowed simultaneously |
| 5 | Mutable Borrowing `&mut` | `&mut x` creates a mutable reference — you can modify the value. Only **one** mutable reference at a time (prevents data races) |
| 6 | The Borrow Checker | The compiler enforces borrowing rules at compile time. No dangling references, no data races, no use-after-free — ever |
| 7 | Lifetimes Intro | `'a` annotations tell the compiler how long references are valid. `fn longest<'a>(x: &'a str, y: &'a str) -> &'a str` |

> [!CAUTION]
> **The borrow checker is your friend, not your enemy.** It catches entire classes of bugs at compile time that would be runtime crashes in C/C++:
> ```rust
> let mut s = String::from("hello");
>
> let r1 = &s;     // OK — immutable borrow
> let r2 = &s;     // OK — multiple immutable borrows allowed
> // let r3 = &mut s; // ERROR — can't borrow mutably while borrowed immutably
>
> println!("{r1}, {r2}"); // r1 and r2 are used here
>
> let r3 = &mut s;  // OK — r1 and r2 are no longer used after this point
> r3.push_str(", world");
> ```
> Fighting the borrow checker is normal at first. It gets easier — and the bugs it prevents are worth it.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain why `let s2 = s1;` invalidates `s1` for a `String`
- [ ] Write a function that borrows a value immutably and mutably
- [ ] Fix a borrow checker error by restructuring your code

</details>

---

## Phase 5: Structs & Enums

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Define custom types with structs and enums — the building blocks of Rust programs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Struct Definition | `struct User { name: String, age: u32 }` — group related data. Field init shorthand: `User { name, age }` |
| 2 | `impl` Blocks | `impl User { fn new(name: String) -> Self { ... } }` — associate functions and methods with a struct |
| 3 | Methods | `fn full_name(&self) -> String` — takes `&self` (immutable) or `&mut self` (mutable). Called with `user.full_name()` |
| 4 | Enum Variants | `enum Direction { Up, Down, Left, Right }` — a type that can be one of several variants. `match` to handle each |
| 5 | Enums with Data | `enum Message { Quit, Echo(String), Move { x: i32, y: i32 } }` — variants can hold different types of data |
| 6 | `Option<T>` | `Option<T>` is `Some(T)` or `None` — Rust has no null. Forces you to handle the absence of a value explicitly |
| 7 | `Result<T, E>` | `Result<T, E>` is `Ok(T)` or `Err(E)` — Rust's error handling. Functions that can fail return `Result` |

> [!IMPORTANT]
> **Rust has no null.** Instead, `Option<T>` makes the absence of a value explicit and forces you to handle it:
> ```rust
> fn find_user(id: u32) -> Option<User> {
>     if id == 1 {
>         Some(User { name: String::from("Alice"), age: 30 })
>     } else {
>         None
>     }
> }
>
> // You MUST handle both cases — the compiler enforces it
> match find_user(1) {
>     Some(user) => println!("Found: {}", user.name),
>     None => println!("User not found"),
> }
>
> // Or use if let for a single pattern
> if let Some(user) = find_user(1) {
>     println!("Found: {}", user.name);
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Define a struct with an `impl` block containing methods
- [ ] Create an enum with data-carrying variants and match on it
- [ ] Use `Option<T>` and `Result<T, E>` in function return types

</details>

---

## Phase 6: Error Handling

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Handle errors gracefully — Rust makes error handling explicit, not exceptional.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `Result` and `Option` | `Result<T, E>` for recoverable errors, `Option<T>` for optional values. No exceptions — errors are values |
| 2 | `unwrap` and `expect` | `result.unwrap()` panics on `Err`, `result.expect("message")` panics with a message. Use only in prototyping |
| 3 | The `?` Operator | `let file = File::open("data.txt")?;` — returns early with the error if `Err`. Clean, concise error propagation |
| 4 | Custom Error Types | `enum AppError { NotFound, InvalidInput(String) }` — implement `std::fmt::Display` and `std::error::Error` |
| 5 | `thiserror` Crate | `#[derive(thiserror::Error)]` — auto-generate `Display` and `Error` impls. Best for libraries |
| 6 | `anyhow` Crate | `anyhow::Result<T>` — wraps any error type. `context("failed to read config")?` adds context. Best for applications |
| 7 | `panic!` vs `Result` | `panic!` is for unrecoverable bugs (index out of bounds). `Result` is for expected failures (file not found, network error) |

> [!TIP]
> Use the `?` operator to propagate errors cleanly. It replaces verbose `match` blocks:
> ```rust
> use std::fs;
> use anyhow::{Context, Result};
>
> // WITHOUT ? — verbose
> fn read_config_verbose() -> Result<String> {
>     match fs::read_to_string("config.toml") {
>         Ok(content) => Ok(content),
>         Err(e) => Err(e.into()),
>     }
> }
>
> // WITH ? — clean and idiomatic
> fn read_config() -> Result<String> {
>     let content = fs::read_to_string("config.toml")
>         .context("failed to read config.toml")?;
>     Ok(content)
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use the `?` operator to propagate errors through multiple functions
- [ ] Create a custom error type with `thiserror`
- [ ] Use `anyhow` for application-level error handling with context

</details>

---

## Phase 7: Collections & Iterators

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Work with dynamic data using Rust's powerful collections and iterator chains.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `Vec<T>` | `let mut v: Vec<i32> = vec![1, 2, 3];` — growable array on the heap. `push`, `pop`, `len`, indexing, slicing |
| 2 | `HashMap<K, V>` | `HashMap::new()` — key-value store. `insert`, `get`, `entry().or_insert()`, iterate with `for (k, v) in &map` |
| 3 | `HashSet<T>` | `HashSet::new()` — unique values. `insert`, `contains`, set operations: `union`, `intersection`, `difference` |
| 4 | `String` | `String` (owned, heap) vs `&str` (borrowed, slice). `String::from("hello")`, `push_str`, `format!`, UTF-8 encoded |
| 5 | Iterators | `.iter()`, `.into_iter()`, `.iter_mut()` — lazy sequences. Nothing happens until consumed (`collect`, `for_each`, `sum`) |
| 6 | `map`/`filter`/`collect` | `v.iter().filter(\|&&x\| x > 2).map(\|&x\| x * 2).collect::<Vec<_>>()` — functional-style data transformation |
| 7 | Closures | `\|x\| x + 1` — anonymous functions that capture their environment. Used with iterators, `map`, `filter`, `sort_by` |

> [!IMPORTANT]
> **Iterators in Rust are zero-cost abstractions.** They compile down to the same code as hand-written loops — no performance penalty:
> ```rust
> // Functional style — same performance as a manual loop
> let sum: i32 = (1..=100)
>     .filter(|x| x % 2 == 0)    // keep even numbers
>     .map(|x| x * x)            // square them
>     .sum();                     // add them up
>
> // String vs &str
> let owned: String = String::from("hello");  // heap-allocated, growable
> let borrowed: &str = &owned;                // just a view into the String
> let literal: &str = "hello";                // points to binary data
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `Vec`, `HashMap`, and `HashSet` with common operations
- [ ] Chain iterators with `map`, `filter`, and `collect`
- [ ] Understand the difference between `String` and `&str`

</details>

---

## Phase 8: Traits & Generics

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable, polymorphic code with traits (like interfaces) and generics.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Trait Definition | `trait Summary { fn summarize(&self) -> String; }` — define shared behavior. Like interfaces in other languages |
| 2 | `impl Trait` | `impl Summary for Article { fn summarize(&self) -> String { ... } }` — implement a trait for a specific type |
| 3 | Default Methods | `trait Summary { fn summarize(&self) -> String { String::from("Read more...") } }` — provide default implementations |
| 4 | Generic Functions | `fn largest<T: PartialOrd>(list: &[T]) -> &T` — write one function that works with many types |
| 5 | Generic Structs | `struct Point<T> { x: T, y: T }` — a struct that works with any type. `Point<f64>`, `Point<i32>` |
| 6 | Trait Bounds | `fn notify(item: &impl Summary)` or `fn notify<T: Summary + Display>(item: &T)` — constrain generics to types with specific behavior |
| 7 | `derive` Macros | `#[derive(Debug, Clone, PartialEq)]` — auto-generate trait implementations. `Debug` for printing, `Clone` for copying |
| 8 | `where` Clauses | `fn process<T>(item: T) where T: Summary + Clone` — cleaner syntax for complex trait bounds |

> [!TIP]
> Traits are Rust's way of achieving polymorphism. Combined with generics, they let you write flexible, reusable code:
> ```rust
> use std::fmt::Display;
>
> trait Area {
>     fn area(&self) -> f64;
> }
>
> struct Circle { radius: f64 }
> struct Rectangle { width: f64, height: f64 }
>
> impl Area for Circle {
>     fn area(&self) -> f64 { std::f64::consts::PI * self.radius * self.radius }
> }
>
> impl Area for Rectangle {
>     fn area(&self) -> f64 { self.width * self.height }
> }
>
> // Works with ANY type that implements Area + Display
> fn print_area(shape: &(impl Area + Display)) {
>     println!("{} has area {:.2}", shape, shape.area());
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Define a trait and implement it for multiple types
- [ ] Write a generic function with trait bounds
- [ ] Use `derive` macros for `Debug`, `Clone`, and `PartialEq`

</details>

---

## Phase 9: Concurrency

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write fearless concurrent code — the compiler prevents data races at compile time.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Threads | `std::thread::spawn(\|\| { })` — OS threads. `handle.join().unwrap()` to wait. Move data with `move \|\|` closures |
| 2 | `Arc<T>` | Atomic Reference Counted — safely share immutable data across threads. `Arc::clone(&data)` is cheap (increments counter) |
| 3 | `Mutex<T>` | Mutual exclusion — `mutex.lock().unwrap()` gives exclusive mutable access. Combined with `Arc` for shared mutable state |
| 4 | `Arc<Mutex<T>>` | The standard pattern for shared mutable state across threads. `let shared = Arc::new(Mutex::new(vec![]))` |
| 5 | Channels | `mpsc::channel()` — multiple producer, single consumer. `tx.send(value)`, `rx.recv()`. Message passing over shared state |
| 6 | `Send` and `Sync` | Marker traits. `Send`: safe to transfer between threads. `Sync`: safe to reference from multiple threads. Most types are both |
| 7 | `async`/`await` with Tokio | `async fn fetch() -> Result<String>` + `#[tokio::main]`. Lightweight tasks, not OS threads. Best for I/O-bound work |

> [!CAUTION]
> **Rust's type system prevents data races at compile time.** But you still need to think about deadlocks and design:
> ```rust
> use std::sync::{Arc, Mutex};
> use std::thread;
>
> let counter = Arc::new(Mutex::new(0));
> let mut handles = vec![];
>
> for _ in 0..10 {
>     let counter = Arc::clone(&counter);
>     let handle = thread::spawn(move || {
>         let mut num = counter.lock().unwrap();
>         *num += 1;
>         // Lock is automatically released when `num` goes out of scope
>     });
>     handles.push(handle);
> }
>
> for handle in handles {
>     handle.join().unwrap();
> }
>
> println!("Result: {}", *counter.lock().unwrap()); // 10
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Spawn threads and share data with `Arc<Mutex<T>>`
- [ ] Use channels for message passing between threads
- [ ] Write an async function with Tokio and `await` multiple futures

</details>

---

## Phase 10: Cargo Ecosystem & Testing

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Test your code, lint it, format it, and publish it — the full Cargo workflow.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `#[test]` | `#[test] fn it_works() { assert_eq!(2 + 2, 4); }` — unit tests live right next to the code they test |
| 2 | `cargo test` | Run all tests: `cargo test`. Filter: `cargo test test_name`. Show output: `cargo test -- --nocapture` |
| 3 | Test Organization | Unit tests in `#[cfg(test)] mod tests {}` within each file. Keep tests close to the code |
| 4 | Integration Tests | Files in `tests/` directory — test your crate as an external user would. Each file is a separate test crate |
| 5 | Documentation | `///` doc comments with examples. `cargo doc --open` generates HTML docs. Doc examples are tested with `cargo test` |
| 6 | [crates.io](https://crates.io) | Rust's package registry. Add dependencies in `Cargo.toml`: `[dependencies] serde = "1.0"`. `cargo add serde` |
| 7 | Clippy | `cargo clippy` — Rust's official linter. Catches common mistakes, suggests idiomatic improvements. Fix all warnings |
| 8 | Rustfmt | `cargo fmt` — auto-format your code to the standard Rust style. Configure with `rustfmt.toml`. Run before every commit |

> [!TIP]
> Rust's doc comments are unique — the code examples inside them are **actually run as tests**:
> ```rust
> /// Adds two numbers together.
> ///
> /// # Examples
> ///
> /// ```
> /// let result = my_crate::add(2, 3);
> /// assert_eq!(result, 5);
> /// ```
> pub fn add(a: i32, b: i32) -> i32 {
>     a + b
> }
> ```
> Run `cargo test` and the example above is compiled and executed. If it fails, your docs are wrong.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write unit tests with `#[test]` and integration tests in `tests/`
- [ ] Run `cargo clippy` and fix all warnings in your project
- [ ] Generate documentation with `cargo doc` and add doc-test examples

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `unwrap()` everywhere | Panics on `None`/`Err` — crashes your program in production | Use `?` for propagation, `match`/`if let` for handling |
| 2 | Fighting the borrow checker | Trying to hold multiple mutable references or references to moved values | Restructure code — clone if needed, use scoping to limit borrow lifetimes |
| 3 | Cloning everything | `clone()` bypasses ownership but wastes memory and CPU | Use references (`&T`) when possible, clone only when necessary |
| 4 | Ignoring `clippy` warnings | Clippy catches real bugs and unidiomatic code | Run `cargo clippy` regularly and fix all warnings |
| 5 | Using `String` when `&str` suffices | `String` allocates on the heap — unnecessary if you only need to read | Accept `&str` in function parameters, return `String` when creating new strings |
| 6 | Not using `cargo fmt` | Inconsistent formatting makes code harder to read and review | Run `cargo fmt` before every commit — or set up format-on-save |
| 7 | Indexing instead of iterating | `v[i]` panics on out-of-bounds. Manual indexing is error-prone | Use iterators: `for item in &v`, `.iter().enumerate()` for index + value |
| 8 | Ignoring the `Result` return type | `let _ = file.write(data);` silently drops errors | Always handle `Result` — use `?`, `match`, or at minimum `expect("reason")` |
| 9 | Mutable global state | `static mut` is `unsafe` and causes data races | Use `std::sync::OnceLock`, `Arc<Mutex<T>>`, or pass state explicitly |
| 10 | Not reading compiler errors | Rust's error messages are excellent — they often tell you exactly how to fix the issue | Read the full error, follow the suggestions, check the error code with `rustc --explain E0xxx` |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is ownership in Rust and why does it matter?**
   - Every value has exactly one owner. When the owner goes out of scope, the value is dropped (freed). This eliminates use-after-free, double-free, and memory leaks without a garbage collector. Ownership is enforced at compile time with zero runtime cost.

2. **What is the difference between `String` and `&str`?**
   - `String` is an owned, heap-allocated, growable string. `&str` is a borrowed reference to a string slice (could point to a `String`, a string literal, or a substring). Functions should accept `&str` for flexibility and return `String` when creating new data.

3. **What is `Option<T>` and why doesn't Rust have null?**
   - `Option<T>` is an enum: `Some(T)` (value present) or `None` (absent). Rust has no null to eliminate null pointer exceptions. The compiler forces you to handle `None` — you can't accidentally use a value that might not exist.

4. **What does the `?` operator do?**
   - Applied to a `Result` or `Option`, it returns early with the error/none if the value is `Err`/`None`, otherwise unwraps the `Ok`/`Some` value. It's syntactic sugar for match-and-return-early. The function must return a compatible `Result`/`Option` type.

5. **What are `Vec`, `HashMap`, and `HashSet`?**
   - `Vec<T>`: growable array (like `ArrayList`). `HashMap<K, V>`: key-value store (like `Map`/`dict`). `HashSet<T>`: unique value collection (like `Set`). All heap-allocated, all generic over their element types.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain borrowing rules and why they exist.**
   - You can have either one mutable reference (`&mut T`) OR any number of immutable references (`&T`) — never both simultaneously. This prevents data races at compile time. References must not outlive the data they point to (no dangling references).

2. **What are traits and how do they compare to interfaces?**
   - Traits define shared behavior: a set of method signatures (and optionally default implementations). Types implement traits with `impl Trait for Type`. Unlike interfaces, traits support default methods, associated types, and can be implemented for external types (orphan rules apply).

3. **What is the difference between `clone()` and `Copy`?**
   - `Copy` is a marker trait for types that can be duplicated by copying bits (stack-only, cheap: integers, bools, chars). `Clone` is explicit deep duplication (may be expensive: heap allocation). All `Copy` types are `Clone`, but not vice versa. `String` is `Clone` but not `Copy`.

4. **How do generics and trait bounds work?**
   - Generics let you write code parameterized over types: `fn max<T: PartialOrd>(a: T, b: T) -> T`. Trait bounds constrain which types are accepted — `T: PartialOrd` means "T must be comparable." Monomorphized at compile time — no runtime overhead.

5. **What is the difference between `iter()`, `into_iter()`, and `iter_mut()`?**
   - `iter()` borrows elements (`&T`). `into_iter()` takes ownership (consumes the collection). `iter_mut()` borrows mutably (`&mut T`). `for x in &v` desugars to `iter()`, `for x in v` desugars to `into_iter()`, `for x in &mut v` desugars to `iter_mut()`.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain lifetimes and when you need explicit annotations.**
   - Lifetimes (`'a`) tell the compiler how long references are valid. Usually inferred (elision rules), but required when a function returns a reference and the compiler can't determine which input it came from. `fn longest<'a>(x: &'a str, y: &'a str) -> &'a str` means the returned reference lives as long as the shorter of the two inputs.

2. **How does Rust achieve fearless concurrency?**
   - The type system enforces thread safety: `Send` (safe to transfer ownership between threads) and `Sync` (safe to share references between threads) are auto-implemented. The borrow checker prevents data races (shared mutable state). `Arc<Mutex<T>>` provides safe shared mutability. Channels enable message passing.

3. **What is zero-cost abstraction and how does Rust achieve it?**
   - Abstractions (iterators, traits, generics) compile down to the same machine code as hand-written low-level code. Generics are monomorphized (a specialized version is generated for each concrete type). Traits use static dispatch by default (inlined). Dynamic dispatch (`dyn Trait`) is opt-in when you need it.

4. **When would you use `Box<dyn Trait>` vs `impl Trait` vs generics?**
   - `impl Trait` / generics: static dispatch, monomorphized, fastest, used when the concrete type is known at compile time. `Box<dyn Trait>`: dynamic dispatch via vtable, used for heterogeneous collections (e.g., `Vec<Box<dyn Animal>>`), trait objects, or when you need runtime polymorphism. `dyn` has a small indirection cost.

5. **Explain `async`/`await` in Rust and how it differs from other languages.**
   - Rust's `async fn` returns a `Future` that does nothing until `.await`ed (lazy). No built-in runtime — you choose one (Tokio, async-std). Futures are state machines compiled to zero-allocation code. Unlike JavaScript/Python, Rust futures don't allocate a task until explicitly spawned. Pinning is required for self-referential futures.

</details>

---

## Practice Projects

### Project 1: CLI Calculator
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A command-line calculator that reads expressions from stdin, parses operators and operands, and prints results. Handle invalid input gracefully.

**Skills practiced:** Variables, types, control flow, pattern matching, functions, `match` expressions.

---

### Project 2: Ownership Puzzle Solver
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A task manager (todo list) using structs and enums. Add, complete, delete, and list tasks. Store data in a `Vec` with proper ownership and borrowing.

**Skills practiced:** Ownership, borrowing, structs, enums, `Option`, `impl` blocks, methods.

---

### Project 3: File Search Tool (mini-grep)
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A command-line tool that searches for a string in files (like a simple `grep`). Read files, handle errors with `Result`, use iterators to filter matching lines.

**Skills practiced:** Error handling with `?`, `Result`, file I/O, iterators, `map`/`filter`/`collect`, closures.

---

### Project 4: Generic Data Store
![Phase 8](https://img.shields.io/badge/After-Phase%208-orange)

**What you'll build:** A generic in-memory key-value store with traits for serialization, querying, and display. Support multiple data types with trait bounds.

**Skills practiced:** Traits, generics, trait bounds, `derive` macros, `where` clauses, trait objects.

---

### Project 5: Concurrent Web Scraper
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** An async web scraper that fetches multiple URLs concurrently with Tokio, parses content, and saves results. Includes full test coverage, Clippy compliance, and documentation.

**Skills practiced:** Everything from all phases — async/await, concurrency, error handling, testing, Clippy, documentation.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [The Rust Programming Language (The Book)](https://doc.rust-lang.org/book/) | The official Rust book — comprehensive, well-written, the definitive learning resource |
| [Rust by Example](https://doc.rust-lang.org/rust-by-example/) | Learn Rust through annotated, runnable code examples |
| [Rust Standard Library Docs](https://doc.rust-lang.org/std/) | API documentation for every type, trait, and function in `std` |
| [The Rustonomicon](https://doc.rust-lang.org/nomicon/) | Advanced — unsafe Rust, memory layout, FFI. Read after mastering the basics |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Rustlings](https://github.com/rust-lang/rustlings) | Small exercises that guide you through reading and writing Rust code. Fix compiler errors to progress |
| [Exercism — Rust Track](https://exercism.org/tracks/rust) | Mentored coding exercises with community feedback |
| [Tour of Rust](https://tourofrust.com/) | Step-by-step interactive tour in the browser |
| [Comprehensive Rust (Google)](https://google.github.io/comprehensive-rust/) | Google's 4-day Rust course — used internally to train Android developers |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Let's Get Rusty](https://www.youtube.com/@letsgetrusty) | Follows The Book chapter-by-chapter with clear visuals |
| [Jon Gjengset](https://www.youtube.com/@jonhoo) | Deep dives into advanced Rust — Crust of Rust series is legendary |
| [No Boilerplate](https://www.youtube.com/@NoBoilerplate) | Short, fast, opinionated Rust videos that explain the "why" |
| [Fireship — Rust in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview to get excited about Rust |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Rust](https://roadmap.sh/rust) | Interactive learning path with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer) | VS Code extension — code completion, inline errors, go-to-definition, refactoring |
| [Clippy](https://github.com/rust-lang/rust-clippy) | Official linter — catches hundreds of common mistakes and anti-patterns |
| [Rustfmt](https://github.com/rust-lang/rustfmt) | Official code formatter — consistent style across the Rust ecosystem |
| [cargo-watch](https://crates.io/crates/cargo-watch) | Auto-run `cargo check`/`cargo test` on file save |
| [cargo-expand](https://crates.io/crates/cargo-expand) | See what macros expand to — essential for debugging `derive` and `macro_rules!` |

### Key Crates

| Crate | What It Does |
|-------|-------------|
| [serde](https://serde.rs/) | Serialization/deserialization (JSON, TOML, YAML, etc.) |
| [tokio](https://tokio.rs/) | Async runtime — the foundation for async Rust |
| [reqwest](https://crates.io/crates/reqwest) | HTTP client (async, built on Tokio) |
| [clap](https://crates.io/crates/clap) | Command-line argument parsing with derive macros |
| [anyhow](https://crates.io/crates/anyhow) | Flexible error handling for applications |
| [thiserror](https://crates.io/crates/thiserror) | Derive macro for custom error types in libraries |
| [tracing](https://crates.io/crates/tracing) | Structured, async-aware logging and diagnostics |
| [rayon](https://crates.io/crates/rayon) | Data parallelism — turn `.iter()` into `.par_iter()` for free multi-threading |
| [axum](https://crates.io/crates/axum) | Web framework built on Tokio — ergonomic, fast, production-ready |
| [sqlx](https://crates.io/crates/sqlx) | Compile-time checked SQL queries — async, pure Rust |

---

[Back to Main Syllabus](../README.md)

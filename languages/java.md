# Java Syllabus

A complete, structured learning path for Java — your one-stop guide from your first `System.out.println` to building production microservices, Android apps, big-data pipelines, and AI-powered services. Whether you have never written code or you've been writing Java for years and want to fill the gaps, this syllabus walks you through every concept in the right order, explains *why* each matters, lists the **entire framework ecosystem** you'll meet on the job, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 16-22 Weeks](https://img.shields.io/badge/Duration-16--22%20Weeks-blue)
![Topics: 15 Phases](https://img.shields.io/badge/Topics-15%20Phases-orange)
![Java: 21 LTS](https://img.shields.io/badge/Java-21%20LTS-ED8B00)

---

## Table of Contents

- [What is Java?](#what-is-java)
- [Why Learn Java in 2026?](#why-learn-java-in-2026)
- [How Java Runs](#how-java-runs)
- [Who This Syllabus Is For](#who-this-syllabus-is-for)
- [Learning Paths](#learning-paths)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Data Types & Variables](#phase-2-data-types--variables)
- [Phase 3: Operators & Control Flow](#phase-3-operators--control-flow)
- [Phase 4: Object-Oriented Programming](#phase-4-object-oriented-programming)
- [Phase 5: Strings & Regular Expressions](#phase-5-strings--regular-expressions)
- [Phase 6: Collections Framework](#phase-6-collections-framework)
- [Phase 7: Generics](#phase-7-generics)
- [Phase 8: Functional Programming & Streams](#phase-8-functional-programming--streams)
- [Phase 9: Exception Handling & I/O](#phase-9-exception-handling--io)
- [Phase 10: Concurrency, Multithreading & Virtual Threads](#phase-10-concurrency-multithreading--virtual-threads)
- [Phase 11: Build Tools, Testing & Modern Project Setup](#phase-11-build-tools-testing--modern-project-setup)
- [Phase 12: Spring Boot & Web APIs](#phase-12-spring-boot--web-apis)
- [Phase 13: The Java Frameworks Ecosystem](#phase-13-the-java-frameworks-ecosystem)
- [Phase 14: Databases, Persistence & Messaging](#phase-14-databases-persistence--messaging)
- [Phase 15: What's Next? (Specializations & Deploy)](#phase-15-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is Java?

**Java is a statically-typed, object-oriented programming language designed to run anywhere there is a Java Virtual Machine (JVM).** It runs the world's largest banks, Amazon, Netflix, Uber, LinkedIn, Twitter (X), Airbnb, every major Indian and Chinese tech company, half the Android apps on Earth, and an enormous chunk of every Fortune 500 backend.

Created by **James Gosling at Sun Microsystems in 1995** and famously based on the slogan **"Write Once, Run Anywhere"** (WORA), Java introduced the radical idea of compiling to **bytecode** — a portable intermediate format that any JVM can execute, on any operating system, any CPU. Sun was acquired by **Oracle in 2010**, and Java is now developed via the [OpenJDK](https://openjdk.org/) project (open source) plus a community process called the **JCP**.

In simple words:

- Java is **strict**: every variable has a type, every method declares what it returns, the compiler catches mistakes before you run.
- Java is **portable**: same `.class` files run on Windows, Mac, Linux, AWS, your phone (Android), without recompilation.
- Java is **object-oriented to the core**: even your `Hello World` lives inside a class.
- Java is **boring** in the best way — it stays running for decades, banks trust it with money, every framework is mature.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 1995 | Java 1.0 | First public release. WORA promise. Applets in the browser. |
| 1998 | Java 2 (1.2) | Swing UI, Collections Framework, JIT compiler — the version that made Java mainstream. |
| 2004 | Java 5 | Generics, annotations, enums, autoboxing, enhanced for-loop. The biggest single language upgrade. |
| 2014 | Java 8 LTS | **Lambdas, Streams, `Optional`, `java.time`** — Java's second great leap. Still everywhere. |
| 2017 | Java 9 | Modules (Project Jigsaw). Move to 6-month release cycle. |
| 2017 | Java 11 LTS | First LTS after 8. The "modern baseline" for many teams. |
| 2021 | Java 17 LTS | Sealed classes, records, pattern matching, text blocks. |
| 2023 | **Java 21 LTS** | **Virtual threads (Project Loom!)**, structured concurrency, pattern matching for `switch`. The 2026 default. |
| 2025 | Java 25 LTS | Stable virtual threads, scoped values, more pattern matching. |

> [!IMPORTANT]
> **Always pick an LTS (Long-Term Support) release for production.** In 2026 that means **Java 21 LTS** (or the newer **Java 25 LTS** if your team is current). Anyone teaching you Java 8 is teaching you 2014 — fine for legacy maintenance, *not* fine for new projects.

### What Makes Java Special

- **The JVM is a marvel of engineering.** Decades of tuning. JIT-compiled hot code reaches near-C speed.
- **Static types, refactoring superpowers.** Renaming a method across 1,000 files is instant in IntelliJ — try that in Python.
- **The biggest enterprise ecosystem in existence.** Spring, Hibernate, Kafka, Hadoop, Spark, Elasticsearch — most named "things" in your job description are Java libraries.
- **Backwards compatibility is religion.** Code from 2005 still compiles. Banks rely on this.
- **Polyglot JVM.** Same JVM runs Kotlin, Scala, Groovy, Clojure — all interoperable with Java.

---

## Why Learn Java in 2026?

| Reason | What It Means |
|--------|---------------|
| **#1 enterprise backend language** | Banks, telecoms, retail, governments, airlines run on Java. Highest job density of any language in India + many EU markets. |
| **Spring Boot dominates JVM backends** | If a JVM company is hiring, it's almost certainly hiring for Spring Boot. |
| **Android (officially)** | Android SDK is Java-first (and Kotlin, which is Java-compatible). Billions of phones run Java code. |
| **Big Data is Java-native** | Hadoop, Spark, Flink, Kafka, Elasticsearch — all written in Java/Scala. Run on the JVM. |
| **Highest-paid mid/senior backend roles** | Senior Java/Spring engineers consistently top backend pay charts. |
| **Stability** | Java 8 code from 2014 still compiles in Java 25. Languages that prize this attract long careers. |
| **JVM languages bonus** | Learn Java once → also unlock Kotlin (Android-preferred), Scala (Spark, finance), Groovy (Gradle). |
| **Massive job market** | More open Java job postings than any language except JavaScript and Python. |
| **Pays well** | Average senior Java/Spring salary in 2026: **$120k–$210k** (US), **₹15L–₹60L** (India). |

---

## How Java Runs

Understanding what happens between `javac` and `java` makes the rest of the syllabus easier.

```
   ┌─────────────────────────┐
   │   You write Java        │  Main.java — human-readable
   └────────────┬────────────┘
                │ javac Main.java
                ▼
   ┌─────────────────────────┐
   │   Bytecode (.class)     │  Platform-independent instructions
   └────────────┬────────────┘
                │ java Main
                ▼
   ┌─────────────────────────┐
   │   JVM (HotSpot, etc.)   │
   │   ├─ ClassLoader        │  Loads .class into memory
   │   ├─ Bytecode Verifier  │  Safety + type checks
   │   ├─ Interpreter        │  Runs bytecode line by line
   │   └─ JIT Compiler       │  Hot code → native machine code
   │       (HotSpot, Graal)  │  Near-C performance after warmup
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │   Native machine code   │  CPU instructions
   └────────────┬────────────┘
                ▼
            Output / OS
```

**Key terminology:**

| Term | What It Is |
|------|-----------|
| **JDK** (Java Development Kit) | Compiler + tools + JRE. You install this to *develop* Java. |
| **JRE** (Java Runtime Environment) | JVM + standard library. Just enough to *run* Java. (Bundled into JDK in modern releases.) |
| **JVM** (Java Virtual Machine) | The actual engine that runs bytecode. |
| **JIT** (Just-In-Time Compiler) | Compiles hot bytecode → native code at runtime for speed. |
| **AOT** (Ahead-Of-Time Compiler) | Compile to native binary *before* running. **GraalVM Native Image** does this — instant startup, lower memory. |
| **OpenJDK** | The official open-source Java reference implementation. |
| **Distributions** | Same OpenJDK packaged by different vendors: **Eclipse Temurin** (recommended), Amazon Corretto, Azul Zulu, Microsoft Build, Oracle JDK. |

> [!TIP]
> Use **Eclipse Temurin** (formerly AdoptOpenJDK) installed via **[SDKMAN!](https://sdkman.io/)** — it's the standard. Manage multiple JDKs side-by-side. Use **GraalVM** when you need fast startup (CLIs, serverless, microservices).

---

## Who This Syllabus Is For

| You Are | What You Get |
|---------|--------------|
| **Absolute beginner** — never coded before | Start at Phase 1. Each concept explained from scratch. Java is verbose but predictable — great teacher. |
| **Coming from another language** (Python/JS/C#) | Skim Phase 1–3, focus on Phase 4 (OOP is non-negotiable in Java), Phase 7 (generics differ), Phase 10 (virtual threads), Phase 13 (frameworks). |
| **Self-taught dev with gaps** | Use [Common Mistakes](#common-mistakes) as a self-audit. Re-do whichever phase you flunk. |
| **Bootcamp grad / Junior dev** | Phases 7–11 are usually weak spots. Drill them hard. Then Phase 12 + 13 to be hireable. |
| **Aspiring backend engineer** | Phases 1–11 → **Phase 12** (Spring Boot) → Phase 13/14 (frameworks + DB). |
| **Aspiring Android dev** | Phases 1–10 → switch to the [Kotlin Syllabus](kotlin.md). Android is officially Kotlin-first now, but Java still ships. |
| **Big Data engineer** | Phases 1–10 → Spark/Flink/Kafka tracks in Phase 13/15. |
| **Mid / Senior dev preparing for interviews** | Phases 7, 10 (virtual threads!), 12, 13 + [Interview Questions](#interview-questions) + LeetCode in Java. |
| **Frontend dev moving full-stack** | All phases → Phase 12 (Spring Boot) is the standard backend. |

---

## Learning Paths

Pick the path that matches your goal.

### Path A — Zero to First Backend Job (16–22 weeks)
Fresher with no coding background, target: junior Java/Spring backend role.

```
Phase 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9 → 10 → 11 → 12 → 13 → 14 → 15
```
- Build all 8 [Practice Projects](#practice-projects).
- Pair with the [SQL Syllabus](sql.md) starting at Phase 6.
- After Phase 12, deploy a real Spring Boot app to a public URL.

### Path B — Spring Backend Specialist (10–14 weeks, post-Java basics)
Already know Java syntax, target: Spring Boot expert.

```
Phase 7 → 8 → 9 → 10 → 11 → 12 → 13 → 14 → 15 (cloud)
```
- Deep on Spring (Boot, Data, Security, Cloud, GraphQL, Batch).
- Pair with the [Docker Syllabus](docker.md).
- Build Project 5 (microservices) + Project 8 (event-driven).

### Path C — Android (Java route, then Kotlin) (12–16 weeks)
Goal: ship an Android app to Play Store.

```
Phase 1 → 2 → 3 → 4 → 6 → 7 → 8 → 9 → 10 → switch to Kotlin Syllabus
```
- Skip Spring (Phase 12). Skip big data.
- Move to [Kotlin Syllabus](kotlin.md) and Android documentation as soon as Java basics solid.

### Path D — Big Data / Data Engineering (12–16 weeks)
Apache Spark, Flink, Kafka — all run on the JVM.

```
Phase 1 → 2 → 3 → 4 → 6 → 7 → 8 → 9 → 10 → 11 → 14 (DBs) → 13 (Big Data section) → 15
```
- Master streams + collections (Phase 6, 8). Spark APIs feel like supercharged streams.
- Add Scala or Kotlin for Spark idioms.

### Path E — Interview Prep (4–6 weeks)
Already know Java, need to crack interviews.

```
Phase 4 → 6 → 7 → 8 → 10 → Common Mistakes → Interview Questions → LeetCode in Java
```
- Solve 100 LeetCode problems in Java (mix of easy + medium).
- Drill: thread safety, hashmap internals, immutability, generics, streams.

---

## Prerequisites

> [!NOTE]
> Java is a **statically-typed, object-oriented language** that runs on the JVM. No prior Java experience is needed — but basic programming familiarity (variables, loops, functions in *any* language) helps you move faster.

- A computer (Windows, Mac, or Linux) with at least 8GB RAM (IDEs are heavy)
- Comfort with the terminal / command line — `cd`, `ls`, running commands
- A code editor or IDE — **[IntelliJ IDEA Community Edition](https://www.jetbrains.com/idea/download/)** strongly recommended (free, the industry default)
- A [GitHub account](https://github.com/) to store your code from day one

---

## How to Use This Syllabus

1. **Don't skip phases.** Each one builds on the last. If Phase 4 (OOP) is shaky, Phase 12 (Spring Boot) feels like magic instead of code.
2. **Type the code yourself.** Copy-pasting gives the illusion of learning. Type every example by hand.
3. **Use IntelliJ from day one.** It teaches you Java idioms via inspections and quick-fixes faster than any tutorial.
4. **Always run the tests.** From Phase 11 onward, every project ships with JUnit tests. Run them. Break them. Fix them.
5. **Use a build tool from Project 2.** Maven or Gradle. Don't compile with raw `javac` past the basics.
6. **Read other people's code.** Browse the source of Spring, Guava, Mockito on GitHub. Java pros read more code than they write.
7. **Commit to GitHub** from your first project. Every project gets a README + screenshots.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. There is no rush — depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what Java is, set up your toolchain, and write your first program.

**What this phase is about.** Before any code, you need a working JDK, an IDE that gives you superpowers, and a clear mental model of the JDK / JRE / JVM trio (the most-asked beginner interview question). This phase covers installing Java the *right* way (SDKMAN!), setting up IntelliJ IDEA, writing the canonical `Hello, World!`, and running it both from the IDE and the terminal.

**Why it matters.** Bad install hygiene (system Java mismatches, old versions, no version manager) wastes more beginner time than any other single thing. Get this right and you save weeks.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Java | Statically typed, object-oriented, compiles to bytecode, runs on the JVM. "Write once, run anywhere" |
| 2 | JDK / JRE / JVM | JVM executes bytecode, JRE = JVM + libraries, JDK = JRE + compiler + tools. You install the JDK |
| 3 | Java Versions | Why Java 21 LTS (or 25 LTS) is the modern baseline. Avoid Java 8 for new code |
| 4 | Java Distributions | Eclipse Temurin (recommended), Amazon Corretto, Azul Zulu, Microsoft Build, Oracle JDK — same OpenJDK underneath |
| 5 | Installation with SDKMAN! | `sdk install java 21-tem` — manage multiple JDKs, switch with one command |
| 6 | IntelliJ IDEA | The industry-standard Java IDE. Free Community edition. Refactoring, debugging, inspections built in |
| 7 | Hello World | `public class Main { public static void main(String[] args) { System.out.println("Hello, World!"); } }` |
| 8 | Compile & Run | `javac Main.java` → `Main.class`, then `java Main`. IDEs do this automatically |
| 9 | Packages | `package com.example.app;` — reverse-domain naming, maps to folder structure |
| 10 | `main` Method, Deconstructed | Why `public static void main(String[] args)` — every word has a reason |
| 11 | The Classpath | Where the JVM looks for classes. `-cp` flag, `CLASSPATH` env var |

> [!TIP]
> Use **SDKMAN!** to install and switch between JDKs — it's the `nvm` of the Java world:
> ```bash
> # Install SDKMAN
> curl -s "https://get.sdkman.io" | bash
>
> # Install Java 21 LTS (Temurin distribution)
> sdk install java 21.0.5-tem
>
> # Switch versions per project
> sdk use java 21.0.5-tem
> ```

<details>
<summary><strong>Quick Reference: Anatomy of Hello World</strong></summary>

```java
package com.example.app;             // (1) Package — folder structure

public class Main {                   // (2) Class — file name must match

    public static void main(          // (3) main — JVM entry point
            String[] args) {          // (4) args — CLI arguments
        System.out.println(           // (5) println — print + newline
            "Hello, World!"
        );
    }
}
```
- `public` — visible everywhere
- `static` — belongs to the class, no instance needed
- `void` — returns nothing
- `main` — the special name the JVM looks for
- `String[] args` — array of command-line arguments

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Java 21 via SDKMAN! and verify with `java --version`
- [ ] Set up IntelliJ IDEA Community Edition
- [ ] Compile and run a Hello World *both* in the IDE and from the terminal
- [ ] Explain JDK vs JRE vs JVM in your own words

</details>

---

## Phase 2: Data Types & Variables

![Phase](https://img.shields.io/badge/Phase-2%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-7 Hours](https://img.shields.io/badge/Time-6--7%20Hours-yellow)

> Learn Java's type system — primitives, wrappers, references, casting, and `final`.

**What this phase is about.** Java's type system is **strict**: every variable has a declared type and the compiler checks every operation. You'll learn the **8 primitive types** (the only "atoms" in Java), their **wrapper objects** (`Integer`, `Double`, etc., needed for collections), the difference between **value types** (primitives) and **reference types** (everything else — objects), the `final` keyword (constants + immutability), and modern conveniences like `var` (local-variable type inference, Java 10+).

**Why it matters.** Almost every confusing Java bug — `==` vs `equals()`, `int` overflow, autoboxing performance traps, `0.1 + 0.2 != 0.3`, `BigDecimal` for money — comes from the type system. Master it here and the rest of Java is calm.

### 2.1 — The 8 Primitive Types

| Type | Size | Range | Default | Use For |
|------|:----:|-------|:-------:|---------|
| `byte` | 8-bit | -128 to 127 | 0 | Raw binary data |
| `short` | 16-bit | -32,768 to 32,767 | 0 | Rarely (use `int`) |
| `int` | 32-bit | ~±2.1 billion | 0 | Default integer |
| `long` | 64-bit | ~±9.2 × 10¹⁸ | 0L | Big counters, timestamps |
| `float` | 32-bit | ~±3.4 × 10³⁸ | 0.0f | Rarely (use `double`) |
| `double` | 64-bit | ~±1.8 × 10³⁰⁸ | 0.0 | Default decimal |
| `char` | 16-bit | UTF-16 code unit | ` ` | Single character |
| `boolean` | JVM-defined | `true`/`false` | `false` | Yes/no |

### 2.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Primitive Types | The 8 above. Stored on the stack, fast |
| 2 | Reference Types | Anything that's not a primitive (objects, arrays, `String`). Stored on the heap |
| 3 | Wrapper Classes | `Integer`, `Double`, `Boolean`, ... — object versions of primitives. Needed for collections |
| 4 | Autoboxing & Unboxing | `Integer x = 5;` (autobox), `int y = x;` (unbox). Performance traps in tight loops |
| 5 | `String` | Immutable sequence of characters. The `String` pool. `equals()` for comparison |
| 6 | `StringBuilder` | Mutable, fast string building. Use in loops to avoid quadratic concatenation |
| 7 | Operators | Arithmetic, comparison, logical, bitwise, shift, ternary |
| 8 | Operator Precedence | Why `1 + 2 * 3` is `7`. Use parentheses when in doubt |
| 9 | `var` (Java 10+) | Local-type inference: `var list = new ArrayList<String>();` — only for local vars |
| 10 | `final` | Constants and immutability. `final int MAX = 100;` |
| 11 | Type Casting | Widening (auto): `int → long`. Narrowing (explicit): `(int) 9.7 → 9` |
| 12 | Numeric Literals | `1_000_000` (underscores), `0xff` (hex), `0b101` (binary), `1L`, `1.0f`, `1d` |
| 13 | Arrays | `int[] nums = {1, 2, 3};`, `nums.length`, multidimensional `int[][]` |
| 14 | `null` | The "no reference" value. Source of `NullPointerException` |
| 15 | `Optional<T>` (Preview) | A wrapper that says "may or may not have a value" — full deep dive in Phase 8 |
| 16 | `BigDecimal` & `BigInteger` | For exact arithmetic — money, crypto, anything where rounding kills you |
| 17 | Text Blocks (Java 13+) | `"""multi-line strings"""` — finally |

> [!WARNING]
> **Never compare strings with `==`.** Use `.equals()` instead. `==` compares object references (memory addresses); `.equals()` compares actual content. Same for `Integer` boxes!
> ```java
> String a = new String("hello");
> String b = new String("hello");
> System.out.println(a == b);       // false — different objects
> System.out.println(a.equals(b));  // true  — same content
>
> Integer x = 200;
> Integer y = 200;
> System.out.println(x == y);       // false — outside the cache range -128..127!
> ```

> [!CAUTION]
> **Never use `float` or `double` for money.** Floating-point math is imprecise: `0.1 + 0.2 != 0.3`. Use `BigDecimal`:
> ```java
> BigDecimal a = new BigDecimal("0.1");
> BigDecimal b = new BigDecimal("0.2");
> BigDecimal sum = a.add(b);   // exactly 0.3
> ```

<details>
<summary><strong>Quick Reference: Mutable vs Immutable</strong></summary>

| Category | Examples |
|----------|----------|
| **Immutable** (cannot change) | `String`, all wrapper classes (`Integer`, `Double`...), `BigDecimal`, `LocalDate`, records |
| **Mutable** | Arrays, `ArrayList`, `HashMap`, `StringBuilder`, your own non-record classes |

`String` immutability means `s.toUpperCase()` returns a *new* string — it doesn't change `s`.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables of all 8 primitive types
- [ ] Explain the difference between primitive and reference types
- [ ] Compare strings correctly with `.equals()` instead of `==`
- [ ] Use `var` for local variables and explain its limits
- [ ] Use `BigDecimal` for a money calculation and verify exactness
- [ ] Use a text block for a multi-line SQL or JSON string

</details>

---

## Phase 3: Operators & Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make decisions, repeat actions, and use modern pattern matching.

**What this phase is about.** Programs do two things: make decisions and repeat work. This phase covers `if/else`, the modern `switch` *expressions* with arrow syntax (Java 14+), all loop forms, and **pattern matching** (Java 21+) — Java's most underrated 2020s upgrade. You'll also meet `Optional` chaining patterns that replace `null` checks.

**Why it matters.** "Modern Java" looks dramatically different from Java 8. Pattern matching + switch expressions + records change how you write conditionals. Hiring managers notice when you use them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `else if` / `else` | Conditional branching. Curly braces always recommended |
| 2 | Comparison Operators | `==`, `!=`, `<`, `>`, `<=`, `>=`. Reference vs value semantics |
| 3 | Logical Operators | `&&`, `\|\|`, `!`. Short-circuit evaluation |
| 4 | Ternary | `var status = age >= 18 ? "adult" : "minor";` |
| 5 | Classic `for` | `for (int i = 0; i < n; i++)` — counted iteration |
| 6 | Enhanced `for` | `for (var item : list)` — iterate without an index |
| 7 | `while` & `do-while` | `while`: check first. `do-while`: run-once-then-check |
| 8 | `break`, `continue`, Labels | Exit, skip, escape nested loops with labels (sparingly) |
| 9 | Switch Statement (classic) | Old-school: `case 1: ...; break;` — fall-through bugs |
| 10 | **Switch Expressions (Java 14+)** | `var s = switch(x) { case 1 -> "one"; default -> "?"; };` — no break, no fall-through, returns value |
| 11 | **Pattern Matching for `instanceof`** (16+) | `if (obj instanceof String s) { ... s ... }` — auto-bind |
| 12 | **Pattern Matching for `switch`** (21+) | `case Integer i -> ...; case String s -> ...; case null -> ...;` — typed branches |
| 13 | **Record Patterns** (21+) | `case Point(int x, int y) -> ...` — destructure records |
| 14 | Exhaustiveness | The compiler checks `switch` covers all cases — sealed types + records |

> [!TIP]
> Use enhanced **switch expressions** (Java 14+) instead of classic switch statements. No `break` needed, no fall-through bugs, can return values:
> ```java
> String message = switch (statusCode) {
>     case 200 -> "OK";
>     case 404 -> "Not Found";
>     case 500 -> "Internal Server Error";
>     default  -> "Unknown: " + statusCode;
> };
> ```

<details>
<summary><strong>Quick Reference: Pattern Matching for Switch (Java 21+)</strong></summary>

```java
sealed interface Shape permits Circle, Square, Triangle {}
record Circle(double radius) implements Shape {}
record Square(double side) implements Shape {}
record Triangle(double base, double height) implements Shape {}

double area(Shape s) {
    return switch (s) {
        case Circle(double r)            -> Math.PI * r * r;
        case Square(double side)         -> side * side;
        case Triangle(double b, double h)-> 0.5 * b * h;
    };  // exhaustive — compiler verifies
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write programs using `if`, `switch` expression, and all loop types
- [ ] Use enhanced `switch` expressions with arrow syntax
- [ ] Use `instanceof` pattern matching
- [ ] Use record patterns to destructure data inside `switch`

</details>

---

## Phase 4: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-4%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> The heart of Java — classes, objects, inheritance, polymorphism, and modern features (records, sealed classes).

**What this phase is about.** Java is **OOP-first**: even `main` lives in a class. This phase covers the four pillars (encapsulation, inheritance, polymorphism, abstraction), the modern features that simplify them (**records** for immutable data classes, **sealed classes** for closed type hierarchies, **pattern matching**), and the design idioms every senior Java dev knows by heart (**composition over inheritance**, **interface segregation**, **immutability by default**).

**Why it matters.** Every framework you'll meet (Spring, Hibernate, Jackson) is OOP-driven. You can't read modern Java code without OOP fluency. Records + sealed classes + switch patterns make Java 2026 feel newer than Java 2014 — using them marks you as current.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | Blueprint vs instance. Fields = state, methods = behavior. `new` creates objects |
| 2 | Constructors | `public User(String name) { this.name = name; }`. Default, parameterized, chaining with `this()` |
| 3 | Static Members | `static` field/method belongs to the class, not instances. Constants, factory methods |
| 4 | Access Modifiers | `public` (everywhere), `protected` (package + subclasses), default (package), `private` (class only) |
| 5 | Encapsulation | Private fields + getters/setters → controlled access. The classic getter/setter is being replaced by records |
| 6 | Inheritance | `class Dog extends Animal {}`. `super()` calls parent. Java has **single** inheritance for classes |
| 7 | `Object` (Root) | Every class extends `Object`. `equals()`, `hashCode()`, `toString()`, `getClass()` |
| 8 | `equals()` & `hashCode()` Contract | If `a.equals(b)`, then `a.hashCode() == b.hashCode()`. Critical for sets/maps |
| 9 | Method Overriding & `@Override` | Subclass replaces parent method. `@Override` is mandatory hygiene |
| 10 | Method Overloading | Same name, different parameter list (count or types) |
| 11 | Polymorphism | One interface, many implementations. Compile-time vs runtime |
| 12 | Interfaces | `interface Drawable { void draw(); }`. Multiple inheritance via interfaces |
| 13 | Default & Static Interface Methods (Java 8+) | Add behavior without breaking implementers |
| 14 | Functional Interfaces | Single-abstract-method interfaces — `Runnable`, `Comparator`, `Predicate`. Lambda targets |
| 15 | Abstract Classes | Can have state + abstract methods. Pick over interface when you need shared state |
| 16 | Inner / Nested / Anonymous Classes | When and why. Mostly replaced by lambdas |
| 17 | **Records** (Java 16+) | `record Point(int x, int y) {}` — immutable data carriers, auto `equals`/`hashCode`/`toString` |
| 18 | **Sealed Classes** (Java 17+) | `sealed class Shape permits Circle, Square` — restrict who can extend, enables exhaustive `switch` |
| 19 | `enum` Types | Type-safe constants, can have fields/methods. `Status.ACTIVE` |
| 20 | `Comparable` & `Comparator` | Natural vs custom ordering for sorting |
| 21 | Composition over Inheritance | Industry-favored design — *has-a* > *is-a* |
| 22 | Immutability | Why immutable classes are easier to test, debug, share across threads |

> [!IMPORTANT]
> **Prefer composition over inheritance.** Deep inheritance trees are fragile.
> ```java
> // AVOID — inheritance chains
> class Animal {}
> class Dog extends Animal {}
> class GuideDog extends Dog {}
>
> // PREFER — composition + interfaces (and records when immutable)
> interface Walkable { void walk(); }
> interface Trainable { void train(); }
>
> record Dog(String name) implements Walkable, Trainable {
>     public void walk()  { /* ... */ }
>     public void train() { /* ... */ }
> }
> ```

<details>
<summary><strong>Quick Reference: When to Use Which</strong></summary>

| You Need | Use |
|----------|-----|
| Immutable data carrier | **`record`** |
| Closed family of types (e.g. `Shape = Circle \| Square`) | **`sealed` + records** |
| Behavior contract, no state | **`interface`** |
| Shared state + partial behavior | **`abstract class`** |
| Type-safe constants | **`enum`** |
| Single instance | `enum` with one value, or DI container |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with constructor, fields, methods, encapsulation
- [ ] Implement inheritance with `extends`, override methods with `@Override`
- [ ] Implement multiple interfaces in one class
- [ ] Replace a getter-heavy class with a `record`
- [ ] Define a `sealed` hierarchy and exhaustively `switch` over it
- [ ] Override `equals()`, `hashCode()`, `toString()` correctly (or use a record)

</details>

---

## Phase 5: Strings & Regular Expressions

![Phase](https://img.shields.io/badge/Phase-5%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Master text manipulation and pattern matching.

**What this phase is about.** Real apps process tons of text: names, emails, URLs, log lines, JSON. Java's `String` is **immutable Unicode (UTF-16)**, with a rich method set; `StringBuilder` is the mutable cousin for tight loops. Java's regex API (`Pattern`, `Matcher`) is the same regex flavor as Python and JavaScript — once you learn it, you've learned it everywhere.

**Why it matters.** Form validation, log scraping, data cleaning, file parsing — text everywhere. Regex pays back forever.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | String Basics | Immutability, the `String` pool, character encoding (UTF-16) |
| 2 | String Methods | `length`, `charAt`, `substring`, `indexOf`, `contains`, `startsWith`, `endsWith`, `replace`, `split`, `trim`, `strip` |
| 3 | Concatenation | `+`, `String.join()`, `String.concat()`, `StringBuilder` |
| 4 | Formatting | `String.format("%s is %d", name, age)`, `printf`, `formatted()` (Java 15+) |
| 5 | Text Blocks (Java 13+) | `"""multi-line"""` — for SQL, JSON, HTML |
| 6 | `StringBuilder` & `StringBuffer` | Mutable building. Buffer is thread-safe + slower |
| 7 | `String.chars()` & Streams | Iterate code points functionally |
| 8 | Regex Introduction | `Pattern.compile("\\d+")`, `Matcher`, `matches()`, `find()`, `replaceAll()` |
| 9 | Character Classes | `\d`, `\w`, `\s`, negations, `[a-z]` |
| 10 | Quantifiers | `*`, `+`, `?`, `{n,m}`, greedy vs lazy |
| 11 | Anchors & Boundaries | `^`, `$`, `\b` |
| 12 | Groups | Capturing `(...)`, non-capturing `(?:...)`, named `(?<name>...)` |
| 13 | Lookaround | `(?=...)`, `(?!...)`, `(?<=...)`, `(?<!...)` |
| 14 | `String.split` with Regex | `"a,b;c".split("[,;]")` |
| 15 | Java Regex Gotchas | Backslashes must be escaped (`\\d`), `Pattern.compile` once if reused in loops |

> [!TIP]
> Compile regex patterns *once* if you reuse them — saves significant time:
> ```java
> private static final Pattern EMAIL =
>     Pattern.compile("^[\\w.+-]+@[\\w-]+\\.[\\w.-]+$");
>
> public boolean isValidEmail(String s) {
>     return EMAIL.matcher(s).matches();
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use 10+ String methods correctly
- [ ] Format a money/date string with `String.format`
- [ ] Build a multi-line SQL query with a text block
- [ ] Validate an email with regex
- [ ] Extract all hashtags from a string with `Matcher.find()`

</details>

---

## Phase 6: Collections Framework

![Phase](https://img.shields.io/badge/Phase-6%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Store and manipulate groups of objects with Java's industrial-strength collections.

**What this phase is about.** The Collections Framework is one of Java's crown jewels — a coherent set of interfaces (`List`, `Set`, `Map`, `Queue`) and battle-tested implementations (`ArrayList`, `HashMap`, `TreeMap`, ...). This phase covers picking the right collection (the most common mid-level interview question), iteration, sorting, and the **immutable factories** (`List.of()`, `Map.of()`) that have replaced verbose initialization.

**Why it matters.** "Which collection should I use?" is the highest-leverage data-structure question in Java. Pick wrong → slow code or bugs. Pick right → idiomatic Java.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Hierarchy | `Iterable` → `Collection` → `List` / `Set` / `Queue`. `Map` is separate (not a `Collection`) |
| 2 | `ArrayList` | Dynamic array. O(1) get, O(n) insert/delete in middle. Default `List` |
| 3 | `LinkedList` | Doubly-linked list. O(1) at ends, O(n) random access. Implements `Deque` |
| 4 | `Vector` & `Stack` (legacy) | Synchronized, slow. Don't use — pick `ArrayDeque` for stack semantics |
| 5 | `HashMap` | Key-value, O(1) average lookup. Insertion-ordered: NO, use `LinkedHashMap` for that |
| 6 | `LinkedHashMap` | HashMap that remembers insertion order |
| 7 | `TreeMap` | Sorted keys, O(log n). Implements `NavigableMap` for range queries |
| 8 | `HashSet`, `LinkedHashSet`, `TreeSet` | Same trio as Maps — choose by ordering needs |
| 9 | `Queue`, `Deque`, `ArrayDeque` | FIFO and double-ended. Use `ArrayDeque` for stacks/queues (faster than `Stack` and `LinkedList`) |
| 10 | `PriorityQueue` | Heap-based — pop the smallest (or custom-comparator) element |
| 11 | Iterating | Enhanced `for`, `Iterator` + `it.remove()`, `forEach`, streams |
| 12 | Sorting | `Collections.sort(list)`, `list.sort(comparator)`, `Comparator.comparing(User::getName)` |
| 13 | `Comparable` vs `Comparator` | Natural ordering vs external. `Comparator` chaining: `.thenComparing(...)` |
| 14 | Immutable Collections | `List.of()`, `Map.of()`, `Set.of()`, `List.copyOf()` (Java 9+) |
| 15 | Concurrent Collections | `ConcurrentHashMap`, `CopyOnWriteArrayList`, `BlockingQueue` (covered in Phase 10) |
| 16 | Choosing the Right Collection | Decision tree — ordered? unique? key-based? sorted? thread-safe? |

> [!TIP]
> Use `List.of()`, `Map.of()`, `Set.of()` (Java 9+) for immutable collections. Use `new ArrayList<>(List.of(...))` if you need mutability:
> ```java
> // Immutable — cannot modify
> var names  = List.of("Alice", "Bob", "Charlie");
> var scores = Map.of("Alice", 95, "Bob", 87);
> var tags   = Set.of("java", "spring", "backend");
>
> // Mutable copy when you need to modify
> var mutableNames = new ArrayList<>(List.of("Alice", "Bob"));
> mutableNames.add("Charlie");
> ```

<details>
<summary><strong>Quick Reference: Decision Table</strong></summary>

| You Need | Use |
|----------|-----|
| Indexed list, fast random access | `ArrayList` |
| Frequent inserts at ends | `ArrayDeque` (or `LinkedList`) |
| Unique values, no order | `HashSet` |
| Unique values, insertion order | `LinkedHashSet` |
| Unique values, sorted | `TreeSet` |
| Key→value, fast lookup, no order | `HashMap` |
| Key→value, insertion order | `LinkedHashMap` |
| Key→value, sorted by key | `TreeMap` |
| FIFO queue | `ArrayDeque` (as `Queue`) |
| LIFO stack | `ArrayDeque` (push/pop) |
| Min/max heap | `PriorityQueue` |
| Thread-safe map | `ConcurrentHashMap` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `ArrayList`, `HashMap`, `HashSet`, `ArrayDeque` correctly
- [ ] Sort a list of records using `Comparator.comparing(...).thenComparing(...)`
- [ ] Pick the right collection given a scenario (interview-style)
- [ ] Use `List.of()` / `Map.of()` for immutable defaults
- [ ] Iterate a `Map`'s `entrySet()` with destructuring

</details>

---

## Phase 7: Generics

![Phase](https://img.shields.io/badge/Phase-7%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Write reusable, type-safe code without `Object` casts.

**What this phase is about.** Generics let you parameterize classes and methods over types: `List<String>` vs `List<Integer>`. The compiler enforces type safety; you avoid casts. Generics also have famous gotchas — **type erasure** (no runtime type info), **wildcards**, and the **PECS** rule (Producer Extends, Consumer Super) — all favorite interview territory.

**Why it matters.** You can't read the Collections Framework, Spring, or any major library without generics. PECS questions appear in nearly every senior Java interview.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Generics? | Compile-time type safety. No casts. Reusable code |
| 2 | Generic Classes | `class Box<T> { T value; }` |
| 3 | Generic Methods | `<T> T firstNonNull(T... values)` |
| 4 | Bounded Type Parameters | `<T extends Number>` (upper), `<T extends Comparable<T>>`, multiple bounds with `&` |
| 5 | Wildcards | `?` (unknown), `? extends Number` (read), `? super Integer` (write) |
| 6 | PECS Rule | **Producer Extends, Consumer Super.** `void copy(List<? extends T> src, List<? super T> dst)` |
| 7 | Type Erasure | Generic types are erased at runtime — `List<String>` and `List<Integer>` are the same class. No `new T()`, no `instanceof T` |
| 8 | Generic Interfaces | `interface Repository<T, ID>` — Spring Data, JPA |
| 9 | Generic Records | `record Pair<A, B>(A first, B second) {}` |
| 10 | Raw Types | `List` (no `<...>`) — legacy, avoid. Compiler warns |

> [!IMPORTANT]
> **PECS — Producer Extends, Consumer Super:**
> - `<? extends T>` = "produces" T (you read it). Adding is forbidden.
> - `<? super T>` = "consumes" T (you write into it). Reading gives `Object`.
> ```java
> static <T> void copy(List<? extends T> src,   // produces T  (read)
>                      List<? super   T> dst) { // consumes T (write)
>     for (T item : src) dst.add(item);
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a generic class with one or more type parameters
- [ ] Write a generic method with a bounded type parameter
- [ ] Use `? extends` and `? super` correctly (PECS)
- [ ] Explain type erasure and one of its consequences

</details>

---

## Phase 8: Functional Programming & Streams

![Phase](https://img.shields.io/badge/Phase-8%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Process data declaratively with lambdas, streams, and `Optional`.

**What this phase is about.** Java 8 (2014) added **lambdas** (anonymous functions), **functional interfaces** (`Predicate`, `Function`, `Consumer`, `Supplier`), **streams** (lazy declarative pipelines), and **`Optional`** (the null-safe wrapper). Together they let you write data-processing code that reads top-to-bottom: filter → map → group → collect, no manual loops, no temp variables.

**Why it matters.** Streams are everywhere in modern Java code — Spring Data, reactive frameworks, every interview. `Optional` (used right) eliminates a huge category of `NullPointerException`s.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Lambda Expressions | `(a, b) -> a + b` — anonymous functions. Replace anonymous classes |
| 2 | Functional Interfaces | `@FunctionalInterface`. The 4 core: `Predicate<T>`, `Function<T,R>`, `Consumer<T>`, `Supplier<T>`. Plus binary, bi-, primitives |
| 3 | Method References | `String::toUpperCase`, `User::new`, `System.out::println` |
| 4 | Closures | Lambdas can read effectively-final outer variables |
| 5 | Stream Basics | `list.stream()`, intermediate ops + terminal ops. Lazy evaluation |
| 6 | Intermediate Ops | `filter`, `map`, `flatMap`, `distinct`, `sorted`, `limit`, `skip`, `peek` |
| 7 | Terminal Ops | `collect`, `forEach`, `reduce`, `count`, `anyMatch`, `allMatch`, `findFirst`, `min`, `max` |
| 8 | Collectors | `toList()`, `toSet()`, `toMap()`, `groupingBy()`, `partitioningBy()`, `joining()` |
| 9 | Primitive Streams | `IntStream`, `LongStream`, `DoubleStream` — avoid boxing in hot loops |
| 10 | Stream Sources | `Stream.of(...)`, `Files.lines(path)`, `IntStream.range()` |
| 11 | Parallel Streams | `.parallelStream()` — when to use, when *not* to (mostly: not) |
| 12 | `Optional<T>` | Wrapper for "may or may not have a value." `.orElse`, `.orElseThrow`, `.map`, `.ifPresent`, `.flatMap` |
| 13 | `Stream.toList()` (Java 16+) | Modern shortcut for `collect(Collectors.toList())` |
| 14 | `Stream.gather()` (Java 24+) | Generic intermediate op — finally |
| 15 | Common Pitfalls | Streams are single-use; `forEach` ≠ `peek`; mutating state from streams is wrong |

> [!TIP]
> Combine streams + lambdas for clean, declarative pipelines:
> ```java
> Map<String, List<String>> emailsByCountry = users.stream()
>     .filter(User::isActive)
>     .filter(u -> u.age() >= 18)
>     .collect(Collectors.groupingBy(
>         User::country,
>         Collectors.mapping(User::email, Collectors.toList())
>     ));
> ```
> Use `Optional` to make absence explicit:
> ```java
> Optional<User> user = repository.findById(id);
> String displayName = user.map(User::name).orElse("Anonymous");
> ```

<details>
<summary><strong>Quick Reference: Functional Interfaces</strong></summary>

| Interface | Signature | Use |
|-----------|-----------|-----|
| `Predicate<T>` | `T -> boolean` | filter |
| `Function<T,R>` | `T -> R` | map |
| `Consumer<T>` | `T -> void` | forEach |
| `Supplier<T>` | `() -> T` | lazy creation |
| `BiFunction<T,U,R>` | `(T,U) -> R` | reduce, merge |
| `UnaryOperator<T>` | `T -> T` | replaceAll |
| `BinaryOperator<T>` | `(T,T) -> T` | reduce |
| `Comparator<T>` | `(T,T) -> int` | sort |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a lambda for each of the 4 core functional interfaces
- [ ] Use method references (`Class::method`, `obj::method`, `Class::new`)
- [ ] Process a list with `filter` → `map` → `collect`
- [ ] Group a list with `Collectors.groupingBy`
- [ ] Replace a chain of `null` checks with `Optional`

</details>

---

## Phase 9: Exception Handling & I/O

![Phase](https://img.shields.io/badge/Phase-9%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Handle errors gracefully and work with files using modern NIO.2.

**What this phase is about.** Real programs fail — files vanish, networks drop, parsers choke. Java has a checked-exception system (a controversial design choice you'll meet) and a modern file API (`java.nio.file`) that replaces the verbose `java.io`. You'll also learn **try-with-resources** (auto-close), custom exceptions, and the `Logger` (use it, never `printStackTrace`).

**Why it matters.** Production Java is judged on how it fails. Senior engineers handle errors thoughtfully; juniors swallow them with bare `catch`. This phase shows you the difference.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Exception Hierarchy | `Throwable` → `Error` (don't catch) + `Exception` → `RuntimeException` (unchecked) |
| 2 | Checked vs Unchecked | Checked: must catch or declare. Unchecked: programming errors |
| 3 | `try` / `catch` / `finally` | Catch specific types, clean up in `finally` |
| 4 | Multi-catch | `catch (IOException \| SQLException e)` — combine handlers |
| 5 | `try-with-resources` | `try (var f = Files.newBufferedReader(p))` — auto-close `AutoCloseable` |
| 6 | `throws` Declaration | Declare checked exceptions a method propagates |
| 7 | Custom Exceptions | `class UserNotFoundException extends RuntimeException` |
| 8 | Exception Chaining | `throw new ServiceException("X failed", cause)` — preserve original |
| 9 | `java.nio.file` (NIO.2) | `Path`, `Paths`, `Files.readString`, `Files.write`, `Files.list`, `Files.walk` |
| 10 | Reading Files | `Files.readAllLines`, `Files.lines` (stream — memory-friendly), `BufferedReader` |
| 11 | Writing Files | `Files.writeString`, `Files.write`, `BufferedWriter` |
| 12 | Streams & Channels | `InputStream`, `OutputStream` for binary; `Reader`/`Writer` for text |
| 13 | Console I/O | `System.in`, `Scanner`, `BufferedReader.readLine` |
| 14 | Serialization | `Serializable` (legacy), JSON via Jackson/Gson (modern, recommended) |
| 15 | Logging | `java.util.logging` (basic), **SLF4J + Logback** (industry standard) |
| 16 | Best Practices | Catch specific exceptions, never swallow, prefer unchecked for unrecoverable, log with context |

> [!WARNING]
> **Never catch `Exception` or `Throwable` generically — it hides real bugs:**
> ```java
> // WRONG
> try { processFile(path); }
> catch (Exception e) { e.printStackTrace(); }
>
> // CORRECT
> try { processFile(path); }
> catch (FileNotFoundException e) { log.warn("Missing file: {}", path); }
> catch (IOException e)           { log.error("Read failed: {}", path, e); throw e; }
> ```

<details>
<summary><strong>Quick Reference: NIO.2 File Recipes</strong></summary>

```java
import java.nio.file.*;

// Read whole file as string
String content = Files.readString(Path.of("data.txt"));

// Write string to file (replaces existing)
Files.writeString(Path.of("out.txt"), "hello");

// Stream lines (lazy, memory-friendly)
try (Stream<String> lines = Files.lines(Path.of("big.csv"))) {
    long count = lines.filter(l -> l.contains("ERROR")).count();
}

// Walk directory recursively
try (Stream<Path> walk = Files.walk(Path.of("src"))) {
    walk.filter(p -> p.toString().endsWith(".java"))
        .forEach(System.out::println);
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `try-with-resources` for every `AutoCloseable`
- [ ] Catch specific exceptions, never bare `catch (Exception e)`
- [ ] Read a CSV with `Files.lines` and stream-process it
- [ ] Define a custom exception class with cause-chaining
- [ ] Set up SLF4J + Logback in a small project

</details>

---

## Phase 10: Concurrency, Multithreading & Virtual Threads

![Phase](https://img.shields.io/badge/Phase-10%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Threads, executors, locks, atomics, `CompletableFuture`, and the game-changing virtual threads.

**What this phase is about.** Java was built for concurrency — `synchronized` is in the language since v1.0. This phase covers the whole stack: **threads** (the OS primitives), **`ExecutorService`** (the modern way to run them), **locks** + **atomics** (when `synchronized` isn't enough), **`CompletableFuture`** (async pipelines), the famous **Java Memory Model** (`volatile`, `happens-before`), and **virtual threads** (Java 21's revolutionary Project Loom — millions of threads instead of thousands, no thread-pool tuning).

**Why it matters.** Concurrency questions dominate senior Java interviews. Virtual threads are the single biggest JVM upgrade in 15 years — knowing them in 2026 separates current devs from those stuck in 2018. Backend systems live or die on concurrency choices.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Concurrency vs Parallelism | Concurrency = many at once. Parallelism = doing many at once |
| 2 | Thread Lifecycle | NEW → RUNNABLE → BLOCKED/WAITING/TIMED_WAITING → TERMINATED |
| 3 | Creating Threads | `new Thread(() -> ...).start()`. Prefer `Runnable` / `Callable` over extending `Thread` |
| 4 | `Runnable` vs `Callable` | Runnable: no return. Callable<T>: returns via `Future<T>`, can throw checked |
| 5 | `synchronized` | Method or block. Object monitor / intrinsic lock |
| 6 | `volatile` | Memory visibility (writes immediately visible across threads). Not atomicity |
| 7 | `java.util.concurrent.atomic` | `AtomicInteger`, `AtomicReference`, `AtomicLong` — lock-free atomic operations |
| 8 | `Lock`, `ReentrantLock`, `ReadWriteLock` | More flexible than `synchronized` (timed, interruptible, fair) |
| 9 | Java Memory Model | `happens-before`, reorderings, why `volatile` and `synchronized` matter |
| 10 | `ExecutorService` | `Executors.newFixedThreadPool`, `newCachedThreadPool`, `newSingleThreadExecutor` |
| 11 | `submit()` & `invokeAll()` | Run tasks, collect futures, gather results |
| 12 | `CompletableFuture` | Async pipelines: `supplyAsync`, `thenApply`, `thenCompose`, `allOf`, `anyOf`, `exceptionally` |
| 13 | Concurrent Collections | `ConcurrentHashMap`, `CopyOnWriteArrayList`, `BlockingQueue`, `ConcurrentLinkedQueue` |
| 14 | Producer/Consumer with `BlockingQueue` | Classic concurrency pattern |
| 15 | `ScheduledExecutorService` | Delayed and periodic execution |
| 16 | `ForkJoinPool` & Parallel Streams | Divide-and-conquer parallelism |
| 17 | `ThreadLocal` | Per-thread state. Pitfalls: leaks in thread pools |
| 18 | **Virtual Threads (Java 21+)** | `Thread.ofVirtual()`, `Executors.newVirtualThreadPerTaskExecutor()` — millions of threads, automatic scheduling |
| 19 | **Structured Concurrency (Java 21+ preview)** | `StructuredTaskScope` — bound the lifetime of forked tasks to a scope |
| 20 | **Scoped Values (Java 21+ preview)** | Modern replacement for `ThreadLocal` — immutable, well-scoped |
| 21 | Common Pitfalls | Deadlocks, race conditions, thread starvation, busy-wait, leaking ThreadLocals |

> [!CAUTION]
> **Never `synchronized` on a public field or `this`.** External code can lock on your instance and deadlock you:
> ```java
> // WRONG — anyone with the reference can lock you
> public synchronized void transfer() { ... }
>
> // CORRECT — private lock object, only you control it
> private final Object lock = new Object();
>
> public void transfer(Account from, Account to, int amt) {
>     synchronized (lock) {
>         from.debit(amt);
>         to.credit(amt);
>     }
> }
> ```

> [!IMPORTANT]
> **In Java 21+, prefer virtual threads for I/O-bound work.** Thread pools become almost unnecessary:
> ```java
> try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
>     IntStream.range(0, 10_000).forEach(i ->
>         executor.submit(() -> {
>             var resp = httpClient.send(request, BodyHandlers.ofString());
>             process(resp);
>             return null;
>         })
>     );
> }
> // 10,000 concurrent HTTP calls — easy.
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Run code in an `ExecutorService`, collect results from `Future`s
- [ ] Build an async pipeline with `CompletableFuture` (compose, exceptionally)
- [ ] Use `AtomicInteger` for a counter shared across threads
- [ ] Implement producer/consumer with `BlockingQueue`
- [ ] Replace a thread pool with `newVirtualThreadPerTaskExecutor`
- [ ] Explain `volatile` vs `synchronized` and when each is enough

</details>

---

## Phase 11: Build Tools, Testing & Modern Project Setup

![Phase](https://img.shields.io/badge/Phase-11%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build, test, lint, package, ship.

**What this phase is about.** Real Java projects ship through Maven or Gradle. You'll write tests in **JUnit 5** (the modern default), mock with **Mockito**, write expressive assertions with **AssertJ**, and run integration tests with **Testcontainers** (real Postgres in Docker — no more "works on my machine"). You'll also see **CI/CD with GitHub Actions** and structure your project the way every Spring shop expects.

**Why it matters.** Untested code is a coin flip. Companies hiring above junior expect tests as a default. Setting up the toolchain right *once* saves you on every project for years.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Test? | Refactor confidence, regression prevention, executable docs |
| 2 | Testing Pyramid | Unit (fast, many) → Integration → E2E (slow, few) |
| 3 | **JUnit 5** | `@Test`, `@BeforeEach`, `@AfterEach`, `@DisplayName`, lifecycle |
| 4 | Assertions | `assertEquals`, `assertThrows`, `assertAll`, `assertTimeout` |
| 5 | Parameterized Tests | `@ParameterizedTest` + `@ValueSource`, `@CsvSource`, `@MethodSource` |
| 6 | **AssertJ** | Fluent assertions: `assertThat(list).hasSize(3).contains("Alice")` |
| 7 | **Mockito** | `mock()`, `when().thenReturn()`, `verify()`, `@Mock`, `@InjectMocks` |
| 8 | **Testcontainers** | Real Postgres / Kafka / Redis in Docker — for true integration tests |
| 9 | **REST Assured** | DSL for testing REST APIs end-to-end |
| 10 | Coverage | **JaCoCo** — line + branch coverage. Aim 80%+ |
| 11 | TDD Basics | Red → Green → Refactor cycle |
| 12 | **Maven** | `pom.xml`, dependencies, plugins, lifecycle, `mvn package` |
| 13 | **Gradle** | `build.gradle.kts` (Kotlin DSL), faster builds, Groovy alt |
| 14 | Maven vs Gradle | Maven: predictable, XML, ubiquitous. Gradle: faster, scriptable, default for Spring + Android |
| 15 | Multi-module Projects | Reactor builds (Maven), composite builds (Gradle) |
| 16 | JAR Packaging | Plain JAR, fat/uber-JAR (Spring Boot), Java modules |
| 17 | Code Quality | **Checkstyle**, **PMD**, **SpotBugs**, **ErrorProne** — static analysis |
| 18 | **GraalVM Native Image** | Compile to a native binary — instant startup, less RAM. Used by Spring Native, Quarkus, Micronaut |
| 19 | GitHub Actions for Java | `actions/setup-java@v4` with `distribution: 'temurin'`. Matrix builds across JDK versions |
| 20 | Publishing | Publish to Maven Central via Sonatype OSS or GitHub Packages |

<details>
<summary><strong>Quick Reference: Modern JUnit 5 + Mockito + AssertJ Test</strong></summary>

```java
@ExtendWith(MockitoExtension.class)
class UserServiceTest {

    @Mock UserRepository repo;
    @InjectMocks UserService service;

    @Test
    @DisplayName("returns user when found")
    void findById_present() {
        var user = new User(1L, "Alice");
        when(repo.findById(1L)).thenReturn(Optional.of(user));

        var result = service.findById(1L);

        assertThat(result).contains(user);
        verify(repo).findById(1L);
    }

    @Test
    void findById_throws_when_missing() {
        when(repo.findById(99L)).thenReturn(Optional.empty());

        assertThatThrownBy(() -> service.findByIdOrFail(99L))
            .isInstanceOf(UserNotFoundException.class)
            .hasMessageContaining("99");
    }
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 10+ JUnit 5 tests with parameterized cases
- [ ] Mock dependencies with Mockito and verify interactions
- [ ] Use AssertJ fluent assertions instead of vanilla `assertEquals`
- [ ] Use Testcontainers to integration-test against real Postgres
- [ ] Set up Maven *or* Gradle for a project
- [ ] Add a GitHub Actions workflow that builds + tests on every push
- [ ] Generate a JaCoCo coverage report and aim for 80%+

</details>

---

## Phase 12: Spring Boot & Web APIs

![Phase](https://img.shields.io/badge/Phase-12%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 12-16 Hours](https://img.shields.io/badge/Time-12--16%20Hours-yellow)

> Build production REST APIs with the most popular Java framework on Earth.

**What this phase is about.** **Spring Boot** is to Java backends what Express is to Node, what Rails is to Ruby — only bigger. This phase covers Spring's core (dependency injection), building REST APIs, request validation with Bean Validation, persistence with **Spring Data JPA**, security with **Spring Security** + JWT, observability with **Actuator** + Micrometer, configuration with profiles, exception handling, and packaging as a fat JAR or container.

**Why it matters.** Almost every JVM job posting says "Spring Boot." This single phase, mastered, makes you employable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Spring? | Convention over configuration, autoconfiguration, embedded servers, massive ecosystem |
| 2 | Spring Initializr | [start.spring.io](https://start.spring.io) — generate a project with chosen deps |
| 3 | `@SpringBootApplication` | Combines `@Configuration`, `@EnableAutoConfiguration`, `@ComponentScan` |
| 4 | Dependency Injection | `@Component`, `@Service`, `@Repository`, `@Controller`, `@Bean` |
| 5 | Constructor Injection | The right way (immutable, testable). Avoid `@Autowired` field injection |
| 6 | Beans & Scopes | `@Scope("singleton")` (default), `prototype`, `request`, `session` |
| 7 | `@Configuration` | Java config classes for beans not on `@Component` classes |
| 8 | Profiles | `@Profile("dev")`, `application-dev.properties` — env-specific configs |
| 9 | `application.properties` / `.yml` | Externalize config. `@Value`, `@ConfigurationProperties` |
| 10 | REST Controllers | `@RestController`, `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`, `@PatchMapping` |
| 11 | Path Vars & Query Params | `@PathVariable`, `@RequestParam`, `@RequestBody`, `@RequestHeader` |
| 12 | Response | `ResponseEntity<T>`, status codes, headers, content negotiation |
| 13 | Bean Validation | `@Valid`, `@NotBlank`, `@Email`, `@Min`, `@Max`, `@Pattern`, custom validators |
| 14 | Global Error Handling | `@ControllerAdvice` + `@ExceptionHandler` |
| 15 | Spring Data JPA | `JpaRepository<T, ID>` — auto-generates `save`, `findById`, `findAll`, derived queries |
| 16 | Database Setup | `application.properties` for JDBC URL, Hibernate dialect, schema generation |
| 17 | DTOs & Mapping | Why never expose entities directly. `MapStruct` / records to map between layers |
| 18 | Pagination & Sorting | `Pageable`, `Page<T>`, sorting params |
| 19 | Spring Security | OAuth2, JWT, password encoding (BCrypt), method-level security, CSRF |
| 20 | Logging | SLF4J + Logback. Levels, file appenders, JSON logs in prod |
| 21 | Spring Boot Actuator | `/actuator/health`, `/metrics`, `/info`, `/env` — production observability |
| 22 | Micrometer + Prometheus | Metrics export. Wire to Grafana for dashboards |
| 23 | Testing Spring | `@SpringBootTest`, `@WebMvcTest`, `@DataJpaTest`, `MockMvc`, `TestRestTemplate` |
| 24 | OpenAPI / Swagger | **springdoc-openapi** — auto-generated API docs at `/swagger-ui.html` |
| 25 | Async & Scheduling | `@Async`, `@Scheduled` for cron-like jobs |
| 26 | Spring WebFlux (reactive) | When you need reactive: `Mono`/`Flux`, R2DBC. Most apps don't need it |
| 27 | Packaging | `mvn package` → fat JAR. `Dockerfile` for container. GraalVM Native for instant startup |

> [!IMPORTANT]
> **Use constructor injection.** It makes dependencies explicit, enables `final` fields, and tests don't need a Spring context:
> ```java
> // CORRECT — Spring auto-wires single constructor (no @Autowired needed)
> @Service
> public class UserService {
>     private final UserRepository repo;
>     private final EmailClient email;
>
>     public UserService(UserRepository repo, EmailClient email) {
>         this.repo = repo;
>         this.email = email;
>     }
> }
> ```

<details>
<summary><strong>Quick Reference: A Tiny Production-Style REST Controller</strong></summary>

```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    private final UserService service;

    public UserController(UserService service) { this.service = service; }

    @GetMapping
    public Page<UserDto> list(Pageable pageable) {
        return service.findAll(pageable);
    }

    @GetMapping("/{id}")
    public UserDto get(@PathVariable Long id) {
        return service.findById(id);
    }

    @PostMapping
    @ResponseStatus(HttpStatus.CREATED)
    public UserDto create(@Valid @RequestBody CreateUserRequest req) {
        return service.create(req);
    }
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Generate a Spring Boot project, run it, see "Whitelabel Error Page"
- [ ] Build CRUD endpoints with `@RestController` + `JpaRepository`
- [ ] Validate request bodies with Bean Validation
- [ ] Add JWT authentication with Spring Security
- [ ] Expose `/actuator/health` + Prometheus metrics
- [ ] Auto-generate Swagger docs with springdoc-openapi
- [ ] Test the API with `@WebMvcTest` + `MockMvc`
- [ ] Package as a fat JAR and run with `java -jar`

</details>

---

## Phase 13: The Java Frameworks Ecosystem

![Phase](https://img.shields.io/badge/Phase-13%2F15-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The single biggest reason Java is unkillable — its library ecosystem.

**What this phase is about.** Java has *the* most mature library ecosystem of any language. Every problem you can think of — HTTP, JSON, validation, database, messaging, search, security, observability, AI, big data, mobile, desktop — has at least one battle-tested library, often three. This phase is a **map**: a categorized directory of every library you'll meet on the job, with one-line descriptions so you know which is which.

**Why it matters.** When a Spring Boot job description lists "Spring Cloud, Resilience4j, Kafka, Caffeine, OpenTelemetry, MapStruct, Lombok, Testcontainers, Liquibase," you should *know what every one of those is* without Googling. This phase is your dictionary.

### 13.1 — Web Frameworks (Backend)

| Framework | What It Is | Best For |
|-----------|-----------|----------|
| **[Spring Boot](https://spring.io/projects/spring-boot)** | The dominant Java backend framework. Auto-config, embedded server | 90% of Java backends |
| **[Quarkus](https://quarkus.io/)** | "Supersonic Subatomic Java" — instant startup via GraalVM | Cloud-native, serverless, Kubernetes |
| **[Micronaut](https://micronaut.io/)** | Compile-time DI, fast startup, low memory | Microservices, serverless |
| **[Helidon](https://helidon.io/)** | Oracle's microservices framework — MP and SE flavors | Lightweight microservices |
| **[Vert.x](https://vertx.io/)** | Reactive, polyglot, event-driven | High-throughput async |
| **[Javalin](https://javalin.io/)** | Tiny Kotlin/Java web framework | Lightweight services |
| **[Spark Java](http://sparkjava.com/)** | Sinatra-inspired micro-framework | Quick prototypes |
| **[Play Framework](https://www.playframework.com/)** | Reactive, Scala/Java | Real-time apps |
| **[Dropwizard](https://www.dropwizard.io/)** | Opinionated production-ready | Standalone services |
| **[Ratpack](https://ratpack.io/)** | Async + reactive on Netty | High-throughput |
| **[Jakarta EE](https://jakarta.ee/) (formerly Java EE)** | Standardized enterprise APIs (Servlet, JSP, JPA, JMS, etc.) | Enterprise apps |

### 13.2 — Spring Ecosystem (the Spring "family")

| Library | What It Does |
|---------|--------------|
| **Spring Boot** | Fast app startup with autoconfig |
| **Spring Framework** | DI core (used by everything below) |
| **Spring MVC** | Servlet-based REST/web |
| **Spring WebFlux** | Reactive web (Reactor-powered) |
| **Spring Data JPA / R2DBC / MongoDB / Redis / Cassandra** | Repository abstractions per data store |
| **Spring Security** | Authentication, authorization, OAuth2, JWT |
| **Spring Cloud** | Microservices: service discovery, config, gateway, circuit breakers |
| **Spring Cloud Gateway** | API gateway, routing, filters |
| **Spring Cloud Stream** | Event-driven microservices over Kafka/RabbitMQ |
| **Spring Batch** | Large-scale batch jobs (ETL) |
| **Spring Integration** | Enterprise integration patterns |
| **Spring HATEOAS** | Hypermedia REST APIs |
| **Spring GraphQL** | First-party GraphQL support |
| **Spring AI** | LLMs, embeddings, RAG, vector DBs — the 2026 must-have |
| **Spring Native / Spring Boot AOT** | GraalVM native image support |
| **Spring Session** | Externalized HTTP sessions (Redis, JDBC) |
| **Spring Authorization Server** | OAuth2 / OIDC server |

### 13.3 — Persistence & ORM

| Library | What It Does |
|---------|--------------|
| **[Hibernate](https://hibernate.org/)** | The most popular JPA implementation |
| **[JPA (Jakarta Persistence)](https://jakarta.ee/specifications/persistence/)** | The spec; pick an implementation |
| **[Spring Data JPA](https://spring.io/projects/spring-data-jpa)** | Repository pattern over JPA |
| **[jOOQ](https://www.jooq.org/)** | Type-safe SQL DSL — a different philosophy from JPA |
| **[MyBatis](https://mybatis.org/)** | SQL-mapper framework — write SQL, MyBatis maps results |
| **[Querydsl](https://querydsl.com/)** | Type-safe queries on JPA / SQL |
| **[Ebean ORM](https://ebean.io/)** | Lightweight ORM alternative |
| **[Flyway](https://flywaydb.org/)** | Versioned database migrations |
| **[Liquibase](https://www.liquibase.org/)** | XML/YAML/JSON-based migrations |
| **[HikariCP](https://github.com/brettwooldridge/HikariCP)** | The connection pool everyone uses |

### 13.4 — Reactive

| Library | What It Does |
|---------|--------------|
| **[Project Reactor](https://projectreactor.io/)** | `Mono` / `Flux` — Spring WebFlux's foundation |
| **[RxJava 3](https://github.com/ReactiveX/RxJava)** | The original ReactiveX implementation for Java |
| **[Vert.x](https://vertx.io/)** | Polyglot reactive toolkit |
| **[Akka](https://akka.io/)** | Actor model, distributed systems |

### 13.5 — Testing

| Library | What It Does |
|---------|--------------|
| **[JUnit 5](https://junit.org/junit5/)** | The default test framework |
| **[TestNG](https://testng.org/)** | JUnit alternative — flexible parameterization |
| **[Mockito](https://site.mockito.org/)** | Mocking framework |
| **[AssertJ](https://assertj.github.io/doc/)** | Fluent assertions |
| **[Hamcrest](http://hamcrest.org/JavaHamcrest/)** | Older matcher library |
| **[Testcontainers](https://www.testcontainers.org/)** | Real DBs / brokers via Docker for tests |
| **[REST Assured](https://rest-assured.io/)** | REST API testing DSL |
| **[WireMock](http://wiremock.org/)** | Mock HTTP services |
| **[Selenium](https://www.selenium.dev/)** | Browser automation |
| **[Cucumber](https://cucumber.io/)** | BDD: Gherkin-syntax tests |
| **[Karate](https://github.com/karatelabs/karate)** | API + UI testing in one |
| **[Pact](https://docs.pact.io/)** | Consumer-driven contract testing |
| **[ArchUnit](https://www.archunit.org/)** | Architecture rule tests |

### 13.6 — JSON & Serialization

| Library | What It Does |
|---------|--------------|
| **[Jackson](https://github.com/FasterXML/jackson)** | The JSON library (used by Spring) |
| **[Gson](https://github.com/google/gson)** | Google's JSON library |
| **[Moshi](https://github.com/square/moshi)** | Square's modern JSON (Android) |
| **[JSON-B](https://jakarta.ee/specifications/jsonb/)** | Jakarta EE binding spec |
| **[Protobuf-java](https://protobuf.dev/)** | Google Protocol Buffers |
| **[Avro](https://avro.apache.org/)** | Apache row-oriented serialization (Kafka pairs well) |

### 13.7 — Logging & Observability

| Library | What It Does |
|---------|--------------|
| **[SLF4J](http://www.slf4j.org/)** | The logging facade — code against this |
| **[Logback](http://logback.qos.ch/)** | The default impl behind SLF4J |
| **[Log4j 2](https://logging.apache.org/log4j/2.x/)** | Apache logging — async, performant |
| **[Tinylog](https://tinylog.org/v2/)** | Lightweight alternative |
| **[Micrometer](https://micrometer.io/)** | Metrics facade — exports to Prometheus, Datadog, etc. |
| **[OpenTelemetry Java](https://opentelemetry.io/docs/instrumentation/java/)** | Modern unified tracing + metrics + logs |
| **[Spring Boot Actuator](https://docs.spring.io/spring-boot/reference/actuator/index.html)** | Health, metrics, info endpoints |
| **[Sleuth → Micrometer Tracing](https://micrometer.io/docs/tracing)** | Distributed tracing |

### 13.8 — Code Generation & Boilerplate Killers

| Library | What It Does |
|---------|--------------|
| **[Lombok](https://projectlombok.org/)** | `@Getter`, `@Setter`, `@Builder`, `@Data` — annotation-driven boilerplate removal |
| **[MapStruct](https://mapstruct.org/)** | Compile-time DTO ↔ entity mapping |
| **[Immutables](https://immutables.github.io/)** | Generate immutable value classes |
| **[Google AutoValue](https://github.com/google/auto/blob/main/value/userguide/index.md)** | Immutable value types |
| **[Records (built-in 16+)](https://openjdk.org/jeps/395)** | Many Lombok use-cases now built-in |

### 13.9 — Validation

| Library | What It Does |
|---------|--------------|
| **[Hibernate Validator](https://hibernate.org/validator/)** | Reference implementation of Bean Validation |
| **[Jakarta Validation (JSR 380)](https://jakarta.ee/specifications/bean-validation/)** | The annotation spec (`@NotNull`, `@Email`, `@Min`...) |

### 13.10 — Messaging, Queues & Streams

| Library | What It Does |
|---------|--------------|
| **[Apache Kafka](https://kafka.apache.org/) (clients)** | The dominant event streaming platform |
| **[Kafka Streams](https://kafka.apache.org/documentation/streams/)** | Stream processing on Kafka |
| **[Spring for Apache Kafka](https://spring.io/projects/spring-kafka)** | Spring integration for Kafka |
| **[RabbitMQ Java client / Spring AMQP](https://www.rabbitmq.com/java-client.html)** | AMQP messaging |
| **[Apache ActiveMQ Artemis](https://activemq.apache.org/components/artemis/)** | JMS messaging |
| **[Apache Pulsar](https://pulsar.apache.org/)** | Multi-tenant messaging + streaming |
| **[NATS Java client](https://github.com/nats-io/nats.java)** | Lightweight messaging |

### 13.11 — Caching

| Library | What It Does |
|---------|--------------|
| **[Caffeine](https://github.com/ben-manes/caffeine)** | Best in-process cache (replaces Guava cache) |
| **[Ehcache](https://www.ehcache.org/)** | Long-running general-purpose cache |
| **[Hazelcast](https://hazelcast.com/)** | Distributed in-memory data grid |
| **[Infinispan](https://infinispan.org/)** | Distributed cache (Red Hat) |
| **[Redis (via Lettuce / Jedis / Redisson)](https://redis.io/docs/clients/java/)** | External cache + data structures |

### 13.12 — Resilience & Circuit Breakers

| Library | What It Does |
|---------|--------------|
| **[Resilience4j](https://resilience4j.readme.io/)** | Modern circuit breaker, rate limiter, retry, bulkhead |
| **[Failsafe](https://failsafe.dev/)** | Lightweight retry/circuit-breaker |
| **[Hystrix (Netflix)](https://github.com/Netflix/Hystrix)** | Legacy — replaced by Resilience4j |

### 13.13 — Security

| Library | What It Does |
|---------|--------------|
| **[Spring Security](https://spring.io/projects/spring-security)** | The standard for Spring apps |
| **[Apache Shiro](https://shiro.apache.org/)** | Spring-Security alternative |
| **[Keycloak (Java client)](https://www.keycloak.org/)** | OIDC / OAuth2 identity provider |
| **[Bouncy Castle](https://www.bouncycastle.org/)** | Cryptography algorithms |
| **[Nimbus JOSE+JWT](https://connect2id.com/products/nimbus-jose-jwt)** | JWT, JWS, JWE |

### 13.14 — HTTP Clients

| Library | What It Does |
|---------|--------------|
| **java.net.http (built-in 11+)** | Modern built-in HTTP client (sync + async) |
| **[OkHttp](https://square.github.io/okhttp/)** | Square's HTTP client (Android default) |
| **[Apache HttpClient 5](https://hc.apache.org/httpcomponents-client-5.4.x/)** | The classic |
| **[Retrofit](https://square.github.io/retrofit/)** | Type-safe REST client |
| **[Spring WebClient](https://docs.spring.io/spring-framework/reference/web/webflux-webclient.html)** | Reactive HTTP client |
| **[Feign / OpenFeign](https://github.com/OpenFeign/feign)** | Declarative HTTP client |

### 13.15 — Templating

| Library | What It Does |
|---------|--------------|
| **[Thymeleaf](https://www.thymeleaf.org/)** | Spring's default server-side template engine |
| **[FreeMarker](https://freemarker.apache.org/)** | Apache template engine |
| **[Velocity](https://velocity.apache.org/)** | Older Apache engine |
| **[Pebble](https://pebbletemplates.io/)** | Twig-inspired |
| **[Mustache](https://github.com/spullara/mustache.java)** | Logic-less |
| **[JTE](https://jte.gg/)** | Modern compiled-template engine |

### 13.16 — GraphQL & API

| Library | What It Does |
|---------|--------------|
| **[Spring for GraphQL](https://spring.io/projects/spring-graphql)** | First-party GraphQL |
| **[Netflix DGS](https://netflix.github.io/dgs/)** | Schema-first GraphQL |
| **[graphql-java](https://www.graphql-java.com/)** | The Java GraphQL implementation |
| **[springdoc-openapi](https://springdoc.org/)** | OpenAPI / Swagger UI for Spring Boot |
| **[gRPC-Java](https://grpc.io/docs/languages/java/)** | gRPC RPC |

### 13.17 — Search

| Library | What It Does |
|---------|--------------|
| **[Elasticsearch Java client](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/index.html)** | Elasticsearch search |
| **[OpenSearch Java client](https://opensearch.org/docs/latest/clients/java/)** | OpenSearch (AWS fork of ES) |
| **[Apache Lucene](https://lucene.apache.org/)** | The search-engine library underneath ES |
| **[Hibernate Search](https://hibernate.org/search/)** | Index JPA entities to Lucene/ES |

### 13.18 — Big Data, Streaming & Analytics

| Library | What It Does |
|---------|--------------|
| **[Apache Spark](https://spark.apache.org/)** | Distributed big-data processing |
| **[Apache Flink](https://flink.apache.org/)** | Stream + batch processing |
| **[Apache Kafka Streams](https://kafka.apache.org/documentation/streams/)** | Stream processing on Kafka |
| **[Apache Beam](https://beam.apache.org/)** | Unified batch + streaming model |
| **[Apache Storm](https://storm.apache.org/)** | Real-time computation |
| **[Hadoop](https://hadoop.apache.org/)** | Distributed storage + compute (HDFS / MapReduce / YARN) |
| **[Apache Druid](https://druid.apache.org/)** | OLAP database |
| **[Trino / Presto](https://trino.io/)** | Distributed SQL query engine |

### 13.19 — AI / ML / LLMs (the 2026 frontier)

| Library | What It Does |
|---------|--------------|
| **[Spring AI](https://spring.io/projects/spring-ai)** | Spring's official LLM / embeddings / RAG / vector DB framework |
| **[LangChain4j](https://github.com/langchain4j/langchain4j)** | Java port of LangChain — LLMs, RAG, agents |
| **[Anthropic Java SDK](https://docs.anthropic.com/en/api/client-sdks)** | Official Claude SDK |
| **[OpenAI Java SDK](https://github.com/openai/openai-java)** | Official OpenAI SDK |
| **[Deep Java Library (DJL)](https://djl.ai/)** | Native Java deep-learning framework (Amazon) |
| **[Tribuo](https://tribuo.org/)** | Oracle ML library |
| **[Weka](https://www.cs.waikato.ac.nz/ml/weka/)** | Classical ML library |
| **[ND4J](https://deeplearning4j.konduit.ai/nd4j)** | NumPy-style arrays for the JVM |
| **[Deeplearning4j](https://deeplearning4j.konduit.ai/)** | Deep learning on JVM |
| **[Jakarta NLP / Apache OpenNLP](https://opennlp.apache.org/)** | Natural language processing |

### 13.20 — Mobile (Android)

| Library | What It Does |
|---------|--------------|
| **[Android SDK](https://developer.android.com/)** | Official Android dev platform |
| **[Jetpack Compose](https://developer.android.com/compose)** | Modern UI toolkit (Kotlin-first, Java-compatible) |
| **[Retrofit](https://square.github.io/retrofit/)** | REST client |
| **[OkHttp](https://square.github.io/okhttp/)** | HTTP client |
| **[Room](https://developer.android.com/training/data-storage/room)** | SQLite ORM |
| **[Dagger / Hilt](https://dagger.dev/)** | Compile-time DI |
| **[Glide](https://github.com/bumptech/glide)** | Image loading |
| **[Picasso](https://square.github.io/picasso/)** | Image loading (Square) |

### 13.21 — Desktop UI

| Library | What It Does |
|---------|--------------|
| **[JavaFX](https://openjfx.io/)** | Modern desktop UI |
| **[Swing](https://docs.oracle.com/javase/tutorial/uiswing/)** | Classic desktop UI (legacy but still used) |
| **[SWT (Eclipse)](https://www.eclipse.org/swt/)** | Native widgets |

### 13.22 — Game Development

| Library | What It Does |
|---------|--------------|
| **[LibGDX](https://libgdx.com/)** | Cross-platform 2D / 3D framework |
| **[jMonkeyEngine](https://jmonkeyengine.org/)** | 3D game engine |

### 13.23 — Utility Libraries Everyone Uses

| Library | What It Does |
|---------|--------------|
| **[Google Guava](https://github.com/google/guava)** | Collections, caches, primitives, util |
| **[Apache Commons (Lang, IO, Collections, Math, ...)](https://commons.apache.org/)** | The Apache standard utility belt |
| **[Vavr](https://www.vavr.io/)** | Functional Java — `Try`, `Either`, persistent collections |
| **[Eclipse Collections](https://www.eclipse.org/collections/)** | Faster, richer collections |
| **[picocli](https://picocli.info/)** | Best CLI framework for Java |
| **[Joda-Time](https://www.joda.org/joda-time/)** | Legacy date/time (replaced by `java.time`) |
| **[ZeroAllocationHashing](https://github.com/OpenHFT/Zero-Allocation-Hashing)** | Fast, allocation-free hashing |

### 13.24 — Documentation, API Docs & Tools

| Library | What It Does |
|---------|--------------|
| **[Javadoc](https://docs.oracle.com/en/java/javase/21/docs/specs/man/javadoc.html)** | Built-in API documentation |
| **[Asciidoctor](https://asciidoctor.org/)** | Tech documentation (Spring uses it) |
| **[springdoc-openapi](https://springdoc.org/)** | OpenAPI/Swagger UI |

> [!IMPORTANT]
> You don't learn all of these. You **recognize** all of these (so you can read job descriptions). You **deeply learn** maybe 8–12 — the ones your team uses + the foundational set: Spring Boot, Hibernate, Jackson, SLF4J, Mockito, Testcontainers, Lombok (or records), MapStruct, Resilience4j, Caffeine.

---

## Phase 14: Databases, Persistence & Messaging

![Phase](https://img.shields.io/badge/Phase-14%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Talk to databases the right way and pass events between services.

**What this phase is about.** Backends are mostly databases under a thin REST layer. Java's database story is **JDBC** (the spec) → **JPA** (object mapping spec) → **Hibernate** (the dominant JPA implementation) → **Spring Data JPA** (the easy mode on top). You'll also cover **migrations** (Flyway / Liquibase), **transactions**, **N+1 queries** (the #1 JPA performance trap), and **Kafka** (event streaming).

**Why it matters.** Most production bugs are database bugs. Most slow APIs are slow because of N+1 queries. Most distributed systems use Kafka. This phase is where junior backend devs grow up.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | JDBC | The bedrock — `Connection`, `PreparedStatement`, `ResultSet`. You rarely write raw JDBC, but it's underneath everything |
| 2 | Connection Pooling | **HikariCP** — the connection pool used everywhere |
| 3 | JPA / Hibernate | `@Entity`, `@Id`, `@GeneratedValue`, `@OneToMany`, `@ManyToOne`, `@ManyToMany` |
| 4 | Spring Data JPA | `JpaRepository`, derived queries (`findByEmail`), `@Query` |
| 5 | DTOs vs Entities | Never expose entities to the API. Map to DTOs (records or MapStruct) |
| 6 | Transactions | `@Transactional`, propagation, isolation levels, rollback rules |
| 7 | The N+1 Query Problem | The #1 JPA performance trap — fix with `JOIN FETCH`, `EntityGraph`, or `@BatchSize` |
| 8 | Lazy vs Eager Loading | Default lazy. When eager makes sense |
| 9 | jOOQ (alternative) | Type-safe SQL DSL — when JPA fights you |
| 10 | Migrations: Flyway | SQL-file versioned migrations |
| 11 | Migrations: Liquibase | XML/YAML/JSON-based migrations |
| 12 | Caching | `@Cacheable` (Spring), Caffeine, Redis |
| 13 | NoSQL: MongoDB | `MongoTemplate`, Spring Data MongoDB |
| 14 | NoSQL: Redis | Lettuce / Jedis / Redisson — caching, pub/sub, distributed locks |
| 15 | Search: Elasticsearch / OpenSearch | `RestHighLevelClient` / `Java Client` |
| 16 | Messaging: Kafka | Producer, consumer, consumer groups, partitions |
| 17 | Spring Kafka | `@KafkaListener`, `KafkaTemplate`, transactions, retries |
| 18 | Kafka Streams | Stream processing — joins, aggregates, windowing |
| 19 | Dead-Letter Queues | What to do with poison messages |
| 20 | Outbox Pattern | Reliably publish events when committing a DB transaction |
| 21 | Distributed Transactions | Why two-phase commit is rare; saga pattern instead |
| 22 | Testing DBs | Testcontainers + real Postgres/Mongo/Kafka in Docker |

> [!CAUTION]
> The N+1 problem strikes most junior backend devs. If you load 100 users and lazily access `user.getOrders()`, you fire 1 + 100 SQL queries. Fix:
> ```java
> @Query("SELECT u FROM User u JOIN FETCH u.orders WHERE u.active = true")
> List<User> findActiveWithOrders();
> ```

<details>
<summary><strong>Quick Reference: A Spring Data JPA Repository</strong></summary>

```java
public interface UserRepository extends JpaRepository<User, Long> {

    Optional<User> findByEmail(String email);

    List<User> findByActiveTrue();

    @Query("SELECT u FROM User u JOIN FETCH u.orders WHERE u.id = :id")
    Optional<User> findByIdWithOrders(@Param("id") Long id);

    @Modifying
    @Query("UPDATE User u SET u.lastLogin = :now WHERE u.id = :id")
    int touchLastLogin(@Param("id") Long id, @Param("now") Instant now);
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up a Spring Boot app with Postgres + HikariCP + Flyway
- [ ] Define entities with `@OneToMany` / `@ManyToOne` / `@ManyToMany`
- [ ] Write derived queries + a custom `@Query`
- [ ] Detect and fix an N+1 query
- [ ] Wrap a service method in `@Transactional` and explain isolation
- [ ] Produce + consume Kafka messages with Spring Kafka
- [ ] Test all of the above with Testcontainers

</details>

---

## Phase 15: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-15%2F15-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You finished the language and the ecosystem. Now pick a track and ship.

**What this phase is about.** Java opens more doors than almost any language — backend, Android, big data, finance, embedded, AI. This phase maps each track and the cross-cutting skills (Git, SQL, Docker, Kubernetes, cloud) you need everywhere.

### 15.1 — Pick a Specialization

| Track | What You Build | Key Tools |
|-------|---------------|-----------|
| **Backend / Microservices** | REST/GraphQL APIs, event-driven services | Spring Boot, Spring Cloud, Kafka, Postgres, Redis |
| **Android (Java → Kotlin)** | Mobile apps | Android SDK, Jetpack Compose, Retrofit, Room (then move to [Kotlin](kotlin.md)) |
| **Big Data / Data Engineering** | Pipelines, lakes, warehouses | Spark, Flink, Kafka Streams, Beam, Iceberg |
| **Finance / Trading** | Low-latency trading, risk engines | Aeron, Disruptor, Chronicle, JOOQ |
| **Cloud-native / Kubernetes** | Containerized microservices | Quarkus, Spring Native, GraalVM, Helm, Kubernetes |
| **Reactive Systems** | Massively concurrent servers | Project Reactor, RxJava, Vert.x, Akka |
| **AI / LLM Engineer** | LLM-backed services | Spring AI, LangChain4j, Anthropic Java SDK |
| **DevOps / Platform** | CI/CD, infra | GitHub Actions, Jenkins, Terraform, Ansible |
| **Security / Pentest** | Burp extensions, custom tools | Spring Security, Bouncy Castle, OkHttp |
| **Game Dev** | 2D / 3D games | LibGDX, jMonkeyEngine |
| **Embedded** | IoT, robotics | Java ME, Pi4J for Raspberry Pi |
| **Desktop apps** | Cross-platform GUIs | JavaFX, Swing |

### 15.2 — Required Cross-cutting Skills

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every team. Every project. |
| **[SQL](sql.md)** | Every backend. Every data role. |
| **[Docker](docker.md)** | Containerize your Spring Boot app. Standard for deploys. |
| **Kubernetes** | Production orchestration. Pair with Docker syllabus. |
| **CI/CD** (GitHub Actions / Jenkins / GitLab CI) | Auto-test and auto-deploy on every push |
| **Cloud basics** (AWS / GCP / Azure) | Where your code lives in production |
| **Linux command line** | Every Java server runs Linux |

### 15.3 — Deploy Your Java App

| Target | Tool / Approach |
|--------|----------------|
| Fat JAR | `java -jar app.jar` on any server |
| Container | Spring Boot's built-in image plugin → ECR / GHCR / Docker Hub |
| Kubernetes | Deploy via Helm chart, ArgoCD, or kubectl |
| AWS | Elastic Beanstalk, ECS Fargate, EKS, App Runner, Lambda (with native image) |
| GCP | Cloud Run, GKE, App Engine |
| Azure | App Service, AKS, Container Apps |
| Native binary | GraalVM `native-image` — instant startup, lower memory |
| Heroku / Railway / Render | Easy small-scale deploys |

### 15.4 — Suggested Order After This Syllabus

```
Pick a specialization → Git → SQL → Docker → Build & deploy a real project → Repeat
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Comparing strings with `==` | Compares references, not content | Always use `.equals()` or `Objects.equals()` |
| 2 | Catching `Exception` generically | Hides real bugs, swallows things you didn't mean to | Catch specific types |
| 3 | Empty `catch` blocks | Eats errors silently | At minimum, log + rethrow |
| 4 | Using raw types | `List` instead of `List<String>` — loses type safety | Use generics: `List<String>` |
| 5 | Returning `null` instead of `Optional` | Forces callers to remember null checks → NPE | Return `Optional<T>` |
| 6 | Mutable data classes everywhere | Public setters → unpredictable state | Use records or final fields |
| 7 | `synchronized` on `this` or public field | External code can lock you, deadlocks | Private final lock object |
| 8 | Not closing resources | File / socket / DB-connection leaks | Try-with-resources |
| 9 | Using `float`/`double` for money | Imprecise: `0.1 + 0.2 != 0.3` | `BigDecimal` |
| 10 | Field injection (`@Autowired` on fields) | Hides deps, breaks immutability, hurts testing | Constructor injection |
| 11 | N+1 queries | Lazy-loading collections in a loop | `JOIN FETCH` / `@EntityGraph` |
| 12 | Exposing entities directly via REST | Lazy-init exceptions, leaks internals | Map to DTOs (records / MapStruct) |
| 13 | Skipping virtual threads in 2026 | Tuning thread pools when you don't have to | `newVirtualThreadPerTaskExecutor()` for I/O work |
| 14 | Ignoring Java 21+ features | Records / sealed / pattern matching shrink your code | Use them |
| 15 | Manually building strings in loops with `+` | Quadratic — recreates the string every time | `StringBuilder` |
| 16 | `printStackTrace()` instead of logger | No levels, no context, no rotation | SLF4J + Logback with structured logs |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between JDK, JRE, and JVM?**
   - JVM (Java Virtual Machine) executes bytecode. JRE (Java Runtime Environment) = JVM + standard libraries. JDK (Java Development Kit) = JRE + compiler + dev tools. You install the JDK to develop Java.

2. **What are the 8 primitive types?**
   - `byte` (8-bit), `short` (16-bit), `int` (32-bit), `long` (64-bit), `float` (32-bit decimal), `double` (64-bit decimal), `char` (16-bit Unicode), `boolean`.

3. **`==` vs `.equals()`?**
   - `==` compares references (memory addresses). `.equals()` compares content. For primitives, `==` compares values. For all objects, prefer `.equals()`.

4. **Abstract class vs interface?**
   - Abstract class: state + constructors + both abstract & concrete methods, single inheritance. Interface: contracts + default/static methods (Java 8+), multiple inheritance.

5. **What does `final` do?**
   - On variable: cannot reassign. On method: cannot override. On class: cannot subclass. For reference types, `final` only locks the reference, not the object's state.

6. **Why is `String` immutable?**
   - Thread safety, caching (string pool), security (file paths can't be mutated mid-call), and `hashCode()` can be cached.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain the Collections Framework hierarchy.**
   - `Iterable` → `Collection` → `List` (ordered: `ArrayList`, `LinkedList`), `Set` (unique: `HashSet`, `TreeSet`), `Queue` (FIFO: `ArrayDeque`). `Map` (key-value: `HashMap`, `TreeMap`) is separate.

2. **What are generics? What is type erasure?**
   - Compile-time type safety: `List<String>` instead of raw `List`. Erasure means generic types are removed at runtime — `List<String>` and `List<Integer>` are the same `List` class. So no `new T()`, no `instanceof T`.

3. **Stream vs Collection?**
   - Streams are lazy pipelines (operations only run on terminal calls), don't store data, can be parallelized, and are consumed once. Collections are data; streams are operations.

4. **Checked vs unchecked exceptions?**
   - Checked (`IOException`, `SQLException`): must catch or declare with `throws`. Unchecked (`RuntimeException`): not enforced. Use unchecked for programmer errors, checked for recoverable conditions.

5. **How does `HashMap` work internally?**
   - Array of buckets. `hashCode()` selects the bucket. Collisions become a linked list (or balanced tree if length > 8). `equals()` resolves within the bucket. Load factor 0.75 triggers a resize.

6. **What's `Optional` and how to use it?**
   - Wrapper indicating "may or may not have a value." Use `.orElse`, `.orElseThrow`, `.map`, `.ifPresent`. Don't use it for fields or method parameters — only return values.

7. **Records vs Lombok `@Data`?**
   - Records are language-level immutable value classes (Java 16+). Lombok generates code via annotations. Records are simpler when you want immutability; Lombok wins for mutable JPA entities.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What are virtual threads (Java 21) and how do they differ from platform threads?**
   - Platform threads are OS threads — heavy (~1 MB stack), thousands max. Virtual threads are JVM-managed, lightweight (~KB), millions possible. Ideal for I/O-bound tasks. They mount/unmount on platform "carrier" threads automatically. Use `Thread.ofVirtual()` or `Executors.newVirtualThreadPerTaskExecutor()`.

2. **Explain PECS — Producer Extends, Consumer Super.**
   - `<? extends T>`: read-only producer of T. `<? super T>`: write-only consumer of T. Example: `void copy(List<? extends T> src, List<? super T> dst)`. Maximizes flexibility while keeping type safety.

3. **How does Spring DI work internally?**
   - Spring scans for `@Component` classes (component scanning), instantiates beans, stores them in the Application Context (IoC container). When a bean needs a dependency, Spring resolves it by type (and `@Qualifier` for ambiguity) and injects via constructor / setter / field. Default scope is singleton.

4. **What is the Java Memory Model? What does `volatile` do?**
   - The JMM defines how threads see memory writes. Without sync, threads may see stale values due to CPU caching/reordering. `volatile` guarantees visibility (no caching of that variable) and prevents reordering around its access. It does NOT provide atomicity for compound operations — use `AtomicInteger` or `synchronized` for those.

5. **Design a thread-safe in-memory cache with TTL and a max size.**
   - Use `ConcurrentHashMap` for lock-free reads. `computeIfAbsent` for atomic compute-or-load. A `ScheduledExecutorService` evicts expired entries. For LRU eviction, use `LinkedHashMap` with `accessOrder=true` wrapped in `Collections.synchronizedMap`, or pick **Caffeine** for production (size-based + time-based + async refresh).

6. **What is the N+1 query problem and how do you fix it in JPA/Hibernate?**
   - Loading a parent then accessing a `@OneToMany` lazy collection in a loop fires 1 + N queries. Fix: `JOIN FETCH` in JPQL, `@EntityGraph` on the repository, or `@BatchSize`. Detect early with logging — every JPA project should log SQL during development.

7. **Explain GraalVM Native Image trade-offs.**
   - AOT-compiles your Java app to a native binary. **Pros:** instant startup (~ms), lower memory, smaller container. **Cons:** much longer build time, no dynamic class loading, reflection requires explicit hints. Best fit: serverless, CLI tools, microservices on Kubernetes with autoscaling.

</details>

---

## Practice Projects

You don't truly know Java until you've shipped real projects. Each project below builds skills from multiple phases and produces something for your portfolio.

> [!TIP]
> Push every project to GitHub with a proper README, screenshots, run instructions, and (where it makes sense) a deployed live demo. A junior portfolio with 5 polished, deployed projects beats a CS degree with no projects.

### Project 1: CLI Task Manager
![Phase 1-6](https://img.shields.io/badge/After-Phase%201--6-green)

**What you'll build:** Command-line task manager: add / list / complete / delete / filter, persisted to a JSON file (Jackson), with proper exception handling. CLI built with Picocli.

**Skills practiced:** Variables, control flow, OOP, Collections, file I/O, JSON.

**Stretch:** Subcommands, due-date reminders, export to CSV.

---

### Project 2: Library Management System (OOP Showcase)
![Phase 4-6](https://img.shields.io/badge/After-Phase%204--6-green)

**What you'll build:** OOP-driven system — `Book`, `Member`, `Loan` records, `Library` service. Borrowing rules (max 3 books, late fees), search, sort by `Comparator`. Persist to file.

**Skills practiced:** Records, sealed types, interfaces, polymorphism, Collections, `Comparable`/`Comparator`.

**Stretch:** Switch from file to SQLite via JDBC.

---

### Project 3: Streams + NIO File Analyzer
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-yellow)

**What you'll build:** Tool that walks a directory tree, counts word frequencies across all `.txt` / `.md` / `.log` files, finds top-N words per file and overall, outputs a summary report — all using NIO.2 + Streams + lambdas.

**Skills practiced:** `Files.walk`, `Files.lines`, `flatMap`, `Collectors.groupingBy`, `Optional`, custom comparators.

**Stretch:** Watch the directory for changes (`WatchService`) and update in real time.

---

### Project 4: Concurrent Web Scraper / URL Health Checker
![Phase 10](https://img.shields.io/badge/After-Phase%2010-yellow)

**What you'll build:** Given a list of URLs, fetch them concurrently with virtual threads, measure response times, detect failures, retry with exponential backoff, generate a JSON + Markdown report. Compare runtimes with platform threads vs virtual threads.

**Skills practiced:** Virtual threads, `ExecutorService`, `CompletableFuture`, retry logic, structured concurrency.

**Stretch:** Add a TUI dashboard, scheduled re-runs.

---

### Project 5: Production Spring Boot REST API + JWT
![Phase 11-12](https://img.shields.io/badge/After-Phase%2011--12-red)

**What you'll build:** Full CRUD API for a bookstore or task service. Spring Boot + Spring Data JPA + PostgreSQL + Bean Validation + global error handler + JWT auth (Spring Security). 80%+ JUnit + Mockito coverage. JaCoCo report. springdoc Swagger UI. GitHub Actions CI. Dockerfile. Deployed to a public URL.

**Skills practiced:** Spring Boot, JPA, Spring Security, JWT, Bean Validation, Mockito, Testcontainers, Maven/Gradle, Docker, CI/CD.

**Stretch:** Switch to Postgres via Testcontainers in CI. Add Liquibase migrations. Expose Prometheus metrics.

---

### Project 6: Event-Driven Microservices (Kafka)
![Phase 13-14](https://img.shields.io/badge/After-Phase%2013--14-red)

**What you'll build:** 3 Spring Boot services: `OrderService`, `PaymentService`, `InventoryService`. Communicate via Kafka topics. Use the **Outbox pattern** for reliable event publishing. Each service has its own DB. Add Resilience4j circuit breakers. Distributed tracing via OpenTelemetry → Jaeger.

**Skills practiced:** Spring Cloud, Spring Kafka, Resilience4j, OpenTelemetry, microservices, the outbox pattern, eventual consistency.

**Stretch:** Saga orchestration. Kafka Streams aggregation service. Helm chart for Kubernetes deployment.

---

### Project 7: GraphQL API + Reactive WebFlux
![Phase 12-13](https://img.shields.io/badge/After-Phase%2012--13-red)

**What you'll build:** A GraphQL API (Spring for GraphQL) over a reactive WebFlux + R2DBC stack. Schema-first design. Handle 10k+ concurrent connections. Subscriptions for real-time updates.

**Skills practiced:** Reactive programming (Project Reactor), GraphQL, WebFlux, R2DBC, subscriptions.

**Stretch:** Hot-reload schema. DataLoader for batched queries.

---

### Project 8: AI-Powered Service with Spring AI / LangChain4j (Capstone)
![Phase 14-15](https://img.shields.io/badge/After-Phase%2014--15-red)

**What you'll build:** Your graduation project. A Spring Boot service that ingests PDFs (Apache PDFBox / Tika), chunks + embeds them (Voyage / OpenAI), stores vectors in **pgvector** (Postgres) or Chroma, exposes a REST endpoint that answers questions via **Claude** (Anthropic Java SDK or LangChain4j) with **streaming** + **prompt caching**. Auth via Spring Security + Keycloak. Full Testcontainers integration tests. Deployed to Vercel / Render / Fly.io / AWS.

**Skills practiced:** Everything from all 15 phases — Spring Boot, JPA, Spring Security, virtual threads, AI SDKs, RAG, vector DBs, streaming, deployment. **This is portfolio gold for any 2026 Java backend interview.**

**Stretch:** Multi-turn conversational memory. Tool use (LLM calls your REST endpoints). Agent-style workflows.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Oracle Java Documentation](https://docs.oracle.com/en/java/javase/21/docs/api/) | Official API docs for every class in the JDK |
| [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/) | Official guides: OOP, collections, concurrency, networking |
| [Spring Boot Reference](https://docs.spring.io/spring-boot/index.html) | Official Spring Boot documentation |
| [Spring Initializr](https://start.spring.io) | Generate Spring Boot projects in seconds |
| [Baeldung](https://www.baeldung.com/) | The encyclopedia of Java + Spring tutorials |
| [Java Almanac](https://javaalmanac.io/) | What's new in every Java version |
| [JEP Index](https://openjdk.org/jeps/0) | Every Java Enhancement Proposal — see what landed in each version |

### Books

| Book | Why Read |
|------|---------|
| **Effective Java (Joshua Bloch)** | The single best Java book ever written. Every Java dev should read it once a year |
| **Java: The Complete Reference (Herbert Schildt)** | The thick reference — everything in one book |
| **Modern Java in Action (Urma, Fusco, Mycroft)** | Streams, lambdas, modules, async — modern features deeply |
| **Java Concurrency in Practice (Goetz)** | The concurrency bible — still essential |
| **Spring in Action (Walls)** | Spring Boot from beginner to advanced |
| **Cloud Native Spring in Action (Vitale)** | Modern Spring Boot, Kubernetes, GraalVM |
| **Designing Data-Intensive Applications (Kleppmann)** | Not Java-specific but essential for senior backend devs |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Codecademy — Learn Java](https://www.codecademy.com/learn/learn-java) | Interactive, in-browser |
| [JetBrains Academy — Java Basics](https://www.jetbrains.com/academy/) | Project-based, runs inside IntelliJ |
| [MOOC.fi — Java Programming I & II](https://java-programming.mooc.fi/) | University of Helsinki — exceptional, free |
| [freeCodeCamp — Java Certification](https://www.freecodecamp.org/learn/) | Free with hands-on projects |
| [HackerRank — Java](https://www.hackerrank.com/domains/java) | Structured challenges |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Coding with John](https://www.youtube.com/@CodingWithJohn) | Clear, concise per-topic videos |
| [Amigoscode](https://www.youtube.com/@amigoscode) | Long-form Java + Spring Boot courses |
| [Java Brains](https://www.youtube.com/@Java.Brains) | Excellent Spring + Java EE depth |
| [Marco Codes](https://www.youtube.com/@MarcoCodes) | Modern Spring Boot, IntelliJ tips |
| [Dan Vega](https://www.youtube.com/@DanVega) | Spring Boot, modern Java features |
| [Defog Tech](https://www.youtube.com/@DefogTech) | System design + Java internals |
| [freeCodeCamp — Java Full Course](https://www.youtube.com/@freecodecamp) | 12-hour comprehensive course |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Java](https://roadmap.sh/java) | Interactive Java roadmap |
| [roadmap.sh — Spring Boot](https://roadmap.sh/spring-boot) | Dedicated Spring Boot roadmap |
| [roadmap.sh — Backend](https://roadmap.sh/backend) | Where Java fits in backend |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [IntelliJ IDEA](https://www.jetbrains.com/idea/) | The best Java IDE. Community Edition is free |
| [VS Code Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack) | Lightweight alternative |
| [Eclipse](https://www.eclipse.org/downloads/) | Classic, still used at large enterprises |
| [SDKMAN!](https://sdkman.io/) | Manage multiple JDK versions |
| [GraalVM](https://www.graalvm.org/) | Polyglot + native-image |
| [Postman](https://www.postman.com/) | Test REST APIs |
| [JMeter](https://jmeter.apache.org/) | Load testing |
| [VisualVM](https://visualvm.github.io/) | JVM monitoring + profiling |
| [JProfiler](https://www.ej-technologies.com/products/jprofiler/overview.html) | Commercial profiler |
| [async-profiler](https://github.com/async-profiler/async-profiler) | Low-overhead profiler — flame graphs |

### Cheat Sheets & Quick References

| Resource | What It Covers |
|----------|---------------|
| [Java Cheat Sheet (Programming with Mosh)](https://programmingwithmosh.com/java/java-cheat-sheet/) | Syntax basics, OOP, collections |
| [Spring Boot Annotations Cheat Sheet](https://www.baeldung.com/spring-boot-annotations) | Every Spring annotation explained |
| [Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) | Maven basics |
| [Gradle User Guide](https://docs.gradle.org/current/userguide/userguide.html) | Gradle reference |
| [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/) | Comprehensive JUnit reference |
| [Java Language Updates (Oracle)](https://docs.oracle.com/en/java/javase/21/language/) | What's new per version |

### Podcasts & Newsletters

| Resource | Format |
|----------|--------|
| [Inside Java](https://inside.java/podcast/) | Official Java podcast — JEPs, language design |
| [Foojay](https://foojay.io/) | Friends of OpenJDK — Java news + articles |
| [Java Weekly (Baeldung)](https://www.baeldung.com/category/java-weekly/) | Weekly Java newsletter |
| [Spring Tips (Josh Long)](https://www.youtube.com/playlist?list=PLgGXSWYM2FpMsmYHRWA8AxAIp4PT1kqdU) | Modern Spring topics, weekly |

### AI / LLM SDK Docs (the 2026 frontier)

| Resource | What It Is |
|----------|-----------|
| [Spring AI](https://docs.spring.io/spring-ai/reference/) | Official Spring AI reference |
| [LangChain4j](https://docs.langchain4j.dev/) | Java port of LangChain |
| [Anthropic Java SDK](https://docs.anthropic.com/en/api/client-sdks) | Claude SDK |
| [OpenAI Java SDK](https://github.com/openai/openai-java) | GPT SDK |

---

[Back to Main Syllabus](../README.md)

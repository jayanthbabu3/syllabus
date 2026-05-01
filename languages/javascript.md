# JavaScript Syllabus

A complete, structured learning path for JavaScript — your one-stop guide from absolute zero to senior engineer. Whether you have never written a line of code, or you already ship JavaScript at work and want to fill gaps, this syllabus walks you through every concept in the right order, explains *why* each matters, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 16 Phases](https://img.shields.io/badge/Topics-16%20Phases-orange)

---

## Table of Contents

- [What is JavaScript?](#what-is-javascript)
- [Why Learn JavaScript in 2026?](#why-learn-javascript-in-2026)
- [How JavaScript Runs](#how-javascript-runs)
- [Who This Syllabus Is For](#who-this-syllabus-is-for)
- [Learning Paths](#learning-paths)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Data Types & Type Conversion](#phase-2-data-types--type-conversion)
- [Phase 3: Operators & Control Flow](#phase-3-operators--control-flow)
- [Phase 4: Functions](#phase-4-functions)
- [Phase 5: Arrays & Objects](#phase-5-arrays--objects)
- [Phase 6: Strings & Regular Expressions](#phase-6-strings--regular-expressions)
- [Phase 7: DOM Manipulation](#phase-7-dom-manipulation)
- [Phase 8: Asynchronous JavaScript](#phase-8-asynchronous-javascript)
- [Phase 9: ES6+ Modern JavaScript](#phase-9-es6-modern-javascript)
- [Phase 10: Tooling & Package Management](#phase-10-tooling--package-management)
- [Phase 11: Error Handling & Debugging](#phase-11-error-handling--debugging)
- [Phase 12: Testing in JavaScript](#phase-12-testing-in-javascript)
- [Phase 13: Advanced Concepts & Design Patterns](#phase-13-advanced-concepts--design-patterns)
- [Phase 14: Browser APIs, Storage & Real-Time](#phase-14-browser-apis-storage--real-time)
- [Phase 15: Performance & Security](#phase-15-performance--security)
- [Phase 16: What's Next? (TypeScript, Frameworks, Node, Deploy)](#phase-16-whats-next-typescript-frameworks-node-deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is JavaScript?

**JavaScript is the programming language that makes web pages interactive.** Click a button, see a popup. Type in a search box, watch suggestions appear. Scroll a feed, get more posts loaded. All of that is JavaScript.

Originally created by **Brendan Eich at Netscape in 1995** in just 10 days, JavaScript was meant to add small bits of behavior to otherwise static HTML pages. Three decades later it has grown into one of the most widely used programming languages in the world — running not only inside every browser, but also on servers (Node.js, Deno, Bun), mobile apps (React Native), desktop apps (Electron — the engine behind VS Code, Slack, Discord), embedded devices, robotics, and even rockets at SpaceX.

In simple words:

- **HTML** is the *structure* of a web page (the skeleton).
- **CSS** is the *style* of a web page (the look).
- **JavaScript** is the *behavior* of a web page (the brain).

> [!IMPORTANT]
> JavaScript is **not** Java. They share a name for marketing reasons in the 90s and nothing else. Java is to JavaScript what a car is to a carpet.

The official name of the language is **ECMAScript**, standardized by the TC39 committee. New features land every year (ES2015, ES2016, ... ES2025). When people say "modern JavaScript" they mean ES2015 (ES6) and everything that came after.

---

## Why Learn JavaScript in 2026?

| Reason | What It Means |
|--------|---------------|
| **The only language native to the browser** | If you want to build websites, web apps, or browser-based tools, you have no choice — JavaScript is the only language browsers natively run. |
| **Full-stack with one language** | Frontend (React/Vue/Angular), backend (Node/Express/Nest), mobile (React Native/Expo), desktop (Electron/Tauri), CLI, scripts — all in one language. |
| **Largest ecosystem on Earth** | npm has over **3 million packages** — more than any other package registry. Whatever you need to build, someone wrote a library for it. |
| **Most-loved & most-used (StackOverflow)** | JavaScript has topped the "most used language" list for 11 years straight. Huge community, endless tutorials, instant answers. |
| **Highest demand on job boards** | More open roles for JS / TypeScript / React / Node than any other stack. Junior, mid, senior — every level is hiring. |
| **AI tooling is built on it** | Vercel AI SDK, LangChain.js, OpenAI SDK, Anthropic SDK — building AI apps in 2026 means JavaScript or Python. |
| **Pays well** | Average frontend / full-stack JS salary in 2026: **$95k–$180k** (US), **₹8L–₹40L** (India) depending on experience. |

---

## How JavaScript Runs

Understanding *where* JavaScript runs makes the rest of this syllabus easier to follow.

```
                   ┌──────────────────────────────┐
                   │     Your JavaScript code     │
                   └──────────────┬───────────────┘
                                  │
            ┌─────────────────────┼─────────────────────┐
            ▼                     ▼                     ▼
     ┌────────────┐        ┌────────────┐        ┌────────────┐
     │  Browser   │        │  Server    │        │  Mobile /  │
     │ (Chrome,   │        │ (Node.js,  │        │  Desktop   │
     │  Firefox,  │        │  Deno,     │        │  (RN,      │
     │  Safari)   │        │  Bun)      │        │  Electron) │
     └────────────┘        └────────────┘        └────────────┘
            │                     │                     │
            ▼                     ▼                     ▼
        DOM, fetch,          File system,         Native APIs,
        localStorage,        databases,           camera, GPS,
        Canvas, etc.         HTTP servers         notifications
```

All of these run JavaScript through an engine — **V8** (Chrome, Node, Edge), **SpiderMonkey** (Firefox), **JavaScriptCore** (Safari, Bun). The engine takes your code and turns it into machine instructions the CPU can execute.

---

## Who This Syllabus Is For

| You Are | What You Get |
|---------|--------------|
| **Absolute beginner** — never coded before | Start at Phase 1. Each concept is explained from scratch with examples. No prior knowledge assumed beyond "I can use a computer". |
| **Coming from another language** (Python/Java/C#) | Skim Phase 1–4, focus on Phase 5 (objects/arrays differ), Phase 8 (async is unique), Phase 13 (prototypes & `this`). |
| **Self-taught dev with gaps** | Use the [Common Mistakes](#common-mistakes) section as a self-audit, then re-do whichever phase you flunk. |
| **Bootcamp grad / Junior dev** | Phases 9, 12, 13, 15 are usually weak spots. Jump there first, then fill the rest. |
| **Mid / Senior dev preparing for interviews** | Phase 13 (advanced) + [Interview Questions](#interview-questions) + Phase 16 (what's next). |
| **Frontend dev moving full-stack** | Finish through Phase 15, then Phase 16's Node section. Pair with the [Node.js Syllabus](nodejs.md). |

---

## Learning Paths

Pick the path that matches your goal. Each path tells you which phases to do, in what order, and roughly how long it takes.

### Path A — Zero to First Job (14–18 weeks)
Fresher with no coding background, target: junior frontend role.

```
Phase 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9 → 10 → 11 → 12 → 15 → Phase 16 (TypeScript + React)
```
- Build all 8 [Practice Projects](#practice-projects).
- Skip Phase 13 (advanced) until after first 2 projects, come back to it.
- After Phase 9, start the [React Syllabus](react.md) in parallel.

### Path B — Interview Prep (4–6 weeks)
Already know JS basics, need to crack interviews.

```
Phase 2 → 5 → 8 → 9 → 13 → 15 → Common Mistakes → Interview Questions
```
- Drill all advanced + interview questions.
- Practice 2 LeetCode (Easy → Medium) per day in JavaScript.
- Re-implement: `Promise.all`, `debounce`, `throttle`, `curry`, `bind`, deep clone from scratch.

### Path C — Modernize Old Skills (3–5 weeks)
You wrote jQuery / ES5 code 5+ years ago and never caught up.

```
Phase 9 → 8 → 10 → 13 → 14 → 16
```
- Focus on async/await, modules, optional chaining, `structuredClone`, modern build tools (Vite over Webpack).

### Path D — Full-Stack JS (16–20 weeks)
Goal: build & ship full apps end-to-end.

```
All 16 phases → Node.js Syllabus → SQL Syllabus → React Syllabus → Docker Syllabus
```

---

## Prerequisites

> [!NOTE]
> You should know **HTML and CSS** before learning JavaScript. If you haven't already, complete the [HTML Syllabus](html.md) and [CSS Syllabus](css.md) first. JavaScript without HTML/CSS is like a brain without a body — nothing for it to control.

- **HTML** fundamentals (elements, attributes, forms, semantic tags)
- **CSS** basics (selectors, box model, Flexbox, Grid)
- A code editor — [VS Code](https://code.visualstudio.com/) recommended (free, best JS support)
- A modern browser — [Chrome](https://www.google.com/chrome/) recommended for the best DevTools
- Comfortable using the terminal / command line (basic `cd`, `ls`, running commands)
- A [GitHub account](https://github.com/) to store and share your code

---

## How to Use This Syllabus

1. **Don't skip phases.** Each one builds on the last. If Phase 5 (Arrays/Objects) is shaky, Phase 8 (Async) will feel impossible.
2. **Type the code yourself.** Copy-pasting from tutorials gives the illusion of learning. Type every example by hand.
3. **Build the project** at the end of each phase block before moving on. Reading is not the same as doing.
4. **Use the Learning Checklist** in each phase to self-check before moving forward.
5. **When stuck, read the error.** Then search the exact error message + "MDN" or "stack overflow". 90% of bugs have already been solved by someone else.
6. **Commit your code to GitHub** from day one. Future you (and future employers) will thank you.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. There is no rush — depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F16-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what JavaScript is and write your first lines of code.

**What this phase is about.** Before you can write JavaScript, you need to know *where* it runs, *how* to make it run, and *how* to read the output. This phase sets up your tools (browser DevTools, code editor), introduces variables — the fundamental building block of every program — and gets you comfortable with the JavaScript console as a scratchpad. Data types get a brief intro here; the next phase covers them in depth.

**Why it matters.** Every concept in the next 15 phases assumes you can declare a variable and use the console. Skipping or skimming this phase guarantees pain later. Spend the time now to make `let`, `const`, and the dev console feel automatic.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is JavaScript | The programming language of the web — makes pages interactive, runs in browsers and servers |
| 2 | Where JS Runs | Browser (client-side), Node.js (server-side), Deno, Bun — JavaScript is everywhere |
| 3 | Developer Console | Open Chrome DevTools (F12), use `console.log()`, `console.error()`, `console.table()` to see output |
| 4 | Adding JS to HTML | Inline (`onclick`), internal (`<script>`), external (`.js` file) — and why external is best |
| 5 | Code Structure | Statements, semicolons, comments (`//` and `/* */`), and `"use strict"` mode |
| 6 | Variables | `var` vs `let` vs `const` — block scope, hoisting, and why `const` should be your default |
| 7 | Data Types (Preview) | 8 types total — full deep dive in Phase 2 |
| 8 | Your First Program | Write, run, and debug a tiny script that prints to the console and the page |

> [!TIP]
> Use `const` by default. Only use `let` when you need to reassign. Never use `var` — it has confusing scoping rules that cause bugs.

<details>
<summary><strong>Quick Reference: var vs let vs const</strong></summary>

| Feature | `var` | `let` | `const` |
|---------|:-----:|:-----:|:-------:|
| Scope | Function | Block | Block |
| Hoisted | Yes (as `undefined`) | Yes (but can't access) | Yes (but can't access) |
| Reassign | Yes | Yes | No |
| Redeclare | Yes | No | No |
| Use in 2026? | Avoid | When you need to reassign | Default choice |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Open the browser console and run JavaScript directly
- [ ] Declare variables with `let` and `const` and explain the difference
- [ ] Link an external `.js` file to an HTML page
- [ ] Write and run your first 5-line program

</details>

---

## Phase 2: Data Types & Type Conversion

![Phase](https://img.shields.io/badge/Phase-2%2F16-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> The foundation of everything: master JavaScript's 8 data types before you write another line.

**What this phase is about.** Every value in JavaScript belongs to one of **8 types**: 7 *primitive* types (`string`, `number`, `bigint`, `boolean`, `undefined`, `symbol`, `null`) and 1 *reference* type (`object` — which includes arrays, functions, dates, regex, and everything else). The difference between primitives (compared and copied **by value**) and references (compared and copied **by reference**) is the single most important mental model in the language. This phase also covers explicit conversion (`Number("5")`), implicit coercion (`"5" * 2`), the gotchas of `NaN` and `null`, and how to safely check what type a value is at runtime.

**Why it matters.** Almost every confusing JavaScript bug — "why is `0.1 + 0.2 !== 0.3`?", "why is `typeof null === 'object'`?", "why is `[] == false`?", "why does mutating one array change another?" — traces back to a misunderstanding of types. Get this phase right and 80% of weird JS bugs disappear before you write them.

### 2.1 — The 8 Data Types

| Type | Category | Example | What It Holds |
|------|----------|---------|---------------|
| `string` | Primitive | `"hello"`, `'a'`, `` `${name}` `` | Text |
| `number` | Primitive | `42`, `3.14`, `-7`, `Infinity`, `NaN` | All numbers (integers + decimals) — IEEE 754 double |
| `bigint` | Primitive | `9007199254740993n` | Integers larger than `Number.MAX_SAFE_INTEGER` |
| `boolean` | Primitive | `true`, `false` | Yes / no |
| `undefined` | Primitive | `undefined` | A variable declared but not assigned |
| `null` | Primitive | `null` | Intentional "no value" set by the developer |
| `symbol` | Primitive | `Symbol("id")` | Unique, immutable identifier (often used as object keys) |
| `object` | Reference | `{}`, `[]`, `function(){}`, `new Date()` | Everything that isn't a primitive |

### 2.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The 8 Types Overview | The mental model: 7 primitives + objects |
| 2 | Strings | Quotes (`'`, `"`, backticks), escape sequences (`\n`, `\t`, `\\`), `.length`, immutability |
| 3 | Template Literals | `` `Hello, ${name}!` `` — interpolation, multi-line, tagged templates |
| 4 | Numbers | Integers, floats, scientific (`1e6`), hex (`0xff`), binary (`0b101`), octal (`0o17`), separators (`1_000_000`) |
| 5 | Number Precision | Why `0.1 + 0.2 === 0.30000000000000004`. `Number.EPSILON`, `toFixed()`, when to use BigInt |
| 6 | Special Numbers | `Infinity`, `-Infinity`, `NaN`. `Number.isNaN()` vs the broken global `isNaN()` |
| 7 | BigInt | `123n` — arbitrary precision integers for IDs, big counters, crypto. Can't mix with Number |
| 8 | Booleans | `true` / `false` and the **6 falsy values**: `false`, `0`, `""`, `null`, `undefined`, `NaN` |
| 9 | `undefined` vs `null` | When each appears, why they're different, why `typeof null` is `"object"` (a 1995 bug) |
| 10 | Symbols | `Symbol("id")` — unique IDs that never collide, well-known symbols (`Symbol.iterator`) |
| 11 | Objects (Reference Type) | Why `{} === {}` is `false` — objects are compared by *reference*, not value |
| 12 | Primitive vs Reference | Copy by value (primitives) vs copy by reference (objects) — the bug behind half of all JS confusion |
| 13 | Type Checking | `typeof`, `instanceof`, `Array.isArray()`, `Object.prototype.toString.call(x)` |
| 14 | Explicit Conversion | `String(x)`, `Number(x)`, `Boolean(x)`, `parseInt(x, 10)`, `parseFloat(x)` |
| 15 | Implicit Coercion | `"5" + 1`, `"5" - 1`, `+"42"`, `!!value` — when JavaScript silently converts types |
| 16 | Date Type | `new Date()` — creating, formatting, math. Why it's painful and what to use instead (`Temporal`, `date-fns`, `dayjs`) |

### 2.3 — Primitives vs References (The Core Mental Model)

```javascript
// PRIMITIVES — copied by VALUE
let a = 5;
let b = a;       // b gets a copy of 5
a = 10;
console.log(b);  // 5 (unchanged — they were always separate)

// OBJECTS — copied by REFERENCE
let user1 = { name: "Alice" };
let user2 = user1;       // user2 points to the SAME object
user1.name = "Bob";
console.log(user2.name); // "Bob" (same object!)

// To actually copy an object: shallow or deep
const shallow = { ...user1 };           // shallow copy (top level only)
const deep    = structuredClone(user1); // deep copy (entire tree)
```

> [!IMPORTANT]
> The **#1 bug for new JS developers** is mutating an object they thought they had copied. If you ever write `array2 = array1` and modify one, both change — they're the same array. Always copy explicitly with `[...arr]`, `{...obj}`, or `structuredClone()`.

### 2.4 — Type Conversion vs Coercion

```javascript
// EXPLICIT (you do it on purpose)
Number("42");        // 42
String(42);          // "42"
Boolean(0);          // false
parseInt("100px", 10); // 100
parseFloat("3.14kg");  // 3.14

// IMPLICIT / COERCION (JavaScript does it silently)
"5" + 1     // "51"   — + with a string concatenates
"5" - 1     // 4      — - only works on numbers, so "5" → 5
+"42"       // 42     — unary + converts to number
!!"hello"   // true   — !! converts to boolean
1 == "1"    // true   — == coerces; ALWAYS use ===
[] + []     // ""     — both arrays coerce to empty strings
[] + {}     // "[object Object]"
```

> [!CAUTION]
> Implicit coercion is JavaScript's most criticized feature. The cure: **always use `===` instead of `==`**, and **convert types explicitly** when in doubt. Tools like ESLint with the `eqeqeq` rule will catch all `==` usage automatically.

### 2.5 — Type Checking Cheatsheet

| Check | Code | Notes |
|-------|------|-------|
| Is it a string? | `typeof x === "string"` | Works for all strings |
| Is it a number? | `typeof x === "number"` | Includes `NaN` (use `Number.isFinite(x)` to exclude) |
| Is it `NaN`? | `Number.isNaN(x)` | NEVER use the global `isNaN()` — it coerces |
| Is it an array? | `Array.isArray(x)` | `typeof []` is `"object"`, so this is the only safe check |
| Is it an object (not null/array)? | `typeof x === "object" && x !== null && !Array.isArray(x)` | The unfortunate truth |
| Is it `null`? | `x === null` | `typeof null === "object"` — historical bug |
| Is it a class instance? | `x instanceof MyClass` | Walks the prototype chain |
| What kind of object? | `Object.prototype.toString.call(x)` | Returns `"[object Date]"`, `"[object RegExp]"`, etc. |

<details>
<summary><strong>Quick Reference: Falsy & Truthy</strong></summary>

```javascript
// The 6 falsy values — memorize these
false
0          // and -0, 0n
""         // empty string (single, double, or backtick)
null
undefined
NaN

// Everything else is truthy, including these surprises:
"0"        // truthy (non-empty string)
"false"    // truthy (non-empty string)
[]         // truthy (object reference, even if empty)
{}         // truthy (object reference, even if empty)
function(){}  // truthy (object reference)
```

</details>

<details>
<summary><strong>Quick Reference: Number Gotchas</strong></summary>

```javascript
0.1 + 0.2 === 0.3              // false — IEEE 754 floats
0.1 + 0.2                      // 0.30000000000000004
(0.1 + 0.2).toFixed(2) === "0.30"  // true (string!)
Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON  // true — proper compare

Number.MAX_SAFE_INTEGER        // 9007199254740991  (2^53 - 1)
Number.MAX_SAFE_INTEGER + 1    // 9007199254740992
Number.MAX_SAFE_INTEGER + 2    // 9007199254740992 — same! Lost precision
9007199254740993n              // BigInt — arbitrary precision

typeof NaN                     // "number" (yes, really)
NaN === NaN                    // false (NaN is not equal to itself)
Number.isNaN(NaN)              // true — the right way to check
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] List all 7 primitive types and the 1 reference type from memory
- [ ] Explain the difference between primitives and references with a code example
- [ ] List all 6 falsy values from memory
- [ ] Explain why `0.1 + 0.2 !== 0.3` and how to safely compare floats
- [ ] Use `typeof`, `instanceof`, and `Array.isArray()` correctly
- [ ] Convert a string `"42abc"` to the number `42` using both `Number()` and `parseInt()` — explain why they differ
- [ ] Predict the output of `"5" + 1`, `"5" - 1`, `[] + []`, `[] + {}` without running them

</details>

---

## Phase 3: Operators & Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F16-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions in code and repeat actions with loops.

**What this phase is about.** Programs do two basic things: make decisions ("if the user clicked, show the menu") and repeat work ("for every item in the cart, calculate tax"). This phase teaches the operators (math, comparison, logical) that produce the values your decisions are based on, and the control-flow constructs (`if`, `switch`, `for`, `while`) that act on them.

**Why it matters.** Every line of useful code is some combination of "compute a value" and "decide what to do with it." Once these are reflexive, you can read any JavaScript codebase and understand the *flow* even if you don't know the libraries yet.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Arithmetic Operators | `+`, `-`, `*`, `/`, `%` (remainder), `**` (exponentiation), `++`, `--` |
| 2 | String Concatenation | `+` joins strings, template literals use backticks: `` `Hello ${name}` `` |
| 3 | Comparison Operators | `==` vs `===` (loose vs strict), `!=` vs `!==`, `<`, `>`, `<=`, `>=` |
| 4 | Logical Operators | `&&` (AND), `\|\|` (OR), `!` (NOT) — combine conditions, short-circuit evaluation |
| 5 | Nullish Coalescing | `??` — returns the right side only if the left is `null` or `undefined` (not `0` or `""`) |
| 6 | Operator Precedence | Why `1 + 2 * 3` is `7`, not `9`. Use parentheses when in doubt |
| 7 | Conditional Statements | `if`, `else if`, `else`, ternary operator (`condition ? yes : no`) |
| 8 | Switch Statement | Cleaner alternative to multiple `if/else` when comparing one value against many options |
| 9 | Loops | `for`, `while`, `do...while` — repeat code. `break` to exit, `continue` to skip |
| 10 | `for...of` and `for...in` | `for...of` iterates values (arrays), `for...in` iterates keys (objects) |
| 11 | Labels | `outer: for(...) { break outer; }` — escape nested loops in one shot (use sparingly) |

> [!CAUTION]
> **Always use `===` (strict equality), never `==`.** Loose equality does type coercion that causes bizarre bugs: `"" == false` is `true`, `0 == ""` is `true`, `null == undefined` is `true`. Strict equality avoids all of this.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the difference between `==` and `===` with examples
- [ ] Write a program using `if/else`, `switch`, and a loop
- [ ] Use short-circuit evaluation (`&&`, `||`) to set defaults
- [ ] Use `for...of` to iterate an array and `for...in` to iterate an object's keys

</details>

---

## Phase 4: Functions

![Phase](https://img.shields.io/badge/Phase-4%2F16-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Functions are the building blocks of JavaScript — learn every way to write and use them.

**What this phase is about.** Functions are reusable units of behavior — *take inputs, return an output*. JavaScript has three syntaxes for functions (declaration, expression, arrow), several ways to pass arguments (default, rest, destructured), and one feature that no other mainstream language handles quite the same: **closures**. This phase covers all of them.

**Why it matters.** JavaScript treats functions as **first-class values** — you can store them in variables, pass them as arguments, and return them from other functions. This is the secret behind callbacks, promises, event listeners, array methods like `map`, and basically every interesting pattern in the language. Get this right and the rest of JS clicks. Get it wrong and you'll fight every framework you ever touch.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Declarations | `function greet() {}` — hoisted, can be called before they're defined |
| 2 | Function Expressions | `const greet = function() {}` — not hoisted, assigned to variables |
| 3 | Arrow Functions | `const greet = () => {}` — shorter syntax, different `this` binding |
| 4 | Parameters & Arguments | Default parameters (`function(x = 10)`), rest parameters (`...args`) |
| 5 | Return Values | `return` exits the function and sends a value back. No return = `undefined` |
| 6 | Scope | Global vs local vs block scope — where variables are accessible |
| 7 | Lexical Scope | Functions remember the scope they were *defined* in, not where they were called |
| 8 | Closures (Intro) | A function remembers variables from where it was created, even after that scope closes |
| 9 | Higher-Order Functions | Functions that take other functions as arguments or return functions |
| 10 | Callback Functions | Passing a function as an argument — the foundation of async JavaScript |
| 11 | Recursion | A function calling itself — base case prevents infinite loops |
| 12 | Pure Functions (Intro) | Same input → same output, no side effects. The cornerstone of functional code |

> [!IMPORTANT]
> **Closures** are the single most important concept in JavaScript. Every interview will ask about them. Don't skip this — revisit it until it clicks:
> ```javascript
> function counter() {
>   let count = 0;
>   return function() {
>     count++;
>     return count;
>   };
> }
> const increment = counter();
> increment(); // 1
> increment(); // 2 — "count" persists because of closure
> ```

<details>
<summary><strong>Quick Reference: Three Ways to Write Functions</strong></summary>

```javascript
// 1. Function Declaration (hoisted)
function add(a, b) {
  return a + b;
}

// 2. Function Expression (not hoisted)
const add = function(a, b) {
  return a + b;
};

// 3. Arrow Function (shortest, different "this")
const add = (a, b) => a + b;
```

> **When to use which?** Arrow functions for callbacks and short functions. Declarations for top-level named functions. Expressions when you need to assign a function to a variable.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions using all three syntaxes (declaration, expression, arrow)
- [ ] Explain closures with a practical example (counter, private state)
- [ ] Use a callback function with `setTimeout` or array methods
- [ ] Write a recursive function (factorial or Fibonacci) and explain the base case

</details>

---

## Phase 5: Arrays & Objects

![Phase](https://img.shields.io/badge/Phase-5%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master JavaScript's two most important data structures.

**What this phase is about.** Real-world data is rarely a single value — it's a *list of users*, a *cart of items*, a *user profile* with name, email, and preferences. Arrays and objects are how JavaScript models that data. This phase teaches the methods you'll use thousands of times (`map`, `filter`, `reduce`), the destructuring and spread syntax that makes modern JS readable, and JSON — the universal data format the web is built on.

**Why it matters.** Once you know `map`, `filter`, `reduce`, and destructuring, you write 30% less code than someone stuck on `for` loops, and that code is more readable. Every API response, every form submission, every Redux action — all of it is arrays and objects. This is also where the line between junior and intermediate JS developers gets drawn.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Object Literals | `{ name: "John", age: 30 }` — key-value pairs, dot vs bracket notation |
| 2 | Object Methods | `Object.keys()`, `Object.values()`, `Object.entries()`, `Object.assign()`, `Object.freeze()` |
| 3 | Array Basics | Create arrays, access by index, `.length`, check with `Array.isArray()` |
| 4 | Array Methods (Transform) | `map()`, `filter()`, `reduce()`, `find()`, `findIndex()` — return new arrays/values |
| 5 | Array Methods (Mutate) | `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, `sort()`, `reverse()` — change the original |
| 6 | Array Iteration | `forEach()`, `some()`, `every()`, `includes()`, `indexOf()` |
| 7 | Newer Array Methods | `at()`, `flat()`, `flatMap()`, `toSorted()`, `toReversed()`, `toSpliced()` (immutable copies) |
| 8 | Destructuring | Extract values: `const [a, b] = array` and `const { name, age } = object` |
| 9 | Spread Operator | `...` — copy arrays/objects, merge them, pass array items as function arguments |
| 10 | Rest Parameters | `function sum(...nums)` — collect remaining arguments into an array |
| 11 | JSON | `JSON.stringify()` (object → string) and `JSON.parse()` (string → object) — data exchange format |
| 12 | Map & Set | `new Map()` (key-value pairs with any key type), `new Set()` (unique values) |
| 13 | Shallow vs Deep Copy | `{...obj}` is shallow. `structuredClone(obj)` for deep. Why this trips everyone up |

> [!WARNING]
> `sort()` converts elements to strings by default: `[10, 2, 1].sort()` gives `[1, 10, 2]`, not `[1, 2, 10]`. Always pass a compare function: `.sort((a, b) => a - b)` for numbers.

<details>
<summary><strong>Quick Reference: Must-Know Array Methods</strong></summary>

| Method | What It Does | Returns | Mutates? |
|--------|-------------|---------|:--------:|
| `map(fn)` | Transform each element | New array | No |
| `filter(fn)` | Keep elements that pass test | New array | No |
| `reduce(fn, init)` | Combine all elements into one value | Single value | No |
| `find(fn)` | First element that passes test | Element or `undefined` | No |
| `forEach(fn)` | Run function on each element | `undefined` | No |
| `some(fn)` | Does any element pass? | `true` / `false` | No |
| `every(fn)` | Do all elements pass? | `true` / `false` | No |
| `flat(depth)` | Flatten nested arrays | New array | No |
| `push(item)` | Add to end | New length | Yes |
| `pop()` | Remove from end | Removed item | Yes |
| `splice(i, n)` | Remove/insert at position | Removed items | Yes |
| `sort(fn)` | Sort in place | Sorted array | Yes |
| `toSorted(fn)` | Sort copy (immutable) | New sorted array | No |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `map`, `filter`, and `reduce` to transform data (e.g. compute total price of cart)
- [ ] Destructure objects and arrays in variable declarations and function parameters
- [ ] Convert data between JavaScript objects and JSON strings
- [ ] Explain shallow vs deep copy with an example
- [ ] Use `Map` and `Set` and explain when each beats a plain object/array

</details>

---

## Phase 6: Strings & Regular Expressions

![Phase](https://img.shields.io/badge/Phase-6%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Master string manipulation and pattern matching with Regular Expressions.

**What this phase is about.** Most data on the web — names, emails, URLs, search queries, error messages, log files — is text. JavaScript ships with a rich set of string methods for slicing, searching, replacing, and formatting that text. **Regular expressions (regex)** are a tiny pattern-matching language embedded inside JavaScript that lets you describe text patterns ("a 10-digit phone number", "an email", "everything inside `<b>` tags") and search/replace based on them.

**Why it matters.** Form validation, URL parsing, log scraping, search highlighting, sanitizing user input, syntax highlighting — all powered by string methods + regex. Regex looks scary at first but pays off forever; the same syntax works in nearly every other language and tool (Python, Java, `grep`, VS Code search).

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | String Methods | `slice()`, `substring()`, `substr()` (deprecated) — extract parts of a string |
| 2 | String Searching | `indexOf()`, `lastIndexOf()`, `includes()`, `startsWith()`, `endsWith()` |
| 3 | String Modification | `replace()`, `replaceAll()`, `trim()`, `toUpperCase()`, `toLowerCase()`, `split()`, `padStart()`, `padEnd()` |
| 4 | Template Literals | Backticks, `${interpolation}`, multi-line strings, tagged templates |
| 5 | Regex Introduction | `/pattern/flags` — what regular expressions are and why they are powerful |
| 6 | Character Classes | `\d` (digits), `\w` (word characters), `\s` (whitespace), `.` (any character) and their negations (`\D`, `\W`, `\S`) |
| 7 | Quantifiers | `*` (0 or more), `+` (1 or more), `?` (0 or 1), `{n,m}` (specific range) |
| 8 | Anchors & Boundaries| `^` (start of string), `$` (end of string), `\b` (word boundary) |
| 9 | Groups & Alternation| `(abc)` for capturing groups, `(?:abc)` for non-capturing, `a\|b` for OR logic |
| 10 | Lookahead & Lookbehind | `(?=...)`, `(?!...)`, `(?<=...)`, `(?<!...)` — match based on what's before/after without consuming |
| 11 | Regex Methods | `regex.test(str)` returns boolean, `regex.exec(str)` returns array or null |
| 12 | String Methods + Regex| `str.match(regex)`, `str.matchAll(regex)`, `str.replace(regex, newSubstr)` |

> [!TIP]
> Use [Regex101](https://regex101.com/) to build and test regular expressions. It breaks down exactly what your pattern is matching step-by-step and explains every character. Pick "ECMAScript (JavaScript)" as the flavor.

<details>
<summary><strong>Quick Reference: Common Regex Patterns</strong></summary>

```javascript
// Email Validation (basic — for production use a library)
const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
emailRegex.test("user@example.com"); // true

// Phone Number (10 digits)
const phoneRegex = /^\d{10}$/;
phoneRegex.test("1234567890"); // true

// Password (min 8 chars, 1 letter, 1 number)
const passwordRegex = /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/;

// Strong Password (8+ chars, upper, lower, digit, symbol)
const strongPasswordRegex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/;

// URL (basic)
const urlRegex = /^https?:\/\/[^\s/$.?#].[^\s]*$/;
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a function that capitalizes the first letter of every word in a string
- [ ] Validate an email address using `regex.test()`
- [ ] Use `String.prototype.replace()` with a regular expression to sanitize user input
- [ ] Extract all hashtags from a tweet using `matchAll`

</details>

---

## Phase 7: DOM Manipulation

![Phase](https://img.shields.io/badge/Phase-7%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Connect JavaScript to the web page — select elements, listen for events, and update the UI.

**What this phase is about.** When the browser loads HTML, it builds a tree-shaped representation called the **DOM (Document Object Model)** — every tag becomes a node, every attribute a property. JavaScript talks to that tree to read content (`textContent`), change styles (`classList`), respond to clicks (`addEventListener`), and add or remove elements on the fly. Combined with CSS, this is what makes a "web page" feel like a "web app".

**Why it matters.** Even if you eventually use React/Vue/Angular (and you should), they all sit *on top of* the DOM. Frameworks abstract DOM updates away, but when something breaks at 2 AM, you need to know what's actually happening. Understanding the DOM also makes you valuable for the millions of legacy codebases still using vanilla JS or jQuery.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The DOM Tree | The browser converts HTML into a tree of objects — JavaScript can read and modify every node |
| 2 | Selecting Elements | `querySelector()`, `querySelectorAll()`, `getElementById()` — find elements in the page |
| 3 | Traversing the DOM | `parentElement`, `children`, `nextElementSibling`, `previousElementSibling`, `closest()` |
| 4 | Creating & Removing Elements | `createElement()`, `appendChild()`, `append()`, `remove()`, `insertAdjacentHTML()` |
| 5 | Modifying Content | `textContent` vs `innerHTML` vs `innerText` — when to use each and security implications |
| 6 | Classes & Styles | `classList.add()`, `.remove()`, `.toggle()`, `.contains()`, and `element.style` for inline styles |
| 7 | Attributes | `getAttribute()`, `setAttribute()`, `removeAttribute()`, `dataset` for data attributes |
| 8 | Forms | Reading inputs, `FormData`, `submit` event, `preventDefault()`, validation |
| 9 | Event Listeners | `addEventListener('click', handler)` — respond to clicks, input, scroll, keyboard, and more |
| 10 | Event Object | `event.target`, `event.currentTarget`, `event.preventDefault()`, `event.stopPropagation()` |
| 11 | Event Bubbling & Capturing | Events travel down (capture) then up (bubble) the DOM tree — control when your handler fires |
| 12 | Event Delegation | Attach one listener to a parent instead of many listeners to children — better performance |
| 13 | Custom Events | `new CustomEvent('myEvent', { detail })` — invent your own events to decouple components |

> [!IMPORTANT]
> **Never use `innerHTML` with user input** — it creates an XSS (Cross-Site Scripting) vulnerability. Use `textContent` for text, or sanitize input with a library like [DOMPurify](https://github.com/cure53/DOMPurify) before inserting HTML.

<details>
<summary><strong>Quick Reference: DOM Selection Methods</strong></summary>

| Method | Returns | Example |
|--------|---------|---------|
| `querySelector('.class')` | First match (or `null`) | `document.querySelector('.btn')` |
| `querySelectorAll('.class')` | NodeList of all matches | `document.querySelectorAll('li')` |
| `getElementById('id')` | Single element (or `null`) | `document.getElementById('header')` |
| `getElementsByClassName('class')` | Live HTMLCollection | `document.getElementsByClassName('card')` |
| `closest('selector')` | Nearest ancestor matching | `e.target.closest('button')` |

> **Use `querySelector` and `querySelectorAll` for everything.** They accept any CSS selector and are the most flexible.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a to-do list that adds/removes items dynamically
- [ ] Implement event delegation on a list (one listener handles all child clicks)
- [ ] Explain why `textContent` is safer than `innerHTML`
- [ ] Read a form's data with `FormData` on submit, prevent the default reload

</details>

---

## Phase 8: Asynchronous JavaScript

![Phase](https://img.shields.io/badge/Phase-8%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Handle operations that take time — API calls, timers, file reading — without freezing the page.

**What this phase is about.** JavaScript has one main thread. If you write `while (true) {}`, the whole page freezes — you can't click, scroll, or even close the tab. So slow operations (HTTP requests, file reads, timers) have to be **asynchronous**: kick them off, let JS keep doing other work, and run a *callback* when they finish. This phase walks through the three generations of async JS — callbacks (1995), promises (2015), and async/await (2017) — and teaches the **event loop**, the runtime mechanism that ties them all together.

**Why it matters.** Every real app talks to a server, reads a file, or waits for user input. If you don't grok promises and async/await, you can't fetch data, can't talk to a database, and can't build anything beyond a calculator. The event loop is also the most-asked senior interview topic on the planet.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Async Matters | JavaScript is single-threaded — blocking operations freeze the entire page |
| 2 | Callbacks | Pass a function to run "later" — the original async pattern (and why it gets messy) |
| 3 | Promises | `new Promise((resolve, reject) => {})` — pending → fulfilled or rejected. Chainable with `.then()` |
| 4 | Promise Chaining | `.then().then().catch()` — handle sequential async operations without nesting |
| 5 | Async/Await | `async function` + `await` — write async code that looks synchronous. Use `try/catch` for errors |
| 6 | Fetch API | `fetch(url)` — make HTTP requests, get JSON responses |
| 7 | Error Handling | Network errors vs HTTP errors — `fetch` doesn't reject on 404/500, check `response.ok` |
| 8 | Promise Combinators | `Promise.all()` (wait for all), `Promise.race()` (first to finish), `Promise.allSettled()`, `Promise.any()` |
| 9 | Event Loop | Call stack → microtask queue (promises) → task queue (setTimeout) — how JS processes async code |
| 10 | Timers | `setTimeout()`, `setInterval()`, `clearTimeout()`, `clearInterval()`, `queueMicrotask()` |
| 11 | AbortController | Cancel in-flight `fetch` requests, timeout requests, clean up listeners |
| 12 | Async Iterators | `for await...of` — consume streams of async values (paginated APIs, file streams) |

> [!CAUTION]
> `fetch()` does NOT reject on HTTP errors (404, 500). It only rejects on network failures. Always check `response.ok`:
> ```javascript
> const response = await fetch(url);
> if (!response.ok) {
>   throw new Error(`HTTP ${response.status}`);
> }
> const data = await response.json();
> ```

<details>
<summary><strong>Quick Reference: Callbacks → Promises → Async/Await</strong></summary>

```javascript
// 1. Callback Hell
getUser(id, function(user) {
  getPosts(user.id, function(posts) {
    getComments(posts[0].id, function(comments) {
      // deeply nested...
    });
  });
});

// 2. Promise Chaining
getUser(id)
  .then(user => getPosts(user.id))
  .then(posts => getComments(posts[0].id))
  .then(comments => /* use comments */)
  .catch(err => /* handle error */);

// 3. Async/Await
async function loadData(id) {
  const user = await getUser(id);
  const posts = await getPosts(user.id);
  const comments = await getComments(posts[0].id);
  return comments;
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data from a public API and display it on a page
- [ ] Handle errors properly with `try/catch` and `response.ok`
- [ ] Explain the event loop: call stack, microtask queue, task queue
- [ ] Cancel a `fetch` request with `AbortController`
- [ ] Use `Promise.all` to fetch from 3 endpoints in parallel and combine results

</details>

---

## Phase 9: ES6+ Modern JavaScript

![Phase](https://img.shields.io/badge/Phase-9%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write modern, clean JavaScript using features from ES6 (2015) and beyond.

**What this phase is about.** JavaScript got a massive upgrade in **2015 (ES6/ES2015)** — the largest single update in the language's history. Classes, modules, arrow functions, template literals, destructuring, spread/rest, promises, `let`/`const` — all introduced at once. Every year since (ES2016 → ES2025) has added more polish: optional chaining, nullish coalescing, top-level `await`, `structuredClone`, immutable array methods, decorators, and more.

**Why it matters.** Every modern codebase, framework, and library assumes you know ES6+ syntax. Reading React without arrow functions and destructuring is impossible. Reading Node 18+ without modules is impossible. This phase brings you to the present so the rest of the ecosystem makes sense.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Template Literals | `` `Hello ${name}` `` — string interpolation, multi-line strings, tagged templates |
| 2 | Enhanced Object Literals | Shorthand properties, computed property names, method shorthand |
| 3 | Classes | `class User { constructor() {} }` — cleaner syntax for constructor functions |
| 4 | Inheritance | `class Admin extends User` — `super()` calls the parent constructor, override methods |
| 5 | Static Methods & Fields | `static create()`, `static count = 0` — belong to the class, not instances |
| 6 | Private Class Fields | `#secret` — true privacy, enforced by the language (ES2022) |
| 7 | Getters & Setters | `get fullName()` and `set fullName()` — computed properties on objects and classes |
| 8 | Modules | `import { func } from './module.js'` and `export` — split code into files |
| 9 | Symbols | `Symbol('id')` — unique identifiers, `Symbol.iterator` for custom iteration |
| 10 | Iterators & Iterables | The iterator protocol — make custom objects work with `for...of` |
| 11 | Generators | `function*` and `yield` — functions that can pause and resume, lazy evaluation |
| 12 | Optional Chaining & Nullish | `user?.address?.city` (safe access) and `??` (default only for null/undefined) |
| 13 | `structuredClone` | Built-in deep clone — finally, no more `JSON.parse(JSON.stringify(obj))` |
| 14 | Top-level `await` | Use `await` outside `async` functions in ES modules |
| 15 | Logical Assignment | `a ??= b`, `a ||= b`, `a &&= b` — combine operator and assignment |

> [!TIP]
> Optional chaining (`?.`) prevents "Cannot read property of undefined" errors — the #1 JavaScript runtime error:
> ```javascript
> // Without optional chaining — crashes if user or address is undefined
> const city = user.address.city;
>
> // With optional chaining — returns undefined instead of crashing
> const city = user?.address?.city;
> ```

<details>
<summary><strong>Quick Reference: ES6+ Features Timeline</strong></summary>

| Feature | ES Version | Year | Example |
|---------|-----------|------|---------|
| `let` / `const` | ES6 | 2015 | `const x = 5;` |
| Arrow Functions | ES6 | 2015 | `(a, b) => a + b` |
| Template Literals | ES6 | 2015 | `` `Hello ${name}` `` |
| Destructuring | ES6 | 2015 | `const { a, b } = obj;` |
| Spread / Rest | ES6 | 2015 | `[...arr]`, `(...args)` |
| Classes | ES6 | 2015 | `class User { }` |
| Modules | ES6 | 2015 | `import / export` |
| Promises | ES6 | 2015 | `new Promise(...)` |
| `async` / `await` | ES8 | 2017 | `await fetch(url)` |
| Optional Chaining | ES11 | 2020 | `obj?.prop` |
| Nullish Coalescing | ES11 | 2020 | `value ?? default` |
| Private Fields | ES13 | 2022 | `#count` |
| `structuredClone()` | ES13 | 2022 | Deep copy objects |
| Top-level `await` | ES13 | 2022 | `await` outside `async` |
| Immutable Array Methods | ES14 | 2023 | `arr.toSorted()`, `toReversed()` |
| `Promise.withResolvers()` | ES15 | 2024 | Externally controlled promise |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with inheritance (`extends`, `super`) and a private `#field`
- [ ] Split a project into modules with `import`/`export`
- [ ] Use optional chaining and nullish coalescing in real code
- [ ] Write a generator that yields an infinite Fibonacci sequence

</details>

---

## Phase 10: Tooling & Package Management

![Phase](https://img.shields.io/badge/Phase-10%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Move beyond `<script>` tags in HTML and learn how real-world JS projects are built.

**What this phase is about.** Real projects don't ship one `script.js` file. They install dozens of third-party libraries from **npm**, split code across hundreds of modules, transpile modern JS for older browsers, bundle everything into optimized chunks, lint for bugs, format consistently, and ship to a CDN. This phase teaches the toolchain — Node, npm, `package.json`, bundlers (Vite/esbuild), Babel, ESLint, Prettier — that turns a folder of `.js` files into a deployed product.

**Why it matters.** Every job posting expects you to know the toolchain. "I cloned the repo and ran `npm install && npm run dev`" should feel as natural as opening a file. This is also where you stop being a tutorial-follower and start being someone who can join an existing codebase and contribute.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Node.js (Intro) | JavaScript outside the browser — why it's necessary for tooling |
| 2 | NPM, Yarn, PNPM, Bun | Node Package Manager and its alternatives — installing third-party libraries |
| 3 | `package.json` | `npm init` — the heart of any JS project, managing metadata and scripts |
| 4 | Dependencies | `dependencies` vs `devDependencies` vs `peerDependencies` — what goes where |
| 5 | Semantic Versioning | Major, Minor, Patch (`^` vs `~` in package.json), `package-lock.json` |
| 6 | NPM Scripts | Automating tasks: `"start": "node server.js"`, `"dev": "vite"`, lifecycle hooks |
| 7 | Module Bundlers | Why we need Vite, Webpack, esbuild, Rollup, or Parcel (combining files, tree-shaking, minification) |
| 8 | Vite (recommended) | The modern bundler default — instant HMR, ESM-first, tiny config |
| 9 | Babel & SWC | Transpiling modern ES6+ JS down to older JS for browser compatibility |
| 10 | ESLint | Catching syntax errors and enforcing coding standards |
| 11 | Prettier | Automatic code formatting so your team's code looks consistent |
| 12 | Husky & lint-staged | Run lint/format on `git commit` so bad code never reaches the repo |
| 13 | `.env` & `dotenv` | Environment variables for secrets (API keys, database URLs) |
| 14 | Publishing to npm | `npm publish` — share your library with the world |

> [!IMPORTANT]
> Never commit your `node_modules/` folder to GitHub. Always add `node_modules` to your `.gitignore` file. Anyone cloning your repo just needs to run `npm install` to download them based on your `package.json` and `package-lock.json`.

<details>
<summary><strong>Quick Reference: Modern JS Project Setup</strong></summary>

```bash
# Create a fresh project with Vite (recommended in 2026)
npm create vite@latest my-app -- --template vanilla
cd my-app
npm install

# Install useful dev tools
npm install -D eslint prettier husky lint-staged

# Run dev server (instant HMR)
npm run dev

# Build for production
npm run build
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Initialize a new project with `npm init -y`
- [ ] Install a library (like `date-fns` or `lodash`) and use it in your code
- [ ] Set up a basic Vite project and run the development server
- [ ] Configure ESLint and Prettier in a project
- [ ] Add a pre-commit hook with Husky that runs the linter

</details>

---

## Phase 11: Error Handling & Debugging

![Phase](https://img.shields.io/badge/Phase-11%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Write robust code that handles failures gracefully, and learn to debug like a pro.

**What this phase is about.** Code fails. Networks drop, users type weird input, dates break across timezones, libraries throw obscure errors. This phase teaches *graceful failure* — wrapping risky code in `try/catch`, throwing meaningful errors, building custom error classes — and *fast diagnosis* — using Chrome DevTools, breakpoints, the call stack, and structured `console` methods to find bugs in seconds instead of hours.

**Why it matters.** The difference between a junior and senior developer often comes down to debugging speed. Juniors `console.log` everywhere and pray. Seniors set a breakpoint, inspect the call stack, and find the bug in three minutes. Learn the tools properly once and you save thousands of hours over your career.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `try / catch / finally` | Catch errors without crashing: `try { risky() } catch(e) { handle(e) } finally { cleanup() }` |
| 2 | Error Object | `e.message`, `e.name`, `e.stack`, `e.cause` — extract useful information from errors |
| 3 | `throw` Statement | Create and throw your own errors: `throw new Error("Invalid input")` |
| 4 | Custom Errors | `class ValidationError extends Error {}` — create domain-specific error types |
| 5 | Error Cause Chain | `new Error('high level', { cause: lowLevelErr })` — preserve original error |
| 6 | Console Methods | Beyond `console.log()`: `.warn()`, `.error()`, `.table()`, `.group()`, `.time()`, `.trace()`, `.assert()` |
| 7 | Chrome Debugger | Breakpoints, step over/into/out, watch expressions, call stack, conditional breakpoints |
| 8 | Source Maps | Debug minified production code as if it were the original source |
| 9 | Network Tab | Inspect every HTTP request, response headers, payload, timing — essential for API debugging |
| 10 | Performance Tab | Record a flame chart, find slow functions, layout thrashing, long tasks |
| 11 | Debugging Strategies | Read the error message first, isolate the problem, use binary search debugging, rubber duck |
| 12 | Logging in Production | Why `console.log` doesn't scale — intro to Sentry, LogRocket, Datadog Browser SDK |

> [!TIP]
> `console.table()` is underrated. When debugging arrays of objects, it displays data in a clean table format instead of collapsed objects:
> ```javascript
> console.table([
>   { name: "Alice", age: 25 },
>   { name: "Bob", age: 30 }
> ]);
> // Shows a formatted table in the console
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `try/catch` to handle async errors with `fetch`
- [ ] Set a breakpoint in Chrome DevTools and step through code
- [ ] Create a custom `ValidationError` class and throw it on bad input
- [ ] Use `console.group()` to organize log output for nested operations

</details>

---

## Phase 12: Testing in JavaScript

![Phase](https://img.shields.io/badge/Phase-12%2F16-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Ensure your code works as expected and doesn't break when you make changes.

**What this phase is about.** Writing code is half the job — proving it works (and stays working) is the other half. This phase introduces the testing pyramid (unit, integration, end-to-end), the modern test runners (Vitest, Jest, Playwright), and the techniques for testing tricky things: async code, network calls, the DOM, components.

**Why it matters.** Tested code is shippable code. Untested code is a coin flip. Companies hiring above junior level expect you to write tests as a default, not an afterthought. Plus — once you have a green test suite, you can refactor fearlessly. That's a superpower.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Testing Pyramid | Unit Tests (fast, many) vs Integration Tests vs E2E Tests (slow, few) |
| 2 | Test Runners | Introduction to Vitest (modern default) and Jest |
| 3 | Anatomy of a Test | `describe()` blocks for grouping, `test()` or `it()` blocks for individual tests |
| 4 | Assertions | `expect(value).toBe(true)`, `toEqual()`, `toBeTruthy()`, `toThrow()`, `toMatchObject()` |
| 5 | Setup & Teardown | `beforeEach`, `afterEach`, `beforeAll`, `afterAll` — manage test state |
| 6 | Mocking Functions | `vi.fn()` / `jest.fn()` — creating fake functions to track if they were called |
| 7 | Mocking Modules | Replacing entire libraries (like Axios/Fetch) to prevent actual network requests during tests |
| 8 | Spies | `vi.spyOn()` — tracking calls to an existing method without completely replacing it |
| 9 | Testing Async Code | Returning promises, using `async/await` in tests, testing resolved/rejected states |
| 10 | Testing the DOM | Testing Library's `render`, `screen`, `userEvent` — test from the user's perspective |
| 11 | E2E with Playwright | Driving a real browser end-to-end — test the whole app like a user |
| 12 | Test Coverage | Generating coverage reports (`--coverage`) to see what lines of code aren't tested |
| 13 | TDD Basics | Test-Driven Development: Red (write failing test) → Green (write code to pass) → Refactor |
| 14 | Snapshot Testing | Capture and compare component output — fast regression detection |

> [!TIP]
> When testing asynchronous code or promises in Vitest/Jest, always remember to `await` the expectation or return the promise. Otherwise, your test might complete before the async operation finishes, giving a false positive.

<details>
<summary><strong>Quick Reference: Basic Unit Test (Vitest)</strong></summary>

```javascript
import { describe, test, expect } from 'vitest';
import { add, getUser } from './math';

describe('Math functions', () => {
  test('add() should sum two numbers', () => {
    expect(add(2, 3)).toBe(5);
  });

  test('getUser() should throw on negative ID', () => {
    expect(() => getUser(-1)).toThrow("Invalid ID");
  });

  test('async fetchUser resolves with a user', async () => {
    const user = await fetchUser(1);
    expect(user).toMatchObject({ id: 1, name: expect.any(String) });
  });
});
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write tests for a few simple utility functions (math, string manipulation)
- [ ] Test a function that uses `fetch` by mocking the global fetch API
- [ ] Run a test suite and generate a coverage report
- [ ] Write a Playwright E2E test that fills a form and asserts the result

</details>

---

## Phase 13: Advanced Concepts & Design Patterns

![Phase](https://img.shields.io/badge/Phase-13%2F16-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> Understand how JavaScript works under the hood — the concepts that separate juniors from seniors.

**What this phase is about.** This is the "why" phase. Why does `this` change meaning depending on how a function is called? Why can you call `.toString()` on `[1,2,3]` even though no one defined it? Why do closures leak memory if you're not careful? How do you reuse battle-tested solutions instead of reinventing them? You'll learn prototypes (JavaScript's actual inheritance model), the four call styles of `this`, functional programming concepts (pure functions, immutability, currying, composition), and the classic design patterns (Module, Singleton, Observer, Pub/Sub, Factory, Strategy) every senior dev recognizes on sight.

**Why it matters.** Frameworks come and go — React might not be cool in 2030. Prototypes, `this`, closures, and the event loop are forever. Once you internalize these, you can reason about *any* JS code, debug problems no Stack Overflow answer covers, and ace any senior interview.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Prototypes | Every object has a prototype chain — this is how JavaScript does inheritance (not classes!) |
| 2 | `this` Deep Dive | `this` changes based on how a function is called: method, function, constructor, arrow, `call`/`apply`/`bind` |
| 3 | Closures (Advanced) | Data privacy with closures, the module pattern, IIFE (Immediately Invoked Function Expressions) |
| 4 | Execution Context | Global context, function context, the call stack — how JavaScript executes your code step by step |
| 5 | Hoisting (Detailed) | Variables and functions are "moved to the top" — but differently for `var`, `let`, `const`, and functions |
| 6 | Memory & Garbage Collection | How JS allocates and frees memory, mark-and-sweep algorithm, common memory leaks |
| 7 | Currying & Partial Application | `add(1)(2)(3)` — transform a function with multiple arguments into a chain of single-argument functions |
| 8 | Function Composition | `compose(f, g)(x)` = `f(g(x))` — pipe data through small functions, the heart of functional programming |
| 9 | Memoization | Cache function results to avoid expensive recalculations — a key performance optimization |
| 10 | Pure Functions & Immutability | Why functional code is easier to test, debug, and parallelize |
| 11 | `WeakMap` & `WeakSet` | Weak references — keys can be garbage collected, preventing memory leaks with DOM caches |
| 12 | Property Descriptors | `Object.defineProperty()`, `writable`, `enumerable`, `configurable` — control object behavior at a low level |
| 13 | Proxies & Reflect | Intercept property reads/writes — the magic behind Vue 3, MobX, immer |
| 14 | **Design Patterns** — Module | Encapsulate private state with closures or ES modules |
| 15 | **Design Patterns** — Singleton | Exactly one instance (e.g. database connection, app config) |
| 16 | **Design Patterns** — Observer / Pub-Sub | Event emitters, signal/slot — the basis of reactive UIs |
| 17 | **Design Patterns** — Factory | Function that creates objects without exposing the construction logic |
| 18 | **Design Patterns** — Strategy | Swap algorithms at runtime (e.g. payment processors, sorters) |
| 19 | **Design Patterns** — Decorator | Wrap a function/class to add behavior (logging, caching, auth) |

> [!WARNING]
> Common memory leaks in JavaScript:
> - Event listeners not removed when elements are deleted
> - `setInterval` not cleared with `clearInterval`
> - Closures holding references to large objects unnecessarily
> - Detached DOM nodes still referenced in variables
> - Global variables that grow unbounded (caches, arrays of every event)

<details>
<summary><strong>Quick Reference: `this` in Different Contexts</strong></summary>

| Context | `this` Refers To | Example |
|---------|-----------------|---------|
| Method call | The object | `obj.method()` → `this = obj` |
| Function call | `undefined` (strict) or `window` | `func()` → `this = undefined` |
| Constructor | The new object | `new User()` → `this = new instance` |
| Arrow function | Outer scope's `this` | Inherits from where it was defined |
| `call`/`apply` | Whatever you pass | `func.call(obj)` → `this = obj` |
| `bind` | Permanently set | `const bound = func.bind(obj)` |
| Event handler | The element | `btn.onclick` → `this = btn` |
| Class method | The instance | `instance.method()` → `this = instance` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the prototype chain and how `Object.create()` works
- [ ] Predict the value of `this` in 5 different scenarios
- [ ] Implement memoization for an expensive function
- [ ] Write a custom event emitter (Pub/Sub) from scratch
- [ ] Explain at least 5 design patterns with a one-line example each

</details>

---

## Phase 14: Browser APIs, Storage & Real-Time

![Phase](https://img.shields.io/badge/Phase-14%2F16-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Use the browser's built-in APIs to build real applications.

**What this phase is about.** Modern browsers ship with hundreds of APIs you can use without installing anything. Want to store data offline? `localStorage`, `IndexedDB`. Want to know when an element scrolls into view? `IntersectionObserver`. Want a chat that updates instantly? `WebSockets`, `Server-Sent Events`. Want to run a heavy computation without freezing the UI? `Web Workers`. Want your site to work offline like a native app? `Service Workers` + `PWA`. This phase tours the APIs that turn JavaScript from a scripting language into an application platform.

**Why it matters.** These APIs are what separate "I built a webpage" from "I built an app". Lazy-loading images, drag-and-drop, offline mode, push notifications, real-time chat, video calling — all available in the browser, all free, all standard.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `localStorage` & `sessionStorage` | Store data in the browser: `localStorage.setItem('key', JSON.stringify(data))` — persists across sessions |
| 2 | Cookies & Storage Quotas | When to use cookies vs storage, size limits, security flags (`HttpOnly`, `SameSite`, `Secure`) |
| 3 | IndexedDB | Browser's built-in database — store gigabytes of structured data, indexed and queryable |
| 4 | Cache API | Programmatic access to the browser's HTTP cache — used by Service Workers |
| 5 | History API | `history.pushState()`, `popstate` event — change the URL without reloading the page (SPA routing) |
| 6 | URL & URLSearchParams | Parse, build, and edit URLs without regex |
| 7 | Geolocation API | `navigator.geolocation.getCurrentPosition()` — get the user's latitude and longitude |
| 8 | Intersection Observer | Detect when elements enter the viewport — lazy loading images, infinite scroll, animations on scroll |
| 9 | Mutation & Resize Observer | React to DOM changes and element size changes without polling |
| 10 | Web Workers | Run JavaScript in a background thread — heavy computation without freezing the UI |
| 11 | Service Workers & PWAs | Intercept network requests, enable offline functionality — the foundation of Progressive Web Apps |
| 12 | File API & Drag-and-Drop | `FileReader`, drag-and-drop file uploads, read file contents in the browser |
| 13 | Clipboard API | `navigator.clipboard.writeText()` / `readText()` — copy/paste programmatically |
| 14 | Canvas API | `<canvas>` + JavaScript — draw graphics, build games, create visualizations |
| 15 | Notifications API | `Notification.requestPermission()` — send browser notifications to the user |
| 16 | WebSockets | Bidirectional persistent connection — chat apps, live cursors, multiplayer games |
| 17 | Server-Sent Events (SSE) | Server pushes updates to client over plain HTTP — perfect for live feeds, AI streaming |
| 18 | Fetch Streaming | Stream a `Response` body chunk by chunk — used for ChatGPT-style streaming UIs |
| 19 | Performance API | `performance.now()`, `performance.mark()`, Core Web Vitals — measure and optimize speed |
| 20 | Internationalization (`Intl`) | `Intl.NumberFormat`, `DateTimeFormat`, `Collator` — locale-aware formatting without libraries |

> [!TIP]
> `Intersection Observer` replaces scroll event listeners for most use cases. It's more performant and easier to use:
> ```javascript
> const observer = new IntersectionObserver((entries) => {
>   entries.forEach(entry => {
>     if (entry.isIntersecting) {
>       entry.target.classList.add('visible');
>     }
>   });
> });
> observer.observe(document.querySelector('.fade-in'));
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build an app that saves data to `localStorage` and loads it on refresh
- [ ] Implement lazy loading images with Intersection Observer
- [ ] Create a simple drawing app with the Canvas API
- [ ] Build a real-time chat using WebSockets (client + a tiny Node WS server)
- [ ] Stream an OpenAI-style response from a server using SSE or fetch streaming

</details>

---

## Phase 15: Performance & Security

![Phase](https://img.shields.io/badge/Phase-15%2F16-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Optimize your JavaScript to run lightning fast and secure it against malicious attacks.

**What this phase is about.** Two topics that get bolted on after launch — and shouldn't. **Performance** is about how the browser turns your JS into pixels: the critical rendering path, repaint vs reflow, debouncing, throttling, code splitting, `requestAnimationFrame`. **Security** is about defending against the OWASP Top 10 web threats: XSS, CSRF, prototype pollution, dependency hijacking, and more.

**Why it matters.** Slow sites lose users (every 100ms of latency drops conversions ~1%). Insecure sites lose users *and* leak their data. Senior engineers are expected to think about both before they write a single line of code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Critical Rendering Path | Parse HTML → DOM Tree → CSSOM → Render Tree → Layout → Paint → Composite |
| 2 | Repaint vs Reflow | Changing layout (reflow) is expensive. Changing colors (repaint) is cheap. How to minimize reflows |
| 3 | Core Web Vitals | LCP, INP, CLS — the metrics Google ranks you on |
| 4 | Debouncing | Wait until the user stops typing/scrolling before firing an expensive function |
| 5 | Throttling | Fire a function at most once every X milliseconds during continuous actions |
| 6 | Code Splitting & Lazy Loading | Loading only the JavaScript necessary for the current page (`import()`) |
| 7 | Tree Shaking | Bundlers drop unused exports — make sure your code is tree-shakeable |
| 8 | `requestAnimationFrame` | The performant way to write JS animations synchronized with the display refresh rate |
| 9 | `requestIdleCallback` | Run low-priority work when the browser is idle |
| 10 | Image & Font Optimization | `loading="lazy"`, modern formats (AVIF, WebP), `font-display: swap` |
| 11 | XSS (Cross-Site Scripting) | How attackers inject malicious scripts, and why `innerHTML` is dangerous |
| 12 | CSRF (Cross-Site Request Forgery) | Forcing users to execute unwanted actions, and how SameSite cookies + CSRF tokens help |
| 13 | Content Security Policy (CSP) | CSP headers — restricting where scripts can be loaded from |
| 14 | CORS | Cross-Origin Resource Sharing — how browsers gate cross-domain requests |
| 15 | Prototype Pollution | Attackers modify `Object.prototype` via merge functions — and how to prevent it |
| 16 | Dependency Security | Using `npm audit`, Snyk, or Dependabot to find and fix vulnerable packages |
| 17 | Secure Auth Basics | JWT vs sessions, token storage (`localStorage` is unsafe!), `HttpOnly` cookies |

> [!CAUTION]
> **XSS Vulnerability Example**: Never trust user input.
> ```javascript
> // DANGEROUS: If user.bio is "<img src=x onerror=alert('Hacked')>", the script runs!
> profileDiv.innerHTML = user.bio;
>
> // SAFE: Treats the input strictly as text, not executable HTML.
> profileDiv.textContent = user.bio;
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Implement a debounce and throttle function from scratch
- [ ] Identify actions that cause a DOM reflow vs a repaint
- [ ] Run `npm audit` on a project and resolve a vulnerability
- [ ] Lazy-load a route using dynamic `import()`
- [ ] Set up a Content Security Policy header on a static site

</details>

---

## Phase 16: What's Next? (TypeScript, Frameworks, Node, Deploy)

![Phase](https://img.shields.io/badge/Phase-16%2F16-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You've finished the language. Now use it to build real things.

**What this phase is about.** Plain JavaScript can build anything, but in 2026 the industry runs on **TypeScript** + a **framework** + **Node.js on the backend** + **deployment to a cloud platform**. This phase is your runway from "JS developer" to "full-stack engineer" — pointing at the right next syllabus for each track and explaining what each tool actually solves.

**Why it matters.** This is the gap most self-taught devs hit. They know vanilla JS, build a side project, then freeze when faced with a job posting that says "TypeScript, React, Next.js, Node, Postgres, AWS". Now you have a map.

### 16.1 — Add Static Types: TypeScript

JavaScript will let you call `user.firstNme` (typo) at runtime and crash. TypeScript catches it at compile time. It's not a different language — it's JS with types layered on top. **Almost every modern company uses TypeScript.**

➡️ Continue with the [TypeScript Syllabus](typescript.md).

### 16.2 — Pick a Frontend Framework

Frameworks solve the "how do I efficiently update the UI when data changes?" problem. The big three:

| Framework | Best For | Companies |
|-----------|----------|-----------|
| **[React](react.md)** (most popular, recommended) | Job market, ecosystem, hiring | Meta, Netflix, Airbnb, Uber, Shopify |
| **[Vue](vuejs.md)** | Gentle learning curve, great docs | Alibaba, GitLab, Nintendo |
| **[Angular](angular.md)** | Large enterprise apps, opinionated | Google, Microsoft, Deutsche Bank |

**Recommendation for 2026:** Start with **React** — it has the most jobs, the largest ecosystem, and the best AI tooling support. Then learn **Next.js** (the React meta-framework) for production apps.

### 16.3 — Go Full-Stack with Node.js

JavaScript on the server. Build APIs, talk to databases, handle auth, send emails, queue jobs.

| Tool | What It Is |
|------|-----------|
| **Express / Fastify / Hono** | Minimal HTTP servers |
| **NestJS** | Opinionated full framework (Angular-style on the backend) |
| **Next.js / Remix** | Full-stack React with built-in API routes |
| **Prisma / Drizzle** | TypeScript-native database ORMs |
| **Zod / Valibot** | Runtime validation that ties to TS types |

➡️ Continue with the [Node.js Syllabus](nodejs.md) and [SQL Syllabus](sql.md).

### 16.4 — Real-World Add-Ons

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every job, every team. |
| **[Docker](docker.md)** | "Works on my machine" → "works everywhere". |
| **CI/CD** (GitHub Actions, Vercel, Netlify) | Auto-test and auto-deploy on every push. |
| **Cloud basics** (Vercel, AWS, Cloudflare) | Where your code actually lives in production. |
| **Auth** (Clerk, Auth0, NextAuth) | Don't roll your own — use a proven provider. |
| **Web Components** | Framework-agnostic custom elements (`<my-button>`) — the future of reusable UI. |
| **AI SDKs** (Vercel AI SDK, OpenAI, Anthropic) | Embed LLMs in your apps. The hottest skill in 2026. |

### 16.5 — Mobile & Desktop

| Track | Tools |
|-------|-------|
| **Mobile** | [React Native](https://reactnative.dev/), [Expo](https://expo.dev/), [Ionic](https://ionicframework.com/) |
| **Desktop** | [Electron](https://www.electronjs.org/), [Tauri](https://tauri.app/) (Rust-powered, lighter) |

### Suggested Order After This Syllabus

```
TypeScript → React (or Vue) → Git → Node.js → SQL → Docker → Deploy a real project
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

Avoid these pitfalls that trip up most JavaScript learners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `==` instead of `===` | Type coercion causes bugs: `"0" == false` is `true` | Always use `===` (strict equality) |
| 2 | Using `var` | Function-scoped, hoisted as `undefined`, can be redeclared — leads to subtle bugs | Use `const` by default, `let` when you need to reassign |
| 3 | Skipping fundamentals for frameworks | Learning React without understanding closures, `this`, and async leads to confusion | Master vanilla JS before touching React/Vue/Angular |
| 4 | Not handling async errors | Unhandled promise rejections crash Node.js and show console errors in browsers | Always use `try/catch` with `async/await` or `.catch()` with promises |
| 5 | Mutating arrays/objects | Changing the original data causes unexpected bugs in other parts of the code | Use `map()`, `filter()`, spread (`...`) to create new copies |
| 6 | `fetch` not checking `response.ok` | `fetch` only rejects on network failure, not HTTP errors (404, 500) | Check `if (!response.ok) throw new Error(...)` |
| 7 | Forgetting `this` context | `this` changes based on how a function is called — common source of `undefined` errors | Use arrow functions for callbacks, or `bind()` |
| 8 | Comparing objects with `===` | `{} === {}` is `false` — objects are compared by reference, not value | Compare specific properties, or use `JSON.stringify()` for simple cases |
| 9 | Off-by-one errors in loops | Using `<=` instead of `<` (or vice versa) iterates one too many or too few times | Arrays are 0-indexed: `for (let i = 0; i < arr.length; i++)` |
| 10 | Not removing event listeners | Listeners on removed elements cause memory leaks and ghost behavior | Use `removeEventListener()` or `AbortController` for cleanup |
| 11 | Storing JWTs in `localStorage` | Vulnerable to XSS — any script on your domain can read it | Use `HttpOnly` cookies or a dedicated auth library |
| 12 | Using `JSON.parse(JSON.stringify(obj))` for deep clone | Loses functions, dates, undefined, Maps, circular refs | Use `structuredClone(obj)` (built-in since 2022) |
| 13 | Not reading the error message | Spending hours guessing instead of reading the stack trace | Read the error first. Then search the *exact* message. |

---

## Interview Questions

Test your JavaScript knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What's the difference between `var`, `let`, and `const`?**
   - `var`: function-scoped, hoisted as `undefined`, can be redeclared. `let`: block-scoped, hoisted but in temporal dead zone, can be reassigned. `const`: block-scoped, must be initialized, cannot be reassigned (but object properties can be mutated).

2. **List all 8 data types in JavaScript.**
   - 7 primitives: `string`, `number`, `bigint`, `boolean`, `undefined`, `null`, `symbol`. 1 reference type: `object` (which includes arrays, functions, dates, etc.).

3. **Explain type coercion. What does `"5" + 1` vs `"5" - 1` return?**
   - `"5" + 1` = `"51"` (string concatenation, `+` prefers strings). `"5" - 1` = `4` (subtraction only works on numbers, so `"5"` is converted). This is implicit type coercion — JS auto-converts types.

4. **What is hoisting?**
   - JavaScript moves declarations to the top of their scope before executing. `var` is hoisted as `undefined`. `let`/`const` are hoisted but can't be accessed before declaration (temporal dead zone). Function declarations are fully hoisted.

5. **What is a callback function?**
   - A function passed as an argument to another function, executed inside that function. Example: `[1,2,3].forEach(num => console.log(num))` — the arrow function is the callback.

6. **What's the difference between `null` and `undefined`?**
   - `undefined`: variable declared but not assigned, or missing function return. `null`: intentionally set to "no value" by the developer. `typeof undefined` is `"undefined"`, `typeof null` is `"object"` (a known JS bug).

7. **What are the falsy values in JavaScript?**
   - Six: `false`, `0`, `""`, `null`, `undefined`, `NaN`. Everything else is truthy — including `"0"`, `"false"`, `[]`, and `{}`.

8. **Explain primitives vs references.**
   - Primitives (string, number, etc.) are copied **by value** — `let b = a` makes a separate copy. Objects/arrays/functions are copied **by reference** — both variables point to the same object, mutating one mutates the other.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain closures with an example.**
   - A closure is a function that retains access to variables from its outer scope even after that scope has finished executing. Example: a counter function returns an inner function that increments a private `count` variable. Each call remembers the previous value because the inner function "closes over" `count`.

2. **How does `this` work in JavaScript?**
   - `this` depends on how the function is called: in a method → the object, standalone function → `undefined` (strict) or `window`, constructor → new instance, arrow function → inherits outer `this`, `call`/`apply`/`bind` → explicitly set. This is the #1 source of confusion in JS.

3. **What's the difference between `Promise.all()` and `Promise.allSettled()`?**
   - `Promise.all()`: resolves when ALL promises resolve, rejects immediately if ANY rejects. `Promise.allSettled()`: waits for ALL promises to complete (resolve or reject), never short-circuits. Use `allSettled` when you need results from every promise regardless of failures.

4. **Explain event delegation.**
   - Instead of attaching event listeners to every child element, attach one listener to the parent. Events bubble up, so you check `event.target` to identify which child was clicked. Benefits: fewer listeners (better performance), automatically works with dynamically added elements.

5. **What's the difference between `map()` and `forEach()`?**
   - `map()` returns a new array with transformed values. `forEach()` returns `undefined` — it's just for side effects (logging, DOM updates). Use `map()` when you need the result, `forEach()` when you just need to iterate.

6. **Implement debounce from scratch.**
   ```javascript
   function debounce(fn, delay) {
     let timer;
     return function(...args) {
       clearTimeout(timer);
       timer = setTimeout(() => fn.apply(this, args), delay);
     };
   }
   ```

7. **What is the difference between shallow and deep copy?**
   - Shallow copy (`{...obj}`, `Object.assign`) copies top-level properties; nested objects still share references. Deep copy (`structuredClone(obj)`) recursively copies everything — modifying the copy never affects the original.

8. **Why does `0.1 + 0.2 !== 0.3`?**
   - JavaScript uses IEEE 754 double-precision floats, which can't represent `0.1` exactly in binary. The result is `0.30000000000000004`. Fix: use `Math.abs(a - b) < Number.EPSILON` for comparisons, or `toFixed()` for display, or `BigInt`/integers for money.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain the event loop, call stack, and task queues.**
   - The call stack executes functions (LIFO). When async operations complete, their callbacks go into queues. The microtask queue (Promises, `queueMicrotask`) has priority over the task queue (`setTimeout`, events). The event loop moves callbacks from queues to the stack only when the stack is empty. This is why `setTimeout(fn, 0)` doesn't run immediately.

2. **How does prototypal inheritance work?**
   - Every object has an internal `[[Prototype]]` link to another object. When you access a property, JS looks up the prototype chain: object → prototype → prototype's prototype → `null`. `class` syntax is syntactic sugar over this system. `Object.create(proto)` creates an object with a specific prototype.

3. **What are generators and when would you use them?**
   - Functions declared with `function*` that can pause execution with `yield` and resume later. They return an iterator. Use cases: lazy evaluation of large datasets (process items one at a time), implementing custom iterables, async iteration with `for await...of`, creating infinite sequences without memory issues.

4. **What are `WeakMap` and `WeakSet`? How do they prevent memory leaks?**
   - `WeakMap`/`WeakSet` hold weak references — if no other reference to a key exists, it's garbage collected automatically. Regular `Map`/`Set` prevent garbage collection. Use cases: caching DOM element data (auto-cleanup when element is removed), storing private data for objects, tracking object instances without preventing cleanup.

5. **What causes memory leaks in JavaScript and how do you prevent them?**
   - Common causes: forgotten event listeners on removed DOM elements, uncleared `setInterval`/`setTimeout`, closures holding references to large objects, global variables, detached DOM nodes. Prevention: use `removeEventListener` or `AbortController`, clear timers, nullify references, use `WeakMap`/`WeakSet`, profile with Chrome DevTools Memory tab.

6. **Implement `Promise.all` from scratch.**
   ```javascript
   function promiseAll(promises) {
     return new Promise((resolve, reject) => {
       const results = [];
       let completed = 0;
       if (promises.length === 0) return resolve([]);
       promises.forEach((p, i) => {
         Promise.resolve(p).then(v => {
           results[i] = v;
           if (++completed === promises.length) resolve(results);
         }, reject);
       });
     });
   }
   ```

7. **What is currying and how would you implement it?**
   - Currying transforms `f(a, b, c)` into `f(a)(b)(c)`. Implementation: collect arguments until the count matches the original function's arity, then call it.
   ```javascript
   const curry = (fn) => {
     return function curried(...args) {
       return args.length >= fn.length
         ? fn(...args)
         : (...next) => curried(...args, ...next);
     };
   };
   ```

8. **Explain prototype pollution and how to prevent it.**
   - Attackers inject properties into `Object.prototype` via insecure merge functions, contaminating every object in the program. Prevent it by using `Object.create(null)` for plain dictionaries, using `Map` instead of objects for user-keyed data, validating keys, and avoiding deep-merge libraries with known CVEs.

</details>

---

## Practice Projects

You don't truly know JavaScript until you've shipped real projects. Each project below builds skills from multiple phases and produces something you can put on your portfolio. **Do them in order — each is harder than the last.**

> [!TIP]
> Push every project to GitHub with a proper README, screenshots, and a live demo (Vercel/Netlify deploys for free). A junior portfolio with 5 polished projects beats a CS degree with no projects.

### Project 1: Interactive Quiz App with Categories & Timer
![Phase 1-5](https://img.shields.io/badge/After-Phase%201--5-green)

**What you'll build:** A multi-category trivia game (Tech / Sports / History) that pulls questions from an API ([Open Trivia DB](https://opentdb.com/)). Per-question timer, score tracking, leaderboard saved per-user, "review wrong answers" screen at the end.

**Skills practiced:** Variables, data types, conditionals, loops, functions, arrays, objects, DOM basics, basic `fetch`.

**Stretch goal:** Add difficulty levels and an "endless mode" with adaptive difficulty.

---

### Project 2: Expense Tracker with Charts
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-green)

**What you'll build:** A personal finance tracker — add/edit/delete income and expenses, categorize them, filter by date range, see balance + monthly summary, render a category-wise pie chart and a 30-day spending line chart with [Chart.js](https://www.chartjs.org/). Persist everything to `localStorage`.

**Skills practiced:** Array methods (`reduce`, `filter`, `map`), DOM manipulation, event delegation, forms, `localStorage`, JSON, date handling, third-party library integration.

**Stretch goal:** Export to CSV. Import from CSV. Multi-currency.

---

### Project 3: Real-Time Weather Dashboard
![Phase 8](https://img.shields.io/badge/After-Phase%208-yellow)

**What you'll build:** Search any city, fetch real weather + 7-day forecast from [OpenWeatherMap API](https://openweathermap.org/api), use the **Geolocation API** to detect the user's location, show weather alerts, dynamic background based on conditions (rain, snow, sunny), unit toggle (°C/°F). Handle loading states, errors (city not found, network down), and cache results for 10 minutes.

**Skills practiced:** `fetch`, `async/await`, error handling, `Promise.all` (parallel API calls), Geolocation, DOM updates, debouncing the search input.

**Stretch goal:** Save favorite cities. Compare weather across multiple cities side-by-side.

---

### Project 4: GitHub Profile Explorer
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-yellow)

**What you'll build:** Search any GitHub username, display profile info, top repos sorted by stars, recent commit activity, contribution graph, language breakdown (donut chart). Built with **ES6 modules**, **classes** (`UserService`, `RepoService`), and proper error handling. Use `AbortController` to cancel previous requests when the user types fast.

**Skills practiced:** Modules, classes, `fetch`, `try/catch`, template literals, destructuring, AbortController, `Intl.DateTimeFormat` for "2 days ago" style timestamps.

**Stretch goal:** Compare two users side-by-side. OAuth login with GitHub for higher rate limits.

---

### Project 5: Markdown Note-Taking App (with Search & Tags)
![Phase 9-11](https://img.shields.io/badge/After-Phase%209--11-yellow)

**What you'll build:** A Notion-lite — create, edit, delete markdown notes; live preview pane (use [Marked.js](https://marked.js.org/)); search notes by title/content/tag with **debouncing**; pin notes; dark/light mode; keyboard shortcuts (Cmd+S to save, Cmd+/ to focus search); store in **IndexedDB** so it scales beyond `localStorage`'s 5MB limit.

**Skills practiced:** Modules, classes, IndexedDB, debouncing, keyboard events, custom events, sanitizing HTML (XSS-safe markdown rendering), error handling.

**Stretch goal:** Cloud sync via Firebase. Markdown → PDF export.

---

### Project 6: Real-Time Multiplayer Chat App
![Phase 12-14](https://img.shields.io/badge/After-Phase%2012--14-red)

**What you'll build:** A multi-room chat (like a tiny Discord) using **WebSockets**. Frontend in vanilla JS, backend a tiny Node.js + `ws` server. Features: rooms, typing indicators, online presence, browser **Notifications** when mentioned, reconnection on disconnect, message history persisted on server, user avatars. Write **unit tests** for the message-formatting/parsing logic.

**Skills practiced:** WebSockets, Node basics, real-time UI, Notifications API, Service Worker for background notifications, testing with Vitest, full-stack thinking.

**Stretch goal:** End-to-end encryption. Voice messages with the MediaRecorder API.

---

### Project 7: Drag-and-Drop Kanban Board (Trello Clone)
![Phase 13-14](https://img.shields.io/badge/After-Phase%2013--14-red)

**What you'll build:** A Trello-style task board — multiple boards, columns (To Do / Doing / Done), drag-and-drop tasks across columns and reorder within a column (use the native HTML5 Drag-and-Drop API), labels, due dates, search, keyboard accessibility (full keyboard nav for users without a mouse), smooth animations with `requestAnimationFrame`, undo/redo with the **Command pattern**, dirty-flag warning before leaving with unsaved changes.

**Skills practiced:** Drag-and-Drop API, design patterns (Command, Observer), keyboard accessibility (a11y), animations, advanced state management (undo/redo stack), `localStorage` + IndexedDB hybrid storage.

**Stretch goal:** Real-time collaboration via WebSockets. Mobile-friendly touch DnD.

---

### Project 8: AI-Powered Code Snippet Manager (Capstone)
![Phase 15-16](https://img.shields.io/badge/After-Phase%2015--16-red)

**What you'll build:** Your graduation project. A snippet manager where users save code snippets with syntax highlighting ([Shiki](https://shiki.style/)), tag and search them, share via public link, and — the kicker — get AI explanations and improvements via an LLM (use [Vercel AI SDK](https://sdk.vercel.ai/) with Claude or OpenAI), streamed back token-by-token using **fetch streaming / SSE**. Auth with [Clerk](https://clerk.com/) or [Auth0](https://auth0.com/). Backend: Node + Express or Next.js API routes. Deploy to **Vercel**. Unit + E2E tests with Playwright. CI on GitHub Actions.

**Skills practiced:** Everything from all 16 phases — modern build tools, TypeScript-ready architecture, AI streaming, auth, testing, CI/CD, deployment. **This is portfolio gold.**

**Stretch goal:** Browser extension version. VS Code extension version.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [javascript.info](https://javascript.info/) | The best JavaScript tutorial on the internet. Covers everything from basics to advanced with clear examples and exercises. Start here |
| [MDN — JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) | The definitive reference. Look up any method, property, or API with examples and browser support |
| [MDN — Learn JavaScript](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting) | Structured learning path from Mozilla — modules with interactive exercises |
| [web.dev — Learn JavaScript](https://web.dev/learn/javascript) | Google's modern JS course. Covers data types, functions, objects, arrays, classes |
| [W3Schools JavaScript Tutorial](https://www.w3schools.com/js/) | "Try It Yourself" editor on every page. Good for quick syntax lookup |
| [TC39 Proposals](https://github.com/tc39/proposals) | The future of JavaScript — every upcoming language feature, by stage |

### Books (Free Online)

| Book | Why Read |
|------|----------|
| [You Don't Know JS Yet (2nd ed.)](https://github.com/getify/You-Dont-Know-JS) | The deep dive every senior dev recommends. 6 books, all free on GitHub |
| [Eloquent JavaScript (4th ed.)](https://eloquentjavascript.net/) | A complete book — fundamentals to async to Node, with project chapters |
| [Exploring JS](https://exploringjs.com/) | Dr. Axel Rauschmayer's deep series — one book per topic (ES6, async, Node) |
| [JavaScript for Impatient Programmers](https://exploringjs.com/impatient-js/) | Modern JS in one book, optimized for people who already code |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — JavaScript Algorithms](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures-v8/) | 100% free. 21 projects from basic JS to algorithms. Earn a certification |
| [The Odin Project — Full Stack JavaScript](https://www.theodinproject.com/paths/full-stack-javascript) | Project-based. Teaches you to think like a developer, not just memorize syntax |
| [Codecademy — Learn JavaScript](https://www.codecademy.com/learn/introduction-to-javascript) | In-browser coding with instant feedback. Step-by-step lessons |
| [JavaScript30](https://javascript30.com/) | 30 projects in 30 days — vanilla JS only, no frameworks. By Wes Bos (free) |
| [Exercism — JavaScript Track](https://exercism.org/tracks/javascript) | 100% free. 140+ exercises with mentor feedback. Practice concepts in isolation |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Traversy Media — JS Crash Course](https://www.youtube.com/@TraversyMedia) | Best first JS video. Covers fundamentals in ~1.5 hours with practical examples |
| [freeCodeCamp — Full JS Course](https://www.youtube.com/@freecodecamp) | 7+ hour complete course. Follow along from zero to confident |
| [The Net Ninja — Modern JS Tutorial](https://www.youtube.com/@NetNinja) | Well-structured playlist. Each video is one focused topic |
| [Fireship](https://www.youtube.com/@Fireship) | "100 seconds of X" format — fast, visual explanations of JS concepts. Perfect for review |
| [Akshay Saini — Namaste JavaScript](https://www.youtube.com/@akshaymarch7) | Deep dives into how JS works under the hood: event loop, closures, hoisting, `this` |
| [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified) | Short, focused videos on specific JS concepts with hands-on examples |
| [Theo (t3.gg)](https://www.youtube.com/@t3dotgg) | Modern JS/TS ecosystem opinions, current tooling, what to use today |

### Practice & Coding Challenges

| Platform | What You Get |
|----------|-------------|
| [Codewars](https://www.codewars.com/) | Gamified coding challenges (kata) ranked by difficulty. Learn by solving, compare solutions |
| [LeetCode](https://leetcode.com/) | 3000+ problems. Essential for interview prep. Filter by "JavaScript" and difficulty |
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional designs to build with HTML, CSS, and JavaScript. Real-world projects |
| [Exercism](https://exercism.org/tracks/javascript) | 140+ JavaScript exercises. Free mentoring from experienced developers |
| [JavaScript30](https://javascript30.com/) | 30 small vanilla JS projects (drum kit, clock, gallery, etc.) — no frameworks |
| [DevChallenges](https://devchallenges.io/) | Full-stack project challenges with varying difficulty |
| [BigFrontend.dev](https://bigfrontend.dev/) | Frontend system design and JS coding questions from FAANG-level interviews |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — JavaScript](https://roadmap.sh/javascript) | Interactive learning path — click each topic to see resources. Track your progress |
| [roadmap.sh — Frontend](https://roadmap.sh/frontend) | Bigger picture — where JS fits in the frontend stack |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Catches bugs and enforces code style as you type. Non-negotiable for JS development |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-formats your code on save. Never argue about formatting again |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | Shows errors and warnings inline — see problems without hovering |
| [Console Ninja](https://marketplace.visualstudio.com/items?itemName=niceplusplus.console-ninja) | See `console.log` output directly in your editor, next to your code |
| [JavaScript (ES6) Code Snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets) | Shortcuts: type `clg` → `console.log()`, `imp` → `import`, `nfn` → `const fn = () => {}` |
| [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode) | Live JavaScript scratchpad — see results inline as you type. Great for experimenting |

### Online Playgrounds

| Playground | Best For |
|-----------|---------|
| [CodePen](https://codepen.io/) | Quick front-end experiments. Huge community with live examples |
| [CodeSandbox](https://codesandbox.io/) | Full project environment with npm packages. Best for framework prototyping |
| [StackBlitz](https://stackblitz.com/) | Runs Node.js in the browser. Full IDE feel, instant npm installs |
| [Replit](https://replit.com/) | Full IDE with collaboration and hosting. Run any language including Node.js |
| [JSFiddle](https://jsfiddle.net/) | Quick and minimal. Great for sharing code snippets |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [javascript.info — JavaScript Cheatsheet](https://javascript.info/js) | Comprehensive reference from the best JS tutorial site |
| [MDN JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) | Complete API reference — every method, every object, every operator |
| [ES6+ Cheatsheet (DrkSephy)](https://github.com/DrkSephy/es6-cheatsheet) | GitHub repo with all ES6+ features explained with examples |
| [Modern JS Cheatsheet](https://mbeaudru.github.io/modern-js-cheatsheet/) | Detailed explanations of modern JS concepts with code samples |

### Podcasts & Newsletters

| Resource | Format |
|----------|--------|
| [JavaScript Weekly](https://javascriptweekly.com/) | Weekly newsletter — top JS news, articles, releases |
| [Frontend Focus](https://frontendfoc.us/) | Weekly newsletter — broader frontend ecosystem |
| [Syntax.fm](https://syntax.fm/) | Wes Bos & Scott Tolinski — fun, opinionated, deep |
| [JS Party](https://changelog.com/jsparty) | Weekly podcast on JS, web platform, and the community |

---

[Back to Main Syllabus](../README.md)

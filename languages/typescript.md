# TypeScript Syllabus

A complete, structured learning path for TypeScript — your one-stop guide from "what is a type?" to advanced generics, conditional types, and shipping production code at scale. Whether you already write JavaScript and want to add types, or you're a senior engineer filling gaps in the type system, this syllabus walks you through every concept in the right order, explains *why* each matters, and gives you real projects to prove you actually learned it.

![Difficulty: Intermediate to Advanced](https://img.shields.io/badge/Difficulty-Intermediate%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 14 Phases](https://img.shields.io/badge/Topics-14%20Phases-orange)
![TypeScript: 5.x](https://img.shields.io/badge/TypeScript-5.x-3178c6)

---

## Table of Contents

- [What is TypeScript?](#what-is-typescript)
- [Why Learn TypeScript in 2026?](#why-learn-typescript-in-2026)
- [How TypeScript Works](#how-typescript-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Basic Types & Type Inference](#phase-2-basic-types--type-inference)
- [Phase 3: Objects, Interfaces & Type Aliases](#phase-3-objects-interfaces--type-aliases)
- [Phase 4: Functions](#phase-4-functions)
- [Phase 5: Unions, Intersections & Narrowing](#phase-5-unions-intersections--narrowing)
- [Phase 6: Generics](#phase-6-generics)
- [Phase 7: The Advanced Type System](#phase-7-the-advanced-type-system)
- [Phase 8: Classes, OOP & Modern Class Features](#phase-8-classes-oop--modern-class-features)
- [Phase 9: Modules, Namespaces & Declaration Files](#phase-9-modules-namespaces--declaration-files)
- [Phase 10: The tsconfig.json Deep Dive](#phase-10-the-tsconfigjson-deep-dive)
- [Phase 11: TypeScript with React](#phase-11-typescript-with-react)
- [Phase 12: TypeScript with Node.js & Backends](#phase-12-typescript-with-nodejs--backends)
- [Phase 13: The TypeScript Ecosystem](#phase-13-the-typescript-ecosystem)
- [Phase 14: What's Next? (Specializations & Deploy)](#phase-14-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is TypeScript?

**TypeScript is JavaScript with types.** That sentence is almost the whole story. Every valid `.js` file is a valid `.ts` file. You add small annotations (`name: string`, `age: number`), the TypeScript compiler checks your program for errors *before* it runs, then strips the types away to produce plain JavaScript that runs anywhere JavaScript runs — browsers, Node.js, Deno, Bun, mobile, desktop, edge functions.

TypeScript was designed by **Anders Hejlsberg** (the same person who designed Turbo Pascal, Delphi, and C#) at **Microsoft** and open-sourced in **October 2012**. The pitch was simple: JavaScript codebases were getting huge (Office for Web, VS Code, Slack), and the lack of static types made refactoring scary and bugs easy. TypeScript layered an optional, structural type system on top of JavaScript so teams could keep shipping JS while gaining the safety of a typed language. It worked. Within a decade, TypeScript went from a curiosity to the default language for serious frontend and Node.js work.

### A Brief History

| Year | Version | Highlights |
|------|---------|-----------|
| 2012 | TS 0.8 | First public release at Microsoft Build |
| 2014 | TS 1.0 | First stable release |
| 2016 | TS 2.0 | `strictNullChecks`, tagged unions, `readonly` |
| 2018 | TS 3.0 | Project references, `unknown` type |
| 2019 | TS 3.7 | Optional chaining (`?.`), nullish coalescing (`??`), assertion functions |
| 2020 | TS 4.0 | Variadic tuples, labeled tuples |
| 2022 | TS 4.7–4.9 | ESM in Node, `satisfies` operator |
| 2023 | TS 5.0 | Stage-3 decorators, `const` type parameters, faster compiler |
| 2023 | TS 5.2 | `using` keyword (explicit resource management) |
| 2024 | TS 5.4–5.5 | Inferred type predicates, regex checks |
| 2025 | TS 5.6+ | `--noUncheckedSideEffectImports`, isolatedDeclarations |

### What Makes TypeScript Special

- **Structural typing.** Two types are compatible if they have the same shape — not the same name. If a value walks like a `Duck`, it *is* a `Duck`.
- **Gradual typing.** You can adopt TS one file at a time. Mix `.js` and `.ts` in the same project (`allowJs: true`).
- **Erased types.** Types disappear at compile time. Zero runtime cost. The output is plain JS.
- **Best-in-class tooling.** Autocomplete, inline docs, refactoring, "find all references" — all from the type system. VS Code itself is a TypeScript app eating its own dog food.
- **A type system you can program.** Conditional types, mapped types, template literal types, and `infer` make the type system practically Turing-complete. You can encode invariants other languages can't express.

> [!IMPORTANT]
> TypeScript is **not** a different language — it is JavaScript with a type checker. The 2026 mental model: write JavaScript, *describe what your data looks like*, and the compiler catches typos and shape mismatches before users do.

### TypeScript vs Flow

Facebook's **Flow** was the early competitor — same idea, different team. Both shipped in 2014–2015, both ported into React's source. By 2020 the community had voted with its feet: TypeScript won because of better IDE integration, a richer type system, and faster releases. Flow still exists inside Meta but is rare elsewhere. In 2026, TypeScript is *the* type layer for JavaScript.

---

## Why Learn TypeScript in 2026?

| Reason | What It Means |
|--------|---------------|
| **Most React/Node jobs require it** | Job postings that say "React" almost always mean "React + TypeScript". Same for Node, Next.js, NestJS, and every modern framework. Not knowing TS shrinks your job market by 70%. |
| **Catches bugs at compile time** | Typos, wrong-shape objects, missing fields, returning `undefined` by mistake — all caught before the code ever runs. The IDE underlines them as you type. |
| **Refactor with confidence** | Rename a property, add a required field, change a function signature — TypeScript shows every place that needs to change. Refactoring a 500-file repo becomes routine. |
| **World-class autocomplete** | Hover any value to see its type. Autocomplete on every property, every method, every imported module. The IDE becomes a teacher. |
| **Self-documenting APIs** | Types *are* the docs. New teammates can read a function signature and know what it takes and returns — no separate documentation needed. |
| **Runtime safety with Zod** | Pair TS types with [Zod](https://zod.dev/) for runtime validation. One schema gives you both compile-time types and runtime checks for API responses, form input, and env vars. |
| **End-to-end type safety** | With tools like tRPC and the Vercel AI SDK, types flow from the database to the UI without manual sync. Change a column, frontend errors show up instantly. |
| **It scales** | Large codebases without types collapse under their own weight. Microsoft, Google, Airbnb, Shopify, Vercel — every company shipping at scale uses TypeScript. |

---

## How TypeScript Works

TypeScript runs *before* your code does. The compiler reads your `.ts` files, checks types, and emits plain JavaScript. **Types are erased** — they exist only at compile time and have zero impact at runtime.

```
                ┌────────────────────────────────────┐
                │  Your TypeScript code (.ts/.tsx)   │
                │  - type annotations                │
                │  - interfaces, generics, unions    │
                └─────────────────┬──────────────────┘
                                  │
                                  ▼
                     ┌──────────────────────────┐
                     │  tsc (TypeScript compiler)│
                     │  - parses your code       │
                     │  - checks types           │
                     │  - reports errors         │
                     │  - strips type annotations│
                     └────────────┬──────────────┘
                                  │
                                  ▼
                ┌────────────────────────────────────┐
                │  Plain JavaScript (.js)            │
                │  - no types                        │
                │  - no extra runtime cost           │
                └─────────────────┬──────────────────┘
                                  │
            ┌─────────────────────┼─────────────────────┐
            ▼                     ▼                     ▼
       Browser              Node.js / Bun          Edge runtime
       (Chrome,             (servers, CLIs,        (Vercel, CF
       Safari, FF)          scripts)               Workers)
```

In modern setups you rarely run `tsc` directly. Bundlers (Vite, esbuild, swc, Bun) strip types in milliseconds. Tools like `tsx` and `ts-node` run TypeScript files directly. The compiler still runs in the background — usually via `tsc --noEmit` in CI — to *type-check* your code without producing output.

Three core ideas to internalize:

1. **Types are erased at runtime.** `if (typeof user === "User")` does not work — `User` does not exist at runtime. Use `instanceof` for classes, or runtime validators like Zod.
2. **TypeScript is structural, not nominal.** Two interfaces with the same shape are interchangeable, even if named differently. This is the opposite of Java/C#.
3. **Gradual typing.** You can start with `any` everywhere and tighten over time. The compiler turns "all bugs are runtime" into "all bugs are compile-time" *as fast as you adopt strictness*.

---

## Pick Your Path

TypeScript's surface area is huge. Pick the track that matches your goal — each one tells you what to focus on, what to skip, and what to do next.

### Track 1 — Frontend with React + TypeScript (8–12 weeks)
**Goal:** ship typed React UIs in production. The single most common TS use case in 2026.

Do every phase, but spend extra time on **Generics**, **Unions & Narrowing**, **Advanced Types** (utility types, mapped types), and **TypeScript with React**. Skip the deep declaration-file phase on first pass — come back when you need it. After Phase 11, jump to the [React Syllabus](react.md) and rebuild your existing JS apps in TS.

### Track 2 — Backend with Node + TypeScript (10–14 weeks)
**Goal:** type-safe APIs, ORMs, and validation end-to-end.

Focus on **Functions**, **Generics**, **Advanced Types**, **Modules & Declaration Files**, **tsconfig**, and the **Node/Backend** phase. Pair with [Node.js Syllabus](nodejs.md) and learn Zod, Drizzle/Prisma, and tRPC together — they are designed to compose. Skip the React phase if you're backend-only.

### Track 3 — Modernize a JS Codebase (3–5 weeks)
**Goal:** add TS to an existing JavaScript repo without a full rewrite.

Phases 1–7 are the must-knows. Phase 9 (declaration files), Phase 10 (tsconfig — especially `allowJs`, `checkJs`, `strict`), and the "Migration" sections in Phase 12 are critical. Add `// @ts-check` to JS files first, then convert one module at a time.

### Track 4 — TypeScript Library Author (8–10 weeks)
**Goal:** publish a typed npm package other developers can consume.

Go deep on **Generics**, **Advanced Types** (conditional types, `infer`, mapped types), **Declaration Files**, and **tsconfig** (especially `declaration`, `composite`, `isolatedDeclarations`). Study `type-fest` and `ts-toolbelt` source code. Read the typings of TanStack Query, Zod, and Drizzle to see how the pros do it.

### Track 5 — Interview Prep (3–5 weeks)
**Goal:** you already write TS daily; you have a senior interview coming up.

Drill: **Type Inference**, **Narrowing** (discriminated unions, exhaustive checks), **Generics with constraints**, **Conditional types + `infer`**, **Mapped types**, the **Utility types** (`Partial`, `Pick`, `Omit`, `Record`, `Awaited`, `ReturnType`, `Parameters`, `NonNullable`). Re-implement `Pick`, `Omit`, `ReturnType`, and `DeepPartial` from scratch. Review [Interview Questions](#interview-questions) and the type-challenges repo.

### Track 6 — AI-Era Full-Stack (12–16 weeks)
**Goal:** build end-to-end type-safe LLM apps.

All phases. Then layer in **Vercel AI SDK** types (typed `streamText`, `generateObject` with Zod schemas), **tRPC** for API type sharing, and **Drizzle** for database types. By the end you can change a DB column and watch the LLM tool-call shape, the API, and the React UI all light up with errors until you fix them. This is the 2026 power loop.

> [!TIP]
> Whichever track you pick, **Phase 5 (Narrowing)** and **Phase 6 (Generics)** are the two phases every other phase depends on — read them carefully and re-read them when you get stuck later.

---

## Prerequisites

> [!NOTE]
> TypeScript is **a superset of JavaScript** — the rules of JS are the rules of TS plus more. You must know modern JavaScript well before starting. If `const`, arrow functions, destructuring, spread, modules, or `async/await` feel shaky, complete the [JavaScript Syllabus](javascript.md) first.

- **Modern JavaScript (ES6+)** — arrow functions, destructuring, spread/rest, classes, modules, promises, `async/await`, optional chaining
- **Node.js & npm** installed (v20+ recommended in 2026)
- **A code editor** — [VS Code](https://code.visualstudio.com/) is the gold standard (it is itself written in TypeScript)
- **Comfortable with the terminal** (`cd`, `ls`, running scripts)
- **Git + GitHub** — every project should be in version control
- *(Helpful, not required)* **Some HTML/CSS** if you plan to do React work

---

## How to Use This Syllabus

1. **Don't skip phases.** Generics (Phase 6) without Functions (Phase 4) is impossible. Conditional types (Phase 7) without Unions (Phase 5) is impossible.
2. **Type the code yourself.** Reading TypeScript and writing TypeScript are different skills. Type every example.
3. **Set `"strict": true` from day one.** Loose TypeScript teaches loose habits. Strict mode teaches the real language.
4. **Hover everything.** In VS Code, hover a variable to see its inferred type. This single habit will teach you more than any tutorial.
5. **Use the Learning Checklist** at the end of each phase to self-check before moving on.
6. **When you see a red squiggly line, READ IT.** TypeScript errors are wordy but precise. Bottom of the message is usually the actionable bit.
7. **Commit each phase to GitHub.** Future you (and future employers) will see the trail of progress.
8. **Pair with a project.** Pick one of the [Practice Projects](#practice-projects) and build it phase by phase as you learn.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F14-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Install TypeScript, write your first typed file, and understand the toolchain.

**What this phase is about.** You will install TypeScript, set up a minimal project with `tsconfig.json`, write your first `.ts` file with type annotations, and run it through the compiler (`tsc`) and direct runners (`tsx`, `ts-node`, `bun`). You will also meet the Playground — a browser-based TS sandbox that is the fastest way to test ideas. The point is to make the compile loop reflexive before any deeper concept lands.

**Why it matters.** TypeScript has more knobs than most languages, and most beginners trip on the *setup* before they trip on the language. Get the compile loop right once and you can focus on types for the rest of the syllabus.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What TypeScript Is | Static type layer on top of JavaScript — checks at compile, erases at runtime |
| 2 | Why TypeScript | Catches typos, enables refactoring, powers IDE autocomplete |
| 3 | Installing | `npm install -g typescript` (global) or `npm i -D typescript` (per-project) |
| 4 | Your First `.ts` File | Add `: string`, `: number`, run `tsc file.ts`, see the emitted `file.js` |
| 5 | The TypeScript Playground | [typescriptlang.org/play](https://www.typescriptlang.org/play) — paste, share, experiment in seconds |
| 6 | `tsconfig.json` (Intro) | `tsc --init`, the most important options: `target`, `module`, `strict`, `outDir` |
| 7 | Running TS Without Compiling | `tsx`, `ts-node`, `bun run`, `deno run` — execute `.ts` files directly |
| 8 | Watch Mode | `tsc --watch` — re-check on every save |
| 9 | Editor Setup | VS Code TypeScript IntelliSense, format-on-save, error lens, tsconfig path resolution |

> [!TIP]
> In 2026, the simplest setup is `npx tsx file.ts` (zero config) or `bun run file.ts` (also zero config). Reach for `tsc` when you need a real build, type-check-only run, or library output.

<details>
<summary><strong>Quick Reference: Hello, TypeScript</strong></summary>

```ts
// hello.ts
function greet(name: string): string {
  return `Hello, ${name}!`;
}

console.log(greet("Anders"));        // OK
console.log(greet(42));              // Error: 42 is not a string
console.log(greet());                // Error: missing argument
```

Run with any of:

```bash
npx tsc hello.ts && node hello.js   # classic compile + run
npx tsx hello.ts                    # one-shot run, no .js produced
bun run hello.ts                    # fastest, also zero-config
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install TypeScript locally and globally and explain the difference
- [ ] Initialize a project with `tsc --init` and read every option in the generated `tsconfig.json`
- [ ] Write a function with annotated parameters and a return type
- [ ] Run a `.ts` file using `tsx`, `ts-node`, and `bun`
- [ ] Open the TypeScript Playground and share a snippet via URL

</details>

---

## Phase 2: Basic Types & Type Inference

![Phase](https://img.shields.io/badge/Phase-2%2F14-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Master the primitive types, the type-of-types (`any`, `unknown`, `never`, `void`), and how inference works.

**What this phase is about.** TypeScript layers types over JavaScript's value system. You will learn the **primitive types** (`string`, `number`, `boolean`, `bigint`, `symbol`, `null`, `undefined`), array and tuple types, the four "special" types (`any`, `unknown`, `never`, `void`) that confuse every beginner, **literal types** (`"GET" | "POST"`), `const` assertions, and — most importantly — **type inference**: how TypeScript figures out types you didn't write down.

**Why it matters.** Once you understand inference, you stop annotating things you don't need to annotate. The signature of an idiomatic TS codebase is *minimal* annotations: types on function boundaries, types on data crossing the network, and let inference do the rest. Get this wrong and your code looks like Java with `: string` on every variable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Primitive Types | `string`, `number`, `boolean`, `bigint`, `symbol`, `null`, `undefined` |
| 2 | Type Inference | TS infers types from initial values: `let x = 5` is `number`, no annotation needed |
| 3 | Type Annotations | `let x: number = 5` — when to annotate (function params, public APIs) |
| 4 | Arrays | `number[]` and `Array<number>` — pick one style and stick with it |
| 5 | Tuples | `[string, number]` — fixed-length, ordered, typed positions |
| 6 | Readonly Arrays & Tuples | `readonly number[]`, `readonly [string, number]`, `as const` |
| 7 | `any` | The escape hatch — disables type checking entirely. Use sparingly |
| 8 | `unknown` | The safe `any` — must be narrowed before use. Always prefer over `any` |
| 9 | `never` | The "this can't happen" type — exhaustive checks, infinite loops, `throw` |
| 10 | `void` | The "no useful return value" type — for functions that do not return |
| 11 | Literal Types | `let x: "GET" \| "POST"` — narrow a string/number/boolean to specific values |
| 12 | Const Assertions | `as const` — turns a literal into its narrowest possible type |
| 13 | Type Aliases (Preview) | `type ID = string` — name a type for reuse (deep dive in Phase 3) |
| 14 | `null` vs `undefined` | With `strictNullChecks`, you must handle both — TS forces you to |

> [!IMPORTANT]
> **Always prefer `unknown` over `any`.** `any` silently disables every check; `unknown` forces you to narrow before use. The single rule of disciplined TS: never write `any` unless you mean "I have no idea and I take responsibility".

<details>
<summary><strong>Quick Reference: any vs unknown vs never vs void</strong></summary>

| Type | Means | When to use |
|------|-------|-------------|
| `any` | "Skip type checking" | Avoid. Last-resort escape hatch |
| `unknown` | "I don't know what this is yet" | API responses, `JSON.parse`, before validation |
| `never` | "This value cannot exist" | Exhaustive switches, functions that always throw |
| `void` | "No useful return value" | Functions that return nothing meaningful |
| `undefined` | "This value is missing" | Optional fields, no-return functions in strict mode |
| `null` | "Explicit absence" | Database "no value", intentional empty |

</details>

```ts
// Type inference — annotation NOT needed
let count = 0;                  // inferred number
const greeting = "hello";       // inferred "hello" (literal type because const)

// Annotation needed (no initializer, function parameter, public API)
let user: string;
function add(a: number, b: number): number { return a + b; }

// Tuples
const pair: [string, number] = ["age", 30];

// any vs unknown
let loose: any = JSON.parse("...");      // anything goes (unsafe)
let safe: unknown = JSON.parse("...");   // must narrow before use
if (typeof safe === "string") {
  safe.toUpperCase();                    // OK after narrowing
}

// never — exhaustive check
type Shape = "circle" | "square";
function area(s: Shape): number {
  switch (s) {
    case "circle": return 3.14;
    case "square": return 4;
    default: {
      const _exhaustive: never = s;      // compile error if Shape grows
      return _exhaustive;
    }
  }
}

// const assertion
const config = { mode: "dark", retries: 3 } as const;
// type: { readonly mode: "dark"; readonly retries: 3 }
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] List the 7 primitive types and write annotations for each
- [ ] Explain the difference between `any`, `unknown`, `never`, and `void`
- [ ] Use a tuple to type a `[name, age]` pair
- [ ] Use `as const` to lock an object to its literal types
- [ ] Add an exhaustive `never` check to a `switch` statement
- [ ] Predict whether each: `let x = 5`, `const x = 5`, `let x = [1, 2]` is inferred as a wide or narrow type

</details>

---

## Phase 3: Objects, Interfaces & Type Aliases

![Phase](https://img.shields.io/badge/Phase-3%2F14-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-7 Hours](https://img.shields.io/badge/Time-6--7%20Hours-yellow)

> Describe the shape of objects with `interface` and `type` — the workhorse of every TS codebase.

**What this phase is about.** Almost every TypeScript value is an object. This phase covers the two ways to describe object shapes — `interface` and `type` — when to use each, and the modifiers that make them production-ready: optional properties (`?`), readonly properties, index signatures (`[key: string]`), and excess-property checks. You will also meet **structural typing** in practice: any object that *has the shape* of an interface is assignable to it, even if it was never declared as such.

**Why it matters.** 90% of TypeScript work is "describe what this object looks like". Interfaces and type aliases are the tools you reach for hundreds of times a day. Get them right and your code is self-documenting; get them wrong and every refactor leaks bugs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Object Type Literals | `let user: { name: string; age: number }` — inline object types |
| 2 | `interface` | `interface User { name: string; age: number }` — named, extendable |
| 3 | `type` Aliases | `type User = { name: string; age: number }` — names *any* type, not just objects |
| 4 | `interface` vs `type` | Pick a default. Both work; pros and cons of each |
| 5 | Optional Properties | `email?: string` — property may be missing |
| 6 | Readonly Properties | `readonly id: string` — assignable on creation, not after |
| 7 | Index Signatures | `[key: string]: number` — for objects with arbitrary keys |
| 8 | Extending Interfaces | `interface Admin extends User { role: string }` |
| 9 | Intersection Types | `type Admin = User & { role: string }` — combine types with `&` |
| 10 | Excess Property Checks | TS rejects extra properties on object literals (subtle but useful) |
| 11 | Structural Typing | Two types are compatible if their shapes match — names don't matter |
| 12 | Nested Objects | Type a deeply nested config or API response |
| 13 | Recursive Types | A `Comment` has `replies: Comment[]` — types can refer to themselves |

> [!TIP]
> **Pick `interface` or `type` and use it consistently.** The TypeScript team uses `interface` for object shapes in their public API and `type` for unions, intersections, and primitives. That is the most common 2026 convention.

```ts
// interface (extendable, mergeable, classic OO feel)
interface User {
  readonly id: string;
  name: string;
  email?: string;            // optional
}

interface Admin extends User {
  role: "admin" | "owner";
}

// type alias (more flexible — works for unions, primitives, tuples)
type UserId = string;
type Status = "idle" | "loading" | "error";
type Pair<A, B> = [A, B];

// Intersection — combine types
type AuditLogged = { createdAt: Date; updatedAt: Date };
type AuditedUser = User & AuditLogged;

// Index signature — arbitrary keys with same value type
interface ScoreMap {
  [playerId: string]: number;
}

// Recursive type
interface Comment {
  id: string;
  text: string;
  replies: Comment[];        // references itself
}

// Structural typing in action
function logName(x: { name: string }) { console.log(x.name); }
const dog = { name: "Rex", breed: "lab" };
logName(dog);   // OK — dog has a name property; nothing else matters
```

<details>
<summary><strong>Quick Reference: interface vs type</strong></summary>

| Feature | `interface` | `type` |
|---------|:-----------:|:------:|
| Object shapes | Yes | Yes |
| Unions | No | Yes |
| Intersections | Via `extends` (limited) | Yes |
| Tuples / primitives | No | Yes |
| `extends` | Yes | Use `&` |
| Declaration merging | Yes (multiple `interface User` blocks merge) | No |
| Performance with deep types | Slightly faster | Slightly slower |
| Best for | Public API, classes, extensible shapes | Unions, primitives, computed types |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write an interface and an equivalent type alias for the same object shape
- [ ] Mark a property as optional and as readonly, and explain when to use each
- [ ] Combine two types with `&` and recreate the result with `extends`
- [ ] Use an index signature to type a "map" object (`Record`-like)
- [ ] Define a recursive type (e.g. nested comments, file tree)
- [ ] Explain structural typing with one example

</details>

---

## Phase 4: Functions

![Phase](https://img.shields.io/badge/Phase-4%2F14-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Type functions like a pro — parameters, returns, overloads, and the subtle traps of `void` and `this`.

**What this phase is about.** This phase covers everything about functions in TypeScript: typing parameters and return values, optional and default parameters, rest parameters, function-type expressions, **call signatures and construct signatures**, **overloads**, the `void` return type (and why it is *not* the same as `undefined`), and the rarely-taught but production-critical `this` parameter for typing methods that depend on context.

**Why it matters.** Functions are how data crosses boundaries — between modules, between layers, between server and client. Almost every TS bug at the boundary is a function-typing bug: missing parameters, wrong return types, callbacks with the wrong signature. Learn this once and your APIs become self-checking.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Parameter Types | `function add(a: number, b: number)` — annotate each parameter |
| 2 | Return Types | `: number` after the parameter list — explicit return types are good practice for public APIs |
| 3 | Inferred Returns | TS can infer the return type from the body — let it for internal helpers |
| 4 | Optional Parameters | `function greet(name: string, salutation?: string)` |
| 5 | Default Parameters | `function paginate(limit = 10, offset = 0)` — type inferred from default |
| 6 | Rest Parameters | `function sum(...nums: number[]): number` |
| 7 | Function Type Expressions | `type Handler = (e: Event) => void` — describe a function shape |
| 8 | Call Signatures | `interface Logger { (msg: string): void; level: string }` — function with properties |
| 9 | Construct Signatures | `interface Ctor { new (s: string): User }` — types for constructors |
| 10 | Function Overloads | Multiple signatures for the same function — narrow input → narrow output |
| 11 | `void` Return Type | "I don't care about your return value" — different from `: undefined` |
| 12 | The `this` Parameter | `function fn(this: HTMLElement) {}` — type the `this` context |
| 13 | Higher-Order Functions | Functions taking/returning functions — typing callbacks |
| 14 | Async Functions | `async function fetchUser(): Promise<User>` — return type wraps in `Promise` |
| 15 | `noImplicitAny` | The strict-mode rule that forces you to type every parameter |

> [!IMPORTANT]
> `void` is a contextual return type — TypeScript allows callbacks declared as `() => void` to actually return values, ignoring the result. This is what makes `forEach((x) => arr.push(x))` work even though `push` returns a number.

```ts
// Annotated parameters and return type
function add(a: number, b: number): number {
  return a + b;
}

// Optional + default parameters
function greet(name: string, salutation: string = "Hello"): string {
  return `${salutation}, ${name}`;
}

// Rest parameters
function sum(...nums: number[]): number {
  return nums.reduce((a, b) => a + b, 0);
}

// Function type expression
type Predicate<T> = (item: T) => boolean;
const isEven: Predicate<number> = (n) => n % 2 === 0;

// Overloads — narrow inputs → narrow outputs
function pick(obj: User, key: "name"): string;
function pick(obj: User, key: "age"): number;
function pick(obj: User, key: keyof User): unknown {
  return obj[key];
}

// `this` parameter (only for typing — erased at runtime)
function onClick(this: HTMLButtonElement, ev: MouseEvent) {
  this.disabled = true;
}

// Async function — return wraps in Promise automatically
async function fetchUser(id: string): Promise<User> {
  const res = await fetch(`/api/users/${id}`);
  return res.json();
}
```

<details>
<summary><strong>Quick Reference: Function Typing Forms</strong></summary>

```ts
// 1. Inline annotation
function f(x: number): string { return String(x); }

// 2. Function type alias
type Mapper<A, B> = (input: A) => B;
const toString: Mapper<number, string> = (n) => String(n);

// 3. Method signature on an interface
interface Service {
  fetch(id: string): Promise<User>;
}

// 4. Call signature
interface Logger {
  (message: string): void;   // it is a function
  level: "info" | "error";   // ...with properties
}

// 5. Construct signature
interface Ctor<T> {
  new (...args: any[]): T;
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Type a function with required, optional, default, and rest parameters
- [ ] Write a function type alias and a function that satisfies it
- [ ] Implement function overloads where the input type determines the output type
- [ ] Explain the difference between `: void` and `: undefined` as return types
- [ ] Type a callback with `this: HTMLElement`
- [ ] Type an async function that returns a `Promise<User[]>`

</details>

---

## Phase 5: Unions, Intersections & Narrowing

![Phase](https://img.shields.io/badge/Phase-5%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Combine types and **narrow** them — the most underrated superpower of TypeScript.

**What this phase is about.** A **union type** says "this value is A *or* B *or* C". An **intersection type** says "this value is A *and* B *and* C". Both are easy to read, but to *use* a union you have to **narrow** it — convince the compiler that, in this branch, the value is the specific member you want. This phase teaches all five flavors of narrowing — `typeof`, `instanceof`, `in`, equality narrowing, and **user-defined type guards** — plus the headline pattern of modern TS: **discriminated unions** and **exhaustive checks**.

**Why it matters.** "Either / or" is everywhere in real code: API responses (`{ ok: true, data } | { ok: false, error }`), state machines, form events, AI tool calls. Narrowing is how you write code that handles every case the compiler knows about — and breaks visibly when you add a new case. Once this clicks, TypeScript becomes a thinking tool, not a type-annotation tool.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Union Types | `type ID = string \| number` — value can be one of several types |
| 2 | Intersection Types | `type Admin = User & HasRole` — value satisfies all member types |
| 3 | `typeof` Narrowing | `if (typeof x === "string")` — TS narrows `x` inside the block |
| 4 | `instanceof` Narrowing | `if (err instanceof Error)` — narrows class types |
| 5 | `in` Operator Narrowing | `if ("email" in user)` — narrow by property presence |
| 6 | Equality Narrowing | `if (status === "ok")` — literal type narrowing |
| 7 | Truthiness Narrowing | `if (value)` — eliminates `null`, `undefined`, `0`, `""`, `false` |
| 8 | Discriminated Unions | A literal "tag" property uniquely identifies each variant |
| 9 | User-Defined Type Guards | `function isString(x: unknown): x is string` |
| 10 | Assertion Functions | `function assert(c: unknown): asserts c` — narrows by side effect |
| 11 | Exhaustive Checks | `default: const _: never = x` — guarantees every case is handled |
| 12 | Narrowing with `Array.isArray` | The right way to narrow arrays |
| 13 | Control-Flow Analysis | TS tracks narrowing through assignments, returns, and throws |

> [!IMPORTANT]
> **Discriminated unions are the #1 TypeScript pattern.** Whenever you have "this thing is one of N kinds", give each kind a literal `kind` (or `type`, `tag`, `_tag`) property and union them. The compiler will narrow exhaustively, and adding a new variant becomes a compile error you can fix one place at a time.

```ts
// Discriminated union — the "Result" pattern
type Result<T, E = Error> =
  | { ok: true; value: T }
  | { ok: false; error: E };

function handle(r: Result<User>) {
  if (r.ok) {
    console.log(r.value.name);   // r is narrowed to the success branch
  } else {
    console.error(r.error.message);
  }
}

// User-defined type guard
function isUser(x: unknown): x is User {
  return typeof x === "object" && x !== null && "name" in x;
}

const data: unknown = await fetchUser();
if (isUser(data)) {
  console.log(data.name);    // narrowed to User
}

// Exhaustive switch with `never`
type Shape =
  | { kind: "circle"; radius: number }
  | { kind: "square"; side: number }
  | { kind: "rect"; w: number; h: number };

function area(s: Shape): number {
  switch (s.kind) {
    case "circle": return Math.PI * s.radius ** 2;
    case "square": return s.side ** 2;
    case "rect":   return s.w * s.h;
    default: {
      const _exhaustive: never = s;        // compile error if Shape grows
      return _exhaustive;
    }
  }
}

// Assertion function
function assertDefined<T>(value: T | undefined, msg = "Required"): asserts value is T {
  if (value === undefined) throw new Error(msg);
}

const id: string | undefined = req.params.id;
assertDefined(id);
console.log(id.toUpperCase());   // id is now string
```

<details>
<summary><strong>Quick Reference: Five Ways to Narrow</strong></summary>

| Narrowing | When to Use | Example |
|-----------|-------------|---------|
| `typeof` | Primitives | `if (typeof x === "string")` |
| `instanceof` | Class instances | `if (err instanceof TypeError)` |
| `in` | Object property presence | `if ("email" in user)` |
| Equality | Literal types / discriminants | `if (s.kind === "circle")` |
| Type guard | Custom predicates | `function isUser(x: unknown): x is User` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a discriminated union for a `Result<T>` type with success/error variants
- [ ] Narrow a union with `typeof`, `instanceof`, `in`, and equality
- [ ] Write a user-defined type guard `isUser(x: unknown): x is User`
- [ ] Write an assertion function `assertDefined`
- [ ] Add an exhaustive `default` branch with `never` and break it by adding a variant
- [ ] Predict why `Array.isArray(x)` narrows but `typeof x === "object"` does not narrow to array

</details>

---

## Phase 6: Generics

![Phase](https://img.shields.io/badge/Phase-6%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write reusable code that keeps its types — the line that separates intermediate from senior TS.

**What this phase is about.** Generics let you write a function, class, or type *once* and use it with many different concrete types — without losing type information. This phase covers everything: generic functions, generic classes, generic interfaces and type aliases, **constraints** (`<T extends Foo>`), **default type parameters**, the new (TS 5.0) `const` type parameters, and how generics flow through async functions, arrays, and React components.

**Why it matters.** Every serious TS library you will use (Zod, TanStack Query, tRPC, Drizzle, the Vercel AI SDK) is built on generics. Reading their APIs without understanding generics is like reading Spanish without verbs. Once you can write `function getById<T>(id: string): Promise<T>`, you can read any modern library doc and a huge chunk of senior interview questions become trivial.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Generics | A typed version of "I don't care what shape, just keep it consistent" |
| 2 | Generic Functions | `function identity<T>(x: T): T` — type parameter on a function |
| 3 | Generic Type Inference | TS infers `T` from the call site — usually no explicit `<T>` needed |
| 4 | Multiple Type Parameters | `function pair<A, B>(a: A, b: B): [A, B]` |
| 5 | Generic Constraints | `<T extends { id: string }>` — restrict what `T` can be |
| 6 | Default Type Parameters | `<T = string>` — fall back to a default if not specified |
| 7 | Generic Interfaces & Aliases | `interface Box<T> { value: T }`, `type Maybe<T> = T \| null` |
| 8 | Generic Classes | `class Stack<T> { push(x: T) {} }` |
| 9 | Generic Methods on Non-Generic Classes | `class Cache { get<T>(key: string): T \| undefined {} }` |
| 10 | `keyof` with Generics | `function get<T, K extends keyof T>(obj: T, key: K): T[K]` |
| 11 | Conditional Types in Generics | `T extends string ? "yes" : "no"` (full deep dive in Phase 7) |
| 12 | `const` Type Parameters (TS 5.0) | `<const T>` — preserve narrow literal inference |
| 13 | Variance & Subtyping | Why `Array<Dog>` is sometimes (not always) assignable to `Array<Animal>` |
| 14 | Generic React Components | `<List<User> items={...} />` — passing type args through JSX |

> [!TIP]
> Read generic signatures from the inside out. `function getById<T>(id: string): Promise<T>` says: "I take an id, I return a promise of *whatever you said T is*". The caller decides `T`; the function preserves it.

```ts
// Generic function with inference
function identity<T>(x: T): T { return x; }
const a = identity("hello");        // T inferred as string
const b = identity(42);             // T inferred as number

// Multiple type parameters
function pair<A, B>(a: A, b: B): [A, B] { return [a, b]; }

// Constraint — only objects with an `id`
function byId<T extends { id: string }>(items: T[], id: string): T | undefined {
  return items.find((x) => x.id === id);
}

// keyof + generics — typed property access
function pluck<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { name: "Ada", age: 35 };
const name = pluck(user, "name");   // typed as string
// pluck(user, "wrong");           // compile error

// Generic class
class Stack<T> {
  private items: T[] = [];
  push(x: T) { this.items.push(x); }
  pop(): T | undefined { return this.items.pop(); }
}

// Generic interface
interface ApiResponse<T> {
  data: T;
  status: number;
  error?: string;
}

// Default type parameter
type Maybe<T = string> = T | null | undefined;

// `const` type parameter (TS 5.0+)
function asTuple<const T extends readonly unknown[]>(...x: T): T {
  return x;
}
const t = asTuple("a", "b", 3);     // type ["a", "b", 3] (preserved literals)
```

<details>
<summary><strong>Quick Reference: When You Need Generics</strong></summary>

- A function whose return type **depends on its input type** (`identity`, `first`, `clone`).
- A container that holds **the same type** in and out (`Stack<T>`, `Queue<T>`, `Cache<T>`).
- A wrapper around an **unknown payload** that adds metadata (`ApiResponse<T>`, `Result<T>`, `Promise<T>`).
- A typed accessor where the **key controls the value type** (`pluck`, `pick`, `Object.keys`).
- A factory or service whose **caller decides the model** (`Repository<User>`, `useFetch<Post>()`).

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write `identity<T>`, `first<T>`, and `pair<A, B>` from scratch
- [ ] Add a constraint `<T extends { id: string }>` and explain what changes
- [ ] Use `keyof` and a generic to write a typed `pluck`
- [ ] Write a generic `Stack<T>` class
- [ ] Type an `ApiResponse<T>` interface and use it in a fetcher
- [ ] Use `<const T>` to preserve a literal tuple type

</details>

---

## Phase 7: The Advanced Type System

![Phase](https://img.shields.io/badge/Phase-7%2F14-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> The type system as a programming language — mapped types, conditional types, `infer`, template literal types, and the standard utility types.

**What this phase is about.** The TypeScript type system is **Turing-complete**. You can write conditional logic (`T extends U ? X : Y`), pattern-match (`infer`), iterate (`{ [K in keyof T]: ... }`), and manipulate strings (template literal types). This phase teaches every advanced building block — `keyof`, `typeof`, indexed access (`T[K]`), mapped types, conditional types, distributive conditional types, `infer`, template literal types — and then the **standard utility types** (`Partial`, `Pick`, `Omit`, `Record`, `Required`, `Readonly`, `Awaited`, `ReturnType`, `Parameters`, `NonNullable`) that ship with TypeScript and which you will use every day.

**Why it matters.** This is where TypeScript stops being a typing tool and becomes a thinking tool. The same techniques used by Zod to infer schemas, by Drizzle to infer SQL row types, by tRPC to share types between server and client — they all live in this phase. You don't need to write these from scratch on day one, but you must be able to **read** them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `keyof` | `keyof User` → union of property names |
| 2 | `typeof` (Type Position) | `typeof user` → the type of a value |
| 3 | Indexed Access Types | `User["name"]` → the type of the `name` property |
| 4 | Mapped Types | `{ [K in keyof T]: T[K] }` — iterate over keys |
| 5 | Mapped Type Modifiers | `+readonly`, `-readonly`, `+?`, `-?` — add or remove modifiers |
| 6 | Conditional Types | `T extends U ? X : Y` |
| 7 | Distributive Conditionals | Conditionals over unions distribute member-by-member |
| 8 | `infer` Keyword | Pattern-match inside a conditional type to *extract* a sub-type |
| 9 | Template Literal Types | `` `Hello, ${T}` `` — string types you can compute |
| 10 | Utility — `Partial<T>` | Make all properties optional |
| 11 | Utility — `Required<T>` | Make all properties required |
| 12 | Utility — `Readonly<T>` | Make all properties `readonly` |
| 13 | Utility — `Pick<T, K>` | Keep only the listed keys |
| 14 | Utility — `Omit<T, K>` | Drop the listed keys |
| 15 | Utility — `Record<K, T>` | Map keys of `K` to values of `T` |
| 16 | Utility — `Exclude / Extract` | Filter unions |
| 17 | Utility — `NonNullable<T>` | Remove `null` and `undefined` |
| 18 | Utility — `ReturnType<F>` | Extract the return type of a function |
| 19 | Utility — `Parameters<F>` | Extract the parameter tuple |
| 20 | Utility — `Awaited<T>` | Unwrap nested Promises |
| 21 | The `satisfies` Operator (TS 4.9) | Type-check a value *without* widening it |

> [!IMPORTANT]
> Memorize `Partial`, `Pick`, `Omit`, `Record`, `Awaited`, and `ReturnType`. You will use them every day. Read the source — every one of them is 1–3 lines of mapped/conditional types. Reading their definitions is the fastest way to grok the advanced type system.

```ts
// keyof and indexed access
interface User { id: string; name: string; age: number }
type UserKey = keyof User;         // "id" | "name" | "age"
type Name    = User["name"];       // string

// Mapped type — recreate Partial<T>
type MyPartial<T> = { [K in keyof T]?: T[K] };
type PartialUser = MyPartial<User>;

// Mapped type — strip readonly
type Mutable<T> = { -readonly [K in keyof T]: T[K] };

// Conditional type
type IsString<T> = T extends string ? true : false;
type A = IsString<"hello">;        // true
type B = IsString<42>;             // false

// infer — extract the array element type
type ElementOf<T> = T extends (infer U)[] ? U : never;
type N = ElementOf<number[]>;      // number

// Template literal type
type EventName<T extends string> = `on${Capitalize<T>}`;
type E = EventName<"click">;       // "onClick"

// Utility types in action
type UserPatch = Partial<Pick<User, "name" | "age">>;
type UsersById = Record<string, User>;
type NameOnly  = Omit<User, "age">;

// satisfies — preserves narrow type while validating shape
const routes = {
  home: "/",
  blog: "/blog",
} satisfies Record<string, `/${string}`>;
// routes.home is "/" (literal, not string), and the shape is checked
```

<details>
<summary><strong>Quick Reference: Standard Utility Types</strong></summary>

| Utility | Recipe | Example |
|---------|--------|---------|
| `Partial<T>` | All keys optional | `Partial<User>` for PATCH bodies |
| `Required<T>` | All keys required | Strip out `?` |
| `Readonly<T>` | All keys `readonly` | Immutable views |
| `Pick<T, K>` | Keep listed keys | `Pick<User, "id" \| "name">` |
| `Omit<T, K>` | Drop listed keys | `Omit<User, "password">` for public API |
| `Record<K, V>` | Object map | `Record<string, number>` |
| `Exclude<T, U>` | Remove from union | `Exclude<"a"\|"b"\|"c", "a">` → `"b"\|"c"` |
| `Extract<T, U>` | Keep from union | Inverse of `Exclude` |
| `NonNullable<T>` | Drop `null/undefined` | Result of narrowing |
| `Parameters<F>` | Tuple of params | Forwarding wrappers |
| `ReturnType<F>` | Return value | `ReturnType<typeof fetchUser>` |
| `Awaited<T>` | Unwrap a Promise | `Awaited<Promise<User>>` → `User` |
| `InstanceType<C>` | Instance of a class | `InstanceType<typeof User>` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `keyof`, `typeof`, and indexed access on a real interface
- [ ] Re-implement `Partial<T>`, `Pick<T, K>`, and `Readonly<T>` from scratch
- [ ] Write a conditional type that uses `infer` to extract an array's element type
- [ ] Compose `Partial<Pick<User, "name" | "email">>` and explain what it means
- [ ] Use a template literal type to type CSS variable names like `--color-${string}`
- [ ] Apply `satisfies` to a config object and explain how it differs from `: Type`

</details>

---

## Phase 8: Classes, OOP & Modern Class Features

![Phase](https://img.shields.io/badge/Phase-8%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Add class semantics on top of JavaScript classes — access modifiers, abstract classes, parameter properties, decorators.

**What this phase is about.** TypeScript classes are JavaScript classes (since ES2015) plus a few extras the type system gives you: access modifiers (`public`, `private`, `protected`), `readonly`, `abstract` classes, **parameter properties** (a one-line shortcut for class fields), `implements` for declaring an interface contract, and **stage-3 decorators** (TS 5.0+) for cross-cutting concerns like logging, caching, and validation. You will also see the difference between TypeScript's `private` (compile-time only) and JavaScript's `#name` private fields (runtime-enforced), and learn when to use each.

**Why it matters.** Even though most React code is functional, classes still dominate Node backends (NestJS, TypeORM, services, repositories, error hierarchies). Decorators are coming back in a big way with stage-3 standardization — knowing them puts you ahead of the wave.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Class Basics | `class User { constructor() {} }` — same as JS, plus typed properties |
| 2 | Field Initializers | `name: string = ""` — declared and initialized in the class body |
| 3 | Constructors | Parameter and return types, default parameters |
| 4 | `public` / `private` / `protected` | Access modifiers — compile-time only |
| 5 | `readonly` Properties | Assignable in the constructor only |
| 6 | Parameter Properties | `constructor(public name: string)` — shorthand for declare + assign |
| 7 | `static` Members | Class-level fields and methods |
| 8 | `abstract` Classes | Cannot be instantiated; force subclasses to implement |
| 9 | `implements` an Interface | Declare that a class fulfills an interface contract |
| 10 | Inheritance with `extends` | `class Admin extends User`, `super()` calls |
| 11 | Method Overriding | `override` keyword (TS 4.3+) ensures a method really overrides |
| 12 | TS `private` vs JS `#field` | Compile-time hidden vs runtime-hidden |
| 13 | Generics on Classes | `class Stack<T>` (recap from Phase 6) |
| 14 | Stage-3 Decorators (TS 5.0) | `@logged class Service {}`, method/field/class decorators |
| 15 | Class Expressions | `const C = class { }` — anonymous classes |

> [!CAUTION]
> Two privacies coexist in modern TS: `private foo` (TS-only — visible in compiled JS) and `#foo` (truly private at runtime). For library APIs and security-sensitive fields, prefer `#foo`.

```ts
// Parameter properties — shortcut for declare + assign
class User {
  constructor(
    public readonly id: string,
    public name: string,
    private passwordHash: string
  ) {}

  changeName(name: string) { this.name = name; }
}

// Abstract class
abstract class Shape {
  abstract area(): number;
  describe(): string { return `Area: ${this.area()}`; }
}

class Circle extends Shape {
  constructor(public radius: number) { super(); }
  override area(): number { return Math.PI * this.radius ** 2; }
}

// implements — declarative interface conformance
interface Logger { log(message: string): void }
class ConsoleLogger implements Logger {
  log(message: string): void { console.log(message); }
}

// Stage-3 decorator (TS 5.0+) — log every method call
function logged(originalMethod: any, context: ClassMethodDecoratorContext) {
  return function (this: any, ...args: any[]) {
    console.log(`-> ${String(context.name)}(${args.join(", ")})`);
    return originalMethod.apply(this, args);
  };
}

class Calculator {
  @logged
  add(a: number, b: number) { return a + b; }
}
```

<details>
<summary><strong>Quick Reference: Access Modifiers</strong></summary>

| Modifier | Visible Where | Notes |
|----------|---------------|-------|
| `public` (default) | Everywhere | Most common |
| `protected` | This class + subclasses | Useful for inheritance APIs |
| `private` | This class only | Compile-time only — visible in JS output |
| `#name` | This class only | True runtime privacy |
| `readonly` | Anywhere; only writable in constructor | Pair with `public` for value objects |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use parameter properties to write a class in 3 lines
- [ ] Write an abstract class with one abstract method and one concrete method
- [ ] Use `implements` and explain how it differs from `extends`
- [ ] Compare TS `private` and JS `#field` with a small demo
- [ ] Write a stage-3 method decorator that times a method call
- [ ] Use the `override` keyword and break it by changing the parent's method name

</details>

---

## Phase 9: Modules, Namespaces & Declaration Files

![Phase](https://img.shields.io/badge/Phase-9%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Share code across files, ship typings to the world, and make sense of `.d.ts` files.

**What this phase is about.** Real projects span hundreds of files. This phase covers **ES modules** (the modern default — `import`/`export`), the legacy CommonJS interop you will still encounter, **namespaces** (mostly historical but used by some declaration files), **declaration files** (`.d.ts`) that describe types for plain JavaScript libraries, **ambient declarations** (`declare`), the **DefinitelyTyped** repository (`@types/*` packages on npm), and **declaration merging** — the surprising but useful TypeScript feature that lets two `interface User` blocks combine into one.

**Why it matters.** Every npm install eventually hits this topic. Configuring path aliases, fixing "Cannot find module 'foo' or its corresponding type declarations", typing a third-party library that ships without types, and authoring your own `.d.ts` for a published package — all live here.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | ES Modules | `import { x } from "./mod"`, `export const y = ...` — the modern default |
| 2 | Default vs Named Exports | Pros, cons, and when to use each |
| 3 | Type-Only Imports | `import type { User } from "./types"` — no runtime cost |
| 4 | `import { type X }` (TS 4.5+) | Mark *some* imports as type-only |
| 5 | CommonJS Interop | `require`, `module.exports`, `esModuleInterop`, default-import gotchas |
| 6 | Path Aliases | `"@/lib/*"` — short imports via `paths` in `tsconfig` |
| 7 | Declaration Files (`.d.ts`) | Type-only files describing the shape of a value or module |
| 8 | Ambient Declarations | `declare const __VERSION__: string` — types for things from outside the module system |
| 9 | DefinitelyTyped (`@types/*`) | The shared repository of typings for thousands of libraries |
| 10 | Authoring Types for Your Library | `"types": "./dist/index.d.ts"` in `package.json` |
| 11 | Declaration Merging | Same `interface` declared twice → merged |
| 12 | Module Augmentation | Add types to existing modules (e.g. add `req.user` to Express) |
| 13 | Namespaces | `namespace Geometry {}` — legacy, sometimes seen in old `.d.ts` files |
| 14 | Triple-Slash Directives | `/// <reference path="..." />` — almost extinct, occasionally seen |

> [!TIP]
> The `import type` syntax (and the `verbatimModuleSyntax` tsconfig option) keeps your bundles smaller and prevents accidental side-effect imports. Use it for any import that is only used in a type position.

```ts
// math.ts — exports
export function add(a: number, b: number): number { return a + b; }
export const PI = 3.14159;
export type Calc = (a: number, b: number) => number;

// app.ts — imports (mixed runtime + type)
import { add, PI } from "./math";
import type { Calc } from "./math";

// Type-only import inline
import { add as runtimeAdd, type Calc as MyCalc } from "./math";

// Ambient declaration — for globals injected by build tools
declare const __APP_VERSION__: string;
console.log(__APP_VERSION__);

// Module augmentation — add to an existing library's types
// types/express.d.ts
import "express";
declare module "express" {
  interface Request {
    user?: { id: string; role: "admin" | "user" };
  }
}

// .d.ts for a JS library that has none
// types/lodash-some-fn.d.ts
declare module "lodash-some-fn" {
  export function someFn(input: string): string;
}
```

<details>
<summary><strong>Quick Reference: When You Need a `.d.ts`</strong></summary>

- You install a JS library with **no types**: `npm i some-lib` → check `npm i -D @types/some-lib` first.
- The package is missing on DefinitelyTyped → write your own `.d.ts` and put it in `types/` with `"include"` in tsconfig.
- You want to type a **global** variable injected at build time (`__VERSION__`).
- You want to **augment** an existing library (add a property to Express's `Request`).
- You're publishing your own library and need to ship `.d.ts` alongside `.js`.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `export` and `import` to split a project across at least three files
- [ ] Use `import type` and explain what changes in the compiled output
- [ ] Configure a `@/*` path alias in `tsconfig.json`
- [ ] Install a third-party library without types and write your own `.d.ts` for it
- [ ] Use module augmentation to add `req.user` to Express
- [ ] Find and read a real `.d.ts` from `node_modules/@types`

</details>

---

## Phase 10: The tsconfig.json Deep Dive

![Phase](https://img.shields.io/badge/Phase-10%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-6 Hours](https://img.shields.io/badge/Time-4--6%20Hours-yellow)

> Master the file that controls everything — strictness, output, modules, paths, project references.

**What this phase is about.** Almost every "weird TypeScript bug" traces back to `tsconfig.json`. This phase walks through the options that actually matter — `target`, `module`, `moduleResolution`, the **strict family** (`strictNullChecks`, `noImplicitAny`, `strictFunctionTypes`, `strictBindCallApply`, etc.), `paths`, `baseUrl`, `outDir`, `rootDir`, `declaration`, `composite`, `incremental`, `isolatedModules`, `verbatimModuleSyntax`, `lib`, and **project references** (the way to scale a TS monorepo). You will also learn to *read* a confusing tsconfig from a real codebase and know which knob is doing what.

**Why it matters.** The difference between "TS that catches bugs" and "TS that lets bugs through" is one flag away. Strict mode is the single most valuable option in the entire compiler. Everything in this phase compounds: get `tsconfig` right and the rest of the syllabus pays off.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `tsc --init` | Generate a starter `tsconfig.json` |
| 2 | `target` | The JS version to emit (`ES2022` is a good 2026 default) |
| 3 | `module` | The module system to emit (`ESNext`, `NodeNext`) |
| 4 | `moduleResolution` | How `import "..."` is resolved (`Bundler` for Vite/esbuild, `NodeNext` for Node) |
| 5 | `lib` | Which built-in types to include (DOM, ES2022, WebWorker, etc.) |
| 6 | `strict: true` | Turns on every recommended strictness flag — always use this |
| 7 | `strictNullChecks` | Forces you to handle `null` and `undefined` |
| 8 | `noImplicitAny` | No more silent `any` parameters |
| 9 | `noUncheckedIndexedAccess` | `arr[0]` is `T \| undefined` — catches off-by-one bugs |
| 10 | `noUnusedLocals / noUnusedParameters` | Catch dead code |
| 11 | `paths` & `baseUrl` | Path aliases like `@/lib/*` |
| 12 | `outDir / rootDir` | Where output goes / where input lives |
| 13 | `declaration / declarationMap` | Emit `.d.ts` and source maps for them |
| 14 | `composite` & Project References | Multi-package monorepos with incremental builds |
| 15 | `isolatedModules` | Each file compiles in isolation — required for esbuild/swc/Babel |
| 16 | `verbatimModuleSyntax` (TS 5.0) | Stricter module syntax — pairs with `import type` |
| 17 | `allowJs / checkJs` | Mix `.js` and `.ts`, type-check JS files |
| 18 | `skipLibCheck` | Skip type-checking inside `node_modules` (fast, sometimes risky) |
| 19 | `tsconfig.json` Extension | `extends` from a base (`@tsconfig/node20`, `@tsconfig/strictest`) |

> [!IMPORTANT]
> Always set `"strict": true` and `"noUncheckedIndexedAccess": true`. These two flags alone catch the majority of beginner TS bugs. The 2026 starter config: extend `@tsconfig/strictest` and override what you need.

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ESNext",
    "moduleResolution": "Bundler",
    "lib": ["ES2022", "DOM", "DOM.Iterable"],

    "strict": true,
    "noUncheckedIndexedAccess": true,
    "noImplicitOverride": true,
    "noFallthroughCasesInSwitch": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,

    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "esModuleInterop": true,
    "skipLibCheck": true,

    "outDir": "dist",
    "rootDir": "src",
    "declaration": true,
    "sourceMap": true,

    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "include": ["src", "types"],
  "exclude": ["node_modules", "dist"]
}
```

<details>
<summary><strong>Quick Reference: Recommended `tsconfig` per Use Case</strong></summary>

| Use Case | Base | Notes |
|----------|------|-------|
| Vite / Next.js / SPA | `@tsconfig/strictest` + `@tsconfig/vite-react` | `moduleResolution: "Bundler"` |
| Node.js library | `@tsconfig/node20` | `module: "NodeNext"`, emit `.d.ts` |
| Monorepo (Turborepo/Nx) | per-package + project references | `composite: true` everywhere |
| Mixed JS/TS migration | base + `allowJs`, `checkJs` | Lower strictness while migrating |
| Browser library | base + `lib: ["ES2020", "DOM"]` | Avoid Node types |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Generate a `tsconfig.json` with `tsc --init` and read every option's default
- [ ] Turn on `strict` and `noUncheckedIndexedAccess` and fix every error in a small project
- [ ] Configure `paths` so `import x from "@/lib/x"` works
- [ ] Use `extends` to inherit from `@tsconfig/strictest`
- [ ] Set up project references between two packages in a monorepo

</details>

---

## Phase 11: TypeScript with React

![Phase](https://img.shields.io/badge/Phase-11%2F14-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Type props, events, hooks, generic components, and Server Components like a senior React engineer.

**What this phase is about.** React + TypeScript is *the* most common stack in 2026 frontend. This phase teaches typed props (with default values, children, and discriminated unions), typed events (`React.MouseEvent<HTMLButtonElement>`), typing every built-in hook (`useState`, `useReducer`, `useRef`, `useEffect`, `useContext`, `useMemo`, `useCallback`), **generic components** (`<List<User> items={...} />`), the **`React.FC` debate** (and why most teams have moved away from it), and the new **Server Components** types in Next.js App Router.

**Why it matters.** Every line of React you write touches the type system. Bad typing makes refactoring scary; great typing makes it routine. This is also the phase that pays off the most in interviews — typed React props and typed hooks are 70% of mid-level TS interview questions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Project Setup | `npm create vite@latest -- --template react-ts` or `create-next-app --typescript` |
| 2 | Component Props | `interface ButtonProps { children: ReactNode; onClick?: () => void }` |
| 3 | `React.FC` Debate | Why most teams now skip `React.FC` and just use prop types directly |
| 4 | `children` Typing | `ReactNode` (most permissive) vs `ReactElement` vs `JSX.Element` |
| 5 | Default Prop Values | Use TS default-parameter syntax inside the component |
| 6 | Event Types | `React.MouseEvent<HTMLButtonElement>`, `ChangeEvent<HTMLInputElement>`, `FormEvent` |
| 7 | `useState<T>` | Inference vs explicit generic; when to use each |
| 8 | `useReducer<S, A>` | Discriminated-union actions, exhaustive reducers |
| 9 | `useRef<T>` | DOM refs (`useRef<HTMLInputElement>(null)`) vs mutable refs |
| 10 | `useEffect` | Typing dependencies, return-type cleanup |
| 11 | `useContext<T>` | Default values, narrowing the union, custom hook pattern |
| 12 | `useMemo / useCallback` | Type inference quirks, when explicit annotations help |
| 13 | Forwarding Refs | `forwardRef<HTMLButtonElement, ButtonProps>` |
| 14 | Generic Components | `function List<T>({ items, render }: Props<T>)` — pass type args through JSX |
| 15 | Discriminated Union Props | `{ variant: "primary" } \| { variant: "icon", icon: ReactNode }` |
| 16 | Polymorphic Components | `<Box as="a" href="..." />` — typed `as` prop |
| 17 | Custom Hooks | Typed return tuples, generic hooks |
| 18 | Server Components Types | `async` function components in Next.js App Router |
| 19 | Server Action Types | Typed `"use server"` actions, `formData` typing |

> [!TIP]
> **Skip `React.FC` in 2026.** It implicitly adds `children`, has weird `defaultProps` interactions, and provides no real benefit over typing props directly. Just write `function Button(props: ButtonProps)`.

```tsx
import { useState, useReducer, useRef, useEffect, type ReactNode } from "react";

// Typed props (no React.FC)
interface ButtonProps {
  children: ReactNode;
  onClick?: () => void;
  variant?: "primary" | "secondary";
  disabled?: boolean;
}

function Button({ children, onClick, variant = "primary", disabled }: ButtonProps) {
  return (
    <button onClick={onClick} disabled={disabled} data-variant={variant}>
      {children}
    </button>
  );
}

// useState with explicit generic when null is allowed initially
const [user, setUser] = useState<User | null>(null);

// useReducer with discriminated-union actions
type Action =
  | { type: "increment" }
  | { type: "set"; value: number };

function counterReducer(state: number, action: Action): number {
  switch (action.type) {
    case "increment": return state + 1;
    case "set":       return action.value;
  }
}

// useRef for DOM nodes
const inputRef = useRef<HTMLInputElement>(null);
useEffect(() => { inputRef.current?.focus(); }, []);

// Generic component
interface ListProps<T> {
  items: T[];
  render: (item: T) => ReactNode;
}

function List<T>({ items, render }: ListProps<T>) {
  return <ul>{items.map((it, i) => <li key={i}>{render(it)}</li>)}</ul>;
}

// Usage with explicit type argument
<List<User> items={users} render={(u) => u.name} />

// Server Component (Next.js App Router) — async, runs on the server
async function PostPage({ params }: { params: { slug: string } }) {
  const post = await db.posts.findOne({ slug: params.slug });
  return <article>{post.body}</article>;
}
```

<details>
<summary><strong>Quick Reference: React Event Types</strong></summary>

| Event | Type |
|-------|------|
| Click | `React.MouseEvent<HTMLButtonElement>` |
| Form submit | `React.FormEvent<HTMLFormElement>` |
| Input change | `React.ChangeEvent<HTMLInputElement>` |
| Keyboard | `React.KeyboardEvent<HTMLInputElement>` |
| Focus / Blur | `React.FocusEvent<HTMLInputElement>` |
| Drag | `React.DragEvent<HTMLDivElement>` |
| Generic any element | `React.SyntheticEvent` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Type a `Button` component with props, default values, and an event handler
- [ ] Use `useState<T>`, `useReducer<S, A>`, and `useRef<T>` correctly
- [ ] Write a generic `<List<T>>` component
- [ ] Type a context with a custom `useX()` hook that throws if the provider is missing
- [ ] Type an async Server Component that fetches data
- [ ] Use a discriminated union to type a `Button` with `variant: "icon"` requiring an `icon` prop

</details>

---

## Phase 12: TypeScript with Node.js & Backends

![Phase](https://img.shields.io/badge/Phase-12%2F14-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Type-safe HTTP servers, ORMs, runtime validation, and end-to-end type sharing.

**What this phase is about.** TypeScript on the server is where the type system pays its biggest dividends. This phase covers Node.js setup with TS (`tsx`, `tsc`, `bun`), HTTP frameworks (Express + types, Fastify, **Hono**), database access with **Drizzle** and **Prisma** (both generate TS types from schema), runtime validation with **Zod** and **Valibot** (the missing half of TypeScript — types only check at compile time, Zod checks at runtime), and **tRPC** for sharing types between server and client without a code generator.

**Why it matters.** TypeScript types disappear at runtime. The data coming from a network, a form, or `process.env` is *not* the type you said it was — until you validate it. Pairing TS with Zod gives you both compile-time and runtime safety. tRPC and Drizzle take it further by making types flow automatically from schema → server → client.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Node + TS Setup | `tsx`/`ts-node` for dev, `tsc` for build, `node --import tsx` (Node 20+) |
| 2 | `@types/node` | Install for `process`, `fs`, `Buffer`, etc. |
| 3 | ESM vs CJS in Node | `"type": "module"`, `.mjs`/`.cjs`, `NodeNext` resolution |
| 4 | Express + Types | `import express, { Request, Response }`, augmenting `Request` |
| 5 | Fastify | TS-native HTTP framework, schema-derived types |
| 6 | Hono | Edge-first, fully typed, Zod-friendly — 2026 favorite for Workers/Bun |
| 7 | Zod (Runtime + Types) | One schema → TS type via `z.infer<>` + runtime parser |
| 8 | Valibot | Tree-shakeable Zod alternative (smaller bundles) |
| 9 | Validating `req.body` | Parse with Zod, return 400 on failure |
| 10 | Validating `process.env` | Boot-time env parsing — fail fast on missing/invalid env |
| 11 | Drizzle ORM | TS-first SQL builder, types come from your schema |
| 12 | Prisma | The original typed ORM — types generated from `schema.prisma` |
| 13 | Kysely | Type-safe SQL query builder |
| 14 | tRPC | End-to-end type-safe APIs without code generation |
| 15 | Auth Patterns | Typed sessions, JWT payloads, role enums |
| 16 | Error Handling | Custom error classes, typed error responses |
| 17 | Testing the API | Vitest + Supertest, Zod for response shape assertions |
| 18 | Building & Deploying | `tsc` → `dist`, `tsup` for libraries, `node --watch` for dev |

> [!IMPORTANT]
> **TypeScript types do not validate runtime data.** Anything from outside your program — network, files, env, user input — must be parsed with a runtime validator (Zod, Valibot) before you trust the type. The pattern: define a Zod schema, derive the TS type with `z.infer<typeof schema>`, parse on the boundary.

```ts
import { z } from "zod";
import express, { type Request, type Response } from "express";

// One schema → both runtime parse and TS type
const CreateUser = z.object({
  email: z.string().email(),
  age: z.number().int().min(0).max(150),
  role: z.enum(["admin", "user"]).default("user"),
});

type CreateUser = z.infer<typeof CreateUser>;

const app = express();
app.use(express.json());

app.post("/users", (req: Request, res: Response) => {
  const parsed = CreateUser.safeParse(req.body);
  if (!parsed.success) {
    return res.status(400).json({ errors: parsed.error.flatten() });
  }
  // parsed.data is fully typed as CreateUser
  return res.json({ ok: true, user: parsed.data });
});

// Env validation on boot — fail fast
const Env = z.object({
  DATABASE_URL: z.string().url(),
  PORT: z.coerce.number().default(3000),
  NODE_ENV: z.enum(["development", "production", "test"]),
});
const env = Env.parse(process.env);

// Drizzle — types derived from schema
import { pgTable, serial, text } from "drizzle-orm/pg-core";
const users = pgTable("users", {
  id: serial("id").primaryKey(),
  email: text("email").notNull(),
});
type User = typeof users.$inferSelect;     // type derived from the schema
type NewUser = typeof users.$inferInsert;
```

<details>
<summary><strong>Quick Reference: Boundary Validation Recipe</strong></summary>

1. **Define a Zod schema** for every external input (HTTP body, query, headers, form data, env, file, AI tool result).
2. **Derive the TS type** with `type X = z.infer<typeof schemaX>`.
3. **Parse on the boundary** with `.safeParse()` (returns a result) or `.parse()` (throws).
4. **Use the typed value inside** — at this point the type *and* the runtime shape match.
5. **Return typed errors** when validation fails (400 Bad Request, structured error body).

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up a Node + TypeScript project that runs with `tsx` in dev and builds with `tsc`
- [ ] Build an Express endpoint that validates `req.body` with Zod and returns 400 on failure
- [ ] Validate `process.env` at startup with Zod
- [ ] Define a Drizzle (or Prisma) schema and use the inferred row type in a service
- [ ] Stand up a tRPC procedure and call it from the frontend with full types
- [ ] Write a typed custom error class and a centralized error handler

</details>

---

## Phase 13: The TypeScript Ecosystem

![Phase](https://img.shields.io/badge/Phase-13%2F14-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The libraries, tools, and frameworks that make up the modern TypeScript stack. Recognize them all; deeply learn 5–8.

**What this phase is about.** TypeScript itself is a language; the *ecosystem* is what you actually ship with. This phase is your **map** — the major libraries by category. Don't try to learn all of them. Recognize each, know what it solves, and deeply learn the ones in your track's stack.

**Why it matters.** Job postings list these by name. "Experience with Zod, tRPC, Drizzle, Vitest, and the Vercel AI SDK" is increasingly the 2026 senior TS posting. Knowing what each tool is for — and what it competes with — lets you read postings, choose stacks, and migrate when something better appears.

### 13.1 — Runtime Validation & Schemas

| Library | What It Is |
|---------|-----------|
| **[Zod](https://zod.dev/)** | The 2026 default. Schemas → types via `z.infer`. Used everywhere |
| **[Valibot](https://valibot.dev/)** | Tree-shakeable Zod alternative — much smaller bundles |
| **[ArkType](https://arktype.io/)** | Schemas as TypeScript syntax — feels native |
| **[Yup](https://github.com/jquense/yup)** | The classic — older, still common in Formik codebases |
| **[Joi](https://joi.dev/)** | Hapi-era classic, mostly Node-only |
| **[Effect Schema](https://effect.website/docs/schema/introduction/)** | Schemas inside the Effect ecosystem |

### 13.2 — End-to-End Type Safety

| Library | What It Is |
|---------|-----------|
| **[tRPC](https://trpc.io/)** | The 2026 default for typed RPC between server and client |
| **[Server Actions (Next.js)](https://nextjs.org/docs/app/building-your-application/data-fetching/server-actions-and-mutations)** | Typed function calls from client → server |
| **[GraphQL Codegen](https://the-guild.dev/graphql/codegen)** | Generate TS types from a GraphQL schema |
| **[Hono RPC](https://hono.dev/docs/guides/rpc)** | tRPC-style typed client for Hono |

### 13.3 — Build Tools & Runners

| Tool | What It Is |
|------|-----------|
| **[tsc](https://www.typescriptlang.org/)** | The official compiler. The source of truth for type-checking |
| **[tsx](https://tsx.is/)** | Run `.ts` files directly — no config |
| **[esbuild](https://esbuild.github.io/)** | Ridiculously fast TS-aware bundler (Go-based) |
| **[swc](https://swc.rs/)** | Rust-based TS compiler used by Next.js and Turbopack |
| **[Vite](https://vitejs.dev/)** | Dev server + bundler — TS works out of the box |
| **[Bun](https://bun.sh/)** | All-in-one runtime that runs `.ts` files natively, no config |
| **[Deno](https://deno.com/)** | TypeScript-first runtime (alternative to Node) |
| **[tsup](https://tsup.egoist.dev/)** | Bundle + emit `.d.ts` for libraries — a thin wrapper over esbuild |
| **[Turbopack](https://turbo.build/pack)** | Next.js's Rust-based bundler |

### 13.4 — Linters & Formatters

| Tool | What It Is |
|------|-----------|
| **[ESLint + typescript-eslint](https://typescript-eslint.io/)** | The classic — TS rules for ESLint |
| **[Biome](https://biomejs.dev/)** | Rust-based, single tool for lint + format. Replaces ESLint + Prettier in many 2026 setups |
| **[Prettier](https://prettier.io/)** | The dominant code formatter |
| **[oxlint](https://oxc.rs/)** | Rust-based ESLint alternative — even faster |

### 13.5 — Type Utilities & Pattern Matching

| Library | What It Is |
|---------|-----------|
| **[type-fest](https://github.com/sindresorhus/type-fest)** | A huge set of bonus utility types (`PartialDeep`, `SetRequired`, `JsonValue`...) |
| **[ts-toolbelt](https://millsp.github.io/ts-toolbelt/)** | Heavy advanced type utilities (lists, tuples, math, strings) |
| **[ts-pattern](https://github.com/gvergnaud/ts-pattern)** | Pattern matching for TS — exhaustive, narrowing-aware |
| **[neverthrow](https://github.com/supermacro/neverthrow)** | Typed `Result<T, E>` for error handling |
| **[Effect](https://effect.website/)** | A whole functional ecosystem on top of TypeScript |

### 13.6 — Frameworks & Meta-Frameworks

| Framework | What It Is |
|-----------|-----------|
| **[Next.js](https://nextjs.org/)** | The TypeScript-first React framework. App Router, Server Components, Server Actions |
| **[Remix / React Router 7](https://remix.run/)** | Web-fundamentals-first React framework |
| **[NestJS](https://nestjs.com/)** | Opinionated Node backend framework with decorators |
| **[Hono](https://hono.dev/)** | Edge-first HTTP framework — works on Workers, Bun, Deno, Node |
| **[Fastify](https://fastify.dev/)** | Schema-first Node HTTP framework |
| **[SvelteKit](https://kit.svelte.dev/)** | Svelte's TypeScript-first meta-framework |
| **[Astro](https://astro.build/)** | Content-first multi-framework runtime |

### 13.7 — Testing

| Tool | What It Is |
|------|-----------|
| **[Vitest](https://vitest.dev/)** | The 2026 default test runner — TS-native, Vite-powered |
| **[Jest](https://jestjs.io/)** | The classic — still huge, still works |
| **[Playwright](https://playwright.dev/)** | E2E testing in real browsers |
| **[Cypress](https://www.cypress.io/)** | Older E2E option |
| **[Testing Library](https://testing-library.com/)** | "Test like a user" — pairs with Vitest/Jest |
| **[tsd](https://github.com/tsdjs/tsd)** | Test your **types** — assertions on type shape |
| **[expect-type](https://github.com/mmkal/expect-type)** | Type-level assertions (`expectTypeOf<X>().toEqualTypeOf<Y>()`) |

### 13.8 — Databases & ORMs

| Library | What It Is |
|---------|-----------|
| **[Drizzle ORM](https://orm.drizzle.team/)** | TS-first SQL ORM. Schemas in TS, types are derived |
| **[Prisma](https://www.prisma.io/)** | The original typed ORM. Codegen from `schema.prisma` |
| **[Kysely](https://kysely.dev/)** | Type-safe SQL query builder (no ORM) |
| **[MikroORM](https://mikro-orm.io/)** | Data Mapper / Unit of Work pattern |
| **[TypeORM](https://typeorm.io/)** | The decorator-heavy classic (NestJS pairs with this) |

### 13.9 — Monorepo & Project Management

| Tool | What It Is |
|------|-----------|
| **[Turborepo](https://turbo.build/repo)** | Vercel's monorepo build orchestrator |
| **[Nx](https://nx.dev/)** | Full monorepo platform (build + lint + test + generators) |
| **[pnpm workspaces](https://pnpm.io/workspaces)** | Lightweight workspace tool — pairs with Turborepo |
| **[Yarn workspaces](https://yarnpkg.com/features/workspaces)** | The original |
| **[Changesets](https://github.com/changesets/changesets)** | Versioning + changelog for monorepo packages |

### 13.10 — Documentation & API Reference

| Tool | What It Is |
|------|-----------|
| **[TypeDoc](https://typedoc.org/)** | Generate API reference HTML from `.d.ts` |
| **[API Extractor](https://api-extractor.com/)** | Microsoft's tool to roll up `.d.ts` for publishing |
| **[Mintlify](https://mintlify.com/)** | Modern docs site builder, AI-aware |

### 13.11 — Code Generation & Refactoring

| Tool | What It Is |
|------|-----------|
| **[ts-morph](https://ts-morph.com/)** | Programmatic API to read and rewrite TS code |
| **[ts-codemod / jscodeshift](https://github.com/facebook/jscodeshift)** | Run codemods across a codebase |
| **[OpenAPI Generator](https://openapi-generator.tech/)** | Generate TS clients from an OpenAPI spec |
| **[GraphQL Codegen](https://the-guild.dev/graphql/codegen)** | Generate TS from GraphQL schemas |

### 13.12 — AI SDKs (the 2026 frontier)

| Library | What It Is |
|---------|-----------|
| **[Vercel AI SDK](https://sdk.vercel.ai/)** | The 2026 default — typed `streamText`, `generateObject` with Zod schemas |
| **[Anthropic TS SDK](https://github.com/anthropics/anthropic-sdk-typescript)** | Claude API |
| **[OpenAI Node SDK](https://github.com/openai/openai-node)** | GPT API |
| **[LangChain.js](https://js.langchain.com/)** | RAG, agents, chains in TS |
| **[LlamaIndex.ts](https://ts.llamaindex.ai/)** | Data framework for LLMs in TS |
| **[Mastra](https://mastra.ai/)** | TS-first agent framework |

### 13.13 — Cheat Sheets & References

| Resource | What It Is |
|----------|-----------|
| **[type-fest README](https://github.com/sindresorhus/type-fest#readme)** | Living index of every utility type |
| **[TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)** | The official reference |
| **[Total TypeScript Cheat Sheet](https://www.totaltypescript.com/cheatsheets)** | Matt Pocock's PDF cheatsheets |
| **[Type Challenges](https://github.com/type-challenges/type-challenges)** | 200+ exercises in pure type-level programming |

> [!IMPORTANT]
> Don't learn all of these. The 2026 default TS stack: **Next.js + Tailwind + shadcn/ui + Zod + Drizzle + tRPC + TanStack Query + Vitest + Playwright + Vercel AI SDK + Biome (or ESLint + Prettier)**. Master that and you can join 70% of TS-heavy teams on day one.

---

## Phase 14: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-14%2F14-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You finished TypeScript. Pick a specialization, ship a real project, and keep going.

**What this phase is about.** TypeScript is a multiplier — it makes whatever you already do better. This phase points at the next syllabus for each track and the cross-cutting skills that pair with TS in 2026.

**Why it matters.** Most engineers stall here. They know TS, they know React or Node, but they never **ship** something at a level a hiring manager will pay for. The cure is a specialization plus a deployed project — not more tutorials.

### 14.1 — Pick a Specialization

| Track | What You Build | Key Tools |
|-------|---------------|-----------|
| **Frontend Engineer** | UIs, dashboards, marketing sites | React + TS + Tailwind + shadcn/ui + TanStack Query |
| **Full-Stack Next.js** | End-to-end apps in one repo | Next.js + Drizzle + Auth.js + Vercel |
| **AI Engineer** | LLM apps, agents, copilots | Vercel AI SDK + Zod + Anthropic/OpenAI + pgvector |
| **Backend Engineer** | APIs, services, jobs | Hono / Fastify / NestJS + Drizzle + Postgres + Redis |
| **Mobile Engineer** | iOS + Android | Expo + React Native + TS + NativeWind |
| **Library Author** | npm packages used by others | tsup + tsd + Changesets + GitHub Actions |
| **Design Systems** | Component libraries | Storybook + Radix + Tailwind + tokens |
| **DevTools / CLIs** | Internal tools, CLIs | Bun / Node + Commander + Ink |

### 14.2 — Required Cross-Cutting Skills

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every team. Every project. |
| **[SQL](sql.md)** | Every full-stack role. Pair with Drizzle/Prisma |
| **[Docker](docker.md)** | "Works on my machine" → "works everywhere" |
| **CI/CD** (GitHub Actions) | Auto-test + auto-deploy on every push |
| **Linux / terminal** | Every server runs Linux |
| **A11y** | Catch issues before users — and lawsuits |
| **Observability** (Sentry, OpenTelemetry) | Production code without monitoring is flying blind |

### 14.3 — Where to Deploy

| Target | Best For |
|--------|----------|
| **[Vercel](https://vercel.com/)** | Next.js, Server Actions, AI SDK — the TS-native default |
| **[Netlify](https://www.netlify.com/)** | Static sites, Vite SPAs |
| **[Cloudflare Workers / Pages](https://workers.cloudflare.com/)** | Edge runtimes, Hono apps |
| **[Render](https://render.com/)** | Long-running Node servers + Postgres |
| **[Fly.io](https://fly.io/)** | Region-pinned servers |
| **[Railway](https://railway.app/)** | Quick Postgres + Node |
| **[Expo EAS](https://expo.dev/eas)** | React Native build + submit |
| **AWS / Azure / GCP** | Enterprise scale |

### 14.4 — Suggested Order After This Syllabus

```
React (deep) → Next.js (deep) → SQL → Drizzle/Prisma → AI SDK capstone → Ship → Repeat
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

Avoid these pitfalls that trip up most TypeScript learners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `any` everywhere | Disables type checking — bugs leak through | Use `unknown` and narrow, or write the right type |
| 2 | Using `as` to silence errors | "Type assertion" lies to the compiler — bug at runtime | Fix the type, or validate with Zod, or narrow properly |
| 3 | `// @ts-ignore` everywhere | Hides real errors and never goes away | Use `// @ts-expect-error` (errors when the issue is gone) and only as a last resort |
| 4 | Mixing `interface` and `type` randomly | Inconsistency confuses readers and reviewers | Pick one default and document it |
| 5 | Annotating every variable | Verbose, ignores inference, looks like Java | Annotate function boundaries; let inference handle locals |
| 6 | Trusting types at runtime | Types are erased — `JSON.parse` returns `any` | Validate every external input with Zod / Valibot |
| 7 | Disabling `strict` | Defeats the purpose of TypeScript | Always `"strict": true`. Add `noUncheckedIndexedAccess: true` |
| 8 | Catching as `Error` | The thrown value type in TS is `unknown` since 4.4 | `catch (err) { if (err instanceof Error) ... }` |
| 9 | Forgetting `noUncheckedIndexedAccess` | `arr[0]` is `T` — TS lies that it's defined | Turn it on; `arr[0]` becomes `T \| undefined` |
| 10 | Using `Function` and `Object` types | They mean almost-`any` — useless | Use `(...args: any[]) => any` or specific function/object types |
| 11 | Writing `React.FC` | Adds implicit children, weird defaults | Type props directly: `function Button(props: ButtonProps)` |
| 12 | Manually typing API responses | Drifts from the real shape | Use Zod to parse + infer, or tRPC, or generated types |
| 13 | Returning `Promise<void>` from a fire-and-forget | Caller may forget to `await` and miss errors | Make intent explicit; consider returning a discriminated `Result` |
| 14 | Wide enums | TS enums emit runtime code, are not always tree-shakeable | Use `as const` objects or string-literal unions |
| 15 | Skipping `package.json` `"types"` | Library users see no types | Always set `"types": "./dist/index.d.ts"` for libraries |
| 16 | Not reading the error | TS errors are wordy but precise | Read the bottom line of the message — that's the fix |

---

## Interview Questions

Test your TypeScript knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is TypeScript and how is it different from JavaScript?**
   - TypeScript is a typed superset of JavaScript developed by Microsoft. It adds compile-time type checking, interfaces, generics, and richer tooling. The compiler erases types and emits plain JS that runs anywhere JS runs. Every valid JS file is a valid TS file.

2. **What is the difference between `any` and `unknown`?**
   - `any` disables type checking — you can do anything with the value. `unknown` is the type-safe counterpart — you must narrow it (with `typeof`, `instanceof`, a type guard, or validation) before using it. Always prefer `unknown`.

3. **What does `strict` mean in `tsconfig.json`?**
   - It turns on a bundle of strict-mode flags including `noImplicitAny`, `strictNullChecks`, `strictFunctionTypes`, `strictBindCallApply`, `alwaysStrict`, and more. It is the single most important option — always enable it.

4. **What is the difference between `interface` and `type`?**
   - Both describe object shapes. `interface` supports declaration merging and `extends`. `type` is more flexible — it can name unions, intersections, primitives, tuples, and computed types. Pick one as your default; teams usually use `interface` for object shapes and `type` for unions.

5. **What is type inference?**
   - The compiler figures out a type from context. `let x = 5` is inferred as `number`. `const x = 5` is inferred as the literal `5`. Inference reduces annotation noise — annotate function boundaries and let inference handle locals.

6. **What does `readonly` do?**
   - Marks a property as assignable only at construction. `readonly id: string` cannot be reassigned. It is a compile-time guarantee — JS still allows mutation at runtime.

7. **What is a literal type?**
   - A type that is *one specific value*: `let x: "GET"` instead of `let x: string`. Combined with unions you get `"GET" | "POST" | "PUT"`. The basis of discriminated unions and exhaustive checks.

8. **Why does `typeof null === "object"` matter in TS?**
   - It means `typeof` cannot distinguish `null` from a real object. With `strictNullChecks` on, TS forces you to handle `null` explicitly with narrowing (`if (x === null)` or `if (x)`).

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain generics with an example.**
   - Generics let a function or type accept a type parameter. `function identity<T>(x: T): T { return x }` works for any `T` and preserves it. Used in `Promise<T>`, `Array<T>`, `Map<K, V>`, and most modern libraries.

2. **What is a discriminated union and why is it useful?**
   - A union of object types where each variant has a unique literal "tag" property. `type R = { ok: true, data: T } | { ok: false, error: E }`. The compiler narrows the value when you check the tag. Adding a new variant becomes a compile error you can fix in one place.

3. **What's the difference between `keyof` and `typeof`?**
   - `typeof X` (in type position) gets the type of a *value* `X`. `keyof T` gets the union of property *names* of a *type* `T`. They compose: `keyof typeof obj` gives you the keys of the object's type.

4. **What does the `satisfies` operator do?**
   - Checks that a value matches a type *without* widening the value. `const r = { a: 1 } satisfies Record<string, number>` keeps `r.a` as `1` (literal) while validating shape. With `: Type` you would lose the literal.

5. **What is structural typing?**
   - Types are compatible based on *shape*, not on declared identity. If two interfaces have the same fields, a value of one is assignable to the other. The opposite of nominal typing in Java/C#.

6. **Implement `Partial<T>` from scratch.**
   ```ts
   type MyPartial<T> = { [K in keyof T]?: T[K] };
   ```

7. **What is the difference between TS `private` and JS `#field`?**
   - TS `private` is a compile-time check; the field is still accessible at runtime via JS. `#field` is enforced by the JavaScript engine and truly private. Prefer `#` for security-sensitive fields.

8. **How would you type a function that takes any object and a key of that object and returns the value?**
   ```ts
   function pluck<T, K extends keyof T>(obj: T, key: K): T[K] {
     return obj[key];
   }
   ```

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain conditional types and `infer`.**
   - `T extends U ? X : Y` is a conditional type. `infer V` inside the `extends` clause pattern-matches and binds a sub-type to `V`. Example: `type ElementOf<T> = T extends (infer U)[] ? U : never` extracts the array element type.

2. **What are mapped types?**
   - Types of the form `{ [K in keyof T]: ... }`. They iterate over keys of an existing type to produce a new one. Modifiers like `?`, `readonly`, `+`, and `-` add or remove. The basis of `Partial`, `Required`, `Readonly`, and `Pick`.

3. **What are template literal types?**
   - String types you can compute. `type Event<T extends string> = `on${Capitalize<T>}` ` produces `"onClick"` from `"click"`. Powers route typings, CSS variable names, and API path types.

4. **What's a distributive conditional type?**
   - When the checked type is a "naked" type parameter, conditionals distribute over union members. `type Boxed<T> = T extends any ? { value: T } : never` applied to `string | number` yields `{ value: string } | { value: number }`. Wrap with `[T]` to disable distribution.

5. **Implement `ReturnType<F>` from scratch.**
   ```ts
   type MyReturnType<F> = F extends (...args: any[]) => infer R ? R : never;
   ```

6. **How does declaration merging work?**
   - Two `interface User { ... }` blocks in the same scope are merged into one. Used to augment third-party libraries (`declare module "express" { interface Request { user?: User } }`). `type` aliases cannot be merged.

7. **How do you handle `catch` clauses in strict TS?**
   - Since TS 4.4 the default `catch` variable type is `unknown`. Narrow before use: `catch (err) { if (err instanceof Error) console.log(err.message) }`. Or use `useUnknownInCatchVariables: false` to fall back to the old `any` behavior (not recommended).

8. **Why are TS types not enough at runtime, and what do you do?**
   - Types are erased at compile time — they cannot validate runtime data. Anything from outside (network, env, file, form, AI tool result) must be parsed by a runtime validator. Use Zod / Valibot / ArkType: define a schema, derive the TS type with `z.infer`, and parse on the boundary.

</details>

---

## Practice Projects

You don't truly know TypeScript until you've shipped real projects. Each project below builds skills from multiple phases and produces something you can put on your portfolio. **Do them in order — each is harder than the last.**

> [!TIP]
> Push every project to GitHub with a proper README, screenshots, and a live demo. A junior portfolio with 5 polished, typed projects beats a CS degree with no projects.

### Project 1: Typed CLI Tool — Smart `ls` / Folder Stats
![Phase 1-5](https://img.shields.io/badge/After-Phase%201--5-green)

**What you'll build:** A Node CLI written in TS that scans a folder and prints typed stats — file count by extension, total size, biggest files, oldest files. Handle command-line args with [`commander`](https://github.com/tj/commander.js) or `node:util parseArgs`. Strictly type every option and result.

**Skills practiced:** Basic types, unions, narrowing, `tsx` / `tsc` setup, `@types/node`, modules.

**Stretch goal:** Add a `--watch` mode that re-prints stats when files change.

---

### Project 2: Type-Safe Form Builder (React)
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A form library where you describe fields as a typed config (`{ name: "email", type: "email", required: true }`) and the resulting form values are **inferred** as a typed object. Render with React + `react-hook-form` + Zod.

**Skills practiced:** Generics, mapped types, conditional types, `infer`, discriminated unions, React + TS.

**Stretch goal:** Generate a Zod schema from the same config, with full type inference.

---

### Project 3: Drizzle + Hono Typed API
![Phase 8-12](https://img.shields.io/badge/After-Phase%208--12-yellow)

**What you'll build:** A typed REST API for a small "Tasks" app. Hono on Bun (or Node), Drizzle for Postgres, Zod for input/output validation, environment validated at boot. CRUD endpoints fully typed end-to-end. Deploy to Cloudflare Workers or Fly.io.

**Skills practiced:** TS + Node setup, Drizzle types, Zod, declaration files, env validation, deployment.

**Stretch goal:** Add auth (JWT or sessions) with typed roles.

---

### Project 4: tRPC Full-Stack To-Do
![Phase 11-12](https://img.shields.io/badge/After-Phase%2011--12-red)

**What you'll build:** A Next.js + tRPC + Drizzle + TanStack Query app. The frontend imports the tRPC router type from the server — no codegen, no manual types. Add a column on the server, and the typed client lights up immediately.

**Skills practiced:** End-to-end type sharing, generics in real codebases, React + TS hooks, server/client integration.

**Stretch goal:** Multi-tenant with workspaces, fully typed permissions.

---

### Project 5: Type-Safe Markdown Note App with Search
![Phase 9-11](https://img.shields.io/badge/After-Phase%209--11-yellow)

**What you'll build:** A Notion-lite — create / edit / delete markdown notes, live preview, full-text search, tags, dark mode, IndexedDB persistence. All interactions strictly typed; sanitize HTML with DOMPurify.

**Skills practiced:** Modules, classes, strict mode, browser API typing, custom hooks.

**Stretch goal:** Cloud sync via tRPC + Drizzle backend.

---

### Project 6: TypeScript Library on npm
![Phase 9-10-13](https://img.shields.io/badge/After-Phase%209--10--13-red)

**What you'll build:** A small, real utility library (e.g. typed event emitter, typed `Result` helper, schema-driven query builder). Build with [`tsup`](https://tsup.egoist.dev/), publish `.d.ts`, write tests with Vitest, add type tests with `expect-type` or `tsd`, set up Changesets for versioning, and publish to npm under your scope.

**Skills practiced:** Declaration files, `tsconfig` deep-dive, generics, build tooling, package authoring.

**Stretch goal:** Add a CHANGELOG generator on every release with Changesets + GitHub Actions.

---

### Project 7: Internal Dashboard with Charts (Next.js + shadcn/ui)
![Phase 11-13](https://img.shields.io/badge/After-Phase%2011--13-red)

**What you'll build:** A typed analytics dashboard — auth, KPIs, charts (Recharts or Tremor), filtering, CSV export. Server Components for data fetching, Client Components for interactivity, Zod for env and input parsing.

**Skills practiced:** Next.js App Router types, Server Components, Server Actions, Zod, generics for typed table components.

**Stretch goal:** Real-time updates via Server-Sent Events with a typed client.

---

### Project 8: AI-Powered Capstone — Type-Safe LLM App
![Phase 12-14](https://img.shields.io/badge/After-Phase%2012--14-red)

**What you'll build:** Your graduation project. A streaming AI chat with **tools** — fully typed end-to-end. Vercel AI SDK's `streamText` with Zod-typed tool inputs/outputs, Drizzle for persistence, tRPC for API, Next.js + shadcn/ui for the UI, Clerk for auth, deployed on Vercel. Bonus: wrap critical tool calls in a runtime `Result<T>` and surface errors as typed UI states.

**Skills practiced:** Everything from all 14 phases — generics, Zod, AI SDK types, end-to-end type safety, deployment, observability. **This is portfolio gold.**

**Stretch goal:** Multi-model fallback (Claude + GPT) via Vercel AI Gateway with typed provider routing.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) | The official docs — concise, accurate, well-organized. Start here |
| [TypeScript Playground](https://www.typescriptlang.org/play) | Browser-based TS sandbox — paste, share, and try every config option |
| [Release Notes](https://www.typescriptlang.org/docs/handbook/release-notes/overview.html) | Every TS version with examples — the best changelog in the JS world |
| [TypeScript Deep Dive (Basarat)](https://basarat.gitbook.io/typescript) | Free book covering everything from fundamentals to advanced patterns |
| [Total TypeScript Tips](https://www.totaltypescript.com/tips) | Matt Pocock's free, searchable, deeply practical TS tips |

### Books

| Book | Why Read |
|------|----------|
| [Effective TypeScript](https://effectivetypescript.com/) — Dan Vanderkam | 83 specific items every TS dev should know. The closest thing to a TS canon |
| [Programming TypeScript](https://www.oreilly.com/library/view/programming-typescript/9781492037644/) — Boris Cherny | Comprehensive deep dive — types, generics, advanced patterns |
| [Total TypeScript](https://www.totaltypescript.com/) — Matt Pocock | Paid course-as-a-book — the most modern TS curriculum on the planet |
| [TypeScript Quickly](https://www.manning.com/books/typescript-quickly) — Yakov Fain & Anton Moiseev | Hands-on, project-based, friendly to JS developers |

### Free Courses

| Course | What Makes It Special |
|--------|----------------------|
| [Total TypeScript — Beginners TypeScript](https://www.totaltypescript.com/tutorials/beginners-typescript) | Free Pocock tutorial — the gentlest serious intro |
| [Execute Program — TypeScript](https://www.executeprogram.com/courses/typescript) | Spaced-repetition TS — interactive, sticks |
| [TypeHero](https://typehero.dev/) | Practice TS challenges in your browser, gamified |
| [Type Challenges](https://github.com/type-challenges/type-challenges) | 200+ pure type-level puzzles, all difficulty levels |
| [freeCodeCamp — TS Crash Course](https://www.youtube.com/watch?v=30LWjhZzg50) | 3+ hour fundamentals video |
| [Microsoft Learn — TypeScript](https://learn.microsoft.com/en-us/training/paths/build-javascript-applications-typescript/) | First-party Microsoft curriculum |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Matt Pocock](https://www.youtube.com/@mattpocockuk) | The premier TS educator. Bite-size advanced TS clips, explained crisply |
| [Theo (t3.gg)](https://www.youtube.com/@t3dotgg) | Modern TS / React opinions, current tooling, what to use today |
| [Jack Herrington](https://www.youtube.com/@jherr) | Deep dives on TS, React, and full-stack patterns |
| [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified) | Short, focused TS topics with hands-on examples |
| [Fireship](https://www.youtube.com/@Fireship) | "100 seconds of TS" — fast visual explainers |
| [ByteGrad](https://www.youtube.com/@ByteGrad) | TS + React + Next career-focused tutorials |
| [Beyond Fireship](https://www.youtube.com/@beyondfireship) | Deeper-than-Fireship walkthroughs |

### Practice & Coding Challenges

| Platform | What You Get |
|----------|-------------|
| [Type Challenges](https://github.com/type-challenges/type-challenges) | 200+ type-level puzzles — easy → extreme. The interview-prep gold standard |
| [TypeHero](https://typehero.dev/) | Browser-based TS challenges, leaderboards |
| [Exercism — TypeScript Track](https://exercism.org/tracks/typescript) | 80+ exercises with mentor feedback, free |
| [Codewars — TypeScript](https://www.codewars.com/?language=typescript) | Gamified katas in TS |
| [Frontend Mentor](https://www.frontendmentor.io/) | Real designs to build with React + TS |
| [LeetCode](https://leetcode.com/) | Interview prep — all problems solvable in TS |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — TypeScript](https://roadmap.sh/typescript) | Interactive learning path — click each topic for resources |
| [roadmap.sh — Frontend](https://roadmap.sh/frontend) | Where TS fits in the broader frontend stack |
| [roadmap.sh — Backend](https://roadmap.sh/backend) | Where TS fits on the server side |

### Tools

| Tool | Why You Need It |
|------|----------------|
| [TypeScript ESLint](https://typescript-eslint.io/) | TS-aware ESLint rules — non-negotiable |
| [Biome](https://biomejs.dev/) | All-in-one Rust-based lint + format. Replaces ESLint + Prettier in many setups |
| [Prettier](https://prettier.io/) | Opinionated formatter — no more arguments |
| [tsx](https://tsx.is/) | Run `.ts` files directly with zero config |
| [tsup](https://tsup.egoist.dev/) | Bundle libraries with `.d.ts` output, no config |
| [Vitest](https://vitest.dev/) | TS-native test runner — Vite speed, Jest API |
| [TypeScript Error Translator](https://ts-error-translator.vercel.app/) | Plain-English explanations of confusing TS errors |
| [ts-reset](https://github.com/total-typescript/ts-reset) | Pocock's set of safer built-in type fixes (`JSON.parse`, `fetch`...) |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [TypeScript Cheat Sheets](https://www.typescriptlang.org/cheatsheets) | Official PDFs — types, control flow, classes, interfaces |
| [type-fest README](https://github.com/sindresorhus/type-fest#api) | Living index of every utility type, with examples |
| [Total TypeScript Cheat Sheets](https://www.totaltypescript.com/cheatsheets) | Matt Pocock's modern PDFs |
| [React TypeScript Cheatsheets](https://react-typescript-cheatsheet.netlify.app/) | The community reference for React + TS |
| [TypeScript Handbook Reference](https://www.typescriptlang.org/docs/handbook/utility-types.html) | All the built-in utility types in one page |

### Newsletters & Podcasts

| Resource | Format |
|----------|--------|
| [Total TypeScript Tips](https://www.totaltypescript.com/tips) | Free, frequent TS tips by Matt Pocock |
| [TypeScript Weekly](https://typescript-weekly.com/) | Weekly newsletter — TS news, articles, releases |
| [JavaScript Weekly](https://javascriptweekly.com/) | Broader JS/TS news weekly |
| [Frontend Focus](https://frontendfoc.us/) | Weekly newsletter — frontend ecosystem |
| [Syntax.fm](https://syntax.fm/) | Wes Bos & Scott Tolinski — fun, opinionated, frequent TS coverage |
| [JS Party](https://changelog.com/jsparty) | Weekly podcast on JS, TS, and the web platform |

---

[Back to Main Syllabus](../README.md)

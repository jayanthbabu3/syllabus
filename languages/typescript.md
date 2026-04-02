# TypeScript Syllabus

A complete, structured learning path for TypeScript — from your first type annotation to advanced generics, conditional types, and production-ready patterns.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Basic Types](#phase-2-basic-types)
- [Phase 3: Objects & Interfaces](#phase-3-objects--interfaces)
- [Phase 4: Functions](#phase-4-functions)
- [Phase 5: Generics](#phase-5-generics)
- [Phase 6: Advanced Types](#phase-6-advanced-types)
- [Phase 7: Classes & OOP](#phase-7-classes--oop)
- [Phase 8: Modules & Declaration Files](#phase-8-modules--declaration-files)
- [Phase 9: TypeScript with React](#phase-9-typescript-with-react)
- [Phase 10: Advanced Patterns & Best Practices](#phase-10-advanced-patterns--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> TypeScript is a **typed superset of JavaScript**. You must know JavaScript well before learning TypeScript — especially ES6+ features.

- JavaScript fundamentals (complete the [JavaScript Syllabus](javascript.md) first)
- ES6+: arrow functions, destructuring, spread/rest, classes, modules, promises
- Node.js and npm installed
- Familiarity with the command line

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand why TypeScript exists and write your first type-safe code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is TypeScript | A typed superset of JavaScript — catches errors at compile time, compiles to plain JS |
| 2 | Why TypeScript | Autocomplete, refactoring, catch bugs before running, self-documenting code |
| 3 | Installation | `npm install -g typescript` or per-project: `npm install -D typescript` |
| 4 | `tsconfig.json` | The configuration file — `target`, `strict`, `outDir`, `rootDir`, `esModuleInterop` |
| 5 | Your First `.ts` File | Write TypeScript, compile with `tsc`, see the generated JavaScript output |
| 6 | Running TypeScript | `tsc` (compile), `ts-node` (run directly), `tsx` (fast runner), Vite (for web) |
| 7 | Type Annotations | `let name: string = "Alice"` — tell TypeScript what type a variable holds |
| 8 | Type Inference | TypeScript often figures out the type automatically — you don't need to annotate everything |

> [!TIP]
> Enable `"strict": true` in `tsconfig.json` from day one. It enables all strict checks. Starting strict is easier than migrating to strict later:
> ```json
> {
>   "compilerOptions": {
>     "strict": true,
>     "target": "ES2020",
>     "module": "ESNext",
>     "outDir": "./dist"
>   }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install TypeScript and create a `tsconfig.json`
- [ ] Write a `.ts` file, compile it, and run the output
- [ ] Explain the difference between TypeScript and JavaScript

</details>

---

## Phase 2: Basic Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Learn every primitive type and when to use each one.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `string`, `number`, `boolean` | The three basic primitives — same as JavaScript but explicitly typed |
| 2 | Arrays | `string[]` or `Array<string>` — typed arrays that only hold one type |
| 3 | Tuples | `[string, number]` — fixed-length arrays where each position has a specific type |
| 4 | Enums | `enum Direction { Up, Down }` — named constants. Numeric by default, can be string enums |
| 5 | `any` | Disables all type checking. Escape hatch for gradual migration — **avoid in new code** |
| 6 | `unknown` | Type-safe version of `any` — you must narrow the type before using the value |
| 7 | `void` | Function returns nothing: `function log(msg: string): void {}` |
| 8 | `never` | Function never returns: throws an error or has an infinite loop. Used for exhaustive checks |
| 9 | Literal Types | `let status: "active" \| "inactive"` — restrict to exact values, not just the type |
| 10 | Type Assertions | `value as string` — tell TypeScript "I know the type". Use sparingly — it bypasses safety |

> [!CAUTION]
> **`any` defeats the entire purpose of TypeScript.** Every time you use `any`, you lose type safety for that value and everything it touches. Use `unknown` instead — it forces you to check the type before using it:
> ```typescript
> // BAD — no safety
> function process(data: any) {
>   data.toUpperCase(); // no error, crashes at runtime if data isn't a string
> }
>
> // GOOD — must narrow first
> function process(data: unknown) {
>   if (typeof data === "string") {
>     data.toUpperCase(); // safe — TypeScript knows it's a string
>   }
> }
> ```

<details>
<summary><strong>Quick Reference: Type Hierarchy</strong></summary>

```
                    unknown (top type — accepts anything)
                        │
    ┌───────────┬───────┼───────┬───────────┐
    │           │       │       │           │
  string     number  boolean  object     symbol
    │           │       │       │
  "hello"      42    true    { key: val }
  "world"     3.14   false   Function
                              Array
                                │
                              never (bottom type — nothing)
```

> `unknown` accepts any value (top). `never` has no value (bottom). Everything else is in between.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables with all basic types
- [ ] Explain the difference between `any`, `unknown`, and `never`
- [ ] Use literal types to restrict values to specific options

</details>

---

## Phase 3: Objects & Interfaces

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Define the shape of your data with types and interfaces.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Type Aliases | `type Point = { x: number; y: number }` — give a name to any type shape |
| 2 | Interfaces | `interface User { name: string; age: number }` — define contracts for objects |
| 3 | Type vs Interface | Interfaces support declaration merging and `extends`. Types support unions and primitives. Use interface for objects, type for everything else |
| 4 | Optional Properties | `age?: number` — property may or may not exist. Access safely with `?.` |
| 5 | Readonly Properties | `readonly id: string` — can be set once, then never changed |
| 6 | Union Types | `string \| number` — value can be one of several types. Narrow with type guards |
| 7 | Intersection Types | `type Admin = User & { role: string }` — combine multiple types into one |
| 8 | Index Signatures | `{ [key: string]: number }` — objects with dynamic property names |
| 9 | Extending Interfaces | `interface Admin extends User { role: string }` — inherit and add properties |
| 10 | Structural Typing | TypeScript checks shape, not name. Two types with the same structure are compatible |

> [!IMPORTANT]
> **`type` vs `interface` — the simple rule:**
> - Use `interface` for object shapes (can be extended and merged)
> - Use `type` for unions, primitives, tuples, and anything that isn't an object shape
> - For objects, `interface` is slightly faster (cached internally) and supports declaration merging

<details>
<summary><strong>Quick Reference: type vs interface</strong></summary>

| Feature | `type` | `interface` |
|---------|:------:|:-----------:|
| Object shapes | Yes | Yes |
| Union types | Yes | No |
| Primitive aliases | Yes | No |
| Tuples | Yes | No |
| `extends` | No (use `&`) | Yes |
| Declaration merging | No | Yes |
| Computed properties | Yes | No |
| Performance (objects) | Recomputed | Cached |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Define types and interfaces for real data structures
- [ ] Use union and intersection types together
- [ ] Explain TypeScript's structural typing with an example

</details>

---

## Phase 4: Functions

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Write fully typed functions — parameters, returns, overloads, and generics.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Parameter Types | `function greet(name: string)` — always type your parameters explicitly |
| 2 | Return Types | `function add(a: number, b: number): number` — TypeScript infers returns, but explicit is clearer |
| 3 | Optional & Default Params | `function greet(name: string, greeting?: string)` and `greeting = "Hello"` |
| 4 | Rest Parameters | `function sum(...nums: number[]): number` — typed variadic functions |
| 5 | Function Type Expressions | `type Callback = (data: string) => void` — type a function signature as a value |
| 6 | Arrow Function Types | `const add: (a: number, b: number) => number = (a, b) => a + b` |
| 7 | Function Overloads | Multiple signatures for one function — TypeScript picks the right one based on arguments |
| 8 | `void` vs `undefined` | `void` means "ignore the return". `undefined` means "must return undefined explicitly" |
| 9 | Generic Functions (Intro) | `function identity<T>(value: T): T` — the `T` placeholder works with any type |

> [!TIP]
> Always annotate **parameters**. Let TypeScript **infer returns** for internal functions. Annotate returns explicitly for public APIs and exported functions:
> ```typescript
> // Internal — infer return type
> function double(n: number) {
>   return n * 2; // TypeScript infers: number
> }
>
> // Exported API — annotate return type
> export function fetchUser(id: string): Promise<User> {
>   return api.get(`/users/${id}`);
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with typed parameters, optional params, and rest params
- [ ] Create a function type alias and use it as a callback type
- [ ] Write a simple generic function

</details>

---

## Phase 5: Generics

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable, type-safe code that works with any type — the most powerful TypeScript feature.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Generic Functions | `function wrap<T>(value: T): T[]` — `T` is a placeholder that gets filled in when you call it |
| 2 | Multiple Generics | `function pair<A, B>(a: A, b: B): [A, B]` — use multiple type parameters |
| 3 | Generic Constraints | `<T extends { length: number }>` — restrict what types `T` can be |
| 4 | `keyof` Constraint | `<T, K extends keyof T>` — ensure `K` is a valid key of `T` |
| 5 | Generic Interfaces | `interface Container<T> { value: T }` — reusable typed containers |
| 6 | Default Generic Types | `interface Response<T = any>` — provide a fallback type when none is specified |
| 7 | Generic Inference | TypeScript infers `T` from how you call the function — you often don't need `<string>` explicitly |
| 8 | Utility Types | `Partial<T>`, `Required<T>`, `Readonly<T>`, `Pick<T, K>`, `Omit<T, K>`, `Record<K, T>` — built-in type transformers |

> [!IMPORTANT]
> Generics are **the** concept that separates TypeScript beginners from intermediate developers. If `<T>` confuses you, think of it as a **function parameter, but for types**:
> ```typescript
> // Regular function: "n" is a placeholder for a value
> function double(n: number) { return n * 2; }
>
> // Generic: "T" is a placeholder for a type
> function identity<T>(value: T): T { return value; }
>
> identity("hello"); // T = string (inferred)
> identity(42);      // T = number (inferred)
> ```

<details>
<summary><strong>Quick Reference: Built-in Utility Types</strong></summary>

| Utility Type | What It Does | Example |
|-------------|-------------|---------|
| `Partial<T>` | All properties optional | `Partial<User>` → all fields are `?` |
| `Required<T>` | All properties required | `Required<Config>` → no `?` fields |
| `Readonly<T>` | All properties readonly | `Readonly<User>` → can't modify |
| `Pick<T, K>` | Keep only specified keys | `Pick<User, "id" \| "name">` |
| `Omit<T, K>` | Remove specified keys | `Omit<User, "password">` |
| `Record<K, T>` | Object with K keys and T values | `Record<string, number>` |
| `Exclude<T, U>` | Remove types from union | `Exclude<"a" \| "b" \| "c", "a">` → `"b" \| "c"` |
| `Extract<T, U>` | Keep matching types from union | `Extract<string \| number, string>` → `string` |
| `NonNullable<T>` | Remove `null` and `undefined` | `NonNullable<string \| null>` → `string` |
| `ReturnType<T>` | Extract function return type | `ReturnType<typeof fn>` |
| `Parameters<T>` | Extract function params as tuple | `Parameters<typeof fn>` |
| `Awaited<T>` | Unwrap Promise type | `Awaited<Promise<string>>` → `string` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a generic function with constraints
- [ ] Use `Pick`, `Omit`, and `Partial` to transform existing types
- [ ] Explain why generics are better than `any`

</details>

---

## Phase 6: Advanced Types

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Transform, combine, and manipulate types — TypeScript's type system is a programming language of its own.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Type Guards | `typeof`, `instanceof`, `in`, and custom type predicates (`value is Type`) — narrow types at runtime |
| 2 | Discriminated Unions | Add a literal `kind` field to each type in a union — enables exhaustive `switch` statements |
| 3 | Conditional Types | `T extends string ? "yes" : "no"` — ternary operator for types |
| 4 | `infer` Keyword | Extract parts of a type: `T extends Promise<infer R> ? R : T` — captures the inner type |
| 5 | Mapped Types | `{ [K in keyof T]: boolean }` — iterate over keys and transform each property |
| 6 | Key Remapping | `{ [K in keyof T as \`get${Capitalize<K>}\`]: () => T[K] }` — rename keys during mapping |
| 7 | Template Literal Types | `` `${A}-${B}` `` — combine string types: `"get" \| "set"` + `"Name" \| "Age"` = `"getName" \| "getAge" \| ...` |
| 8 | Exhaustive Checking | Use `never` in the default case to ensure every union member is handled |
| 9 | Recursive Types | Types that reference themselves: `type NestedArray<T> = T \| NestedArray<T>[]` |
| 10 | Type Compatibility | Structural subtyping — an object with extra properties is still assignable to a type with fewer |

> [!TIP]
> **Discriminated unions** are the most practical advanced type. Use them for API responses, state machines, and action types:
> ```typescript
> type Result<T> =
>   | { status: "success"; data: T }
>   | { status: "error"; message: string }
>   | { status: "loading" };
>
> function handle(result: Result<User>) {
>   switch (result.status) {
>     case "success": return result.data;    // TypeScript knows: { data: User }
>     case "error":   return result.message;  // TypeScript knows: { message: string }
>     case "loading": return "Loading...";
>   }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a custom type guard function
- [ ] Implement a discriminated union with exhaustive checking
- [ ] Create a mapped type that transforms object properties

</details>

---

## Phase 7: Classes & OOP

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Build object-oriented code with TypeScript's class features and access control.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Class Basics | Constructor, properties, methods — same as JS classes but with types |
| 2 | Access Modifiers | `public` (default, anyone), `private` (class only), `protected` (class + subclasses) |
| 3 | Parameter Properties | `constructor(private name: string)` — shorthand that declares and assigns in one line |
| 4 | Readonly Properties | `readonly id: string` — set in constructor, immutable after |
| 5 | Getters & Setters | `get fullName()` / `set fullName()` — computed properties with validation logic |
| 6 | Static Members | `static count = 0` — belong to the class, not instances. Called as `User.count` |
| 7 | Inheritance | `class Admin extends User` — `super()`, method overriding, calling parent methods |
| 8 | Abstract Classes | `abstract class Shape` — can't be instantiated, forces subclasses to implement methods |
| 9 | `implements` | `class Dog implements Animal` — class must satisfy the interface contract |
| 10 | Decorators | `@log`, `@injectable` — experimental feature for adding metadata/behavior to classes |

> [!NOTE]
> Modern TypeScript and React favor **functions and composition** over classes. Classes are still important for understanding libraries (Angular, NestJS, TypeORM) and design patterns, but don't default to them for everything.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with `private`, `public`, and `protected` members
- [ ] Use `abstract` to force subclasses to implement specific methods
- [ ] Implement an interface with a class

</details>

---

## Phase 8: Modules & Declaration Files

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Organize code across files and add types to libraries that don't have them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | ES Modules with TS | `import { User } from './types'` and `export interface User {}` — same as JS, TypeScript resolves types |
| 2 | Type-Only Imports | `import type { User } from './types'` — imported for types only, removed at compile time |
| 3 | Declaration Files (`.d.ts`) | Type definitions without implementation — describe the shape of JS libraries |
| 4 | `@types` Packages | `npm install -D @types/lodash` — community-maintained types for JS libraries (DefinitelyTyped) |
| 5 | The `declare` Keyword | `declare const API_URL: string` — tell TypeScript about global variables from outside |
| 6 | Module Augmentation | `declare module 'express' { interface Request { userId: string } }` — extend external library types |
| 7 | Path Mapping | `"paths": { "@/*": ["./src/*"] }` in `tsconfig.json` — clean import paths |
| 8 | Publishing Types | Ship `.d.ts` files with your npm package so consumers get type safety |

> [!TIP]
> Use `import type` to make it clear you're only importing types. It keeps your bundles clean — these imports are completely removed at compile time:
> ```typescript
> // Regular import — included in bundle
> import { formatDate } from './utils';
>
> // Type-only import — removed at compile time
> import type { User, Post } from './types';
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `import type` for type-only imports
- [ ] Install and use `@types` packages for untyped libraries
- [ ] Write a `.d.ts` declaration file for a simple JS module

</details>

---

## Phase 9: TypeScript with React

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Type your React components, hooks, events, and context properly.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Setting Up | `npm create vite@latest my-app -- --template react-ts` — React + TypeScript with Vite |
| 2 | Typing Props | `interface Props { title: string; count?: number }` + `function Card({ title }: Props)` |
| 3 | `children` Prop | `children: React.ReactNode` — the correct type for anything renderable |
| 4 | Typing `useState` | `useState<User \| null>(null)` — generic type for state, especially useful for nullable initial state |
| 5 | Typing `useRef` | `useRef<HTMLInputElement>(null)` — type the DOM element you're referencing |
| 6 | Typing Events | `(e: React.ChangeEvent<HTMLInputElement>)` — every event handler has a specific type |
| 7 | Typing Context | `createContext<ThemeContextType \| null>(null)` — type the context value with a generic |
| 8 | Typing `useReducer` | Type the state, actions (discriminated union), and reducer function |
| 9 | Generic Components | `function List<T>({ items, renderItem }: Props<T>)` — components that work with any data type |
| 10 | Typing Custom Hooks | Return typed tuples or objects from hooks, use generics for flexible hooks |

> [!TIP]
> The most common React + TypeScript event types:
> ```typescript
> onClick:  (e: React.MouseEvent<HTMLButtonElement>) => void
> onChange: (e: React.ChangeEvent<HTMLInputElement>) => void
> onSubmit: (e: React.FormEvent<HTMLFormElement>) => void
> onKeyDown: (e: React.KeyboardEvent<HTMLInputElement>) => void
> ```

<details>
<summary><strong>Quick Reference: React TypeScript Patterns</strong></summary>

```typescript
// Typing component props
interface CardProps {
  title: string;
  description?: string;      // optional
  children: React.ReactNode;  // anything renderable
  onClick: () => void;        // callback
}

// Typing useState with union
const [user, setUser] = useState<User | null>(null);

// Typing useRef for DOM elements
const inputRef = useRef<HTMLInputElement>(null);

// Typing event handlers
const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  setName(e.target.value);
};

// Generic component
interface ListProps<T> {
  items: T[];
  renderItem: (item: T) => React.ReactNode;
}
function List<T>({ items, renderItem }: ListProps<T>) {
  return <ul>{items.map(renderItem)}</ul>;
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a React component with fully typed props (including `children`)
- [ ] Type `useState`, `useRef`, and event handlers correctly
- [ ] Build a generic component that works with any data type

</details>

---

## Phase 10: Advanced Patterns & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write production-ready TypeScript — migration strategies, error patterns, and config mastery.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Strict Mode Deep Dive | Every `strict` flag explained: `strictNullChecks`, `noImplicitAny`, `strictFunctionTypes`, `noUncheckedIndexedAccess` |
| 2 | Migrating JS to TS | Rename `.js` → `.ts`, enable `allowJs`, add types gradually file by file. Don't rewrite everything at once |
| 3 | Error Handling Patterns | `Result<T, E>` type, discriminated union errors, avoid `throw` for expected failures |
| 4 | `tsconfig.json` Mastery | Project references, composite builds, multiple configs (dev/prod/test), `paths` for aliases |
| 5 | Performance | Speed up compilation: `incremental: true`, `skipLibCheck: true`, avoid deep type intersections |
| 6 | Testing with TypeScript | Type-safe tests with Vitest/Jest, testing types themselves, `@testing-library` types |
| 7 | Validation at Boundaries | Types don't exist at runtime. Use Zod or Valibot at API boundaries to validate external data |
| 8 | Advanced Utility Patterns | `ReturnType`, `Parameters`, `Awaited`, `ThisParameterType`, custom utility types |
| 9 | Monorepo Patterns | Shared types across packages, project references, `composite: true`, path mapping |
| 10 | Documentation | JSDoc comments in TypeScript for IDE tooltips, auto-generated API docs from types |

> [!WARNING]
> **TypeScript types don't exist at runtime.** A type annotation doesn't validate data — it only checks at compile time. Always validate external data (API responses, user input, env vars) with a runtime validator:
> ```typescript
> import { z } from 'zod';
>
> // Type says it's a User — but is it really?
> const userSchema = z.object({
>   name: z.string(),
>   email: z.string().email(),
> });
>
> // Now it's validated AND typed
> const user = userSchema.parse(apiResponse);
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Configure `tsconfig.json` with strict mode and path aliases
- [ ] Migrate a small JavaScript project to TypeScript
- [ ] Use Zod to validate API responses at runtime

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most TypeScript learners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `any` everywhere | Disables all type checking — defeats the purpose of TypeScript | Use `unknown` and narrow with type guards |
| 2 | Disabling strict mode | Hides bugs, creates technical debt, makes migration harder | Enable `"strict": true` from the start |
| 3 | Type assertions over guards | `value as string` bypasses safety — no runtime check | Use `typeof`, `instanceof`, or custom type predicates |
| 4 | Ignoring `null`/`undefined` | "Cannot read property of undefined" — the #1 runtime error | Enable `strictNullChecks`, use optional chaining (`?.`) |
| 5 | Using `interface` for unions | Interfaces can't represent `string \| number` | Use `type` for unions, primitives, tuples |
| 6 | Not using utility types | Duplicating type definitions instead of deriving them | Use `Pick`, `Omit`, `Partial`, `ReturnType` to build from existing types |
| 7 | Confusing structural typing | Expecting types to be compared by name (like Java) | TypeScript compares by shape — same structure = compatible |
| 8 | Over-typing everything | Annotating types that TypeScript already infers correctly | Let inference work. Annotate parameters; infer returns (for internal code) |
| 9 | Ignoring `@types` packages | Writing manual types for popular libraries that already have types | Check for `@types/library-name` on npm first |
| 10 | Mixing `export type` and `export` | Types that should be removed at compile time end up in the bundle | Use `import type` / `export type` for type-only exports |

---

## Interview Questions

Test your TypeScript knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is TypeScript and why use it?**
   - TypeScript is a typed superset of JavaScript that compiles to plain JS. Benefits: catch bugs at compile time (not runtime), better IDE autocomplete, self-documenting code, safer refactoring. All valid JS is valid TS.

2. **What's the difference between `any` and `unknown`?**
   - `any` disables all type checking — you can do anything with it. `unknown` is the type-safe version — you must narrow the type (with `typeof`, `instanceof`, etc.) before using the value. Always prefer `unknown`.

3. **`type` vs `interface` — when do you use each?**
   - `interface` for object shapes (supports `extends`, declaration merging, cached internally). `type` for unions (`string | number`), primitives, tuples, and anything non-object. For objects, either works — `interface` is slightly preferred due to performance and extensibility.

4. **What are type assertions?**
   - `value as Type` tells TypeScript "I know the type". It's a compile-time override — no runtime check. Unsafe because it bypasses type safety. Prefer type guards (`typeof`, `instanceof`) which provide both compile-time and runtime safety.

5. **Explain the `never` type.**
   - `never` represents values that never occur: functions that always throw, infinite loops, unreachable code. Key use: exhaustive checking in switch statements — `const _: never = unmatchedCase` will error if a union member is unhandled.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain generics with a practical example.**
   - Generics are type parameters (like function arguments, but for types). `function identity<T>(value: T): T` — `T` is inferred from usage. Constraints: `<T extends { id: string }>` restricts T. Use cases: typed containers, utility functions, React components that work with any data.

2. **Name 5 utility types and what they do.**
   - `Partial<T>`: all properties optional. `Readonly<T>`: all properties immutable. `Pick<T, K>`: select specific keys. `Omit<T, K>`: remove specific keys. `Record<K, T>`: object with K keys and T values. Others: `ReturnType<T>`, `Parameters<T>`, `Exclude<T, U>`, `NonNullable<T>`, `Awaited<T>`.

3. **What is a discriminated union?**
   - A union where each member has a common literal field (the "discriminant") that TypeScript uses for narrowing. Example: `{ status: "success"; data: T } | { status: "error"; message: string }`. In a switch on `status`, TypeScript knows the exact type in each case. Enables exhaustive checking.

4. **How do type guards work?**
   - Type guards narrow a union type to a specific member. Built-in: `typeof x === "string"`, `x instanceof Date`, `"key" in obj`. Custom: `function isUser(x: unknown): x is User { ... }` — the `x is User` return type tells TypeScript the narrowed type. Runtime check + compile-time narrowing.

5. **What is structural typing?**
   - TypeScript checks type compatibility by structure (shape), not by name. If two types have the same properties, they're compatible — even if they have different names. This is unlike Java/C# (nominal typing). Implication: a function accepting `{ name: string }` will accept any object that has a `name: string`, regardless of its declared type.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain conditional types and the `infer` keyword.**
   - Conditional types: `T extends U ? X : Y` — if T matches U, resolve to X, else Y. `infer` captures a type inside a conditional: `T extends Promise<infer R> ? R : T` extracts the Promise's inner type. Distributive behavior: when T is a union, the condition is applied to each member. This is how `ReturnType<T>` and `Parameters<T>` work.

2. **How do mapped types work?**
   - Mapped types iterate over keys and transform each property: `{ [K in keyof T]: boolean }` turns all properties to boolean. Key remapping (`as`) lets you rename keys: `[K in keyof T as \`get${Capitalize<K>}\`]`. Combined with conditionals and template literals, you can build powerful type transformations. Built-in utilities like `Partial`, `Readonly`, `Pick` are implemented as mapped types.

3. **What is declaration merging?**
   - When you declare the same `interface` name twice, TypeScript merges them into one: both sets of properties are included. Works for interfaces and namespaces. Does NOT work for `type` aliases. Use case: augmenting library types (`declare module 'express' { interface Request { userId: string } }`) without modifying the library's source code.

4. **Explain template literal types.**
   - String types with interpolation: `` type Route = \`/api/${string}\` ``. Unions multiply: `"get" | "set"` + `"Name" | "Age"` = `"getName" | "getAge" | "setName" | "setAge"`. Combined with mapped types and key remapping, you can auto-generate property names. Built-in string manipulators: `Uppercase<T>`, `Lowercase<T>`, `Capitalize<T>`.

5. **How do you ensure type safety at runtime boundaries?**
   - TypeScript types are erased at compile time — they don't exist at runtime. For external data (API responses, user input, env vars, file reads), use a runtime validation library: Zod (`z.object({}).parse(data)`), Valibot, or io-ts. The validator checks the data AND infers the TypeScript type. Without validation, `apiResponse as User` is unsafe — it's a lie to the compiler.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Type-Safe CLI Tool
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A command-line note-taking app with typed data structures, file storage (JSON), and input validation.

**Skills practiced:** Basic types, interfaces, type aliases, union types, file I/O with types.

---

### Project 2: Generic Data Structures
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A library with typed `Stack<T>`, `Queue<T>`, `LinkedList<T>`, and `HashMap<K, V>` — all with full generic support.

**Skills practiced:** Generics, constraints, utility types, function types, classes.

---

### Project 3: REST API with Express
![Phase 6-8](https://img.shields.io/badge/After-Phase%206--8-yellow)

**What you'll build:** A typed REST API with Express: request/response types, middleware typing, error handling with discriminated unions, module organization.

**Skills practiced:** Advanced types, declaration files, module augmentation, discriminated unions, type guards.

---

### Project 4: React App with Full Typing
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** A full React application (todo/task manager) with typed components, hooks, context, router, and Zod validation on API responses.

**Skills practiced:** React + TypeScript patterns, generic components, typed hooks, event handling, runtime validation.

---

### Project 5: Type Challenge Solver
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** Solve 20+ challenges from [Type Challenges](https://github.com/type-challenges/type-challenges) — from Easy to Hard difficulty.

**Skills practiced:** Conditional types, mapped types, template literals, `infer`, recursive types — your TypeScript graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) | The official handbook by Microsoft. Covers every feature with clear examples |
| [TypeScript Playground](https://www.typescriptlang.org/play/) | Try TypeScript in the browser. See compiled JS output, share code via URL |
| [TSConfig Reference](https://www.typescriptlang.org/tsconfig/) | Every compiler option explained. Bookmark this for `tsconfig.json` questions |
| [Total TypeScript (Matt Pocock)](https://www.totaltypescript.com/) | The best TypeScript educator. Free tutorials, exercises, and a comprehensive learning path |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Total TypeScript — Free Tutorials](https://www.totaltypescript.com/tutorials) | Exercise-driven learning from the best TS educator. Editor-first, not lecture-based |
| [Type Challenges](https://github.com/type-challenges/type-challenges) | 200+ type-system puzzles from Warm Up to Extreme. The gym for TypeScript's type system |
| [freeCodeCamp — TypeScript Course](https://www.freecodecamp.org/news/learn-typescript-beginners-guide/) | Free full course with projects and certification |
| [Codecademy — Learn TypeScript](https://www.codecademy.com/learn/learn-typescript) | In-browser coding with instant feedback. Step-by-step lessons |
| [Learning TypeScript](https://www.learningtypescript.org/) | Interactive playground with exercises — practice each concept immediately |
| [W3Schools TypeScript](https://www.w3schools.com/typescript/) | "Try It Yourself" editor. Quick reference for syntax |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Matt Pocock (Total TypeScript)](https://www.youtube.com/@maaborern) | Short, focused TypeScript tips and deep dives. The #1 TS channel |
| [Traversy Media — TypeScript Crash Course](https://www.youtube.com/@TraversyMedia) | Best first TypeScript video. Covers fundamentals in ~1 hour |
| [The Net Ninja — TypeScript Tutorial](https://www.youtube.com/@NetNinja) | Well-paced series from basics to generics |
| [Jack Herrington — No BS TS](https://www.youtube.com/@jherr) | Advanced TypeScript patterns, generics deep dives, React + TS |
| [Fireship — TypeScript in 100 Seconds](https://www.youtube.com/@Fireship) | Quick overview to get the big picture |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — TypeScript](https://roadmap.sh/typescript) | Interactive learning path — click each topic to see resources. Track progress |
| [Total TypeScript — Learning Path](https://www.totaltypescript.com/typescript-learning-path) | Matt Pocock's recommended 13-week learning progression |

### Practice & Challenges

| Platform | What You Get |
|----------|-------------|
| [Type Challenges](https://github.com/type-challenges/type-challenges) | 200+ type-system puzzles. The best way to master advanced TypeScript types |
| [Exercism — TypeScript Track](https://exercism.org/tracks/typescript) | 95+ exercises with mentor feedback. Practice fundamentals |
| [LeetCode](https://leetcode.com/) | Solve algorithm problems in TypeScript. Filter by language |
| [Frontend Mentor](https://www.frontendmentor.io/) | Build projects with TypeScript + React |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [TypeScript Language Features](https://code.visualstudio.com/docs/languages/typescript) | Built into VS Code. IntelliSense, refactoring, error highlighting — works out of the box |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Use with `@typescript-eslint/parser` for TypeScript-specific linting rules |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format TypeScript on save |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | Show type errors inline — see problems instantly without hovering |
| [Pretty TypeScript Errors](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors) | Makes complex TypeScript errors readable with syntax highlighting |
| [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) | See the size of imported packages — keep bundles small |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [React TypeScript Cheatsheet](https://react-typescript-cheatsheet.netlify.app/) | The definitive guide for React + TypeScript patterns. Bookmark this |
| [TypeScript Cheat Sheets (Official)](https://www.typescriptlang.org/cheatsheets/) | Official one-page references for types, interfaces, classes, control flow |
| [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/) | Free online book covering TypeScript in depth |

---

[Back to Main Syllabus](../README.md)

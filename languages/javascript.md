# JavaScript Syllabus

A complete, structured learning path for JavaScript — from your first `console.log()` to mastering async programming, closures, and browser APIs.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Operators & Control Flow](#phase-2-operators--control-flow)
- [Phase 3: Functions](#phase-3-functions)
- [Phase 4: Arrays & Objects](#phase-4-arrays--objects)
- [Phase 5: DOM Manipulation](#phase-5-dom-manipulation)
- [Phase 6: Asynchronous JavaScript](#phase-6-asynchronous-javascript)
- [Phase 7: ES6+ Modern JavaScript](#phase-7-es6-modern-javascript)
- [Phase 8: Error Handling & Debugging](#phase-8-error-handling--debugging)
- [Phase 9: Advanced Concepts](#phase-9-advanced-concepts)
- [Phase 10: Browser APIs & Real-World JS](#phase-10-browser-apis--real-world-js)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> You should know **HTML and CSS** before learning JavaScript. If you haven't already, complete the [HTML Syllabus](html.md) and [CSS Syllabus](css.md) first.

- HTML fundamentals (elements, attributes, forms)
- CSS basics (selectors, box model, layout)
- A code editor ([VS Code](https://code.visualstudio.com/) recommended)
- A web browser (Chrome recommended for DevTools)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what JavaScript is and write your first lines of code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is JavaScript | The programming language of the web — makes pages interactive, runs in browsers and servers |
| 2 | Where JS Runs | Browser (client-side), Node.js (server-side), Deno — JavaScript is everywhere |
| 3 | Developer Console | Open Chrome DevTools (F12), use `console.log()`, `console.error()`, `console.table()` to see output |
| 4 | Adding JS to HTML | Inline (`onclick`), internal (`<script>`), external (`.js` file) — and why external is best |
| 5 | Code Structure | Statements, semicolons, comments (`//` and `/* */`), and `"use strict"` mode |
| 6 | Variables | `var` vs `let` vs `const` — block scope, hoisting, and why `const` should be your default |
| 7 | Data Types | 7 primitives: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint` + `object` |
| 8 | `typeof` Operator | Check what type a value is — `typeof "hello"` returns `"string"` |

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
| Use in 2025? | Avoid | When you need to reassign | Default choice |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Open the browser console and run JavaScript directly
- [ ] Declare variables with `let` and `const` and explain the difference
- [ ] Identify all 7 primitive data types

</details>

---

## Phase 2: Operators & Control Flow

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions in code and repeat actions with loops.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Arithmetic Operators | `+`, `-`, `*`, `/`, `%` (remainder), `**` (exponentiation), `++`, `--` |
| 2 | String Concatenation | `+` joins strings, template literals use backticks: `` `Hello ${name}` `` |
| 3 | Comparison Operators | `==` vs `===` (loose vs strict), `!=` vs `!==`, `<`, `>`, `<=`, `>=` |
| 4 | Logical Operators | `&&` (AND), `\|\|` (OR), `!` (NOT) — combine conditions |
| 5 | Nullish Coalescing | `??` — returns the right side only if the left is `null` or `undefined` (not `0` or `""`) |
| 6 | Type Coercion | JavaScript auto-converts types: `"5" + 1` = `"51"` but `"5" - 1` = `4`. Learn the gotchas |
| 7 | Conditional Statements | `if`, `else if`, `else`, ternary operator (`condition ? yes : no`) |
| 8 | Switch Statement | Cleaner alternative to multiple `if/else` when comparing one value against many options |
| 9 | Loops | `for`, `while`, `do...while` — repeat code. `break` to exit, `continue` to skip |
| 10 | `for...of` and `for...in` | `for...of` iterates values (arrays), `for...in` iterates keys (objects) |

> [!CAUTION]
> **Always use `===` (strict equality), never `==`.** Loose equality does type coercion that causes bizarre bugs: `"" == false` is `true`, `0 == ""` is `true`, `null == undefined` is `true`. Strict equality avoids all of this.

<details>
<summary><strong>Quick Reference: Type Coercion Gotchas</strong></summary>

```javascript
// These are all TRUE with == (loose equality) 😱
"" == false       // true
0 == ""           // true
0 == false        // true
null == undefined // true
" " == 0          // true

// These are all FALSE with === (strict equality) ✅
"" === false      // false
0 === ""          // false
0 === false       // false
null === undefined // false
```

> This is why `===` exists. Use it everywhere.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the difference between `==` and `===` with examples
- [ ] Write a program using `if/else`, `switch`, and a loop
- [ ] Explain what type coercion is and name 3 gotchas

</details>

---

## Phase 3: Functions

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Functions are the building blocks of JavaScript — learn every way to write and use them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Declarations | `function greet() {}` — hoisted, can be called before they're defined |
| 2 | Function Expressions | `const greet = function() {}` — not hoisted, assigned to variables |
| 3 | Arrow Functions | `const greet = () => {}` — shorter syntax, different `this` binding |
| 4 | Parameters & Arguments | Default parameters (`function(x = 10)`), rest parameters (`...args`) |
| 5 | Return Values | `return` exits the function and sends a value back. No return = `undefined` |
| 6 | Scope | Global vs local vs block scope — where variables are accessible |
| 7 | Closures (Intro) | A function remembers variables from where it was created, even after that scope closes |
| 8 | Higher-Order Functions | Functions that take other functions as arguments or return functions |
| 9 | Callback Functions | Passing a function as an argument — the foundation of async JavaScript |
| 10 | Recursion | A function calling itself — base case prevents infinite loops |

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

> **When to use which?** Arrow functions for callbacks and short functions. Declarations for main functions. Expressions when you need to assign a function to a variable.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions using all three syntaxes (declaration, expression, arrow)
- [ ] Explain closures with a practical example
- [ ] Use a callback function with `setTimeout` or array methods

</details>

---

## Phase 4: Arrays & Objects

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master JavaScript's two most important data structures.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Object Literals | `{ name: "John", age: 30 }` — key-value pairs, dot vs bracket notation |
| 2 | Object Methods | `Object.keys()`, `Object.values()`, `Object.entries()`, `Object.assign()`, `Object.freeze()` |
| 3 | Array Basics | Create arrays, access by index, `.length`, check with `Array.isArray()` |
| 4 | Array Methods (Transform) | `map()`, `filter()`, `reduce()`, `find()`, `findIndex()` — return new arrays/values |
| 5 | Array Methods (Mutate) | `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, `sort()`, `reverse()` — change the original |
| 6 | Array Iteration | `forEach()`, `some()`, `every()`, `includes()`, `indexOf()` |
| 7 | Destructuring | Extract values: `const [a, b] = array` and `const { name, age } = object` |
| 8 | Spread Operator | `...` — copy arrays/objects, merge them, pass array items as function arguments |
| 9 | Rest Parameters | `function sum(...nums)` — collect remaining arguments into an array |
| 10 | JSON | `JSON.stringify()` (object → string) and `JSON.parse()` (string → object) — data exchange format |

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
| `push(item)` | Add to end | New length | Yes |
| `pop()` | Remove from end | Removed item | Yes |
| `splice(i, n)` | Remove/insert at position | Removed items | Yes |
| `sort(fn)` | Sort in place | Sorted array | Yes |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `map`, `filter`, and `reduce` to transform data
- [ ] Destructure objects and arrays in variable declarations
- [ ] Convert data between JavaScript objects and JSON strings

</details>

---

## Phase 5: DOM Manipulation

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Connect JavaScript to the web page — select elements, listen for events, and update the UI.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The DOM Tree | The browser converts HTML into a tree of objects — JavaScript can read and modify every node |
| 2 | Selecting Elements | `querySelector()`, `querySelectorAll()`, `getElementById()` — find elements in the page |
| 3 | Traversing the DOM | `parentElement`, `children`, `nextElementSibling`, `previousElementSibling` — navigate the tree |
| 4 | Creating & Removing Elements | `createElement()`, `appendChild()`, `remove()`, `insertAdjacentHTML()` |
| 5 | Modifying Content | `textContent` vs `innerHTML` vs `innerText` — when to use each and security implications |
| 6 | Classes & Styles | `classList.add()`, `.remove()`, `.toggle()`, `.contains()`, and `element.style` for inline styles |
| 7 | Attributes | `getAttribute()`, `setAttribute()`, `removeAttribute()`, `dataset` for data attributes |
| 8 | Event Listeners | `addEventListener('click', handler)` — respond to clicks, input, scroll, keyboard, and more |
| 9 | Event Object | `event.target`, `event.preventDefault()`, `event.stopPropagation()` — control event behavior |
| 10 | Event Delegation | Attach one listener to a parent instead of many listeners to children — better performance |

> [!IMPORTANT]
> **Never use `innerHTML` with user input** — it creates an XSS (Cross-Site Scripting) vulnerability. Use `textContent` for text, or sanitize input before inserting HTML.

<details>
<summary><strong>Quick Reference: DOM Selection Methods</strong></summary>

| Method | Returns | Example |
|--------|---------|---------|
| `querySelector('.class')` | First match (or `null`) | `document.querySelector('.btn')` |
| `querySelectorAll('.class')` | NodeList of all matches | `document.querySelectorAll('li')` |
| `getElementById('id')` | Single element (or `null`) | `document.getElementById('header')` |
| `getElementsByClassName('class')` | Live HTMLCollection | `document.getElementsByClassName('card')` |

> **Use `querySelector` and `querySelectorAll` for everything.** They accept any CSS selector and are the most flexible.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a to-do list that adds/removes items dynamically
- [ ] Implement event delegation on a list
- [ ] Explain why `textContent` is safer than `innerHTML`

</details>

---

## Phase 6: Asynchronous JavaScript

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Handle operations that take time — API calls, timers, file reading — without freezing the page.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Async Matters | JavaScript is single-threaded — blocking operations freeze the entire page |
| 2 | Callbacks | Pass a function to run "later" — the original async pattern (and why it gets messy) |
| 3 | Promises | `new Promise((resolve, reject) => {})` — pending → fulfilled or rejected. Chainable with `.then()` |
| 4 | Promise Chaining | `.then().then().catch()` — handle sequential async operations without nesting |
| 5 | Async/Await | `async function` + `await` — write async code that looks synchronous. Use `try/catch` for errors |
| 6 | Fetch API | `fetch(url)` — make HTTP requests, get JSON responses: `const data = await fetch(url).then(r => r.json())` |
| 7 | Error Handling | Network errors vs HTTP errors — `fetch` doesn't reject on 404/500, check `response.ok` |
| 8 | Promise Methods | `Promise.all()` (wait for all), `Promise.race()` (first to finish), `Promise.allSettled()`, `Promise.any()` |
| 9 | Event Loop | Call stack → microtask queue (promises) → task queue (setTimeout) — how JavaScript processes async code |
| 10 | Timers | `setTimeout()`, `setInterval()`, `clearTimeout()`, `clearInterval()` — schedule code execution |

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
// 1. Callback Hell 😩
getUser(id, function(user) {
  getPosts(user.id, function(posts) {
    getComments(posts[0].id, function(comments) {
      // deeply nested...
    });
  });
});

// 2. Promise Chaining 🙂
getUser(id)
  .then(user => getPosts(user.id))
  .then(posts => getComments(posts[0].id))
  .then(comments => /* use comments */)
  .catch(err => /* handle error */);

// 3. Async/Await 😍
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

</details>

---

## Phase 7: ES6+ Modern JavaScript

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write modern, clean JavaScript using features from ES6 (2015) and beyond.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Template Literals | `` `Hello ${name}` `` — string interpolation, multi-line strings, tagged templates |
| 2 | Enhanced Object Literals | Shorthand properties, computed property names, method shorthand |
| 3 | Classes | `class User { constructor() {} }` — cleaner syntax for constructor functions |
| 4 | Inheritance | `class Admin extends User` — `super()` calls the parent constructor, override methods |
| 5 | Getters & Setters | `get fullName()` and `set fullName()` — computed properties on objects and classes |
| 6 | Modules | `import { func } from './module.js'` and `export` — split code into files |
| 7 | Symbols | `Symbol('id')` — unique identifiers, `Symbol.iterator` for custom iteration |
| 8 | Iterators & Iterables | The iterator protocol — make custom objects work with `for...of` |
| 9 | Generators | `function*` and `yield` — functions that can pause and resume, lazy evaluation |
| 10 | Optional Chaining & Nullish | `user?.address?.city` (safe access) and `??` (default only for null/undefined) |

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
| `async` / `await` | ES8 | 2017 | `await fetch(url)` |
| Optional Chaining | ES11 | 2020 | `obj?.prop` |
| Nullish Coalescing | ES11 | 2020 | `value ?? default` |
| `structuredClone()` | ES13 | 2022 | Deep copy objects |
| Top-level `await` | ES13 | 2022 | `await` outside `async` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with inheritance (`extends`, `super`)
- [ ] Split a project into modules with `import`/`export`
- [ ] Use optional chaining and nullish coalescing in real code

</details>

---

## Phase 8: Error Handling & Debugging

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Write robust code that handles failures gracefully, and learn to debug like a pro.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `try / catch / finally` | Catch errors without crashing: `try { risky() } catch(e) { handle(e) } finally { cleanup() }` |
| 2 | Error Object | `e.message`, `e.name`, `e.stack` — extract useful information from errors |
| 3 | `throw` Statement | Create and throw your own errors: `throw new Error("Invalid input")` |
| 4 | Custom Errors | `class ValidationError extends Error {}` — create domain-specific error types |
| 5 | Console Methods | Beyond `console.log()`: `.warn()`, `.error()`, `.table()`, `.group()`, `.time()`, `.trace()` |
| 6 | Chrome Debugger | Breakpoints, step over/into/out, watch expressions, call stack — debug without console.log |
| 7 | Debugging Strategies | Read the error message first, isolate the problem, use binary search debugging |
| 8 | Testing Basics | Unit testing concepts, writing your first tests with Jest or Vitest |

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
- [ ] Write a simple test with Jest or Vitest

</details>

---

## Phase 9: Advanced Concepts

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Understand how JavaScript works under the hood — the concepts that separate juniors from seniors.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Prototypes | Every object has a prototype chain — this is how JavaScript does inheritance (not classes!) |
| 2 | `this` Deep Dive | `this` changes based on how a function is called: method, function, constructor, arrow, `call`/`apply`/`bind` |
| 3 | Closures (Advanced) | Data privacy with closures, the module pattern, IIFE (Immediately Invoked Function Expressions) |
| 4 | Execution Context | Global context, function context, the call stack — how JavaScript executes your code step by step |
| 5 | Hoisting (Detailed) | Variables and functions are "moved to the top" — but differently for `var`, `let`, `const`, and functions |
| 6 | Memory & Garbage Collection | How JS allocates and frees memory, mark-and-sweep algorithm, common memory leaks |
| 7 | Currying | `add(1)(2)(3)` — transform a function with multiple arguments into a chain of single-argument functions |
| 8 | Memoization | Cache function results to avoid expensive recalculations — a key performance optimization |
| 9 | `WeakMap` & `WeakSet` | Weak references — keys can be garbage collected, preventing memory leaks with DOM caches |
| 10 | Property Descriptors | `Object.defineProperty()`, `writable`, `enumerable`, `configurable` — control object behavior at a low level |

> [!WARNING]
> Common memory leaks in JavaScript:
> - Event listeners not removed when elements are deleted
> - `setInterval` not cleared with `clearInterval`
> - Closures holding references to large objects unnecessarily
> - Detached DOM nodes still referenced in variables

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

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the prototype chain and how `Object.create()` works
- [ ] Predict the value of `this` in 5 different scenarios
- [ ] Implement memoization for an expensive function

</details>

---

## Phase 10: Browser APIs & Real-World JS

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Use the browser's built-in APIs to build real applications.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `localStorage` & `sessionStorage` | Store data in the browser: `localStorage.setItem('key', JSON.stringify(data))` — persists across sessions |
| 2 | Geolocation API | `navigator.geolocation.getCurrentPosition()` — get the user's latitude and longitude |
| 3 | History API | `history.pushState()`, `popstate` event — change the URL without reloading the page (SPA routing) |
| 4 | Intersection Observer | Detect when elements enter the viewport — lazy loading images, infinite scroll, animations on scroll |
| 5 | Web Workers | Run JavaScript in a background thread — heavy computation without freezing the UI |
| 6 | Service Workers | Intercept network requests, enable offline functionality — the foundation of PWAs |
| 7 | File API | `FileReader`, drag-and-drop file uploads, read file contents in the browser |
| 8 | Canvas API | `<canvas>` + JavaScript — draw graphics, build games, create visualizations |
| 9 | Notifications API | `Notification.requestPermission()` — send browser notifications to the user |
| 10 | Performance API | `performance.now()`, `performance.mark()` — measure and optimize your code's speed |

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

</details>

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

---

## Interview Questions

Test your JavaScript knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What's the difference between `var`, `let`, and `const`?**
   - `var`: function-scoped, hoisted as `undefined`, can be redeclared. `let`: block-scoped, hoisted but in temporal dead zone, can be reassigned. `const`: block-scoped, must be initialized, cannot be reassigned (but object properties can be mutated).

2. **Explain type coercion. What does `"5" + 1` vs `"5" - 1` return?**
   - `"5" + 1` = `"51"` (string concatenation, `+` prefers strings). `"5" - 1` = `4` (subtraction only works on numbers, so `"5"` is converted). This is implicit type coercion — JS auto-converts types.

3. **What is hoisting?**
   - JavaScript moves declarations to the top of their scope before executing. `var` is hoisted as `undefined`. `let`/`const` are hoisted but can't be accessed before declaration (temporal dead zone). Function declarations are fully hoisted.

4. **What is a callback function?**
   - A function passed as an argument to another function, executed inside that function. Example: `[1,2,3].forEach(num => console.log(num))` — the arrow function is the callback.

5. **What's the difference between `null` and `undefined`?**
   - `undefined`: variable declared but not assigned, or missing function return. `null`: intentionally set to "no value" by the developer. `typeof undefined` is `"undefined"`, `typeof null` is `"object"` (a known JS bug).

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

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Interactive Quiz App
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A multiple-choice quiz with score tracking, timer, and results screen. Questions stored in an array of objects.

**Skills practiced:** Variables, conditionals, loops, functions, arrays, objects, DOM basics.

---

### Project 2: To-Do List with LocalStorage
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-green)

**What you'll build:** A full-featured to-do app: add, edit, delete, mark complete, filter (all/active/completed), persist to `localStorage`.

**Skills practiced:** Array methods, DOM manipulation, event delegation, `localStorage`, JSON.

---

### Project 3: Weather App (API)
![Phase 6](https://img.shields.io/badge/After-Phase%206-yellow)

**What you'll build:** Search for a city, fetch real weather data from an API, display temperature, conditions, and a 5-day forecast. Handle loading and error states.

**Skills practiced:** `fetch`, `async/await`, error handling, Promises, DOM updates.

---

### Project 4: GitHub Profile Finder
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** Search GitHub usernames, display profile info, repos, and activity. Built with ES6 modules, classes, and proper error handling.

**Skills practiced:** Modules, classes, `fetch`, `try/catch`, template literals, destructuring.

---

### Project 5: Kanban Task Board
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** A drag-and-drop task board (like Trello) with columns (To Do, In Progress, Done), `localStorage` persistence, keyboard accessibility, and smooth animations.

**Skills practiced:** Everything from all phases — your JavaScript graduation project.

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

### Practice & Coding Challenges

| Platform | What You Get |
|----------|-------------|
| [Codewars](https://www.codewars.com/) | Gamified coding challenges (kata) ranked by difficulty. Learn by solving, compare solutions |
| [LeetCode](https://leetcode.com/) | 3000+ problems. Essential for interview prep. Filter by "JavaScript" and difficulty |
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional designs to build with HTML, CSS, and JavaScript. Real-world projects |
| [Exercism](https://exercism.org/tracks/javascript) | 140+ JavaScript exercises. Free mentoring from experienced developers |
| [JavaScript30](https://javascript30.com/) | 30 small vanilla JS projects (drum kit, clock, gallery, etc.) — no frameworks |
| [DevChallenges](https://devchallenges.io/) | Full-stack project challenges with varying difficulty |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — JavaScript](https://roadmap.sh/javascript) | Interactive learning path — click each topic to see resources. Track your progress |

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

---

[Back to Main Syllabus](../README.md)

# Node.js Syllabus

A complete, structured learning path for Node.js — your one-stop guide from your first `console.log("hello")` on the server to shipping production REST/GraphQL APIs, real-time apps, AI backends, CLI tools, serverless functions, and edge deployments. Whether you've never run JavaScript outside a browser or you've been writing Express for a decade and want to catch up to the modern stack (Fastify/Hono, Drizzle, Vitest, native fetch, ESM, Bun, Vercel AI SDK), this syllabus walks you through every concept in the right order, explains *why* each matters, lists the **frameworks and libraries** you'll meet on the job, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 15 Phases](https://img.shields.io/badge/Topics-15%20Phases-orange)
![Node.js: 22 LTS](https://img.shields.io/badge/Node.js-22%20LTS-339933)

---

## Table of Contents

- [What is Node.js?](#what-is-nodejs)
- [Why Learn Node.js in 2026?](#why-learn-nodejs-in-2026)
- [How Node.js Works](#how-nodejs-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Core Modules & Globals](#phase-2-core-modules--globals)
- [Phase 3: Asynchronous Patterns](#phase-3-asynchronous-patterns)
- [Phase 4: File System & Streams](#phase-4-file-system--streams)
- [Phase 5: HTTP & Networking](#phase-5-http--networking)
- [Phase 6: Web Frameworks (Express, Fastify, Hono)](#phase-6-web-frameworks-express-fastify-hono)
- [Phase 7: REST API Patterns](#phase-7-rest-api-patterns)
- [Phase 8: Databases & ORMs](#phase-8-databases--orms)
- [Phase 9: Authentication & Security](#phase-9-authentication--security)
- [Phase 10: Real-time — WebSockets, SSE, Streaming](#phase-10-real-time--websockets-sse-streaming)
- [Phase 11: Testing & Quality](#phase-11-testing--quality)
- [Phase 12: Performance, Observability & Scaling](#phase-12-performance-observability--scaling)
- [Phase 13: Deployment & Production](#phase-13-deployment--production)
- [Phase 14: The Node.js Ecosystem](#phase-14-the-nodejs-ecosystem)
- [Phase 15: What's Next? (Specializations & Deploy)](#phase-15-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is Node.js?

**Node.js is a JavaScript runtime built on Chrome's V8 engine — it lets you run JavaScript outside the browser.** APIs, websockets, CLI tools, build tools (Vite, esbuild, Webpack — all Node), serverless functions, AI agents, real-time servers, even desktop apps (Electron, the engine behind VS Code / Slack / Discord) — all powered by Node.

Created by **Ryan Dahl in 2009** to fix a problem nobody else had named: web servers using one OS thread per request didn't scale. Node introduced an **event-driven, non-blocking I/O** model — single-threaded for your code, but able to handle tens of thousands of concurrent connections without breaking a sweat. Combined with **npm** (the largest package registry on Earth, 3+ million packages), Node became the default backend runtime for JavaScript developers everywhere.

In simple words:

- Browsers run JS to control web pages. **Node runs JS to control servers, files, processes, and networks.**
- Node is **single-threaded with an event loop** — great for I/O (HTTP, DB, files), bad for CPU-bound math (use worker threads or a different tool).
- The standard library (built-in modules) is huge: HTTP servers, file systems, crypto, streams, child processes — all built in.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 2009 | Node 0.1 | Ryan Dahl unveils Node.js at JSConf EU. Built on V8 + libuv. |
| 2011 | Node 0.6 | Stable release. The Express era begins. |
| 2014 | io.js fork | Community fork over governance. Forced Node Foundation creation. |
| 2015 | Node 4 + io.js merge | Reunified. ES6 features (mostly) supported. |
| 2018 | Node 10 LTS | Native HTTP/2, async iteration. |
| 2021 | Node 16 LTS | Stable native fetch (experimental). Apple Silicon support. |
| 2022 | Node 18 LTS | **Native `fetch`**, **native test runner** (`node:test`), **watch mode** (`--watch`), Web Streams. |
| 2024 | Node 22 LTS | **WebSocket client native**, native `.env` loader (`--env-file`), `require()` of ESM, V8 12.4. |
| 2025+ | Node 23/24 | Continued ESM + native API expansion. Permission model. |

> [!IMPORTANT]
> **"Modern Node" in 2026** means: Node 22 LTS (or 24), **ESM modules** (not CJS for new code), native `fetch` (not `axios` for simple cases), native test runner or **Vitest** (not Mocha/Chai), TypeScript-first, **Fastify** or **Hono** (not Express for new projects). If a tutorial uses CommonJS + `request` + Mocha — it's outdated.

### Node's Cousins: Deno & Bun

Two runtimes have emerged as Node alternatives:

| Runtime | What It Is | When to Use |
|---------|-----------|------------|
| **[Bun](https://bun.sh/)** | Drop-in faster Node clone (Zig-built). Native TS, JSX, bundler, test runner, package manager — all in one binary. | New projects valuing speed and DX |
| **[Deno](https://deno.com/)** | Ryan Dahl's "do-over" of Node — secure by default, native TS, web-standard APIs, npm-compatible. | Edge runtime, security-sensitive scripts |
| **[Node.js](https://nodejs.org/)** | The original. Largest ecosystem, most production deployments. | The default — and what this syllabus covers |

Most concepts transfer between all three.

### What Makes Node Special

- **One language end-to-end.** Frontend, backend, mobile (RN), desktop (Electron), CLI, serverless — all JavaScript/TypeScript.
- **The npm ecosystem.** Whatever you need is on npm. 3+ million packages.
- **Excellent for I/O.** Real-time chats, streaming APIs, proxies, gateways — Node was built for this.
- **AI-native.** OpenAI SDK, Anthropic SDK, Vercel AI SDK, LangChain.js — the modern AI stack runs on Node.
- **Massive job market.** Node + React/Next is the most-listed full-stack combo on every major job board.

---

## Why Learn Node.js in 2026?

| Reason | What It Means |
|--------|---------------|
| **Full-stack with one language** | Frontend (React/Vue), backend (Node), mobile (React Native), CLI (Node) — same language everywhere. |
| **AI app stack runs on Node** | Vercel AI SDK, Anthropic/OpenAI SDKs, LangChain.js, RAG pipelines — all Node-first. |
| **Native to serverless / edge** | Vercel Functions, AWS Lambda, Cloudflare Workers, Fastly Compute — Node is the default runtime. |
| **Real-time is a Node home turf** | WebSockets, SSE, streaming — Node's non-blocking I/O makes this natural. |
| **The largest registry on Earth** | npm has more packages than any other language registry, by 5×. |
| **Most-listed backend in 2026** | Node + Express/Fastify/Next.js API Routes is on more job postings than any other backend stack. |
| **Tooling for *every* language** | Most modern build tools (Vite, esbuild, Tailwind, Prettier, Storybook) are Node-based — even for non-JS languages. |
| **Pays well** | Senior Node/full-stack salaries in 2026: **$110k–$200k** (US), **₹12L–₹40L** (India). |

---

## How Node.js Works

Internalize this and the rest of the syllabus clicks.

```
   ┌──────────────────────────────────────────────────────┐
   │                     Your code                        │
   │                       (JS/TS)                        │
   └───────────────────────────┬──────────────────────────┘
                               ▼
   ┌──────────────────────────────────────────────────────┐
   │                       V8 Engine                      │
   │             Compiles JS to machine code              │
   └───────────────────────────┬──────────────────────────┘
                               ▼
   ┌──────────────────────────────────────────────────────┐
   │                    Node Bindings                     │
   │              (fs, http, net, crypto…)                │
   └───────────────────────────┬──────────────────────────┘
                               ▼
   ┌──────────────────────────────────────────────────────┐
   │                        libuv                         │
   │      Event loop + thread pool for slow syscalls      │
   └───────────────────────────┬──────────────────────────┘
                               ▼
                       OS / hardware

   The Event Loop phases:
     timers → pending → idle → poll → check → close
                  ↑___________________________|
                       (loops forever)
```

**Three things to internalize:**

1. **Single-threaded JavaScript, multi-threaded I/O.** Your code runs on one thread; libuv's thread pool handles slow syscalls (file I/O, DNS, crypto) in the background.
2. **Non-blocking by default.** `fs.readFile` returns immediately and calls back when done. **Never block the event loop** with sync operations or heavy CPU work — every other request waits.
3. **The event loop has phases.** Timers (`setTimeout`), I/O callbacks, `setImmediate`, microtasks (Promises). Knowing the order is the most-asked senior interview question.

---

## Pick Your Path

Node is huge — most people don't need every phase equally. Pick the track that matches your goal.

### Track 1 — REST API Backend (12–16 weeks)
**Goal:** ship production REST APIs in TypeScript with Fastify/Hono + Postgres.

Do every phase in order. Spend extra time on **Async Patterns**, **Web Frameworks**, **REST API Patterns**, **Databases**, **Auth**, and **Testing**. Pair with the [SQL Syllabus](sql.md) and [Docker Syllabus](docker.md). Build the production REST capstone and deploy it.

### Track 2 — Real-time Engineer (10–14 weeks)
**Goal:** ship multiplayer / live apps — chat, dashboards, collab editors.

All language phases through Async, then dive into **WebSockets, SSE, Streaming**, **Performance & Scaling**. Learn Socket.io or `ws`, presence systems, CRDTs (Yjs), and Redis pub-sub. Build the real-time chat capstone.

### Track 3 — AI Backend Engineer (10–14 weeks)
**Goal:** build AI/LLM-powered backends — agents, RAG, streaming.

All fundamentals through **Web Frameworks** + **Databases**, then go deep on **Streaming**, **Auth**, **Testing**, and the AI section of the **Ecosystem** phase. Master the **Vercel AI SDK**, **Anthropic SDK**, and **pgvector**. Build the AI capstone — most hireable demo in 2026.

### Track 4 — Serverless / Edge (8–12 weeks)
**Goal:** ship Vercel Functions, AWS Lambda, or Cloudflare Workers.

All fundamentals → **Web Frameworks** (Hono is edge-native) → **Auth** → **Deployment**. Skip heavy threading/cluster topics. Master cold-start optimization, function-level concurrency, and edge KV stores (Vercel KV, Cloudflare KV/D1).

### Track 5 — CLI Tools (6–8 weeks)
**Goal:** ship npm-publishable command-line tools.

Phases 1–5, plus **Testing**, **Deployment** (npm publish + GitHub Releases). Master Commander/Yargs/Clack, prompts, spinners, and packaging. Skip web/database phases.

### Track 6 — Modernize Old Node (4–6 weeks)
**Goal:** you wrote callback-style Express + CommonJS years ago and stopped.

Skip basics. Focus on **Async** (promises, async/await), **Web Frameworks** (Fastify/Hono replace Express), **Databases** (Drizzle replaces Sequelize), **Testing** (Vitest replaces Mocha), **ESM** (replaces CommonJS). Replace your `axios` with native `fetch`.

> [!TIP]
> Whichever track you pick, **Phase 3 (Async Patterns)** and **Phase 5 (HTTP)** are the two phases every track depends on — read them carefully.

---

## Prerequisites

> [!IMPORTANT]
> Node.js is **JavaScript on the server**. You need solid JavaScript first — especially async/await, promises, modules, and ES6+ features. Skipping JS fundamentals is the #1 reason people struggle with Node.

Before starting, you should be comfortable with:

- **JavaScript essentials** — arrow functions, destructuring, spread/rest, `map`/`filter`/`reduce`, modules (`import`/`export`)
- **Async JS deeply** — promises, `async`/`await`, `try/catch`, the event loop concept
- **Closures** — at the heart of every async bug you'll write
- **Terminal / command line** — `cd`, `ls`, running commands
- A code editor — [VS Code](https://code.visualstudio.com/) recommended
- A modern browser for testing APIs (or [Postman](https://www.postman.com/) / [Bruno](https://www.usebruno.com/))
- A [GitHub account](https://github.com/) and an account on a free deploy platform ([Vercel](https://vercel.com/), [Render](https://render.com/), [Fly.io](https://fly.io/))

If JS feels shaky, do the [JavaScript Syllabus](javascript.md) first — especially Phases 4 (Functions), 5 (Arrays & Objects), 7 (Async). Strongly recommended: **TypeScript from day one** for any new project. See the [TypeScript Syllabus](typescript.md).

---

## How to Use This Syllabus

1. **Don't skip phases.** Each builds on the last. Async (Phase 3) is the gateway — get it wrong and Phases 5–10 feel impossible.
2. **Type the code yourself.** Copy-pasting gives the illusion of learning.
3. **Use TypeScript from Phase 6+.** Almost every job uses TS for backend.
4. **Use ESM, not CommonJS** — `import`/`export`, `"type": "module"` in `package.json`. New code only.
5. **Pick Fastify or Hono for new projects** — Express is legacy. Cover Express enough to read it (most existing codebases use it), but build new projects on the modern stack.
6. **Always use a `.env` file** for secrets. Use `--env-file=.env` (Node 20+) or `dotenv` library. Never commit `.env`.
7. **Build the project at the end of each phase block.** Reading is not the same as doing.
8. **Deploy every project.** Free options: Vercel, Render, Fly.io, Railway, Cloudflare Workers.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Install Node, run your first script, understand the package ecosystem.

**What this phase is about.** Install Node *the right way* (using a version manager, never the system installer), understand `package.json` as the project's source of truth, learn the difference between **CommonJS** and **ES Modules** (the future), and pick a package manager (npm, pnpm, yarn, or bun). You'll also meet Node 22's modern conveniences — native `--watch`, `--env-file`, native test runner — that mean fewer libraries, less config.

**Why it matters.** Wrong install hygiene (system Node, no version manager, mixing CJS and ESM accidentally) wastes more beginner time than any other single thing. Get this right and the rest flies.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Node.js | JS runtime built on V8. Created by Ryan Dahl in 2009. Single-threaded event loop |
| 2 | Installing with `fnm` / `nvm` | `fnm install --lts` (Rust-based, fast) or `nvm install --lts`. Manage multiple versions |
| 3 | Node 22 LTS | Native `fetch`, `--watch`, `--env-file`, `node:test`. Use 22+ for new projects |
| 4 | Bun & Deno (Briefly) | Faster Node alternatives. Bun is a drop-in replacement; Deno is a security-first redesign |
| 5 | Your First Script | `node hello.js` — `console.log("Hello!")`. The REPL: just `node` for an interactive shell |
| 6 | `package.json` | The heart of every project. `npm init -y` to scaffold |
| 7 | Dependencies | `dependencies`, `devDependencies`, `peerDependencies`. Semantic versioning (`^`, `~`) |
| 8 | npm vs pnpm vs yarn vs bun | Compare. **pnpm is recommended** in 2026 (fast, disk-efficient, monorepo-friendly) |
| 9 | npm Scripts | `"dev": "node --watch src/index.js"`, `"start"`, `"test"`. Lifecycle hooks |
| 10 | ESM vs CommonJS | `import`/`export` (ESM, modern) vs `require`/`module.exports` (CJS, legacy). Set `"type": "module"` in `package.json` |
| 11 | `node:` Prefix | `import fs from 'node:fs'` — modern, explicit, clearer |
| 12 | `.env` Files | `node --env-file=.env app.js` — Node 20+ has it built-in. No more `dotenv` for simple cases |

> [!TIP]
> The 2026 starter for a fresh Node + TypeScript project:

```bash
mkdir my-app && cd my-app
pnpm init
pnpm add -D typescript tsx @types/node
pnpm dlx tsc --init
echo '{"type":"module"}' > .npmrc
```

> Then in `package.json`:

```json
{
  "type": "module",
  "scripts": {
    "dev": "tsx watch src/index.ts",
    "build": "tsc",
    "start": "node dist/index.js"
  }
}
```

<details>
<summary><strong>Quick Reference: Node CLI Flags You'll Actually Use</strong></summary>

| Flag | What It Does |
|------|--------------|
| `--watch` | Auto-restart on file change (Node 22+) |
| `--env-file=.env` | Load env vars (Node 22+) |
| `--inspect` | Open Chrome DevTools debugger |
| `--inspect-brk` | Same, but pause at the first line |
| `--experimental-strip-types` | Run `.ts` files directly (Node 22+) |
| `--test` | Run files with `node:test` |
| `--require ./preload.js` | Run a script before main |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Node 22 via `fnm` or `nvm`
- [ ] Run a hello-world script and the REPL
- [ ] Initialize `package.json`, install a dep, use it in code
- [ ] Set up an ESM project with `"type": "module"` and TypeScript via `tsx`
- [ ] Use `--watch` and `--env-file` flags
- [ ] Compare disk usage of `npm install` vs `pnpm install`

</details>

---

## Phase 2: Core Modules & Globals

![Phase](https://img.shields.io/badge/Phase-2%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> The standard library — the modules baked into Node.

**What this phase is about.** Node ships with ~40 built-in modules: `fs` (file system), `path` (cross-platform paths), `os` (CPU/memory info), `crypto` (hashing, encryption, UUIDs), `process` (env vars, args, signals), `Buffer` (raw bytes), `URL`, plus globals like `console`, `setTimeout`, `process`, `Buffer`. Modern Node also exposes web-standard globals: `fetch`, `URL`, `URLSearchParams`, `crypto.subtle`, `WebSocket`, `EventTarget`, `AbortController`.

**Why it matters.** Knowing the standard library means *not* installing a library for every task. Less bloat, fewer security holes, faster onboarding. Senior code is full of `node:fs/promises` and `node:crypto`; junior code is full of `axios` and `uuid` packages.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Globals | `console`, `process`, `Buffer`, `setTimeout`, `setInterval`, `setImmediate`, `queueMicrotask` |
| 2 | `process` | `process.env`, `process.argv`, `process.exit()`, `process.cwd()`, `process.platform`, `process.on('SIGINT')` |
| 3 | `console` Beyond `log` | `.error`, `.warn`, `.table`, `.time/.timeEnd`, `.group`, `.dir` |
| 4 | `path` | `path.join`, `path.resolve`, `path.dirname`, `path.basename`, `path.extname`. Cross-platform paths |
| 5 | `os` | `os.cpus()`, `os.totalmem()`, `os.hostname()`, `os.platform()`, `os.tmpdir()` |
| 6 | `crypto` | `crypto.randomUUID()`, `randomBytes`, `createHash` (SHA-256), `createHmac`, `pbkdf2`/`scrypt` for passwords |
| 7 | Web Crypto (`crypto.subtle`) | The async, web-standard API. Modern preferred for new code |
| 8 | `Buffer` | Raw binary data. `Buffer.from`, `.toString('utf8')`, `.length`, encoding/decoding |
| 9 | `URL` & `URLSearchParams` | Parse and build URLs. Replaces the old `url` module |
| 10 | Native `fetch` | Web-standard HTTP client built into Node 18+. No more `node-fetch` or `axios` for simple cases |
| 11 | `AbortController` | Cancel in-flight `fetch` requests, timers, async work |
| 12 | `EventEmitter` | Pub/sub primitive. Most Node objects extend it (servers, streams) |
| 13 | `node:util` | `promisify`, `inspect` (pretty-print), `parseArgs` (CLI args) |
| 14 | `__dirname` & `__filename` in ESM | They don't exist! Use `import.meta.url` + `URL` instead |

<details>
<summary><strong>Quick Reference: __dirname in ESM</strong></summary>

```ts
import { fileURLToPath } from 'node:url';
import { dirname } from 'node:path';

const __filename = fileURLToPath(import.meta.url);
const __dirname  = dirname(__filename);
```

Or use the modern shortcut (Node 21+):
```ts
const __dirname = import.meta.dirname;
const __filename = import.meta.filename;
```

</details>

<details>
<summary><strong>Quick Reference: Common process Patterns</strong></summary>

```ts
// Read CLI arg
const name = process.argv[2];

// Read env var with default
const port = Number(process.env.PORT ?? 3000);

// Graceful shutdown
process.on('SIGTERM', () => { server.close(); process.exit(0); });

// Top-level error catch (last resort)
process.on('unhandledRejection', err => console.error('UNHANDLED', err));
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read CLI arguments with `process.argv` and `util.parseArgs`
- [ ] Read env vars with `--env-file` or `process.env`
- [ ] Hash a password using `node:crypto` (`scrypt`)
- [ ] Generate UUIDs with `crypto.randomUUID()`
- [ ] Make an HTTP call with native `fetch`
- [ ] Cancel a `fetch` with `AbortController`
- [ ] Build `__dirname` in an ESM file

</details>

---

## Phase 3: Asynchronous Patterns

![Phase](https://img.shields.io/badge/Phase-3%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> The single most important phase. Async is Node's superpower and its biggest footgun.

**What this phase is about.** The **event loop**, in detail (timers / pending / poll / check / close phases, microtasks vs macrotasks, why `setTimeout(fn, 0)` doesn't fire immediately). The three generations of async (callbacks → promises → async/await). **Promise combinators** (`Promise.all`, `allSettled`, `race`, `any`). **AbortController** for cancellation. **EventEmitter** as Node's core pub/sub. Plus the rules: never block the loop, never mix callback and promise styles, always handle rejection.

**Why it matters.** Every senior Node interview tests the event loop. Every "why is my server slow?" or "why does this hang?" question traces to async mistakes. Master this phase and Node feels predictable.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Event Loop Phases | timers → pending callbacks → idle → poll → check → close. The *order* matters |
| 2 | Microtasks vs Macrotasks | Promises = microtask (highest priority). `setTimeout` = macrotask. Microtasks drain between every macrotask |
| 3 | Callbacks (Legacy) | Node's original style: `fn(err, data)`. The "error-first" convention |
| 4 | Promises | `new Promise((resolve, reject) => …)`. Chainable `.then`/`.catch`/`.finally` |
| 5 | `async`/`await` | Modern preferred style. Must use `try/catch` for error handling |
| 6 | Promise Combinators | `Promise.all` (parallel, fail-fast), `allSettled` (wait all), `race`, `any`, `withResolvers` (modern) |
| 7 | `util.promisify` | Convert a callback API to a promise API |
| 8 | Sequential vs Parallel | Don't `await` in a loop when calls are independent — use `Promise.all` |
| 9 | `AbortController` | Cancel `fetch`, timers, custom async work. Standard API |
| 10 | Top-level `await` | Allowed in ESM modules. No more wrapping in `(async () => {})()` |
| 11 | EventEmitter | `emitter.on('event', cb)`, `.emit('event', data)`. The pattern under streams + servers |
| 12 | `events.once()` | Wait for an EventEmitter to fire — promise-based |
| 13 | `setImmediate` vs `setTimeout(fn, 0)` | Different phases. `setImmediate` runs in *check* phase, `setTimeout` in *timers* |
| 14 | `process.nextTick` | Highest priority — runs before any other I/O. Use sparingly |
| 15 | Worker Threads (Brief) | True parallelism for CPU-bound work. Covered in Phase 12 |
| 16 | Async Iteration | `for await (const chunk of stream)` — built-in for streams |
| 17 | Common Pitfalls | Forgetting `await`, unhandled rejections, blocking the loop, double callbacks |

> [!CAUTION]
> The classic "why is my server slow?" — blocking the event loop:

```ts
// BAD — blocks all requests for ~2 seconds while computing
app.get('/hash', (req, res) => {
  const h = crypto.scryptSync(password, salt, 32, { N: 2**20 });
  res.send(h);
});

// GOOD — async version, event loop stays free
app.get('/hash', async (req, res) => {
  const h = await scryptAsync(password, salt, 32, { N: 2**20 });
  res.send(h);
});
```

<details>
<summary><strong>Quick Reference: Promise Combinators</strong></summary>

| Combinator | Resolves When | Rejects When | Returns |
|------------|---------------|--------------|---------|
| `Promise.all` | ALL resolve | ANY rejects (fast) | Array of values |
| `Promise.allSettled` | ALL settle | Never | Array of `{status, value/reason}` |
| `Promise.race` | First settles | First rejects | Single value/error |
| `Promise.any` | First resolves | ALL reject | Single value or `AggregateError` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Predict the output of an event-loop puzzle (mix of `setTimeout`, `Promise.then`, `process.nextTick`)
- [ ] Convert callback-based `fs.readFile` to promise-based using `util.promisify`
- [ ] Run 100 HTTP requests in parallel with `Promise.all` and 10-at-a-time with batching
- [ ] Cancel a `fetch` with `AbortController`
- [ ] Replace a callback EventEmitter listener with `events.once`
- [ ] Explain why `Promise.all` rejects fast and `allSettled` doesn't

</details>

---

## Phase 4: File System & Streams

![Phase](https://img.shields.io/badge/Phase-4%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Read, write, and pipe data without ever loading 10GB into memory.

**What this phase is about.** The `fs` module — both sync (only at startup) and the modern promise-based (`fs/promises`) flavors. **Streams** — Node's signature feature for handling data that doesn't fit in memory. The four kinds (Readable, Writable, Duplex, Transform), the `pipeline` helper that handles backpressure + errors automatically, async iteration over streams.

**Why it matters.** Every backend reads or writes data. Doing it as a stream instead of loading whole files = the difference between handling 100 MB and 100 GB. Streams are also how Node's HTTP, TCP, and child_process APIs work — you'll see them everywhere.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `fs.promises` API | `await fs.readFile`, `writeFile`, `mkdir`, `rm`, `stat`, `readdir`, `cp` |
| 2 | Why Avoid Sync APIs | `readFileSync` blocks the event loop. Only OK at startup or in CLI tools |
| 3 | Reading & Writing Text | `readFile(path, 'utf8')`, `writeFile(path, content, 'utf8')` |
| 4 | Reading & Writing Binary | Default binary returns a `Buffer`. Specify encoding for text |
| 5 | File Handles | `fs.open()` returns a handle for fine-grained control |
| 6 | Walking Directories | `fs.readdir`, `recursive: true` (Node 18+), `fs.glob` (experimental) |
| 7 | Watching Files | `fs.watch` for change events. Cross-platform caveats (use `chokidar` library for production) |
| 8 | Why Streams? | Process data piece-by-piece. Constant memory regardless of size |
| 9 | The 4 Stream Types | Readable (source), Writable (sink), Duplex (both), Transform (modify) |
| 10 | Reading Streams | `for await (const chunk of stream)` — async iteration is the modern way |
| 11 | Writing Streams | `writable.write(chunk)`, `.end()`. Backpressure: respect `false` return |
| 12 | `pipeline()` | The right way to connect streams — handles cleanup + errors. Promise-based |
| 13 | Transform Streams | Custom data transformers (compression, encryption, JSON parse) |
| 14 | Web Streams Interop | Convert between Node streams and Web Streams (`Readable.fromWeb`) |
| 15 | Common Patterns | Read→gzip→write, CSV streaming parser, line-by-line file processing |

```ts
import { pipeline } from 'node:stream/promises';
import { createReadStream, createWriteStream } from 'node:fs';
import { createGzip } from 'node:zlib';

// Read big.log → gzip → write big.log.gz, with backpressure handled.
await pipeline(
  createReadStream('big.log'),
  createGzip(),
  createWriteStream('big.log.gz'),
);
```

> [!TIP]
> Use `pipeline()` (not the older `.pipe()` method) — it auto-cleans up streams on errors and you can `await` it.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write JSON files with `fs.promises`
- [ ] Walk a directory recursively
- [ ] Stream a 1GB file from disk → transform → write to another file using `pipeline`
- [ ] Build a custom Transform stream (e.g. uppercase every line)
- [ ] Convert a Web Stream to a Node Readable
- [ ] Watch a directory for changes with `chokidar`

</details>

---

## Phase 5: HTTP & Networking

![Phase](https://img.shields.io/badge/Phase-5%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build HTTP servers + clients without a framework.

**What this phase is about.** Before frameworks, there's the raw `node:http` module — the foundation everything else builds on. You'll write a server in 5 lines, parse query strings, set headers, stream responses. You'll also learn **HTTPS/TLS basics**, **HTTP/2**, native **WebSocket** client (Node 22+), and the modern **fetch** + **undici** for outbound requests.

**Why it matters.** Frameworks (Express, Fastify, Hono) hide all this — but understanding the raw layer makes them less magical and helps you debug weird bugs. Most production performance issues live in the HTTP layer.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The HTTP Module | `http.createServer((req, res) => …)` — a server in 5 lines |
| 2 | Request Object | `req.url`, `req.method`, `req.headers`. Reading a request body (stream!) |
| 3 | Response Object | `res.statusCode`, `res.setHeader`, `res.end()`. It's a Writable stream |
| 4 | Parsing JSON Bodies | Manually with stream → JSON.parse, or use a framework |
| 5 | Routing By Hand | `if (req.url === '/api/users')` — fine for tiny apps, painful at scale |
| 6 | HTTPS & TLS | `https.createServer({ key, cert }, …)`. Use a reverse proxy (Caddy/nginx) in production instead |
| 7 | HTTP/2 | `node:http2`. Multiplexing, server push, prioritization |
| 8 | HTTP Status Codes | 2xx success, 3xx redirects, 4xx client errors, 5xx server errors |
| 9 | Native fetch (Outbound) | `await fetch(url, { method, headers, body })` — Node 18+ |
| 10 | `undici` | The HTTP client library powering native fetch — better perf for high-throughput |
| 11 | Streaming Responses | `res.write` chunk-by-chunk, perfect for AI streaming + huge files |
| 12 | Server-Sent Events (SSE) | Long-lived response with `Content-Type: text/event-stream` |
| 13 | WebSocket Server | `ws` library; client native in Node 22+ |
| 14 | Reverse Proxies | Why your Node server is *behind* nginx/Caddy/Cloudflare in production |
| 15 | TCP & UDP | `node:net` and `node:dgram` for low-level protocols |

```ts
import { createServer } from 'node:http';

const server = createServer((req, res) => {
  if (req.url === '/' && req.method === 'GET') {
    res.writeHead(200, { 'Content-Type': 'text/html' });
    return res.end('<h1>Hello, World!</h1>');
  }
  res.writeHead(404).end('Not Found');
});

server.listen(3000, () => console.log('http://localhost:3000'));
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a raw `http` server with 3 routes
- [ ] Parse a JSON POST body manually
- [ ] Stream a large file response with chunked encoding
- [ ] Make 50 outbound HTTP calls with native `fetch` + `Promise.all`
- [ ] Build a Server-Sent Events endpoint (long-lived response)
- [ ] Build a WebSocket server with `ws`

</details>

---

## Phase 6: Web Frameworks (Express, Fastify, Hono)

![Phase](https://img.shields.io/badge/Phase-6%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Stop writing routing by hand. Use a framework.

**What this phase is about.** Three frameworks dominate the modern Node landscape:
- **[Express](https://expressjs.com/)** — the classic. Most existing code. Slow, no built-in validation, no TS-first design. **Legacy.**
- **[Fastify](https://fastify.dev/)** — modern, fast, JSON-schema-first, ecosystem-rich. **Recommended for traditional Node servers in 2026.**
- **[Hono](https://hono.dev/)** — ultra-fast, web-standards-based, edge-native (runs on Cloudflare Workers, Bun, Deno). **Recommended for edge / serverless.**

You'll learn the patterns common to all three: routing, middleware, request lifecycle, error handling — then dive deep into Fastify or Hono.

**Why it matters.** Every Node backend job lists at least one of these three. Knowing which to pick (and why) is itself a senior signal.

### 6.1 — Comparison

| Framework | Speed | TS-first? | Schema validation | Best for |
|-----------|:-----:|:---------:|:------------------:|----------|
| **Express** | ★★ | No | Manual | Maintaining existing apps |
| **Fastify** | ★★★★★ | Yes | Built-in JSON Schema | New traditional Node servers |
| **Hono** | ★★★★★ | Yes | Via Zod / Valibot | Edge / serverless / Bun / Deno |
| **NestJS** | ★★★ | Yes | Class-validator | Enterprise / Angular-ish backend |
| **Koa** | ★★★ | Partial | Manual | Express alternative (legacy) |
| **Elysia** (Bun) | ★★★★★ | Yes | Via TypeBox | Bun-only |

### 6.2 — Topics

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Routing | `app.get('/users/:id', handler)`. Static + dynamic paths |
| 2 | Middleware | Functions that run before/after handlers. Logging, auth, parsing |
| 3 | Request Lifecycle | Request → middleware chain → route handler → response → cleanup |
| 4 | Body Parsers | JSON, URL-encoded, multipart (file uploads) |
| 5 | Express Basics | `app = express()`, classic middleware, `res.json` |
| 6 | Fastify Basics | `fastify({ logger: true })`, schema-first routes, hooks |
| 7 | Hono Basics | `new Hono()`, web-standard `Request`/`Response`, runs anywhere |
| 8 | Schema Validation | Fastify's JSON Schema, Hono's `@hono/zod-validator`, Express's `express-validator` |
| 9 | Error Handling | Centralized error handler, async error catching, `try/catch` patterns |
| 10 | CORS | `@fastify/cors`, `hono/cors`, `cors` for Express |
| 11 | Rate Limiting | `@fastify/rate-limit`, `hono/rate-limiter`, `express-rate-limit` |
| 12 | Helmet (Security Headers) | `@fastify/helmet`, `hono/secure-headers`, `helmet` for Express |
| 13 | Logger | Use **pino** (built into Fastify, optional in Hono/Express) |
| 14 | Plugins / Adapters | Each framework has a plugin system — understand the patterns |

```ts
// Modern Hono example — runs on Node, Bun, Deno, Cloudflare, Vercel
import { Hono } from 'hono';
import { logger } from 'hono/logger';
import { cors } from 'hono/cors';
import { z } from 'zod';
import { zValidator } from '@hono/zod-validator';

const app = new Hono();

app.use(logger(), cors());

const userSchema = z.object({ name: z.string().min(1), email: z.string().email() });

app.post('/users', zValidator('json', userSchema), async (c) => {
  const data = c.req.valid('json');
  return c.json({ id: crypto.randomUUID(), ...data }, 201);
});

export default app;
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build the same CRUD API in Express, Fastify, and Hono
- [ ] Add request validation using Fastify schema or Hono + Zod
- [ ] Add a custom middleware for request logging
- [ ] Centralize error handling
- [ ] Compare benchmarks (use `autocannon`)

</details>

---

## Phase 7: REST API Patterns

![Phase](https://img.shields.io/badge/Phase-7%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Ship REST APIs that don't embarrass you in code review.

**What this phase is about.** Real APIs need: consistent **resource URLs**, correct HTTP **status codes**, **idempotency**, **pagination** (cursor or offset), **filtering/sorting**, **versioning**, **OpenAPI** docs (auto-generated), **DTOs** vs models, error envelopes, and the **HATEOAS** debate (mostly: skip it).

**Why it matters.** Anyone can build a REST API; few build one a stranger can use without asking questions. This phase is what separates "junior REST" from "production REST."

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | RESTful Resource Design | Nouns not verbs: `/users` (GET list, POST create), `/users/:id` (GET/PUT/PATCH/DELETE) |
| 2 | HTTP Methods | GET (read, idempotent), POST (create), PUT (replace), PATCH (partial), DELETE (remove) |
| 3 | Status Codes | 200 OK, 201 Created, 204 No Content, 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 409 Conflict, 422 Unprocessable, 500 Internal |
| 4 | Idempotency | GET, PUT, DELETE are idempotent. POST is not. Why this matters for retries |
| 5 | Validation | Zod or schema-first (Fastify). Validate at the boundary; trust internally |
| 6 | DTOs vs Domain Models | Don't expose your DB schema. Map between layers |
| 7 | Pagination — Offset | `?page=2&limit=20`. Simple but slow on huge tables |
| 8 | Pagination — Cursor | `?cursor=abc&limit=20`. Faster, stable for changing data |
| 9 | Filtering & Sorting | `?status=active&sort=-createdAt`. Whitelist allowed fields |
| 10 | Versioning | URL (`/v1/users`) vs header (`Accept: application/vnd.x.v2+json`) |
| 11 | OpenAPI / Swagger | Auto-generate docs from Fastify schemas or `@hono/zod-openapi` |
| 12 | Error Envelopes | Consistent shape: `{ error: { code, message, details } }` |
| 13 | Webhooks | Receive events from third parties. Verify signatures (Stripe, GitHub) |
| 14 | Rate Limiting | Token bucket per IP / user. Return `429 Too Many Requests` with `Retry-After` |
| 15 | Idempotency Keys | Client-supplied keys to dedupe POSTs (like Stripe) |
| 16 | GraphQL & tRPC (Brief) | Alternatives. tRPC = type-safe RPC over HTTP, no schema language |

> [!IMPORTANT]
> **Validate at the boundary; trust internally.** Use Zod (or your framework's schema) on every incoming request body, query, and params. Never trust client input.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a fully RESTful CRUD with proper status codes
- [ ] Add Zod validation on body, query, and params
- [ ] Implement cursor pagination
- [ ] Add OpenAPI docs at `/docs`
- [ ] Standardize error responses
- [ ] Verify a Stripe webhook signature

</details>

---

## Phase 8: Databases & ORMs

![Phase](https://img.shields.io/badge/Phase-8%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Talk to a database the modern way: TypeScript-first, type-safe, migration-driven.

**What this phase is about.** PostgreSQL is the default in 2026. Three ORM/query-builder options dominate Node:
- **[Drizzle](https://orm.drizzle.team/)** — TypeScript-first, SQL-like syntax, lightweight. **Recommended for new projects.**
- **[Prisma](https://www.prisma.io/)** — full ORM, schema-first, great DX. Heavy but feature-rich.
- **[Kysely](https://kysely.dev/)** — pure type-safe query builder. No magic, no ORM overhead.

You'll also meet **Redis** (cache + pub/sub + queues), **MongoDB** (document store via Mongoose), migrations (drizzle-kit, Prisma Migrate, Alembic-style), and connection pooling.

**Why it matters.** Most production bugs are database bugs. Most slow APIs are slow because of bad queries. This phase decides whether your backend can survive scale.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Pick a Database | Postgres = default. SQLite = local. Redis = cache. MongoDB = niche |
| 2 | Postgres + `pg` | The raw driver. `node-postgres` |
| 3 | Connection Pools | Always pool. Tune `max` based on Postgres limits |
| 4 | **Drizzle ORM** | Schema as TS, queries that look like SQL, lightning fast |
| 5 | **Prisma** | Schema-first, codegen client, schema migrations |
| 6 | **Kysely** | Pure type-safe SQL builder — no ORM magic |
| 7 | Migrations | Drizzle Kit, Prisma Migrate, or `node-pg-migrate` |
| 8 | Schema Design Recap | Foreign keys, indexes, JSONB columns. See the [SQL Syllabus](sql.md) |
| 9 | Transactions | All-or-nothing operations. `begin/commit/rollback` |
| 10 | The N+1 Problem | Loading a parent then querying children in a loop = 1+N queries. Fix with joins or DataLoader |
| 11 | Read Replicas | Spread reads across replicas; writes to primary |
| 12 | **Redis** | In-memory store. Cache, sessions, rate limit counters, pub/sub |
| 13 | **BullMQ** | Job queue on Redis — background work, retries, scheduled jobs |
| 14 | MongoDB + Mongoose | Document model, schema, populate (joins) |
| 15 | Vector DBs | pgvector (Postgres extension), Pinecone, Qdrant — for AI/RAG |
| 16 | Cloud Postgres | Neon (Vercel default), Supabase, Railway, AWS RDS |

```ts
// Drizzle ORM example
import { pgTable, serial, text, timestamp } from 'drizzle-orm/pg-core';
import { drizzle } from 'drizzle-orm/postgres-js';
import postgres from 'postgres';

export const users = pgTable('users', {
  id: serial('id').primaryKey(),
  email: text('email').notNull().unique(),
  name: text('name').notNull(),
  createdAt: timestamp('created_at').defaultNow(),
});

const client = postgres(process.env.DATABASE_URL!);
export const db = drizzle(client, { schema: { users } });

// Type-safe query
const allUsers = await db.select().from(users).limit(10);
```

> [!TIP]
> The 2026 default DB stack: **Postgres on [Neon](https://neon.tech/) + Drizzle ORM + Drizzle Kit migrations**. Free tier, instant branching, type-safe end-to-end.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Connect to Postgres with `pg` and a connection pool
- [ ] Define a schema with Drizzle and run a migration
- [ ] Write joins, filters, and pagination type-safely
- [ ] Wrap multiple statements in a transaction
- [ ] Spot and fix an N+1 query pattern
- [ ] Set up Redis caching for a slow endpoint

</details>

---

## Phase 9: Authentication & Security

![Phase](https://img.shields.io/badge/Phase-9%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Don't roll your own auth. But understand it well enough to know when a vendor is wrong.

**What this phase is about.** **Password hashing** done right (`argon2id` > `bcrypt` > `scrypt` > anything-else), **session-based** vs **token-based** (JWT) auth, **OAuth 2.0** + **OIDC**, **CSRF**, **CORS**, **rate limiting**, the **OWASP Top 10**. In 2026 most teams don't write auth from scratch — they use **Clerk**, **Auth.js**, or **Better-Auth**. This phase teaches you to use them well *and* to recognize when something's off.

**Why it matters.** Auth bugs make headlines (and lawsuits). Security is the area where one mistake = the whole company. Senior interviews always ask about it.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Password Hashing | Use **argon2id**. Never store plaintext. Never use MD5/SHA-1 alone |
| 2 | Sessions vs JWT | Sessions: server-side state, simple to revoke. JWT: stateless, harder to invalidate |
| 3 | Cookies | `HttpOnly`, `Secure`, `SameSite=Lax`. **Never store JWTs in localStorage** |
| 4 | JWT Internals | Header.Payload.Signature. Verify signature server-side. Short access tokens + refresh tokens |
| 5 | OAuth 2.0 + OIDC | "Sign in with Google/GitHub". Authorization code + PKCE flow |
| 6 | Magic Links / Passwordless | Email-based one-time login (Slack, Notion). Easy + secure |
| 7 | MFA / 2FA | TOTP via apps (Google Authenticator). WebAuthn / Passkeys (modern, phishing-proof) |
| 8 | RBAC / Permissions | Role-based access (admin, user). Scope-based for APIs |
| 9 | Auth Libraries | **Auth.js** (Next.js + Node), **Better-Auth**, **Lucia**, **Clerk** (managed), **Supabase Auth**, **WorkOS** |
| 10 | OWASP Top 10 | Injection, broken auth, sensitive data exposure, XSS, CSRF, etc. |
| 11 | CSRF Protection | SameSite cookies + tokens for traditional apps; not needed for cookie-less Bearer auth |
| 12 | CORS | Configure allowed origins precisely. Never `*` for credentialed requests |
| 13 | SQL Injection Prevention | Always use parameterized queries (your ORM does this) |
| 14 | Rate Limiting & Brute Force | Per-IP, per-account locks, exponential back-off |
| 15 | Secrets Management | `.env` for dev. Vercel/Doppler/AWS Secrets Manager for prod. Never commit secrets |
| 16 | Security Headers | `helmet`, CSP, HSTS, X-Content-Type-Options |
| 17 | `npm audit` & Dependabot | Keep deps patched. Auto-PRs for vulnerabilities |

> [!CAUTION]
> **Three mistakes that lose data:** (1) MD5/SHA-1 for passwords. (2) JWT in localStorage (XSS = your token gone). (3) Trusting client-set "admin" flags. Avoid all three.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Hash a password with `argon2`
- [ ] Issue and verify a JWT, with refresh-token rotation
- [ ] Add Google OAuth via Auth.js
- [ ] Implement TOTP-based 2FA
- [ ] Set up rate limiting per IP
- [ ] Run `npm audit` and resolve a vulnerability

</details>

---

## Phase 10: Real-time — WebSockets, SSE, Streaming

![Phase](https://img.shields.io/badge/Phase-10%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Live data — chats, dashboards, AI streaming, multiplayer.

**What this phase is about.** Three protocols cover most real-time needs:
- **WebSockets** — bidirectional, persistent. Chat, multiplayer, live cursors.
- **Server-Sent Events (SSE)** — server → client, plain HTTP, auto-reconnect. Live feeds, AI streaming.
- **HTTP Streaming** (`fetch` with `transfer-encoding: chunked`) — modern AI responses (ChatGPT-style), large CSV downloads.

You'll also learn **Socket.io** (high-level WS framework) and **presence** systems (who's online).

**Why it matters.** Real-time is one of Node's biggest strengths. Every modern app has a real-time component — and AI apps *demand* streaming.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | When to Use Which | WS for bidirectional, SSE for one-way push, streaming for one-shot long responses |
| 2 | The `ws` Library | Lightweight WS library. The standard primitive |
| 3 | Native WebSocket Client (Node 22+) | Built-in `WebSocket` global — no library needed for clients |
| 4 | Socket.io | Higher-level: rooms, namespaces, fallback to long-polling, automatic reconnect |
| 5 | Connection Lifecycle | Connect → handshake → message → close. Cleanup on disconnect |
| 6 | Pings, Heartbeats, Reconnection | Detect dead connections; client retry with back-off |
| 7 | Rooms & Channels | Subscribe a connection to a "room" (chat channel, document, game) |
| 8 | Scaling WebSockets | Sticky sessions + Redis pub/sub adapter for multi-server fan-out |
| 9 | Presence Systems | "Who's online?" "Who's typing?" — usually Redis-backed |
| 10 | SSE | `Content-Type: text/event-stream`. Built-in browser auto-reconnect |
| 11 | HTTP Streaming for AI | `ReadableStream` + `transfer-encoding: chunked` |
| 12 | Backpressure | Don't queue infinitely if the client is slow. Drop or buffer with limits |
| 13 | Auth for WebSockets | Pass token in connection URL, verify before accepting |
| 14 | CRDTs (Brief) | For collab editing — Yjs is the standard |

```ts
// Server-Sent Events for AI streaming
app.get('/chat/stream', async (c) => {
  return new Response(
    new ReadableStream({
      async start(controller) {
        for await (const chunk of askLLM(prompt)) {
          controller.enqueue(`data: ${JSON.stringify({ chunk })}\n\n`);
        }
        controller.close();
      },
    }),
    { headers: { 'Content-Type': 'text/event-stream' } }
  );
});
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a multi-room chat with `ws` and rooms
- [ ] Build the same chat with Socket.io
- [ ] Stream AI tokens to a client via SSE
- [ ] Stream AI tokens via HTTP `ReadableStream`
- [ ] Add presence ("who's online") with Redis

</details>

---

## Phase 11: Testing & Quality

![Phase](https://img.shields.io/badge/Phase-11%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Tested code is shippable code. Untested code is a coin flip.

**What this phase is about.** Modern Node testing in 2026: **Vitest** (the fast default) or **`node:test`** (built-in, no deps), **Supertest** for HTTP integration tests, **Testcontainers** for real Postgres in CI, **Playwright** for E2E. Linters: **Biome** (10× faster, replaces ESLint+Prettier) or **ESLint + Prettier**. **TypeScript** in strict mode. **Husky + lint-staged** for pre-commit gates.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Testing Pyramid | Unit (many, fast) → Integration (some) → E2E (few, slow) |
| 2 | Vitest | The dominant Node test runner — 10× faster than Jest, ESM-first, native TS |
| 3 | `node:test` | Node's built-in test runner. Use when you want zero dependencies |
| 4 | Assertions | `expect(x).toBe(y)`, `toEqual`, `toThrow`, `toMatchObject` |
| 5 | Setup / Teardown | `beforeEach`, `afterEach`, `beforeAll`, `afterAll` |
| 6 | Mocking | `vi.fn()`, `vi.mock(...)`, dependency injection |
| 7 | Supertest | HTTP integration tests against your live app |
| 8 | Testcontainers | Real Postgres / Kafka / Redis in Docker for CI tests |
| 9 | Playwright (Brief) | Browser E2E for full-stack apps |
| 10 | Coverage | `--coverage` flag. Aim 80%+ on critical paths |
| 11 | TDD | Red → Green → Refactor cycle |
| 12 | **Biome** | Rust-based formatter + linter, replaces ESLint + Prettier |
| 13 | ESLint + Prettier | The classic combo — slower, more configurable |
| 14 | TypeScript Strict | `strict: true`, `noUncheckedIndexedAccess: true` |
| 15 | pre-commit Hooks | **Husky** + **lint-staged** — gate quality on every commit |
| 16 | CI/CD | GitHub Actions: lint → test → build → deploy |

```ts
import { describe, test, expect } from 'vitest';
import request from 'supertest';
import { buildApp } from '../src/app.js';

describe('GET /health', () => {
  test('returns 200 OK', async () => {
    const app = await buildApp();
    const res = await request(app.server).get('/health');
    expect(res.status).toBe(200);
    expect(res.body).toMatchObject({ status: 'ok' });
  });
});
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 10+ Vitest unit tests for a module
- [ ] Add Supertest integration tests for an API
- [ ] Use Testcontainers to spin up Postgres in CI
- [ ] Set up Biome (or ESLint + Prettier) with pre-commit hooks
- [ ] Configure GitHub Actions to test on every PR
- [ ] Achieve 80%+ coverage on a project

</details>

---

## Phase 12: Performance, Observability & Scaling

![Phase](https://img.shields.io/badge/Phase-12%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Make it fast. Then know it's fast. Then keep it fast in production.

**What this phase is about.** Profile before you optimize (`--inspect` + Chrome DevTools, **clinic.js**, **0x**), parallelize CPU work with **worker threads** or **`cluster`** (or just multiple containers), add **structured logging** with **pino**, **distributed tracing** with **OpenTelemetry**, and metrics with **Prometheus + Grafana** or **Datadog**.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Profile First | Don't optimize what you didn't measure |
| 2 | `--inspect` + Chrome DevTools | CPU profiles, heap snapshots, async stacks |
| 3 | `clinic.js` & `0x` | Flame graphs for Node — find the hot function |
| 4 | Memory Leaks | Heap snapshots, common patterns (closures over big objects, leaking listeners) |
| 5 | Worker Threads | True parallelism for CPU-bound tasks (image processing, hashing, parsing) |
| 6 | The `cluster` Module | Fork N processes, one per CPU core. Mostly replaced by container scaling |
| 7 | Container Scaling | The modern answer: many small containers, load-balanced |
| 8 | Caching | Redis, in-memory LRU, HTTP cache headers, CDN |
| 9 | **pino** | The fastest Node logger. Structured JSON, child loggers, log levels |
| 10 | OpenTelemetry | Distributed tracing — see a request flow across services |
| 11 | Metrics | Prometheus + Grafana, or Datadog/New Relic |
| 12 | Health Checks | `/health`, `/ready` — for Kubernetes / load balancers |
| 13 | Graceful Shutdown | `SIGTERM` → drain connections → close DB → exit |
| 14 | Backpressure & Concurrency Limits | `p-limit` for parallelism, queue length limits |
| 15 | `autocannon` | Load test your endpoints |

```ts
// pino structured logger
import pino from 'pino';
const log = pino({ level: process.env.LOG_LEVEL ?? 'info' });

log.info({ userId, requestId }, 'User signed in');
log.error({ err, userId }, 'Sign-in failed');
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Profile a Node app with Chrome DevTools (CPU profile)
- [ ] Generate a flame graph with `clinic flame`
- [ ] Move a CPU-bound task to a worker thread
- [ ] Set up `pino` for structured logging
- [ ] Add OpenTelemetry tracing across a request
- [ ] Implement graceful shutdown on `SIGTERM`
- [ ] Load test with `autocannon`

</details>

---

## Phase 13: Deployment & Production

![Phase](https://img.shields.io/badge/Phase-13%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Get your code out the door. Keep it running.

**What this phase is about.** Three modern deploy paradigms:
- **Container** (Docker → ECS/Cloud Run/Fly.io/Kubernetes) — control + portability
- **Serverless** (Vercel Functions, AWS Lambda, Cloudflare Workers) — pay per request, auto-scale
- **PaaS** (Render, Railway, Heroku-style) — git push to deploy

You'll also learn **Docker** for Node, **environment management**, **secrets**, **process supervisors** (PM2 vs containers), and **CI/CD pipelines**.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Pick a Deploy Target | Container vs serverless vs PaaS — trade-offs |
| 2 | Dockerizing Node | Multi-stage builds, slim base images (`node:22-alpine`), non-root user, `.dockerignore` |
| 3 | Environment Variables | `.env` for dev, platform secret managers for prod |
| 4 | **Vercel** | The Next.js home. Functions in Node 20+, auto-scaling, free tier covers a lot |
| 5 | **Cloudflare Workers** | Edge runtime — closer to users, V8 isolates, fast cold starts |
| 6 | **AWS Lambda** | Mature serverless, integrates with everything in AWS |
| 7 | **Render / Railway / Fly.io** | Modern PaaS — git push to deploy |
| 8 | **Kubernetes (Briefly)** | When you need orchestration. Pair with the [Docker Syllabus](docker.md) |
| 9 | PM2 (Legacy) | Process manager for VMs. Containers replaced most use cases |
| 10 | Reverse Proxies | Caddy / nginx in front of your app for TLS, gzip, static files |
| 11 | TLS / HTTPS | Let's Encrypt + Caddy = free, auto-renewing certs |
| 12 | CI/CD | GitHub Actions: build → test → deploy on `main` |
| 13 | Zero-Downtime Deploys | Blue-green, rolling, canary patterns |
| 14 | Monitoring & Alerts | Datadog, Sentry, BetterStack — sleep through the night |
| 15 | Backups & DR | DB backups, point-in-time recovery, runbooks |

```dockerfile
# Multi-stage Node Dockerfile (production-ready)
FROM node:22-alpine AS deps
WORKDIR /app
COPY package*.json pnpm-lock.yaml ./
RUN corepack enable && pnpm install --frozen-lockfile

FROM node:22-alpine AS build
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
RUN pnpm build

FROM node:22-alpine AS prod
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/dist ./dist
COPY --from=deps /app/node_modules ./node_modules
USER node
EXPOSE 3000
CMD ["node", "dist/index.js"]
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Dockerize a Node app with a multi-stage build
- [ ] Deploy to Vercel from GitHub (auto-deploy on push)
- [ ] Deploy to Fly.io with `fly launch`
- [ ] Deploy a Hono app to Cloudflare Workers
- [ ] Set up GitHub Actions: lint → test → build → deploy
- [ ] Add Sentry error tracking

</details>

---

## Phase 14: The Node.js Ecosystem

![Phase](https://img.shields.io/badge/Phase-14%2F15-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The libraries you'll meet on every job posting. Recognize them all; deeply learn 8–10.

### 14.1 — Web Frameworks

| Framework | Best For |
|-----------|----------|
| **[Fastify](https://fastify.dev/)** | Modern Node servers, schema-first, fast |
| **[Hono](https://hono.dev/)** | Edge / serverless / Bun / Deno |
| **[Express](https://expressjs.com/)** | Maintaining legacy apps |
| **[NestJS](https://nestjs.com/)** | Enterprise, Angular-style decorators |
| **[Koa](https://koajs.com/)** | Express alternative (legacy modern) |
| **[Elysia](https://elysiajs.com/)** | Bun-native |
| **[h3](https://github.com/unjs/h3)** | The HTTP framework powering Nitro / Nuxt |

### 14.2 — Validation / Schemas

| Library | What It Is |
|---------|-----------|
| **[Zod](https://zod.dev/)** | The dominant runtime + types schema library |
| **[Valibot](https://valibot.dev/)** | Tree-shakeable Zod alternative |
| **[ArkType](https://arktype.io/)** | Fastest TS-native validator |
| **[TypeBox](https://github.com/sinclairzx81/typebox)** | JSON Schema + TS types |
| **[Yup](https://github.com/jquense/yup)** | The classic validator |
| **[Joi](https://joi.dev/)** | Hapi.js's validator, server-only |

### 14.3 — ORMs & Query Builders

| Library | What It Is |
|---------|-----------|
| **[Drizzle](https://orm.drizzle.team/)** | TS-first, lightweight, SQL-like |
| **[Prisma](https://www.prisma.io/)** | Schema-first, full ORM |
| **[Kysely](https://kysely.dev/)** | Pure type-safe SQL builder |
| **[TypeORM](https://typeorm.io/)** | Decorator-based (legacy) |
| **[MikroORM](https://mikro-orm.io/)** | Identity map ORM |
| **[Mongoose](https://mongoosejs.com/)** | MongoDB ODM |
| **[Sequelize](https://sequelize.org/)** | The classic JS ORM (legacy) |

### 14.4 — Auth

| Library | What It Is |
|---------|-----------|
| **[Auth.js](https://authjs.dev/)** | Open-source auth (formerly NextAuth). Works with Next, Express, etc. |
| **[Better-Auth](https://www.better-auth.com/)** | Modern TS-first auth library |
| **[Lucia](https://lucia-auth.com/)** | Lightweight session-based auth |
| **[Clerk](https://clerk.com/)** | Hosted auth — drop-in components |
| **[Supabase Auth](https://supabase.com/auth)** | Bundled with Supabase |
| **[WorkOS](https://workos.com/)** | Enterprise SSO, SAML, SCIM |
| **[Passport](http://www.passportjs.org/)** | The classic strategy-based auth (legacy) |

### 14.5 — Real-time

| Library | What It Is |
|---------|-----------|
| **[Socket.io](https://socket.io/)** | High-level WS framework, fallbacks |
| **[ws](https://github.com/websockets/ws)** | The minimal WS library |
| **[Liveblocks](https://liveblocks.io/)** | Hosted multiplayer (cursors, presence, comments) |
| **[Yjs](https://yjs.dev/)** | CRDT for collab editing |
| **[Pusher](https://pusher.com/)** / **[Ably](https://ably.com/)** | Hosted real-time |
| **[PartyKit](https://www.partykit.io/)** | Real-time on Cloudflare |

### 14.6 — Queues & Background Jobs

| Library | What It Is |
|---------|-----------|
| **[BullMQ](https://docs.bullmq.io/)** | Redis-backed, the dominant queue |
| **[Inngest](https://www.inngest.com/)** | Serverless workflow engine |
| **[Trigger.dev](https://trigger.dev/)** | Background jobs as code |
| **[Resque](https://resque.io/)** | Older Redis queue |
| **[Agenda](https://github.com/agenda/agenda)** | MongoDB-backed cron jobs |

### 14.7 — Email

| Library | What It Is |
|---------|-----------|
| **[Resend](https://resend.com/)** | Modern transactional email API + React Email templates |
| **[Nodemailer](https://nodemailer.com/)** | The classic SMTP library |
| **[SendGrid SDK](https://github.com/sendgrid/sendgrid-nodejs)** | Twilio's email |
| **[React Email](https://react.email/)** | Build email templates as React components |

### 14.8 — File Storage

| Library | What It Is |
|---------|-----------|
| **[AWS SDK v3](https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/welcome.html)** | S3, SES, etc. — the standard |
| **[Vercel Blob](https://vercel.com/docs/storage/vercel-blob)** | Vercel's file storage |
| **[Cloudflare R2](https://www.cloudflare.com/developer-platform/r2/)** | S3-compatible, no egress fees |
| **[Uploadthing](https://uploadthing.com/)** | Drop-in upload SDK |

### 14.9 — Logging / Observability

| Library | What It Is |
|---------|-----------|
| **[pino](https://getpino.io/)** | The fastest JSON logger |
| **[winston](https://github.com/winstonjs/winston)** | The classic logger |
| **[OpenTelemetry](https://opentelemetry.io/)** | Distributed tracing standard |
| **[Sentry SDK](https://sentry.io/)** | Error tracking |
| **[Datadog APM](https://docs.datadoghq.com/tracing/)** | Hosted tracing + metrics |

### 14.10 — HTTP Clients

| Library | What It Is |
|---------|-----------|
| **Native `fetch`** (Node 18+) | The default — no library needed |
| **[undici](https://github.com/nodejs/undici)** | The HTTP client powering native fetch — best perf |
| **[ofetch](https://github.com/unjs/ofetch)** | Better defaults, retries, hooks |
| **[ky](https://github.com/sindresorhus/ky)** | Tiny fetch wrapper with retries |
| **[axios](https://axios-http.com/)** | The classic — many existing codebases |
| **[got](https://github.com/sindresorhus/got)** | Sindre Sorhus's HTTP client |

### 14.11 — CLI Tools

| Library | What It Is |
|---------|-----------|
| **[Commander](https://github.com/tj/commander.js)** | The classic CLI framework |
| **[Yargs](https://yargs.js.org/)** | Argument parser, mature |
| **[Clack](https://github.com/natemoo-re/clack)** | Beautiful prompts, modern |
| **[Inquirer](https://github.com/SBoudrias/Inquirer.js)** | Classic prompts |
| **[Ora](https://github.com/sindresorhus/ora)** | Spinners |
| **[Chalk](https://github.com/chalk/chalk)** | Terminal colors |
| **[Bun's `parseArgs`](https://bun.sh/docs/cli/run)** | Built-in (and Node has `util.parseArgs` too) |

### 14.12 — Build / Bundlers

| Tool | What It Does |
|------|--------------|
| **[esbuild](https://esbuild.github.io/)** | Insanely fast bundler |
| **[tsx](https://tsx.is/)** | Run TS directly. The 2026 "ts-node" replacement |
| **[tsup](https://tsup.egoist.dev/)** | Bundle TS packages with esbuild |
| **[swc](https://swc.rs/)** | Rust-based JS/TS compiler |
| **[Rollup](https://rollupjs.org/)** | Bundler used by Vite for production |
| **[Vite](https://vitejs.dev/)** | Mostly frontend, but works for libraries |

### 14.13 — Testing

| Library | What It Is |
|---------|-----------|
| **[Vitest](https://vitest.dev/)** | The dominant test runner |
| **[node:test](https://nodejs.org/api/test.html)** | Built-in, zero deps |
| **[Jest](https://jestjs.io/)** | The classic — many existing codebases |
| **[Mocha](https://mochajs.org/)** | Older test framework |
| **[Supertest](https://github.com/ladjs/supertest)** | HTTP integration tests |
| **[Testcontainers](https://node.testcontainers.org/)** | Real DBs in CI |
| **[Playwright](https://playwright.dev/)** | E2E in real browsers |
| **[MSW](https://mswjs.io/)** | Mock HTTP at the network layer |

### 14.14 — Linting / Formatting

| Tool | What It Does |
|------|--------------|
| **[Biome](https://biomejs.dev/)** | Rust formatter + linter — replaces ESLint + Prettier |
| **[ESLint](https://eslint.org/)** | The classic linter |
| **[Prettier](https://prettier.io/)** | The classic formatter |
| **[oxlint](https://oxc.rs/)** | Rust-based linter (faster than ESLint) |

### 14.15 — Monorepo

| Tool | What It Is |
|------|-----------|
| **[pnpm workspaces](https://pnpm.io/workspaces)** | The simplest monorepo |
| **[Turborepo](https://turbo.build/)** | Build orchestrator on top |
| **[Nx](https://nx.dev/)** | Full monorepo platform |
| **[Bazel](https://bazel.build/)** | Heavyweight, used at scale |
| **[Changesets](https://github.com/changesets/changesets)** | Versioning & changelogs |

### 14.16 — AI SDKs (the 2026 frontier)

| Library | What It Is |
|---------|-----------|
| **[Vercel AI SDK](https://sdk.vercel.ai/)** | Streaming + tool calling + multi-provider — the default |
| **[Anthropic TS SDK](https://github.com/anthropics/anthropic-sdk-typescript)** | Claude API |
| **[OpenAI Node SDK](https://github.com/openai/openai-node)** | GPT API |
| **[LangChain.js](https://js.langchain.com/)** | Agents, chains, RAG |
| **[LlamaIndex.ts](https://ts.llamaindex.ai/)** | Data framework for LLMs |
| **[Mastra](https://mastra.ai/)** | Agent framework |

### 14.17 — Edge Runtimes & Frameworks

| Tool | What It Is |
|------|-----------|
| **[Cloudflare Workers](https://workers.cloudflare.com/)** | V8 isolates, global edge |
| **[Vercel Edge Functions](https://vercel.com/docs/functions)** | Runs at the edge |
| **[Fastly Compute](https://www.fastly.com/products/edge-compute)** | WASM-based edge |
| **[Hono](https://hono.dev/)** | Edge-native framework |
| **[Nitro](https://nitro.unjs.io/)** | Universal Node + edge framework (powers Nuxt) |

> [!IMPORTANT]
> Don't learn all of them. **Recognize** all of them. **Deeply learn** the 2026 default stack: **TypeScript + Fastify (or Hono) + Drizzle + Postgres + Zod + pino + Vitest + BullMQ + Redis + Auth.js (or Better-Auth) + Vercel AI SDK + Vercel/Render deploy**. That's roughly what 70% of new Node jobs use.

---

## Phase 15: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-15%2F15-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You finished Node. Pick a track and ship.

### 15.1 — Pick a Specialization

| Track | What You Build | Key Tools |
|-------|----------------|-----------|
| **REST/GraphQL APIs** | CRUD, integrations, multi-tenant | Fastify/Hono + Drizzle + Postgres + Zod |
| **Real-time / Multiplayer** | Chat, dashboards, collab | ws/Socket.io + Redis + Yjs |
| **AI Backend** | Agents, RAG, streaming | Vercel AI SDK + Anthropic + pgvector |
| **Edge / Serverless** | Cloudflare Workers, Vercel | Hono + KV + D1 |
| **CLI Tools** | Dev tooling, automation | Commander + Clack + tsx |
| **Data Pipelines** | ETL, ingestion | streams + BullMQ + Postgres |
| **Microservices** | Service mesh, message-driven | NestJS or Fastify + Kafka + gRPC |
| **DevOps Tooling** | Internal platforms | Node + Docker + Kubernetes |

### 15.2 — Required Cross-cutting Skills

| Skill | Why |
|-------|-----|
| **[TypeScript](typescript.md)** | The 2026 default. Non-negotiable for senior |
| **[Git](git.md)** | Mandatory |
| **[SQL](sql.md)** | Every backend |
| **[Docker](docker.md)** | Containers everywhere |
| **CI/CD** | GitHub Actions, GitLab CI |
| **Cloud basics** | AWS / GCP / Vercel / Cloudflare |
| **Linux / shell** | Every server runs Linux |

### 15.3 — Where to Deploy

| Target | Best For |
|--------|----------|
| **[Vercel](https://vercel.com/)** | Next.js + Functions; free tier covers a lot |
| **[Render](https://render.com/)** | Full backend + DB |
| **[Fly.io](https://fly.io/)** | Global edge with regions |
| **[Railway](https://railway.app/)** | git push to deploy |
| **[Cloudflare Workers](https://workers.cloudflare.com/)** | Edge-native (Hono) |
| **AWS Lambda / ECS / Fargate** | Enterprise |
| **Kubernetes (EKS/GKE)** | Big scale, big team |

### 15.4 — Suggested Order After This Syllabus

```
TypeScript (deep) → SQL → Docker → Build & deploy a Fastify+Drizzle app → AI capstone → Repeat
```

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do Instead |
|---|---------|----------------|------------|
| 1 | Blocking the event loop | Sync fs / heavy CPU = every other request waits | Async APIs; worker threads for CPU work |
| 2 | Swallowed unhandled rejections | Crashes silently or noisily later | `process.on('unhandledRejection')`; try/catch around async |
| 3 | `axios` for simple cases | Extra dep, slower than native | Use native `fetch` |
| 4 | Storing JWTs in localStorage | XSS = all tokens stolen | `HttpOnly` cookies |
| 5 | Plain-text passwords | Disastrous breach | `argon2id` |
| 6 | Mixing CJS and ESM | Subtle bugs, broken imports | Pick ESM for new code |
| 7 | No timeouts on `fetch` | Hung requests pile up | Pass an `AbortSignal.timeout(5000)` |
| 8 | `console.log` in prod | Slow, no levels, no structure | `pino` structured logging |
| 9 | Express for new projects | Slow, no built-in validation, dated | Fastify or Hono |
| 10 | Sequelize / TypeORM for new projects | Heavy, leaky abstractions | Drizzle or Prisma |
| 11 | No graceful shutdown | Drops in-flight requests on deploy | Listen to `SIGTERM`, drain, exit |
| 12 | No connection pool | New DB connection per request = slow + fragile | Always pool |
| 13 | Hardcoded secrets | Leak on every push | `.env` files + secret managers |
| 14 | Sync `fs.*` in request handlers | Blocks the loop | `fs/promises` always |
| 15 | Trusting client input | Top OWASP issue | Zod validate at the boundary |
| 16 | Missing error boundaries on async | Crashes entire process | Centralized error handler in framework |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is Node.js?**
   - A JavaScript runtime built on V8 + libuv. Single-threaded with an event loop and non-blocking I/O. Created by Ryan Dahl in 2009.

2. **CommonJS vs ESM?**
   - CJS: `require`/`module.exports`, sync, default in older Node. ESM: `import`/`export`, async, modern. New code should be ESM with `"type": "module"`.

3. **What's the event loop?**
   - The mechanism that lets single-threaded JS handle async I/O. Has phases: timers, pending, poll, check, close. Microtasks (Promises) drain between every macrotask.

4. **Why is Node single-threaded?**
   - Your JS runs on one thread; libuv has a thread pool for slow syscalls. Avoids data races, simpler model. CPU-bound work needs worker threads or separate processes.

5. **`require` vs `import`?**
   - `require` is synchronous and CJS. `import` is asynchronous and ESM. ESM enables tree-shaking and top-level await.

6. **What is npm?**
   - Node Package Manager. Installs packages from the npm registry (3M+ packages). pnpm and yarn are alternatives; pnpm is recommended in 2026.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **`Promise.all` vs `Promise.allSettled`?**
   - `all` rejects on the first rejection (fast-fail). `allSettled` waits for everything and returns `{status, value/reason}` for each.

2. **What's a stream and when do you use one?**
   - A way to process data in chunks instead of loading it all in memory. Use for large files, HTTP responses, anything potentially big. `pipeline()` is the modern API.

3. **How do you handle errors in async code?**
   - `try/catch` with `async/await`. For top-level: `process.on('unhandledRejection')`. Centralize at the framework level (`fastify.setErrorHandler`).

4. **Sessions vs JWT?**
   - Sessions: server-side state, easy to revoke, more storage. JWT: stateless, scales horizontally, hard to invalidate before expiry. Use refresh tokens to mitigate.

5. **What's middleware?**
   - A function that runs in the request lifecycle, between the request arriving and the handler running. Used for logging, auth, parsing, CORS, etc.

6. **How do you prevent SQL injection?**
   - Always use parameterized queries (your ORM does this). Never concatenate user input into SQL. Validate input shape with Zod first.

7. **What is connection pooling and why?**
   - A pool of pre-opened DB connections shared across requests. Avoids the overhead of opening a new connection per request. Configure `max` based on the DB's `max_connections`.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Walk through the event loop phases.**
   - timers → pending callbacks → idle/prepare → poll (most I/O) → check (`setImmediate`) → close. Microtasks (Promises, `queueMicrotask`) drain between every callback. `process.nextTick` runs even before microtasks.

2. **Worker threads vs cluster vs child_process?**
   - **worker_threads**: in-process, share memory via `SharedArrayBuffer`. Best for CPU work. **cluster**: forks N Node processes, load-balances across them. Mostly replaced by container scaling. **child_process**: run any executable.

3. **How does Node handle backpressure on streams?**
   - Writable streams return `false` from `.write()` when their buffer is full. The producer should pause. The `pipeline()` function handles this automatically — it's the modern correct API.

4. **What's the difference between `setImmediate` and `setTimeout(fn, 0)`?**
   - Different phases. `setImmediate` runs in the *check* phase (after poll). `setTimeout(fn, 0)` runs in the *timers* phase. In I/O callbacks, `setImmediate` always wins.

5. **How do you debug a memory leak?**
   - Take heap snapshots over time with Chrome DevTools (`--inspect`). Compare. Find growing object types. Common causes: closures over big objects, event listeners not removed, caches without eviction.

6. **Design a rate limiter.**
   - Token-bucket or leaky-bucket. Per-user or per-IP. Store counters in Redis with TTL. Increment + check + return `429` with `Retry-After` header. For distributed, use a Redis Lua script for atomicity.

7. **What's the cost of `JSON.parse` on a hot path?**
   - Synchronous and CPU-bound. For a 10MB payload it can block the loop for hundreds of milliseconds. Mitigations: stream-parsing (`stream-json`), worker threads, smaller payloads, avoid double-parse via direct schema.

</details>

---

## Practice Projects

> [!TIP]
> Push every project to GitHub. Deploy to Vercel/Render/Fly.io. **5 deployed projects beat any tutorial certificate.**

### Project 1: CLI Task Manager
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

CLI app: add, list, complete, filter tasks. Persisted to JSON. Built with `node:fs/promises` + `Commander` + `node:test`.

**Skills:** core modules, async, fs, CLI parsing, native test runner.

---

### Project 2: File Processor with Streams
![Phase 4](https://img.shields.io/badge/After-Phase%204-yellow)

Walk a directory, gzip every `.log` file, write a Markdown report with sizes. Uses `pipeline`, recursive `readdir`, transform streams.

**Skills:** streams, fs, pipeline, async iteration.

---

### Project 3: REST API with Fastify + Drizzle + Zod
![Phase 5-8](https://img.shields.io/badge/After-Phase%205--8-yellow)

Production-style CRUD: users + posts + comments. Postgres + Drizzle + migrations. Zod validation. Pagination. OpenAPI docs at `/docs`. Tested with Vitest + Supertest.

**Skills:** Fastify, Drizzle, Zod, REST patterns, Vitest, Supertest.

---

### Project 4: Auth Service (JWT + OAuth + 2FA)
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

Sign up, sign in, password reset, OAuth (Google/GitHub), TOTP 2FA, refresh tokens, session management. argon2 hashing. Rate limiting. CSRF protection. Implemented with Better-Auth or from scratch.

**Skills:** argon2, JWT, OAuth, TOTP, sessions, rate limiting.

---

### Project 5: Real-time Chat
![Phase 10](https://img.shields.io/badge/After-Phase%2010-orange)

Multi-room chat: WebSocket server (`ws` + Hono), rooms, presence, message history (Postgres), typing indicators, file uploads (S3-compatible). Reconnection logic. 10k concurrent connections in load tests.

**Skills:** WebSockets, Redis pub/sub for scale, presence, file uploads.

---

### Project 6: Job Queue + Worker
![Phase 11-12](https://img.shields.io/badge/After-Phase%2011--12-red)

API enqueues image-processing jobs (resize + watermark). BullMQ workers process them. Status endpoints. Failure retries with exponential backoff. Metrics in Prometheus + Grafana. Distributed tracing.

**Skills:** BullMQ, Redis, worker threads, observability.

---

### Project 7: Edge API on Cloudflare Workers
![Phase 13](https://img.shields.io/badge/After-Phase%2013-red)

Build a low-latency API with Hono on Cloudflare Workers. Global KV cache. Rate limiting per IP. Sub-50ms p99 worldwide. Deploy with `wrangler`.

**Skills:** Hono, edge runtime, KV, deploy automation.

---

### Project 8: AI Backend with Streaming + RAG (Capstone)
![Phase 14](https://img.shields.io/badge/After-Phase%2014-red)

Your graduation project. A Fastify (or Hono) API where users upload PDFs / paste URLs / ask questions. Pipeline: extract text → chunk → embed → store in pgvector → on query, retrieve top-K → call **Claude** via Vercel AI SDK with **streaming** + **prompt caching** + **tool calling**. Auth (Better-Auth or Clerk). Rate limited. Tested. Deployed to Vercel/Fly.io. **Portfolio gold for any 2026 Node/AI interview.**

**Skills:** everything from all 15 phases — async, streaming, AI SDKs, RAG, vector DBs, auth, deploy.

---

## Resources

### Documentation

| Resource | Why |
|----------|-----|
| [nodejs.org/docs](https://nodejs.org/docs/latest/api/) | Official API reference |
| [Node.js Learn](https://nodejs.org/learn) | Official getting-started |
| [Fastify Docs](https://fastify.dev/docs/latest/) | The framework reference |
| [Hono Docs](https://hono.dev/docs/) | Edge-native framework |
| [Drizzle Docs](https://orm.drizzle.team/docs/overview) | TS-first ORM |
| [Vercel AI SDK](https://sdk.vercel.ai/docs) | LLM streaming + tool calling |
| [Anthropic Docs](https://docs.anthropic.com/) | Claude API |

### Books & Long-form

| Book | Why |
|------|-----|
| **Node.js Design Patterns (Mario Casciaro)** | The book to read at year 2 |
| **Node Cookbook (David Mark Clements)** | Practical recipes |
| **Building Microservices (Sam Newman)** | Architecture book — applies to Node |
| [Patterns.dev](https://www.patterns.dev/) | Free book on web patterns |

### Free Courses

| Course | Why |
|--------|-----|
| [The Odin Project — NodeJS](https://www.theodinproject.com/paths/full-stack-javascript) | Project-based |
| [freeCodeCamp Backend cert](https://www.freecodecamp.org/learn/back-end-development-and-apis/) | 100% free certification |

### YouTube

| Channel | Why |
|---------|-----|
| [Theo (t3.gg)](https://www.youtube.com/@t3dotgg) | Modern Node/TS opinions |
| [Web Dev Cody](https://www.youtube.com/@WebDevCody) | Project-based modern stack |
| [Jack Herrington](https://www.youtube.com/@jherr) | Architecture + perf |
| [Hussein Nasser](https://www.youtube.com/@hnasr) | DB internals + networking |
| [ByteGrad](https://www.youtube.com/@ByteGrad) | Practical projects |

### Roadmaps

| Resource | What |
|----------|------|
| [roadmap.sh — Node.js](https://roadmap.sh/nodejs) | Interactive roadmap |
| [roadmap.sh — Backend](https://roadmap.sh/backend) | Where Node fits |
| [roadmap.sh — AI Engineer](https://roadmap.sh/ai-engineer) | If going AI |

### Cheat Sheets

| Resource | What |
|----------|------|
| [Node.js Cheatsheet (devhints)](https://devhints.io/nodejs) | Quick reference |
| [TanStack Query (for full-stack)](https://tanstack.com/query/latest) | Server state |
| [Fastify schemas reference](https://fastify.dev/docs/latest/Reference/Validation-and-Serialization/) | JSON Schema |

### Newsletters & Podcasts

| Resource | Format |
|----------|--------|
| [Node Weekly](https://nodeweekly.com/) | Weekly newsletter |
| [Bytes](https://bytes.dev/) | Weekly newsletter — fun, sharp |
| [JS Party](https://changelog.com/jsparty) | Weekly podcast |
| [Syntax.fm](https://syntax.fm/) | Wes Bos & Scott Tolinski |

---

[Back to Main Syllabus](../README.md)

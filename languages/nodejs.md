# Node.js Syllabus

A complete, structured learning path for Node.js — from your first server to building production APIs with Express, databases, authentication, and deployment.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Node: v20+](https://img.shields.io/badge/Node-v20%2B-339933)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Core Modules](#phase-2-core-modules)
- [Phase 3: Async Patterns](#phase-3-async-patterns)
- [Phase 4: HTTP & Web Servers](#phase-4-http--web-servers)
- [Phase 5: Express.js](#phase-5-expressjs)
- [Phase 6: REST APIs](#phase-6-rest-apis)
- [Phase 7: Databases](#phase-7-databases)
- [Phase 8: Authentication & Security](#phase-8-authentication--security)
- [Phase 9: Advanced Patterns](#phase-9-advanced-patterns)
- [Phase 10: Testing & Deployment](#phase-10-testing--deployment)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Node.js is **JavaScript on the server**. You need strong JavaScript fundamentals — especially async/await, modules, and ES6+ features.

- JavaScript ES6+ (complete the [JavaScript Syllabus](javascript.md) first)
- Command line / terminal basics
- Understanding of HTTP (requests, responses, status codes)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Node.js is and set up your development environment.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Node.js | JavaScript runtime built on V8 — runs JS outside the browser. Single-threaded, event-driven, non-blocking |
| 2 | Node vs Browser | No DOM, no `window`. Instead: `global`, `process`, file system access, networking, OS interaction |
| 3 | Installation | Install Node.js LTS (v20+). Use `nvm` (Node Version Manager) to switch between versions |
| 4 | npm & pnpm | Package managers — `npm install`, `package.json`, `node_modules`, `package-lock.json`, semantic versioning |
| 5 | `package.json` | Dependencies, devDependencies, scripts, `"type": "module"` for ES modules, engines |
| 6 | ES Modules | `import`/`export` (modern) vs `require`/`module.exports` (legacy CommonJS). Use ESM for new projects |
| 7 | Running Scripts | `node app.js`, npm scripts (`npm run dev`), `npx` for one-off commands, REPL for quick experiments |

> [!TIP]
> Set `"type": "module"` in your `package.json` to use modern `import`/`export` syntax instead of `require()`:
> ```json
> {
>   "type": "module",
>   "scripts": {
>     "start": "node src/index.js",
>     "dev": "node --watch src/index.js"
>   }
> }
> ```
> Node.js v18+ has `--watch` mode built in — no need for `nodemon`.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Node.js and verify with `node --version`
- [ ] Create a `package.json` with `npm init`
- [ ] Write and run a `.js` file with ES module imports

</details>

---

## Phase 2: Core Modules

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Master Node's built-in modules — no npm packages needed.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `fs` (File System) | Read, write, create, delete files. `fs.readFile()`, `fs.writeFile()`, `fs/promises` for async |
| 2 | `path` | `path.join()`, `path.resolve()`, `path.basename()`, `path.extname()` — OS-safe file path handling |
| 3 | `http` | Create HTTP servers from scratch: `http.createServer((req, res) => {})` — the foundation of Express |
| 4 | `events` | `EventEmitter` — create custom event-driven architectures. `.on()`, `.emit()`, `.once()` |
| 5 | `process` | `process.env` (environment variables), `process.argv` (CLI arguments), `process.exit()`, `process.cwd()` |
| 6 | `os` | System info: `os.cpus()`, `os.freemem()`, `os.platform()`, `os.homedir()` |
| 7 | `streams` | Read/write data in chunks. `Readable`, `Writable`, `Transform`, `pipe()` — handle large files without memory issues |
| 8 | `crypto` | `crypto.randomUUID()`, hashing with `createHash()`, encryption — built-in security utilities |

> [!IMPORTANT]
> **Always use `fs/promises`** (not callback-based `fs`) for clean async file operations:
> ```javascript
> import { readFile, writeFile } from 'node:fs/promises';
>
> const data = await readFile('./config.json', 'utf-8');
> const config = JSON.parse(data);
> await writeFile('./output.json', JSON.stringify(config, null, 2));
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write files with `fs/promises`
- [ ] Create a simple HTTP server with the `http` module
- [ ] Use `EventEmitter` to build a custom event system

</details>

---

## Phase 3: Async Patterns

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Understand how Node.js handles concurrency without threads.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Event Loop | Node is single-threaded but non-blocking. The event loop processes callbacks from a queue while the main thread runs |
| 2 | Event Loop Phases | Timers → pending callbacks → poll → check → close. `setTimeout` vs `setImmediate` vs `process.nextTick` order |
| 3 | Callbacks | The original async pattern: `fs.readFile(path, (err, data) => {})`. Error-first convention |
| 4 | Promises | `new Promise((resolve, reject) => {})`. `.then()`, `.catch()`, `.finally()`. Promisify callback APIs |
| 5 | `async`/`await` | `await` pauses execution until the promise resolves. Always wrap in `try/catch`. The modern standard |
| 6 | `Promise.all()` & Friends | `Promise.all()` (wait for all), `Promise.allSettled()` (don't short-circuit), `Promise.race()` (first wins) |
| 7 | Streams | Process data chunk-by-chunk instead of loading everything into memory. `pipe()`, `pipeline()`, transform streams |
| 8 | Error Handling | Unhandled rejections crash Node. Always handle errors: `try/catch`, `.catch()`, `process.on('unhandledRejection')` |

> [!CAUTION]
> **Never block the event loop.** CPU-heavy operations (JSON parsing huge files, image processing, crypto) block all other requests. Use worker threads or child processes for heavy computation:
> ```javascript
> // WRONG — blocks the event loop for all users
> app.get('/hash', (req, res) => {
>   const result = heavyCryptoOperation(); // blocks!
>   res.json(result);
> });
>
> // RIGHT — offload to a worker thread
> import { Worker } from 'node:worker_threads';
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the event loop phases and callback queue
- [ ] Convert a callback-based function to async/await
- [ ] Process a large file using streams instead of `readFile`

</details>

---

## Phase 4: HTTP & Web Servers

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Build HTTP servers from scratch before using a framework.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Creating a Server | `http.createServer((req, res) => {}).listen(3000)` — handle requests and send responses |
| 2 | Request Object | `req.method`, `req.url`, `req.headers` — extract data from incoming requests |
| 3 | Response Object | `res.statusCode`, `res.setHeader()`, `res.end()`, `res.write()` — send data back to the client |
| 4 | Routing (Manual) | Parse `req.url` and `req.method` to route to different handlers — understand what Express automates |
| 5 | Parsing Request Body | Collect data from `req.on('data')` chunks, parse JSON with `JSON.parse()` |
| 6 | Serving Static Files | Read files with `fs` and send them with proper `Content-Type` headers |
| 7 | HTTP Methods | `GET` (read), `POST` (create), `PUT` (replace), `PATCH` (update), `DELETE` (remove) |

> [!TIP]
> Build a raw HTTP server first — then Express will make much more sense, because you'll understand what it's doing for you under the hood.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create an HTTP server that responds to different routes
- [ ] Parse a JSON request body manually
- [ ] Serve an HTML file with proper content type

</details>

---

## Phase 5: Express.js

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> The most popular Node.js framework — build web servers and APIs fast.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Express Setup | `npm install express` → `const app = express()` → `app.listen(3000)` — minimal server in 5 lines |
| 2 | Routing | `app.get('/users', handler)`, `app.post()`, `app.put()`, `app.delete()` — clean route definitions |
| 3 | Route Parameters | `app.get('/users/:id', (req, res) => {})` → `req.params.id` — dynamic URLs |
| 4 | Query Parameters | `/search?q=node&limit=10` → `req.query.q`, `req.query.limit` — filter and search |
| 5 | Middleware | `app.use((req, res, next) => {})` — functions that run before your route handler. Logging, auth, parsing |
| 6 | Built-in Middleware | `express.json()` (parse JSON body), `express.urlencoded()` (parse form data), `express.static()` (serve files) |
| 7 | Error Handling | `app.use((err, req, res, next) => {})` — centralized error handler. Always use 4 parameters |
| 8 | Router | `express.Router()` — split routes into separate files for organization |

> [!IMPORTANT]
> **Middleware is the core concept of Express.** Every request flows through a chain of middleware functions. Each one can modify `req`/`res` or call `next()` to pass to the next middleware:
> ```javascript
> // 1. Parse JSON body
> app.use(express.json());
>
> // 2. Log every request
> app.use((req, res, next) => {
>   console.log(`${req.method} ${req.url}`);
>   next(); // Pass to next middleware
> });
>
> // 3. Route handler (also middleware)
> app.get('/users', (req, res) => {
>   res.json(users);
> });
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create an Express server with 5+ routes
- [ ] Write custom middleware (logging, auth check)
- [ ] Implement centralized error handling

</details>

---

## Phase 6: REST APIs

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Design and build professional REST APIs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | REST Principles | Resources, HTTP verbs, stateless, URI design: `/api/users/:id`, not `/api/getUser` |
| 2 | CRUD Operations | `GET` (list/read), `POST` (create), `PUT`/`PATCH` (update), `DELETE` (remove) — map to database operations |
| 3 | Status Codes | `200` OK, `201` Created, `204` No Content, `400` Bad Request, `401` Unauthorized, `404` Not Found, `500` Server Error |
| 4 | Request Validation | Validate request body with Zod: `const schema = z.object({ name: z.string() }); schema.parse(req.body)` |
| 5 | Response Format | Consistent API envelope: `{ success: true, data: {...}, meta: { page, total } }` |
| 6 | Pagination | Offset-based (`?page=2&limit=20`) or cursor-based — don't return all records at once |
| 7 | Filtering & Sorting | `?status=active&sort=-createdAt` — query parameters for flexible data retrieval |
| 8 | API Versioning | `/api/v1/users` — version your API so changes don't break existing clients |

> [!TIP]
> Use Zod for request validation — it validates AND gives you TypeScript types:
> ```javascript
> import { z } from 'zod';
>
> const createUserSchema = z.object({
>   name: z.string().min(2),
>   email: z.string().email(),
>   age: z.number().int().min(0).optional()
> });
>
> app.post('/users', (req, res) => {
>   const result = createUserSchema.safeParse(req.body);
>   if (!result.success) return res.status(400).json(result.error);
>   // result.data is typed and validated
> });
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a complete CRUD API with proper status codes
- [ ] Add request validation with Zod
- [ ] Implement pagination and filtering

</details>

---

## Phase 7: Databases

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Connect your API to a database — store and retrieve real data.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | SQL vs NoSQL | SQL (PostgreSQL, MySQL): structured, relations, ACID. NoSQL (MongoDB): flexible, documents, horizontal scaling |
| 2 | MongoDB & Mongoose | Schema definition, models, CRUD operations, validation, population (joins), indexing |
| 3 | PostgreSQL & Prisma | Schema file, migrations, type-safe queries, relations, Prisma Studio for visual editing |
| 4 | SQL Basics | `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `JOIN`, `WHERE`, `ORDER BY`, `GROUP BY` — universal across SQL databases |
| 5 | ORMs & Query Builders | Prisma (type-safe, modern), Drizzle (SQL-like), Knex (query builder) — abstract database operations |
| 6 | Migrations | Version your database schema. `prisma migrate dev`, `knex migrate:latest` — track changes like git for your DB |
| 7 | Connection Pooling | Reuse database connections instead of creating new ones per request. `pool: { max: 20 }` |
| 8 | Data Modeling | One-to-many, many-to-many, embedded vs referenced documents, normalization vs denormalization |

> [!WARNING]
> **Never put database credentials in your code.** Use environment variables:
> ```bash
> # .env file (add to .gitignore!)
> DATABASE_URL="postgresql://user:pass@localhost:5432/mydb"
> ```
> ```javascript
> // Access in code
> const url = process.env.DATABASE_URL;
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Connect to MongoDB and perform CRUD with Mongoose
- [ ] Set up Prisma with PostgreSQL, create a schema, and run migrations
- [ ] Write SQL queries for filtering, joining, and aggregating data

</details>

---

## Phase 8: Authentication & Security

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Secure your API — authentication, authorization, and protection against common attacks.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Password Hashing | `bcrypt.hash(password, 10)` — never store plain text passwords. `bcrypt.compare()` to verify |
| 2 | JWT (JSON Web Tokens) | `jwt.sign(payload, secret)` → send token → `jwt.verify(token, secret)` — stateless authentication |
| 3 | Auth Middleware | Protect routes: extract token from `Authorization` header, verify, attach `req.user` |
| 4 | Sessions & Cookies | `express-session` for server-side sessions. `httpOnly`, `secure`, `sameSite` cookie flags |
| 5 | CORS | `cors()` middleware — control which origins can access your API. Whitelist specific domains |
| 6 | Helmet | `helmet()` — sets security HTTP headers. Prevents clickjacking, XSS, MIME sniffing attacks |
| 7 | Rate Limiting | `express-rate-limit` — prevent brute force and DDoS. `max: 100` requests per `windowMs: 15 * 60 * 1000` |
| 8 | Input Sanitization | Prevent SQL injection (parameterized queries), XSS (`express-validator`), NoSQL injection |
| 9 | OWASP Top 10 | The 10 most critical web security risks — injection, broken auth, sensitive data exposure, etc. |

> [!CAUTION]
> **Never store JWTs in localStorage** — it's vulnerable to XSS attacks. Use httpOnly cookies:
> ```javascript
> res.cookie('token', jwt, {
>   httpOnly: true,    // JS can't access it
>   secure: true,      // HTTPS only
>   sameSite: 'strict', // No cross-site sending
>   maxAge: 7 * 24 * 60 * 60 * 1000 // 7 days
> });
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Implement user registration and login with bcrypt + JWT
- [ ] Create auth middleware that protects API routes
- [ ] Add Helmet, CORS, and rate limiting to your server

</details>

---

## Phase 9: Advanced Patterns

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Scale your application with real-time features, caching, and background jobs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | WebSockets | `socket.io` or `ws` — real-time bidirectional communication (chat, live updates, notifications) |
| 2 | File Uploads | `multer` middleware — handle `multipart/form-data`, save to disk or cloud (S3), validate file types |
| 3 | Caching with Redis | Cache API responses, session storage, rate limiting backend. `redis` or `ioredis` npm packages |
| 4 | Job Queues | `BullMQ` — background job processing (email sending, image resizing, data processing). Don't block the API |
| 5 | Child Processes | `child_process.exec()`, `fork()`, `spawn()` — run system commands or parallel Node.js processes |
| 6 | Worker Threads | `worker_threads` — true multi-threading for CPU-intensive tasks without blocking the event loop |
| 7 | Clustering | `cluster` module — fork multiple Node processes across CPU cores. One process per core |
| 8 | Logging | `pino` or `winston` — structured logging. Log levels (debug, info, warn, error), JSON format, log rotation |

> [!TIP]
> Use `pino` for production logging — it's the fastest Node.js logger (5x faster than winston):
> ```javascript
> import pino from 'pino';
> const logger = pino({ level: 'info' });
>
> logger.info({ userId: 123 }, 'User logged in');
> logger.error({ err }, 'Database connection failed');
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a real-time chat with WebSockets
- [ ] Implement file upload with validation and cloud storage
- [ ] Set up a background job queue with BullMQ

</details>

---

## Phase 10: Testing & Deployment

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Test your APIs and deploy to production.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `node:test` (Built-in) | Node.js v20+ has a built-in test runner: `import { test } from 'node:test'` — no npm package needed |
| 2 | Vitest / Jest | Popular test frameworks. `describe`, `it`, `expect`, mocking, code coverage |
| 3 | API Testing | `supertest` — test Express routes without starting the server: `request(app).get('/users').expect(200)` |
| 4 | Environment Variables | `.env` files with `dotenv`, `process.env`, different configs for dev/staging/production |
| 5 | Docker | `Dockerfile` — containerize your Node.js app. Consistent environment across dev and production |
| 6 | PM2 | Process manager — `pm2 start app.js`. Auto-restart on crash, cluster mode, log management |
| 7 | CI/CD | GitHub Actions — run tests, lint, build, and deploy automatically on every push |
| 8 | Monitoring | Health checks (`/health` endpoint), error tracking (Sentry), APM (Application Performance Monitoring) |

> [!TIP]
> Use `supertest` to test your API routes without starting the server:
> ```javascript
> import { describe, it, expect } from 'vitest';
> import request from 'supertest';
> import app from './app.js';
>
> describe('GET /users', () => {
>   it('returns a list of users', async () => {
>     const res = await request(app).get('/api/users');
>     expect(res.status).toBe(200);
>     expect(res.body.data).toBeInstanceOf(Array);
>   });
> });
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write API tests with supertest and Vitest
- [ ] Containerize your app with Docker
- [ ] Deploy to a cloud platform with PM2 or Docker

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Blocking the event loop | CPU-heavy tasks freeze all requests | Use worker threads or child processes |
| 2 | Not handling errors | Unhandled rejections crash the process in Node 20+ | Always use `try/catch` with async/await |
| 3 | Callback hell | Deeply nested callbacks are unreadable and error-prone | Use `async`/`await` with `fs/promises` |
| 4 | Hardcoding secrets | API keys and DB passwords in source code → exposed in git | Use `.env` files + `process.env` |
| 5 | No input validation | Trusting client data leads to injection and crashes | Validate with Zod at every API boundary |
| 6 | Not using `helmet()` | Missing security headers → vulnerable to XSS, clickjacking | Add `app.use(helmet())` to every Express app |
| 7 | Loading entire files | `fs.readFileSync` on large files blocks the event loop and uses huge memory | Use streams for files > 10MB |
| 8 | No rate limiting | APIs without rate limits are targets for DDoS and brute force | Add `express-rate-limit` to all public endpoints |
| 9 | Using `var` and `require` | Legacy patterns that cause scoping bugs and don't tree-shake | Use `const`/`let` and ES module `import` |
| 10 | No logging | `console.log` in production is unstructured and hard to search | Use `pino` with structured JSON logging |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is Node.js and how is it different from browser JavaScript?**
   - Node.js is a JavaScript runtime built on V8. Unlike browsers: no DOM/window, has file system access, networking, and OS modules. Single-threaded with an event loop for non-blocking I/O. Used for servers, CLI tools, APIs.

2. **What is the event loop?**
   - The mechanism that allows Node to perform non-blocking I/O despite being single-threaded. It processes callbacks from a queue: timers → pending I/O → poll → check (`setImmediate`) → close. While waiting for I/O, other callbacks can execute.

3. **What is `package.json` and what are its key fields?**
   - Project manifest. Key fields: `name`, `version`, `scripts` (npm run commands), `dependencies` (production), `devDependencies` (dev only), `type: "module"` (ESM), `engines` (Node version). Created with `npm init`.

4. **CommonJS vs ES Modules — what's the difference?**
   - CommonJS: `require()`/`module.exports`, synchronous, Node's original module system. ESM: `import`/`export`, async, standard across browsers and Node. Use ESM for new projects (`"type": "module"` in package.json).

5. **What is middleware in Express?**
   - Functions with `(req, res, next)` signature that process requests before the route handler. Chain with `app.use()`. Examples: parsing JSON, logging, authentication, error handling. Order matters — they run sequentially.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain streams and when to use them.**
   - Streams process data in chunks instead of loading everything into memory. Types: Readable, Writable, Transform, Duplex. Use for: large file processing, HTTP responses, piping data between sources. `readable.pipe(writable)` chains them.

2. **How does `async`/`await` work with the event loop?**
   - `async` functions return Promises. `await` pauses execution of that function (not the event loop) until the Promise resolves. Other code keeps running. Under the hood, resolved promises go to the microtask queue, which has priority over the task queue.

3. **JWT vs Sessions — when to use each?**
   - JWT: stateless (no server storage), scalable, good for APIs and microservices. Sessions: server-side state, easier to revoke, better for traditional web apps. JWT for SPAs/mobile, sessions for server-rendered apps.

4. **How do you handle errors in Express?**
   - Use `try/catch` in async route handlers. Create error-handling middleware with 4 parameters: `(err, req, res, next)`. Use `next(err)` to pass errors to the handler. Distinguish operational errors (400s) from programmer errors (500s).

5. **What is connection pooling and why is it important?**
   - Reusing database connections instead of creating a new one per request. Creating connections is expensive (TCP handshake, auth). Pools maintain a set of open connections. Set `pool.max` based on your database's connection limit and server count.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How would you handle CPU-intensive tasks without blocking the event loop?**
   - Three options: (1) Worker threads (`worker_threads`) — true threads within one process, share memory. (2) Child processes (`child_process.fork()`) — separate Node processes. (3) External services — offload to a job queue (BullMQ + Redis) processed by dedicated workers.

2. **Explain the `cluster` module.**
   - Forks the Node process across CPU cores. One master process manages multiple workers (one per core). Workers share the same port. If one crashes, the master can restart it. Use for production — a single Node process only uses one CPU core.

3. **How do you prevent memory leaks in Node.js?**
   - Common causes: global variables growing unbounded, event listeners not removed, closures holding references, uncleared timers. Prevention: use `WeakMap`/`WeakSet`, limit cache sizes, clean up in process exit handlers, monitor with `--inspect` and Chrome DevTools heap snapshots.

4. **Streams backpressure — what is it and how do you handle it?**
   - When a writable stream can't consume data as fast as the readable produces it. `pipe()` handles it automatically. Manual handling: check `writable.write()` return value (false = pause reading), listen for `drain` event to resume. Ignoring backpressure causes memory overflow.

5. **How do you architect a Node.js microservices system?**
   - Each service owns its data, communicates via HTTP/gRPC or message queues (RabbitMQ, Kafka). API gateway routes requests. Service discovery for finding services. Each service is independently deployable. Use Docker + Kubernetes for orchestration. Monitor with distributed tracing (Jaeger/Zipkin).

</details>

---

## Practice Projects

### Project 1: CLI File Organizer
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A CLI tool that scans a directory and organizes files into folders by type (images, documents, videos). Uses `fs`, `path`, and `process.argv`.

**Skills practiced:** Core modules, async file operations, streams, CLI arguments.

---

### Project 2: REST API (Todo/Notes)
![Phase 4-6](https://img.shields.io/badge/After-Phase%204--6-yellow)

**What you'll build:** A complete CRUD REST API with Express, validation, pagination, filtering, and proper error handling.

**Skills practiced:** Express, routing, middleware, request validation, REST design.

---

### Project 3: Blog API with Auth
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** A blog API with user registration/login (JWT), post CRUD (only authors can edit/delete), comments, and role-based access.

**Skills practiced:** Database (Prisma/Mongoose), JWT auth, bcrypt, middleware, CORS, Helmet.

---

### Project 4: Real-Time Chat App
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** A WebSocket-based chat with rooms, user presence, message history, file sharing, and Redis-backed sessions.

**Skills practiced:** WebSockets, Redis caching, file uploads, worker threads, logging.

---

### Project 5: Production API Platform
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A full API with Docker, CI/CD, monitoring, rate limiting, health checks, structured logging, and 80%+ test coverage.

**Skills practiced:** Everything from all phases — your Node.js graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [nodejs.org — Docs](https://nodejs.org/en/docs/) | Official API documentation for every built-in module |
| [nodejs.org — Learn](https://nodejs.org/en/learn/) | Official guides: getting started, async, debugging, streams |
| [Express.js — Guide](https://expressjs.com/en/guide/routing.html) | Official Express documentation — routing, middleware, error handling |
| [MDN — Server-side Node](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs) | Mozilla's Express/Node tutorial — thorough and beginner-friendly |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Backend & APIs](https://www.freecodecamp.org/learn/back-end-development-and-apis/) | Free certification. Build 5 API projects |
| [The Odin Project — NodeJS](https://www.theodinproject.com/paths/full-stack-javascript/courses/nodejs) | Project-based. Build real applications, not toy examples |
| [Codecademy — Learn Node.js](https://www.codecademy.com/learn/learn-node-js) | Interactive, in-browser coding with instant feedback |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Traversy Media — Node.js Crash Course](https://www.youtube.com/@TraversyMedia) | Best first Node video. Build a project in ~1.5 hours |
| [The Net Ninja — Node.js Tutorial](https://www.youtube.com/@NetNinja) | Well-structured playlist from basics to Express |
| [Fireship — Node.js in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview |
| [Codevolution — Node.js Tutorial](https://www.youtube.com/@Codevolution) | Systematic, topic-by-topic Node.js series |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Node.js](https://roadmap.sh/nodejs) | Interactive learning path with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client) | API testing inside VS Code — like Postman but in your editor |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Catch bugs and enforce code style |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format on save |
| [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) | Send HTTP requests from `.http` files in VS Code |
| [Postman](https://www.postman.com/) | Industry-standard API testing tool |

### Key npm Packages

| Package | What It Does |
|---------|-------------|
| [express](https://expressjs.com/) | Web framework |
| [prisma](https://www.prisma.io/) | Type-safe database ORM |
| [zod](https://zod.dev/) | Schema validation |
| [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken) | JWT authentication |
| [bcrypt](https://github.com/kelektiv/node.bcrypt.js) | Password hashing |
| [helmet](https://helmetjs.github.io/) | Security headers |
| [cors](https://github.com/expressjs/cors) | Cross-origin resource sharing |
| [pino](https://getpino.io/) | Fast structured logging |
| [socket.io](https://socket.io/) | Real-time WebSockets |
| [bullmq](https://bullmq.io/) | Job queues with Redis |

---

[Back to Main Syllabus](../README.md)

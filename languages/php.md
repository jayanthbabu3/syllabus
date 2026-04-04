# PHP Syllabus

A complete, structured learning path for PHP — from your first `echo` to building secure web applications and APIs with Composer, PDO, testing, and modern frameworks.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![PHP: 8.5+](https://img.shields.io/badge/PHP-8.5%2B-777BB4)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Syntax, Variables & Control Flow](#phase-2-syntax-variables--control-flow)
- [Phase 3: Functions, Arrays & Forms](#phase-3-functions-arrays--forms)
- [Phase 4: HTTP, Sessions & State](#phase-4-http-sessions--state)
- [Phase 5: Object-Oriented Programming & Modern PHP](#phase-5-object-oriented-programming--modern-php)
- [Phase 6: Databases with PDO & SQL](#phase-6-databases-with-pdo--sql)
- [Phase 7: Composer, Packages & Code Quality](#phase-7-composer-packages--code-quality)
- [Phase 8: APIs & Frameworks](#phase-8-apis--frameworks)
- [Phase 9: Testing, Security & Performance](#phase-9-testing-security--performance)
- [Phase 10: Architecture & Production PHP](#phase-10-architecture--production-php)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> PHP is primarily a **web language**, so basic HTML, forms, HTTP requests, and SQL concepts will help you move much faster.

- HTML and CSS basics
- Basic command line usage
- A code editor ([VS Code](https://code.visualstudio.com/) recommended)
- A local development stack (PHP CLI plus a built-in server, XAMPP, MAMP, Laragon, or Docker)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand where PHP runs and how modern PHP projects are set up.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is PHP | A server-side scripting language used to generate HTML, power APIs, and run full web applications |
| 2 | Installation | Install PHP and verify with `php --version` |
| 3 | PHP CLI vs Web Server | `php script.php` vs running PHP through Apache, Nginx, or the built-in dev server |
| 4 | First Script | `<?php echo "Hello, world!";` and basic file execution |
| 5 | Embedded PHP in HTML | How PHP mixes with templates and why clean separation matters |
| 6 | Built-in Server | `php -S localhost:8000` for local development |
| 7 | Configuration | `php.ini`, error reporting, timezone, and development-safe defaults |

> [!TIP]
> Start with the PHP CLI and the built-in server. It keeps the learning loop simple before adding a full framework or web stack.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install PHP and run a script from the terminal
- [ ] Start the built-in server and load a PHP page in the browser
- [ ] Explain the difference between PHP CLI and PHP in a web request

</details>

---

## Phase 2: Syntax, Variables & Control Flow

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the core syntax and how PHP code behaves.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Variables | `$name`, dynamic typing, naming conventions |
| 2 | Scalars & Arrays | Strings, integers, floats, booleans, arrays, `null` |
| 3 | Operators | Arithmetic, comparison, strict vs loose equality, null coalescing |
| 4 | Conditionals | `if`, `elseif`, `else`, `switch`, match expressions |
| 5 | Loops | `for`, `while`, `foreach`, `break`, `continue` |
| 6 | String Handling | Interpolation, concatenation, heredoc, basic string functions |
| 7 | Type Juggling | How PHP converts types implicitly and where it becomes dangerous |
| 8 | Strict Types | `declare(strict_types=1);` and modern PHP expectations |

> [!IMPORTANT]
> Learn `===` and `!==` early. PHP's loose comparisons can produce surprising results and are a common beginner trap.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use strict comparison operators correctly
- [ ] Write scripts with loops and conditionals
- [ ] Explain what `declare(strict_types=1);` does

</details>

---

## Phase 3: Functions, Arrays & Forms

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable logic and handle common web inputs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Functions | Parameters, return types, default values, named arguments |
| 2 | Arrays | Indexed arrays, associative arrays, nested arrays |
| 3 | Array Functions | `array_map`, `array_filter`, `array_reduce`, sorting helpers |
| 4 | Superglobals | `$_GET`, `$_POST`, `$_SERVER`, `$_FILES`, `$_COOKIE` |
| 5 | Forms | Submitting form data and reading it safely |
| 6 | Validation Basics | Checking required fields, types, and expected values |
| 7 | Sanitization & Escaping | Escaping output to HTML and handling untrusted input |
| 8 | File Upload Basics | How uploads work and why validation matters |

> [!CAUTION]
> Never trust user input. Validate what should be accepted and escape what gets rendered back into HTML.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write typed functions with defaults and return types
- [ ] Process form input using `$_POST`
- [ ] Escape output safely with `htmlspecialchars()`

</details>

---

## Phase 4: HTTP, Sessions & State

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Understand how PHP handles state in a stateless web environment.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Request / Response Model | How PHP runs per request and sends output back to the browser |
| 2 | Headers | Redirects, content types, status codes, caching headers |
| 3 | Cookies | Storing small client-side values and related security flags |
| 4 | Sessions | `session_start()`, session storage, auth state basics |
| 5 | Authentication Flow | Login, logout, session regeneration, protecting routes |
| 6 | CSRF Basics | Why forms need CSRF protection in real applications |
| 7 | REST vs Server Rendered Apps | Different ways PHP apps can be structured |
| 8 | Output Buffering | When it helps and why headers must be sent before output |

> [!IMPORTANT]
> Regenerate the session ID after login. It is one of the simplest defenses against session fixation.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use sessions to keep a user logged in
- [ ] Send redirects and custom status codes correctly
- [ ] Explain the difference between cookies and sessions

</details>

---

## Phase 5: Object-Oriented Programming & Modern PHP

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Learn the modern PHP features expected in real projects.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | Properties, methods, constructors, visibility |
| 2 | Inheritance & Interfaces | Shared behavior and contracts |
| 3 | Traits | Horizontal reuse without deep inheritance |
| 4 | Namespaces | Avoiding naming collisions and organizing code |
| 5 | Typed Properties | Stronger object models with explicit types |
| 6 | Enums & Attributes | Modern language features introduced in PHP 8.x |
| 7 | Exceptions | Throwing, catching, and propagating errors cleanly |
| 8 | SOLID Basics | Writing maintainable classes instead of procedural sprawl |

> [!TIP]
> Modern PHP is not "just templating." Typed properties, enums, namespaces, Composer, and testing are standard expectations now.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a small object model with interfaces or traits
- [ ] Use namespaces and autoloaded classes
- [ ] Explain when to use an enum or custom exception

</details>

---

## Phase 6: Databases with PDO & SQL

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Connect PHP to relational databases the right way.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | SQL Fundamentals | CRUD, filtering, joins, constraints, normalization basics |
| 2 | PDO | PHP Data Objects for database access |
| 3 | Prepared Statements | Safe queries that prevent SQL injection |
| 4 | Fetch Modes | Associative arrays, objects, typed hydration strategies |
| 5 | Transactions | `beginTransaction`, `commit`, `rollBack` and atomic changes |
| 6 | Migrations | Versioning database schema changes |
| 7 | Query Design | Efficient filtering, pagination, and indexing awareness |
| 8 | Error Handling | Handling database failures predictably |

> [!WARNING]
> Never interpolate user input into SQL strings. Always use prepared statements with bound values.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Connect to a database with PDO
- [ ] Write CRUD operations using prepared statements
- [ ] Use a transaction for a multi-step database workflow

</details>

---

## Phase 7: Composer, Packages & Code Quality

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Move from standalone scripts to maintainable applications.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Composer | Dependency management and `composer.json` |
| 2 | PSR-4 Autoloading | Organizing classes and loading them automatically |
| 3 | Coding Standards | PSR-12 formatting and shared team conventions |
| 4 | Static Analysis | Tools like PHPStan and Psalm for catching issues early |
| 5 | Linting & Refactoring | PHP CS Fixer, Rector, and automated cleanup |
| 6 | Environment Variables | Configuring apps without hardcoding secrets |
| 7 | Logging | Structured logs and actionable error information |
| 8 | Project Structure | Separating routes, services, controllers, views, and config |

> [!TIP]
> Composer is not optional in modern PHP. If a project grows beyond a few files, you want autoloading and real dependency management immediately.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a `composer.json` and install a package
- [ ] Autoload classes with PSR-4
- [ ] Run a static analysis tool on your code

</details>

---

## Phase 8: APIs & Frameworks

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build complete applications with the broader PHP ecosystem.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Routing | Defining endpoints and mapping requests to handlers |
| 2 | JSON APIs | Returning structured responses and validating request bodies |
| 3 | Middleware | Request/response pipelines for auth, logging, rate limiting |
| 4 | Laravel Basics | Routing, controllers, Eloquent, Blade, queues, jobs |
| 5 | Symfony Basics | Services, dependency injection, console, HTTP foundation |
| 6 | Validation Layers | Keeping validation out of controllers where possible |
| 7 | Authentication | Sessions, tokens, password hashing, role checks |
| 8 | Framework Tradeoffs | When to choose plain PHP, micro-frameworks, or full-stack frameworks |

> [!IMPORTANT]
> Learn one framework well, but keep the PHP fundamentals underneath it strong. Framework knowledge without language fundamentals becomes very fragile.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a small JSON API with proper status codes
- [ ] Implement authentication and validation
- [ ] Explain the differences between Laravel and Symfony at a high level

</details>

---

## Phase 9: Testing, Security & Performance

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Make PHP systems reliable, secure, and fast enough for production.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | PHPUnit / Pest | Unit, integration, and feature tests |
| 2 | Testable Design | Dependency injection and isolating side effects |
| 3 | Password Security | `password_hash`, `password_verify`, upgrade strategies |
| 4 | Common Web Vulnerabilities | XSS, CSRF, SQL injection, file upload abuse, insecure deserialization |
| 5 | Validation vs Sanitization | Where each belongs in a secure app |
| 6 | Caching | Opcode cache, application cache, HTTP cache basics |
| 7 | Profiling | Measuring before optimizing |
| 8 | Performance Patterns | Avoiding N+1 queries, reducing unnecessary work, keeping responses small |

> [!CAUTION]
> Security in PHP is mostly about boring habits done consistently: prepared statements, output escaping, proper auth, validated uploads, and dependency updates.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write tests for core application behavior
- [ ] Explain how PHP prevents password storage mistakes with modern APIs
- [ ] Identify and fix an XSS or SQL injection risk

</details>

---

## Phase 10: Architecture & Production PHP

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Ship PHP applications that can survive real traffic, teams, and ongoing change.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Layered Architecture | Controllers, services, repositories, domain logic boundaries |
| 2 | Queues & Background Work | Offloading email, image processing, and scheduled jobs |
| 3 | Error Reporting | Logs, alerting, and structured exception handling |
| 4 | Deployment | Nginx/Apache, PHP-FPM, containers, platform services |
| 5 | Secrets & Configuration | Environment-based config and secret rotation habits |
| 6 | CI/CD | Linting, tests, static analysis, deployment pipelines |
| 7 | Dependency Maintenance | Tracking framework and package updates safely |
| 8 | Long-Term Maintainability | Refactoring, ADRs, internal docs, and code review discipline |

> [!TIP]
> Production PHP is rarely limited by syntax. It is limited by architecture, test quality, deployment discipline, and security habits.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Structure a PHP project into clear layers
- [ ] Deploy an app with repeatable configuration
- [ ] Add CI checks for tests, linting, and static analysis

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using loose comparison everywhere | `==` can coerce types unexpectedly | Use `===` and `!==` by default |
| 2 | Building SQL with string concatenation | Leads directly to SQL injection | Use PDO prepared statements |
| 3 | Mixing HTML, SQL, and business logic in one file | Becomes impossible to maintain | Separate presentation, routing, and domain logic |
| 4 | Skipping Composer | Dependencies and autoloading become chaotic | Use Composer from the start |
| 5 | Ignoring `strict_types` | Hidden coercions make bugs harder to spot | Enable `declare(strict_types=1);` in modern code |
| 6 | Storing passwords manually | Easy to do insecurely | Use `password_hash()` and `password_verify()` |
| 7 | Trusting uploads or form data blindly | Security and stability risk | Validate size, type, and destination carefully |
| 8 | Catching broad exceptions and hiding them | Masks real production issues | Log clearly and catch specific failure modes |
| 9 | No tests around business rules | Refactors become dangerous | Add unit and integration tests |
| 10 | Treating old tutorials as current best practice | Many older PHP guides teach outdated patterns | Prefer modern PHP 8.x material and current framework docs |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is PHP primarily used for?**
   - PHP is mostly used for server-side web development: rendering HTML, processing forms, accessing databases, and building APIs and full web applications.

2. **What are superglobals in PHP?**
   - Built-in global arrays like `$_GET`, `$_POST`, `$_SERVER`, `$_COOKIE`, and `$_SESSION` that provide request and environment data.

3. **What is the difference between `==` and `===` in PHP?**
   - `==` compares after type coercion. `===` compares both value and type. `===` is the safer default.

4. **Why use PDO instead of older database APIs?**
   - PDO supports prepared statements, multiple databases, better error handling, and modern database access patterns.

5. **What does Composer do?**
   - Composer manages dependencies, autoloading, version constraints, and package installation for PHP projects.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What is PSR-4 autoloading?**
   - A standard that maps namespaces to file paths so classes load automatically without manual `require` calls.

2. **How do sessions work in PHP?**
   - PHP stores session data server-side and typically links it to the browser through a session cookie containing the session ID.

3. **How do you prevent SQL injection in PHP?**
   - Use prepared statements with PDO, never concatenate untrusted input into SQL strings.

4. **What is the difference between validation and escaping?**
   - Validation checks whether input is acceptable. Escaping makes output safe in a specific context like HTML, JSON, SQL, or URLs.

5. **When would you use a framework like Laravel or Symfony?**
   - When the application needs routing, middleware, DI, validation, auth, queues, and long-term maintainability rather than ad hoc scripts.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How would you structure a large PHP application?**
   - Separate transport concerns from business logic, keep controllers thin, use services or handlers, define clear module boundaries, and rely on tests and static analysis.

2. **What are common security issues in PHP apps?**
   - SQL injection, XSS, CSRF, weak authentication, unsafe deserialization, insecure file uploads, and outdated dependencies.

3. **How do you improve performance in a PHP application?**
   - Measure first, avoid expensive database patterns, use caches appropriately, keep payloads small, and tune PHP-FPM or infrastructure only after bottlenecks are understood.

4. **Why is static analysis valuable in PHP?**
   - PHP is dynamic, so tools like PHPStan or Psalm catch type mismatches, dead code, and invalid assumptions before runtime.

5. **What is the role of PHP-FPM in production?**
   - PHP-FPM manages pools of PHP worker processes efficiently behind a web server like Nginx, making PHP apps scalable and production-friendly.

</details>

---

## Practice Projects

### Project 1: Contact Form Processor
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A contact form that validates input, shows errors, and safely stores submissions.

**Skills practiced:** Forms, superglobals, validation, escaping, functions.

---

### Project 2: Session-Based Login App
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A small app with registration, login, logout, session management, and access-controlled pages.

**Skills practiced:** Sessions, cookies, OOP, password hashing.

---

### Project 3: CRUD App with PDO
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A notes, inventory, or student manager app backed by MySQL or PostgreSQL.

**Skills practiced:** PDO, prepared statements, SQL, Composer, project structure.

---

### Project 4: REST API with Laravel or Symfony
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A token-protected JSON API with validation, pagination, and tests.

**Skills practiced:** Framework routing, middleware, testing, auth, API design.

---

### Project 5: Production Web Platform
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A full PHP application with CI, background jobs, monitoring, and deployment.

**Skills practiced:** Everything from all phases — your PHP graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [PHP Manual](https://www.php.net/docs) | Official language and library documentation |
| [PHP Supported Versions](https://www.php.net/supported-versions.php) | Shows which PHP versions are currently supported |
| [PHP: The Right Way](https://phptherightway.com/) | Modern best-practices guide that filters out outdated habits |
| [Laravel Documentation](https://laravel.com/docs) | Best official docs for learning the Laravel ecosystem |
| [Symfony Documentation](https://symfony.com/doc/current/index.html) | Strong official docs for architecture-heavy PHP development |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Exercism — PHP Track](https://exercism.org/tracks/php) | Practical exercises with feedback |
| [Codecademy — Learn PHP](https://www.codecademy.com/learn/learn-php) | Browser-based guided introduction |
| [freeCodeCamp YouTube](https://www.youtube.com/@freecodecamp) | Long-form free backend and PHP courses |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [Laracasts](https://laracasts.com/) | Best-known PHP and Laravel teaching platform |
| [Traversy Media](https://www.youtube.com/@TraversyMedia) | Strong beginner-friendly web development videos |
| [Program With Gio](https://www.youtube.com/@ProgramWithGio) | High-quality modern PHP explanations |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client) | IntelliSense and navigation for PHP in VS Code |
| [Composer](https://getcomposer.org/) | Dependency management and autoloading |
| [Xdebug](https://xdebug.org/) | Step debugging and profiling |
| [PHPStan](https://phpstan.org/) | Static analysis for safer PHP |
| [Pest](https://pestphp.com/) | Clean testing syntax for modern PHP |

### Cheat Sheets & Further Reading

| Resource | Format |
|----------|--------|
| [PHP Delusions](https://phpdelusions.net/) | Pragmatic explanations of common PHP topics |
| [PHP Manual Function Reference](https://www.php.net/manual/en/funcref.php) | Searchable reference for built-in functions |

---

[Back to Main Syllabus](../README.md)

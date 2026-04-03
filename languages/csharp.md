# C# Syllabus

A complete, structured learning path for C# — from your first `Console.WriteLine()` to building web APIs with ASP.NET Core, querying databases with Entity Framework, and writing production-ready code.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![.NET: 8+](https://img.shields.io/badge/.NET-8%2B-512BD4)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Types](#phase-2-variables--types)
- [Phase 3: Control Flow](#phase-3-control-flow)
- [Phase 4: Object-Oriented Programming](#phase-4-object-oriented-programming)
- [Phase 5: Collections & LINQ](#phase-5-collections--linq)
- [Phase 6: Exception Handling & I/O](#phase-6-exception-handling--io)
- [Phase 7: Async Programming](#phase-7-async-programming)
- [Phase 8: ASP.NET Core](#phase-8-aspnet-core)
- [Phase 9: Entity Framework Core](#phase-9-entity-framework-core)
- [Phase 10: Testing & Best Practices](#phase-10-testing--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> C# is a strongly typed, object-oriented language built on the .NET platform. It powers everything from desktop apps and games (Unity) to enterprise web APIs and cloud services. With .NET 8+, C# is cross-platform, high-performance, and one of the most in-demand languages in the industry.

- A computer (Windows, Mac, or Linux)
- A text editor ([Visual Studio Code](https://code.visualstudio.com/) with C# Dev Kit or [Visual Studio](https://visualstudio.microsoft.com/) on Windows/Mac)
- [.NET 8 SDK](https://dotnet.microsoft.com/download) installed
- Willingness to practice daily

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write your first C# program and understand the .NET ecosystem.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is C# / .NET | C# is a modern, type-safe language. .NET is the runtime and framework. Cross-platform, open-source since .NET Core |
| 2 | Installation | Install .NET 8 SDK, verify with `dotnet --version`, set up VS Code with C# Dev Kit or Visual Studio |
| 3 | dotnet CLI | `dotnet new console`, `dotnet run`, `dotnet build`, `dotnet add package` — the command-line toolchain for everything |
| 4 | Hello World | `Console.WriteLine("Hello, World!");` — with top-level statements, this single line is a valid program |
| 5 | Project Structure | `.csproj` (project file), `Program.cs` (entry point), `bin/` and `obj/` (build output), `*.sln` (solution file) |
| 6 | Top-Level Statements | C# 9+ allows code without `Main()` method boilerplate — just write statements directly in `Program.cs` |
| 7 | Visual Studio vs VS Code | Visual Studio: full IDE with debugger, designer, profiler. VS Code: lightweight, cross-platform, extensible with C# Dev Kit |
| 8 | Comments & Documentation | `//` single-line, `/* */` multi-line, `///` XML doc comments for IntelliSense and auto-generated documentation |

> [!TIP]
> Use **top-level statements** (C# 9+) for quick programs — no class or `Main()` boilerplate needed:
> ```csharp
> // This entire file is a valid C# program in .NET 8
> var name = Console.ReadLine();
> Console.WriteLine($"Hello, {name}!");
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install .NET 8 SDK and create a console app with `dotnet new console`
- [ ] Run your program with `dotnet run` and understand the project structure
- [ ] Write a program that takes user input and prints a greeting

</details>

---

## Phase 2: Variables & Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Understand C#'s type system — the foundation of everything you'll write.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Value Types vs Reference Types | Value types (`int`, `bool`, `struct`) live on the stack. Reference types (`string`, `class`, `array`) live on the heap |
| 2 | Primitive Types | `int`, `long`, `double`, `decimal`, `float`, `bool`, `char`, `byte` — each with specific size and range |
| 3 | Strings | Immutable reference type: `string name = "Alice";`. Concatenation with `+`, but prefer interpolation |
| 4 | String Interpolation | `$"Hello, {name}! You are {age} years old."` — embed expressions directly in strings with `$` prefix |
| 5 | Nullable Types | `int? age = null;` — value types can't be null by default. Add `?` to allow null. `HasValue`, `.Value`, `??` null-coalescing |
| 6 | `var` Keyword | `var name = "Alice";` — compiler infers the type. Use when the type is obvious from the right side |
| 7 | Type Casting | Implicit (safe): `int` to `double`. Explicit (risky): `(int)myDouble`. Safe casting: `as`, `is`, `Convert` class |
| 8 | Constants & Readonly | `const` — compile-time constant, must be assigned at declaration. `readonly` — runtime constant, assigned in constructor |
| 9 | Enums | `enum Color { Red, Green, Blue }` — named integer constants. Type-safe alternative to magic numbers |

> [!IMPORTANT]
> **Value types vs Reference types** is the most important concept in C#:
> - **Value types** (`int`, `bool`, `struct`, `enum`) are copied on assignment — changing the copy doesn't affect the original
> - **Reference types** (`class`, `string`, `array`, `interface`) share a reference — multiple variables can point to the same object
> - `string` is a reference type but behaves like a value type because it's **immutable**

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables using explicit types and `var`, and explain when to use each
- [ ] Use nullable types with `?`, `??`, and `?.` operators
- [ ] Convert between types using casting and the `Convert` class

</details>

---

## Phase 3: Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions, loop through data, and leverage modern pattern matching.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `else if` / `else` | Conditional branching: `if (age >= 18) { ... }` — curly braces define code blocks |
| 2 | Switch Statements | `switch (value) { case 1: ... break; }` — classic multi-way branching with fall-through prevention |
| 3 | Switch Expressions | `var result = value switch { 1 => "one", 2 => "two", _ => "other" };` — concise, expression-based (C# 8+) |
| 4 | `for` Loops | `for (int i = 0; i < 10; i++) { ... }` — classic counted loop with initializer, condition, iterator |
| 5 | `foreach` Loops | `foreach (var item in collection) { ... }` — iterate over any `IEnumerable`. Preferred for collections |
| 6 | `while` & `do-while` | `while (condition) { ... }` checks first. `do { ... } while (condition);` executes at least once |
| 7 | Pattern Matching | `if (obj is string s)` — type patterns, property patterns, relational patterns (`> 0 and < 100`) |
| 8 | Ternary Operator | `var status = age >= 18 ? "Adult" : "Minor";` — inline conditional expression |
| 9 | LINQ Preview | `var adults = people.Where(p => p.Age >= 18);` — a taste of querying collections (deep dive in Phase 5) |

> [!TIP]
> **Switch expressions** (C# 8+) are far more concise than switch statements and support pattern matching:
> ```csharp
> string GetDiscount(Customer customer) => customer.Tier switch
> {
>     "Gold" => "30% off",
>     "Silver" => "20% off",
>     "Bronze" => "10% off",
>     _ => "No discount"  // _ is the discard pattern (default)
> };
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a program using `if/else`, `for`, `foreach`, and `while` loops
- [ ] Refactor a switch statement into a switch expression
- [ ] Use pattern matching with `is` and property patterns

</details>

---

## Phase 4: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Master OOP in C# — the language was built for it.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | `class User { }` — blueprints for objects. `new User()` creates an instance on the heap |
| 2 | Constructors | `public User(string name) { Name = name; }` — initialize objects. Primary constructors in C# 12: `class User(string name)` |
| 3 | Properties | `public string Name { get; set; }` — auto-properties with backing fields. `init` for immutable setters (C# 9+) |
| 4 | Inheritance | `class Admin : User { }` — single inheritance. `base` keyword calls parent constructor/methods |
| 5 | Interfaces | `interface IRepository { Task<T> GetById(int id); }` — contracts that classes must implement. Multiple interface inheritance |
| 6 | Abstract Classes | `abstract class Shape { abstract double Area(); }` — can't be instantiated, can have implementation. Mix of interface + class |
| 7 | Records | `record User(string Name, string Email);` — immutable reference types with value equality, `with` expressions, deconstruction |
| 8 | Sealed Classes | `sealed class Config { }` — prevents inheritance. Used for security, performance, and design intent |
| 9 | Partial Classes | `partial class User { }` — split a class across multiple files. Used by code generators and EF Core |
| 10 | Access Modifiers | `public`, `private`, `protected`, `internal`, `protected internal`, `file` — control visibility and encapsulation |

> [!TIP]
> Use **records** (C# 9+) for immutable data objects — they give you value equality, `ToString()`, and `with` expressions for free:
> ```csharp
> record Product(string Name, decimal Price);
>
> var original = new Product("Widget", 9.99m);
> var discounted = original with { Price = 7.99m };  // non-destructive mutation
>
> Console.WriteLine(original == discounted);  // False (value equality)
> Console.WriteLine(original);  // Product { Name = Widget, Price = 9.99 }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class hierarchy with inheritance, interfaces, and abstract classes
- [ ] Use properties with `get`, `set`, and `init` accessors
- [ ] Define a record type and use `with` expressions for immutable updates

</details>

---

## Phase 5: Collections & LINQ

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Work with data collections and query them with LINQ — one of C#'s superpowers.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `List<T>` | Dynamic array: `new List<string>()`. Methods: `.Add()`, `.Remove()`, `.Contains()`, `.Count`, `.Sort()` |
| 2 | `Dictionary<TKey, TValue>` | Key-value pairs: `new Dictionary<string, int>()`. O(1) lookup. `.TryGetValue()` for safe access |
| 3 | `HashSet<T>` | Unique elements: `new HashSet<int>()`. Set operations: `.UnionWith()`, `.IntersectWith()`, `.ExceptWith()` |
| 4 | `Queue<T>` & `Stack<T>` | Queue: FIFO (`.Enqueue()`, `.Dequeue()`). Stack: LIFO (`.Push()`, `.Pop()`). Use for processing pipelines |
| 5 | Lambda Expressions | `(x, y) => x + y` — anonymous functions. Used heavily with LINQ, events, and delegates |
| 6 | LINQ: `Where` & `Select` | `items.Where(x => x.IsActive).Select(x => x.Name)` — filter and project collections |
| 7 | LINQ: `OrderBy` & `GroupBy` | `.OrderBy(x => x.Name)`, `.GroupBy(x => x.Category)` — sort and group data |
| 8 | LINQ: Aggregation | `.Count()`, `.Sum()`, `.Average()`, `.Min()`, `.Max()`, `.Aggregate()` — reduce collections to values |
| 9 | LINQ: Advanced | `.Any()`, `.All()`, `.First()`, `.FirstOrDefault()`, `.Distinct()`, `.SelectMany()`, `.Zip()` |
| 10 | Query Syntax vs Method Syntax | `from x in items where x > 5 select x` vs `items.Where(x => x > 5)` — two ways to write LINQ |

> [!IMPORTANT]
> **LINQ is lazy** — queries don't execute until you iterate or call a terminal method (`.ToList()`, `.Count()`, `.First()`):
> ```csharp
> var query = products
>     .Where(p => p.Price > 10)     // no execution yet
>     .OrderBy(p => p.Name)         // still no execution
>     .Select(p => p.Name);         // still deferred
>
> var results = query.ToList();     // NOW it executes
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `List<T>`, `Dictionary<K,V>`, and `HashSet<T>` in a program
- [ ] Write LINQ queries using `Where`, `Select`, `OrderBy`, and `GroupBy`
- [ ] Explain the difference between deferred and immediate execution in LINQ

</details>

---

## Phase 6: Exception Handling & I/O

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Handle errors gracefully, work with files, and serialize data.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `try` / `catch` / `finally` | `try { ... } catch (Exception ex) { ... } finally { ... }` — catch specific exceptions, always run cleanup |
| 2 | Exception Hierarchy | `Exception` → `SystemException` → `IOException`, `ArgumentException`, `NullReferenceException`. Catch most specific first |
| 3 | Custom Exceptions | `class OrderNotFoundException : Exception { }` — domain-specific errors with meaningful names and messages |
| 4 | `using` Statement | `using var stream = File.OpenRead("data.txt");` — auto-disposes `IDisposable` resources (files, connections, streams) |
| 5 | File I/O (System.IO) | `File.ReadAllText()`, `File.WriteAllText()`, `File.ReadAllLines()`, `StreamReader`, `StreamWriter` |
| 6 | Async File Operations | `await File.ReadAllTextAsync("file.txt")` — non-blocking file I/O for responsive applications |
| 7 | JSON Serialization | `System.Text.Json`: `JsonSerializer.Serialize(obj)`, `JsonSerializer.Deserialize<T>(json)` — built-in, fast JSON handling |
| 8 | Exception Filters | `catch (HttpRequestException ex) when (ex.StatusCode == 404)` — conditional catch blocks for precise error handling |

> [!CAUTION]
> **Never catch `Exception` as a blanket handler** without rethrowing or logging — it hides bugs:
> ```csharp
> // WRONG - swallows all errors silently
> try { Process(); }
> catch (Exception) { }
>
> // RIGHT - catch specific exceptions and handle them
> try { Process(); }
> catch (FileNotFoundException ex)
> {
>     logger.LogError(ex, "Config file not found");
>     throw;  // rethrow to preserve stack trace
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Handle exceptions with `try/catch` for specific exception types
- [ ] Read and write files using `using` statements for proper resource disposal
- [ ] Serialize and deserialize objects to/from JSON with `System.Text.Json`

</details>

---

## Phase 7: Async Programming

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write non-blocking, scalable code with async/await — essential for modern C#.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `async` / `await` | `async Task<string> GetDataAsync()` — write asynchronous code that reads like synchronous code |
| 2 | `Task` & `Task<T>` | `Task` = async void operation, `Task<T>` = async operation with a result. Always prefer `Task` over `void` |
| 3 | `Task.WhenAll` | `await Task.WhenAll(task1, task2, task3)` — run multiple async operations concurrently, wait for all to finish |
| 4 | `Task.WhenAny` | `await Task.WhenAny(tasks)` — returns when the first task completes. Useful for timeouts and racing |
| 5 | `CancellationToken` | `async Task FetchAsync(CancellationToken ct)` — cooperative cancellation for long-running operations |
| 6 | `IAsyncEnumerable<T>` | `await foreach (var item in GetItemsAsync())` — stream async data one item at a time (C# 8+) |
| 7 | Parallel Programming | `Parallel.ForEachAsync()`, `Task.Run()` — CPU-bound parallelism vs I/O-bound async. Know when to use each |
| 8 | Async Best Practices | Avoid `async void`, don't block with `.Result` or `.Wait()`, use `ConfigureAwait(false)` in libraries |

> [!IMPORTANT]
> **Never block on async code** — it causes deadlocks in UI and ASP.NET contexts:
> ```csharp
> // WRONG - can deadlock
> var result = GetDataAsync().Result;
> var result = GetDataAsync().GetAwaiter().GetResult();
>
> // RIGHT - async all the way
> var result = await GetDataAsync();
>
> // RIGHT - concurrent execution
> var tasks = urls.Select(url => httpClient.GetStringAsync(url));
> var results = await Task.WhenAll(tasks);
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Convert a synchronous method to async using `async`/`await`
- [ ] Use `Task.WhenAll` to run multiple HTTP requests concurrently
- [ ] Implement cancellation with `CancellationToken`

</details>

---

## Phase 8: ASP.NET Core

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Build web APIs with ASP.NET Core — the most popular C# web framework.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Minimal APIs | `app.MapGet("/", () => "Hello!");` — lightweight API endpoints without controllers (`.NET 6+`) |
| 2 | Controllers | `[ApiController]` + `ControllerBase` — organized, feature-rich API endpoints with attributes |
| 3 | Routing | `[Route("api/[controller]")]`, `[HttpGet("{id}")]` — attribute routing, route parameters, query strings |
| 4 | Middleware | `app.UseAuthentication()`, `app.UseAuthorization()` — request pipeline. Order matters. Custom middleware |
| 5 | Dependency Injection | `builder.Services.AddScoped<IUserService, UserService>()` — built-in DI container. Scoped, Transient, Singleton lifetimes |
| 6 | Model Binding & Validation | `[FromBody]`, `[FromQuery]`, `[Required]`, `[Range]` — automatic request deserialization and validation |
| 7 | Swagger / OpenAPI | `builder.Services.AddEndpointsApiExplorer()` + Swashbuckle — auto-generated interactive API documentation |
| 8 | Configuration | `appsettings.json`, `IConfiguration`, `IOptions<T>` — environment-specific settings with strong typing |
| 9 | Error Handling | `app.UseExceptionHandler()`, `ProblemDetails` — global error handling with RFC 7807 problem details |

> [!TIP]
> **Minimal APIs** (`.NET 6+`) are perfect for small services and getting started quickly:
> ```csharp
> var builder = WebApplication.CreateBuilder(args);
> var app = builder.Build();
>
> app.MapGet("/api/products", () => new[] { "Widget", "Gadget" });
> app.MapGet("/api/products/{id}", (int id) => $"Product {id}");
> app.MapPost("/api/products", (Product product) => Results.Created($"/api/products/{product.Id}", product));
>
> app.Run();
>
> record Product(int Id, string Name, decimal Price);
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a minimal API with CRUD endpoints
- [ ] Register and inject services using the built-in DI container
- [ ] Add Swagger documentation and test your API in the browser

</details>

---

## Phase 9: Entity Framework Core

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Access databases with Entity Framework Core — the official .NET ORM.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is EF Core | Object-Relational Mapper — map C# classes to database tables. Write LINQ instead of SQL |
| 2 | DbContext | `class AppDbContext : DbContext` — the gateway to the database. Configures models and manages connections |
| 3 | Models & Configuration | `DbSet<Product> Products { get; set; }` — entity classes, data annotations, Fluent API configuration |
| 4 | Migrations | `dotnet ef migrations add Init`, `dotnet ef database update` — version-control your database schema |
| 5 | CRUD Operations | `Add()`, `Find()`, `Update()`, `Remove()`, `SaveChangesAsync()` — create, read, update, delete entities |
| 6 | LINQ Queries | `await db.Products.Where(p => p.Price > 10).ToListAsync()` — type-safe queries translated to SQL |
| 7 | Relationships | One-to-many, many-to-many, one-to-one: navigation properties, foreign keys, `.Include()` for eager loading |
| 8 | Database Providers | SQL Server, PostgreSQL (Npgsql), SQLite, MySQL — swap databases by changing the provider package |
| 9 | Performance Tips | `.AsNoTracking()` for read-only queries, avoid N+1 with `.Include()`, use projections with `.Select()` |

> [!TIP]
> Use **projections** with `.Select()` to query only the data you need — avoid loading entire entities:
> ```csharp
> // SLOW - loads all columns for all products
> var products = await db.Products.ToListAsync();
>
> // FAST - loads only the columns you need
> var productNames = await db.Products
>     .Where(p => p.IsActive)
>     .Select(p => new { p.Name, p.Price })
>     .ToListAsync();
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up a DbContext with models and run migrations
- [ ] Perform CRUD operations with `SaveChangesAsync()`
- [ ] Define relationships and use `.Include()` for eager loading

</details>

---

## Phase 10: Testing & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write tests, structure projects professionally, and ship production-quality code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | xUnit | `dotnet new xunit` — `[Fact]` for simple tests, `[Theory]` + `[InlineData]` for parameterized tests. Most popular .NET test framework |
| 2 | NUnit | `[Test]`, `[TestCase]`, `Assert.That()` — alternative test framework with a rich assertion model |
| 3 | Moq | `var mock = new Mock<IUserService>()` — mock interfaces and dependencies. `.Setup()`, `.Returns()`, `.Verify()` |
| 4 | Integration Testing | `WebApplicationFactory<Program>` — test ASP.NET Core APIs end-to-end with an in-memory test server |
| 5 | Test Coverage | `dotnet test --collect:"XPlat Code Coverage"` + ReportGenerator — measure and visualize code coverage |
| 6 | Project Structure | `src/` + `tests/` directories, solution files, multi-project architecture: API, Domain, Infrastructure, Tests |
| 7 | NuGet Packages | `dotnet add package Serilog` — discover, install, and manage third-party packages from nuget.org |
| 8 | CI/CD | GitHub Actions for .NET: `dotnet build`, `dotnet test`, `dotnet publish` — automate build, test, and deployment |

> [!TIP]
> Use `[Theory]` with `[InlineData]` for parameterized tests — test multiple inputs with a single method:
> ```csharp
> public class CalculatorTests
> {
>     [Theory]
>     [InlineData(2, 3, 5)]
>     [InlineData(-1, 1, 0)]
>     [InlineData(0, 0, 0)]
>     public void Add_ReturnsSum(int a, int b, int expected)
>     {
>         var calculator = new Calculator();
>         Assert.Equal(expected, calculator.Add(a, b));
>     }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write unit tests with xUnit using `[Fact]` and `[Theory]`
- [ ] Mock dependencies with Moq in a service test
- [ ] Set up a CI pipeline with GitHub Actions that builds and tests your project

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Not handling `null` | `NullReferenceException` is the most common runtime error in C# | Enable nullable reference types (`<Nullable>enable</Nullable>`) and use `?.`, `??`, `??=` operators |
| 2 | Blocking on async code | `.Result` or `.Wait()` on a `Task` causes deadlocks in UI and ASP.NET contexts | Use `await` all the way up the call chain — "async all the way" |
| 3 | Catching `Exception` without rethrowing | Swallows all errors including critical ones — hides bugs completely | Catch specific exceptions. If you must catch `Exception`, log it and use `throw;` (not `throw ex;`) |
| 4 | Using `throw ex;` instead of `throw;` | `throw ex;` resets the stack trace, destroying debugging information | Use `throw;` to preserve the original stack trace |
| 5 | Forgetting `await` | Calling an async method without `await` fires and forgets — exceptions are silently lost | Always `await` async methods. The compiler warns you (CS4014) — don't ignore it |
| 6 | Mutable shared state | Modifying shared objects across threads causes race conditions and unpredictable bugs | Use immutable types (`record`), `ConcurrentDictionary`, or proper locking |
| 7 | String concatenation in loops | `string +=` in a loop creates a new string each iteration — O(n^2) memory allocation | Use `StringBuilder` for building strings in loops |
| 8 | Not disposing resources | File handles, database connections, HTTP clients leak when not disposed | Use `using` statements or `using` declarations for all `IDisposable` objects |
| 9 | N+1 query problem in EF Core | Lazy loading fires a separate SQL query for each related entity in a loop | Use `.Include()` for eager loading or `.Select()` projections |
| 10 | Hardcoding configuration | Connection strings, API keys, and URLs baked into source code | Use `appsettings.json`, environment variables, and `IOptions<T>` pattern |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between value types and reference types?**
   - Value types (`int`, `bool`, `struct`, `enum`) are stored on the stack and copied on assignment. Reference types (`class`, `string`, `array`) are stored on the heap and share references. Changing a value type copy doesn't affect the original; changing a reference type through one variable affects all variables pointing to it.

2. **What are properties in C# and why use them?**
   - Properties are members with `get` and `set` accessors: `public string Name { get; set; }`. They encapsulate fields, allowing validation, computed values, and controlled access. Auto-properties generate a hidden backing field automatically.

3. **What is the difference between `==` and `.Equals()`?**
   - `==` compares references for reference types (unless overloaded) and values for value types. `.Equals()` can be overridden for custom equality. For strings, both compare values. Records override both to provide value equality.

4. **What is the `using` statement for?**
   - `using` ensures `IDisposable` objects are disposed when they go out of scope — preventing resource leaks for files, database connections, HTTP clients, and streams. C# 8+ supports `using` declarations: `using var file = File.OpenRead("data.txt");`.

5. **What is the difference between `string` and `StringBuilder`?**
   - `string` is immutable — every modification creates a new string object. `StringBuilder` is mutable — it modifies a buffer in place. Use `StringBuilder` when concatenating strings in loops for O(n) performance instead of O(n^2).

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain the difference between `abstract class` and `interface`.**
   - An `abstract class` can have implementation, fields, constructors, and access modifiers. An `interface` defines only a contract (though C# 8+ allows default implementations). A class can implement multiple interfaces but inherit only one abstract class. Use interfaces for contracts, abstract classes for shared behavior.

2. **What is dependency injection and why is it important?**
   - DI provides dependencies to a class instead of the class creating them. ASP.NET Core has a built-in DI container with three lifetimes: `Transient` (new each time), `Scoped` (once per request), `Singleton` (once per app). It enables loose coupling, testability, and separation of concerns.

3. **What is LINQ and how does deferred execution work?**
   - LINQ (Language Integrated Query) provides query syntax for collections and databases. Deferred execution means the query is not executed when defined — only when iterated (e.g., `foreach`) or materialized (`.ToList()`, `.Count()`). This allows composing queries efficiently.

4. **What is the difference between `Task` and `Thread`?**
   - `Thread` is an OS-level thread — heavyweight, limited in number. `Task` is a higher-level abstraction managed by the thread pool — lightweight, scalable. `async`/`await` with `Task` doesn't block threads during I/O, allowing thousands of concurrent operations.

5. **What are records and when should you use them?**
   - Records (`record class` or `record struct`) are types with value-based equality, immutability by default, and built-in `ToString()`. Use them for DTOs, value objects, API responses, and any type where identity is based on data rather than reference. `with` expressions create modified copies.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain the async/await state machine.**
   - The compiler transforms `async` methods into a state machine class. Each `await` is a suspension point — the method returns a `Task` to the caller and resumes after the awaited operation completes. The state machine tracks local variables, the current state, and the continuation. This is why `async` methods have allocation overhead.

2. **What is the difference between `IEnumerable<T>` and `IQueryable<T>`?**
   - `IEnumerable<T>` evaluates queries in memory — LINQ methods execute C# delegates. `IQueryable<T>` builds expression trees that are translated to SQL by providers like EF Core. Using `IEnumerable` on a database query pulls all data into memory first; `IQueryable` sends the filter to the database.

3. **How does the .NET garbage collector work?**
   - The GC uses a generational algorithm with three generations (0, 1, 2). Most objects die young (Gen 0). Objects that survive collections are promoted. Gen 0 is collected most frequently (cheap), Gen 2 is collected rarely (expensive). Large objects (>85KB) go directly to the Large Object Heap. Understanding this helps avoid excessive allocations and GC pressure.

4. **Explain covariance and contravariance in generics.**
   - Covariance (`out T`): `IEnumerable<Derived>` can be used as `IEnumerable<Base>` — safe for output. Contravariance (`in T`): `Action<Base>` can be used as `Action<Derived>` — safe for input. This enables flexible generic interfaces while maintaining type safety.

5. **How would you design a high-performance ASP.NET Core API?**
   - Use `async`/`await` throughout to avoid blocking threads. Use `IAsyncEnumerable<T>` for streaming large datasets. Minimize allocations with `Span<T>`, `ArrayPool`, and object pooling. Use response caching and output caching middleware. Apply `.AsNoTracking()` for read-only EF Core queries. Use projection (`.Select()`) to avoid over-fetching. Profile with `dotnet-counters` and `BenchmarkDotNet`.

</details>

---

## Practice Projects

### Project 1: Task Manager CLI
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** Command-line task manager — add, list, complete, and delete tasks. Save tasks to a JSON file for persistence between sessions.

**Skills practiced:** Variables, types, control flow, pattern matching, string interpolation, file I/O with `System.Text.Json`.

---

### Project 2: Library Management System
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** Object-oriented library system with `Book`, `Member`, and `Loan` classes. Search and filter books with LINQ. Track overdue items and generate reports.

**Skills practiced:** Classes, interfaces, inheritance, records, `List<T>`, `Dictionary<K,V>`, LINQ queries, lambda expressions.

---

### Project 3: Async File Processor
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** Process multiple large CSV files concurrently — read, transform, and write output. Progress reporting, cancellation support, and error handling for each file.

**Skills practiced:** Exception handling, `using` statements, async/await, `Task.WhenAll`, `CancellationToken`, `IAsyncEnumerable`.

---

### Project 4: REST API with ASP.NET Core
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A complete REST API for a blog platform — posts, comments, tags. EF Core with SQLite, Swagger docs, input validation, and proper error responses.

**Skills practiced:** Minimal APIs or controllers, dependency injection, EF Core, migrations, relationships, model binding, Swagger.

---

### Project 5: Full-Stack Production App
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** Production-ready inventory management API with authentication, role-based authorization, 80%+ test coverage, Docker containerization, and CI/CD pipeline.

**Skills practiced:** Everything from all phases — xUnit, Moq, integration tests, project architecture, NuGet, GitHub Actions, Docker.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [learn.microsoft.com/dotnet/csharp](https://learn.microsoft.com/dotnet/csharp/) | Official C# documentation — language reference, tutorials, and what's new in each version |
| [learn.microsoft.com/aspnet/core](https://learn.microsoft.com/aspnet/core/) | Official ASP.NET Core docs — web APIs, MVC, Blazor, SignalR |
| [learn.microsoft.com/ef/core](https://learn.microsoft.com/ef/core/) | Official Entity Framework Core docs — getting started, migrations, querying |
| [C# Language Specification](https://learn.microsoft.com/dotnet/csharp/language-reference/language-specification/) | The definitive reference for every C# language feature |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Microsoft Learn — C# Path](https://learn.microsoft.com/training/paths/get-started-c-sharp-part-1/) | Free, official Microsoft learning path with hands-on exercises |
| [freeCodeCamp — C# Certification](https://www.freecodecamp.org/learn/foundational-c-sharp-with-microsoft/) | Free certification built in partnership with Microsoft |
| [Exercism — C# Track](https://exercism.org/tracks/csharp) | 100+ exercises with free mentor feedback |
| [Codecademy — Learn C#](https://www.codecademy.com/learn/learn-c-sharp) | In-browser coding with instant feedback |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Nick Chapsas](https://www.youtube.com/@nickchapsas) | Best .NET YouTube channel — deep dives into modern C#, performance, and best practices |
| [Tim Corey (IAmTimCorey)](https://www.youtube.com/@IAmTimCorey) | Clear, thorough tutorials covering C# from beginner to advanced |
| [Raw Coding](https://www.youtube.com/@RawCoding) | ASP.NET Core, authentication, and advanced .NET topics |
| [dotnet](https://www.youtube.com/@dotnet) | Official .NET channel — conference talks, what's new, live streams |
| [Fireship — C# in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview of the language |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — ASP.NET Core](https://roadmap.sh/aspnet-core) | Interactive learning path with progress tracking for ASP.NET Core development |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [C# Dev Kit (VS Code)](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) | Essential — IntelliSense, debugging, testing, solution explorer in VS Code |
| [Visual Studio 2022](https://visualstudio.microsoft.com/) | Full IDE with debugger, profiler, designer, NuGet manager — free Community edition |
| [JetBrains Rider](https://www.jetbrains.com/rider/) | Cross-platform .NET IDE with powerful refactoring and code analysis |
| [LINQPad](https://www.linqpad.net/) | Interactive C# scratchpad — test LINQ queries, snippets, and database queries instantly |
| [dotnet-ef tool](https://learn.microsoft.com/ef/core/cli/dotnet) | CLI tool for EF Core migrations and database management |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [C# Quick Reference](https://www.thecodingguys.net/resources/cs-cheat-sheet.pdf) | PDF covering syntax, types, collections, and LINQ |
| [LINQ Cheat Sheet](https://vslapp.files.wordpress.com/2011/11/linq-cheatsheet.pdf) | PDF covering all LINQ methods with examples |

---

[Back to Main Syllabus](../README.md)

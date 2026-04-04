# Go (Golang) Syllabus

A complete, structured learning path for Go — from your first program to building production services with concurrency, testing, and idiomatic Go patterns.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Go: 1.22+](https://img.shields.io/badge/Go-1.22%2B-00ADD8)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Types](#phase-2-variables--types)
- [Phase 3: Control Flow & Functions](#phase-3-control-flow--functions)
- [Phase 4: Structs & Interfaces](#phase-4-structs--interfaces)
- [Phase 5: Pointers & Methods](#phase-5-pointers--methods)
- [Phase 6: Packages & Modules](#phase-6-packages--modules)
- [Phase 7: Concurrency](#phase-7-concurrency)
- [Phase 8: Error Handling](#phase-8-error-handling)
- [Phase 9: Standard Library](#phase-9-standard-library)
- [Phase 10: Testing & Best Practices](#phase-10-testing--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Go is designed to be **simple and readable**. You don't need deep programming experience, but basic familiarity with any language (variables, loops, functions) will help you move faster.

- Basic programming concepts (variables, loops, conditionals, functions)
- Command line / terminal basics
- Understanding of compiled vs interpreted languages (helpful, not required)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Go is, install it, and write your first program.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Go | A statically typed, compiled language created at Google. Fast compilation, built-in concurrency, garbage collected, simple by design |
| 2 | Why Go | Built for simplicity, speed, and concurrency. Powers Docker, Kubernetes, Terraform, and many cloud-native tools |
| 3 | Installation | Install Go from golang.org. Verify with `go version`. Set up `GOPATH` and `GOROOT` (Go manages these automatically now) |
| 4 | Go Modules | `go mod init module-name` — the modern way to manage dependencies. Creates `go.mod` and `go.sum` files |
| 5 | Hello World | `package main`, `import "fmt"`, `func main()`, `fmt.Println("Hello, World!")` — every Go program starts here |
| 6 | `go run` & `go build` | `go run main.go` compiles and runs. `go build` creates a standalone binary. No runtime dependencies needed |
| 7 | Go Playground | [go.dev/play](https://go.dev/play) — write, run, and share Go code in the browser. Great for quick experiments |

> [!TIP]
> Go has an opinionated formatter built in. Run `gofmt` or `go fmt` to auto-format your code — no debates about style:
> ```go
> // Format all files in current directory
> go fmt ./...
>
> // Or use goimports (also fixes imports)
> go install golang.org/x/tools/cmd/goimports@latest
> goimports -w .
> ```
> Most editors run `gofmt` on save automatically. Set this up from day one.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Go and verify with `go version`
- [ ] Create a module with `go mod init` and write a Hello World program
- [ ] Build a binary with `go build` and run it directly

</details>

---

## Phase 2: Variables & Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Learn Go's type system — strict, explicit, and designed to prevent bugs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `var` Declaration | `var name string = "Go"` — explicit type declaration. Can declare multiple variables in a block |
| 2 | Short Declaration `:=` | `name := "Go"` — type inferred from value. Only works inside functions. The most common way to declare variables |
| 3 | Basic Types | `int`, `float64`, `string`, `bool`, `byte`, `rune`. Also sized types: `int8`, `int16`, `int32`, `int64`, `uint` |
| 4 | Zero Values | Uninitialized variables get zero values: `0` for numbers, `""` for strings, `false` for bools, `nil` for pointers/slices/maps |
| 5 | Type Conversions | Go has no implicit conversions. Must be explicit: `float64(myInt)`, `int(myFloat)`, `string(myBytes)` |
| 6 | Constants | `const Pi = 3.14` — immutable values determined at compile time. Cannot use `:=` for constants |
| 7 | `iota` | Auto-incrementing constant generator: `iota` starts at 0 and increments in each `const` block entry. Perfect for enums |

> [!IMPORTANT]
> Go has **no implicit type conversions** — you must convert explicitly. This prevents subtle bugs:
> ```go
> var x int = 42
> var y float64 = float64(x) // Must explicitly convert
>
> // This will NOT compile:
> // var z float64 = x  // cannot use x (type int) as type float64
>
> // iota for enums
> type Status int
> const (
>     Pending Status = iota // 0
>     Active                // 1
>     Closed                // 2
> )
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables using both `var` and `:=`
- [ ] List the zero values for all basic types
- [ ] Create an enum-like set of constants using `iota`

</details>

---

## Phase 3: Control Flow & Functions

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Master Go's control structures and function patterns.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if`/`else` | No parentheses around conditions. Supports init statement: `if val, err := get(); err != nil { }` |
| 2 | `switch` | No `break` needed — cases don't fall through by default. Use `fallthrough` keyword if you want it. Expression and type switches |
| 3 | `for` Loops | Go's only loop keyword. `for i := 0; i < 10; i++ {}`, `for condition {}` (while), `for {}` (infinite) |
| 4 | `range` | Iterate over slices, maps, strings, channels: `for index, value := range slice {}`. Use `_` to ignore index or value |
| 5 | Functions | `func add(a int, b int) int { return a + b }`. Functions are first-class citizens — pass them as arguments |
| 6 | Multiple Returns | `func divide(a, b float64) (float64, error)` — return multiple values. The idiomatic Go error handling pattern |
| 7 | Named Returns | `func divide(a, b float64) (result float64, err error)` — named return values can use bare `return` (use sparingly) |
| 8 | `defer` | `defer file.Close()` — deferred calls execute when the surrounding function returns. LIFO order. Perfect for cleanup |

> [!TIP]
> `defer` is Go's way of guaranteeing cleanup. It runs when the function exits, even on panic:
> ```go
> func readFile(path string) (string, error) {
>     f, err := os.Open(path)
>     if err != nil {
>         return "", err
>     }
>     defer f.Close() // Always closes, even if ReadAll fails
>
>     data, err := io.ReadAll(f)
>     if err != nil {
>         return "", err
>     }
>     return string(data), nil
> }
> ```
> Place `defer` immediately after acquiring a resource — never separate them.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with multiple return values including errors
- [ ] Use `range` to iterate over slices, maps, and strings
- [ ] Use `defer` for resource cleanup in a function that opens a file

</details>

---

## Phase 4: Structs & Interfaces

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Go doesn't have classes — it uses structs and interfaces for composition over inheritance.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Struct Definition | `type User struct { Name string; Age int }` — group related fields together. Go's replacement for classes |
| 2 | Methods with Receivers | `func (u User) Greet() string` — attach methods to types. Value receivers get a copy, pointer receivers can modify |
| 3 | Interfaces | `type Reader interface { Read(p []byte) (int, error) }` — define behavior. Implemented implicitly — no `implements` keyword |
| 4 | Empty Interface | `interface{}` (or `any` in Go 1.18+) — accepts any type. Used by `fmt.Println`, JSON marshaling. Use sparingly |
| 5 | Type Assertions | `val, ok := i.(string)` — extract the concrete type from an interface. Always use the two-value form to avoid panics |
| 6 | Embedding | `type Admin struct { User; Level int }` — composition, not inheritance. Admin "has a" User and promotes all its methods |

> [!IMPORTANT]
> Interfaces in Go are **satisfied implicitly** — no `implements` keyword. If a type has the right methods, it satisfies the interface:
> ```go
> type Shape interface {
>     Area() float64
> }
>
> type Circle struct { Radius float64 }
>
> // Circle satisfies Shape — no declaration needed
> func (c Circle) Area() float64 {
>     return math.Pi * c.Radius * c.Radius
> }
>
> func printArea(s Shape) {
>     fmt.Printf("Area: %.2f\n", s.Area())
> }
>
> printArea(Circle{Radius: 5}) // Works — Circle satisfies Shape
> ```
> Keep interfaces small — the standard library's `io.Reader` has just one method.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Define a struct with methods using both value and pointer receivers
- [ ] Create an interface and implement it with two different types
- [ ] Use struct embedding to compose types together

</details>

---

## Phase 5: Pointers & Methods

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand how Go passes data — and when to use pointers.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Pointer Basics | `&x` gets the address, `*p` dereferences the pointer. `var p *int` declares a pointer to int |
| 2 | Value vs Pointer Receivers | Value receiver `(u User)` works on a copy. Pointer receiver `(u *User)` can modify the original struct |
| 3 | When to Use Pointers | Use pointers when: the method modifies the receiver, the struct is large, you need to signal "no value" with `nil` |
| 4 | `new()` vs `make()` | `new(T)` allocates zeroed memory and returns a pointer. `make()` initializes slices, maps, and channels (returns value, not pointer) |
| 5 | `nil` | The zero value for pointers, slices, maps, channels, interfaces, and functions. Accessing a nil pointer causes a panic |
| 6 | Slices & Maps | Slices (`[]int`) are reference types backed by arrays. Maps (`map[string]int`) are reference types — both passed by reference automatically |

> [!CAUTION]
> **Always check for `nil` before dereferencing pointers.** A nil pointer dereference causes a runtime panic:
> ```go
> type Config struct { Port int }
>
> func getConfig() *Config {
>     return nil // Could happen in real code
> }
>
> // WRONG — panics if config is nil
> // port := getConfig().Port
>
> // CORRECT — check for nil first
> config := getConfig()
> if config != nil {
>     port := config.Port
>     fmt.Println(port)
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the difference between `&` and `*` operators
- [ ] Write methods with pointer receivers that modify struct fields
- [ ] Create slices and maps using `make()` and explain when to use `new()`

</details>

---

## Phase 6: Packages & Modules

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Organize Go code into packages and manage dependencies with modules.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `go mod` | `go mod init`, `go mod tidy` — manage dependencies. `go.mod` declares the module path and Go version |
| 2 | Importing Packages | `import "fmt"`, `import "github.com/user/repo"` — standard library and third-party packages |
| 3 | Exported vs Unexported | Uppercase = exported (`User`, `GetName()`). Lowercase = unexported (`user`, `getName()`). No `public`/`private` keywords |
| 4 | `init()` Function | Runs automatically when a package is imported, before `main()`. Use for setup/initialization. Avoid side effects |
| 5 | Organizing Code | One package per directory. Package name matches directory name. Group by domain/feature, not by type |
| 6 | `go get` | `go get github.com/pkg/errors` — download and add dependencies. `go get -u` updates to latest version |
| 7 | Internal Packages | `internal/` directory restricts access — code inside can only be imported by the parent module. Enforced by the compiler |

> [!TIP]
> Go's capitalization rule is the entire visibility system. No keywords needed:
> ```go
> package user
>
> // Exported — accessible from other packages
> type User struct {
>     Name  string  // Exported field
>     Email string  // Exported field
>     age   int     // Unexported — only accessible within this package
> }
>
> // Exported function
> func NewUser(name, email string) User {
>     return User{Name: name, Email: email, age: 0}
> }
>
> // Unexported — only used internally
> func validate(email string) bool {
>     return strings.Contains(email, "@")
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a multi-package project with `go mod init`
- [ ] Export and import types and functions between packages
- [ ] Add a third-party dependency with `go get` and clean up with `go mod tidy`

</details>

---

## Phase 7: Concurrency

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Go's killer feature — lightweight concurrency with goroutines and channels.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Goroutines | `go doWork()` — launch thousands of lightweight concurrent functions. Cost: ~2KB stack each (vs ~1MB per OS thread) |
| 2 | Channels | `ch := make(chan int)` — typed pipes for goroutine communication. Send: `ch <- value`. Receive: `value := <-ch` |
| 3 | Buffered Channels | `ch := make(chan int, 10)` — hold up to N values without blocking. Unbuffered channels block until both sides are ready |
| 4 | `select` | Multiplex across multiple channels: `select { case v := <-ch1: ... case ch2 <- v: ... default: ... }` — like a switch for channels |
| 5 | `WaitGroup` | `sync.WaitGroup` — wait for a group of goroutines to finish. `Add()`, `Done()`, `Wait()` |
| 6 | `Mutex` | `sync.Mutex` — protect shared data from concurrent access. `Lock()`, `Unlock()`. Also `sync.RWMutex` for read-heavy workloads |
| 7 | `sync` Package | `sync.Once` (run something exactly once), `sync.Map` (concurrent-safe map), `sync.Pool` (object reuse) |

> [!CAUTION]
> **"Don't communicate by sharing memory; share memory by communicating."** — Go proverb. Use channels instead of shared variables with mutexes whenever possible:
> ```go
> // Pattern: Fan-out, fan-in
> func process(jobs <-chan int, results chan<- int) {
>     for job := range jobs {
>         results <- job * 2 // Process and send result
>     }
> }
>
> func main() {
>     jobs := make(chan int, 100)
>     results := make(chan int, 100)
>
>     // Launch 3 worker goroutines
>     for w := 0; w < 3; w++ {
>         go process(jobs, results)
>     }
>
>     // Send jobs
>     for j := 0; j < 9; j++ {
>         jobs <- j
>     }
>     close(jobs)
> }
> ```
> Always close channels from the sender side, never the receiver.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Launch goroutines and synchronize them with `WaitGroup`
- [ ] Build a producer-consumer pipeline using channels
- [ ] Use `select` to handle multiple channels with a timeout

</details>

---

## Phase 8: Error Handling

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Go handles errors explicitly — no try/catch, no exceptions. Errors are values.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Error Interface | `type error interface { Error() string }` — any type with an `Error()` method is an error. Return `error` as the last value |
| 2 | `errors.New` | `errors.New("something failed")` — create simple error values for expected failure cases |
| 3 | `fmt.Errorf` | `fmt.Errorf("failed to load %s: %w", name, err)` — format error messages with context. `%w` wraps the original error |
| 4 | Wrapping & Unwrapping | `fmt.Errorf("context: %w", err)` wraps. `errors.Unwrap()`, `errors.Is()`, `errors.As()` — inspect the error chain |
| 5 | Custom Errors | Define struct types that implement the `error` interface for errors that carry additional data (status codes, fields) |
| 6 | `panic` & `recover` | `panic()` crashes the program. `recover()` catches panics in deferred functions. Use only for truly unrecoverable errors |

> [!IMPORTANT]
> **Always handle errors immediately.** The `if err != nil` pattern is intentional — it forces you to think about failure at every step:
> ```go
> // WRONG — ignoring the error
> // data, _ := os.ReadFile("config.json")
>
> // CORRECT — handle with context
> data, err := os.ReadFile("config.json")
> if err != nil {
>     return fmt.Errorf("reading config: %w", err)
> }
>
> // errors.Is checks the chain
> if errors.Is(err, os.ErrNotExist) {
>     // File doesn't exist — use defaults
> }
>
> // errors.As extracts a specific error type
> var pathErr *os.PathError
> if errors.As(err, &pathErr) {
>     fmt.Println("Failed path:", pathErr.Path)
> }
> ```
> Never use `panic` for normal error handling — reserve it for programming bugs or impossible states.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions that return errors and handle them with `if err != nil`
- [ ] Wrap errors with context using `fmt.Errorf` and `%w`
- [ ] Create a custom error type and inspect it with `errors.As`

</details>

---

## Phase 9: Standard Library

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Go's standard library is famously comprehensive — you can build production services without any third-party packages.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `net/http` | Build HTTP servers and clients. `http.HandleFunc`, `http.ListenAndServe`, `http.Get` — no framework needed |
| 2 | `encoding/json` | `json.Marshal` (struct to JSON), `json.Unmarshal` (JSON to struct), struct tags: `` `json:"name"` ``. `json.Encoder`/`Decoder` for streams |
| 3 | `io` | `io.Reader`, `io.Writer` — the core interfaces. `io.Copy`, `io.ReadAll`, `io.TeeReader`. Compose with pipes |
| 4 | `os` | File operations: `os.Open`, `os.Create`, `os.ReadFile`, `os.WriteFile`. Environment: `os.Getenv`, `os.Args` |
| 5 | `fmt` | `fmt.Println`, `fmt.Printf` (formatted), `fmt.Sprintf` (returns string), `fmt.Errorf` (returns error). Verb: `%v`, `%s`, `%d`, `%+v` |
| 6 | `strings` & `strconv` | `strings.Contains`, `Split`, `Join`, `TrimSpace`, `Replace`. `strconv.Atoi` (string to int), `strconv.Itoa` (int to string) |
| 7 | `time` | `time.Now()`, `time.Duration`, `time.Sleep`, `time.Parse`, `time.Format`. Layout: `"2006-01-02 15:04:05"` (reference time) |
| 8 | `context` | `context.Background()`, `context.WithTimeout`, `context.WithCancel` — pass deadlines, cancellation, and values across API boundaries |

> [!TIP]
> Go's `net/http` is production-ready out of the box. You can build a full API server without any framework:
> ```go
> mux := http.NewServeMux()
>
> mux.HandleFunc("GET /users", listUsers)
> mux.HandleFunc("POST /users", createUser)
> mux.HandleFunc("GET /users/{id}", getUser)
>
> // Go 1.22+ supports method and path patterns natively
> server := &http.Server{
>     Addr:         ":8080",
>     Handler:      mux,
>     ReadTimeout:  5 * time.Second,
>     WriteTimeout: 10 * time.Second,
> }
> server.ListenAndServe()
> ```
> Go 1.22+ added enhanced routing patterns — method matching and path parameters without a third-party router.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build an HTTP server with multiple routes using `net/http`
- [ ] Marshal and unmarshal JSON with struct tags
- [ ] Use `context.WithTimeout` to cancel long-running operations

</details>

---

## Phase 10: Testing & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Go has testing built into the language and toolchain — no third-party test framework needed.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `go test` | Files named `_test.go` are test files. Functions named `TestXxx(t *testing.T)` are tests. Run with `go test ./...` |
| 2 | Table-Driven Tests | Define test cases as a slice of structs, loop through them. The idiomatic Go testing pattern — clean and extensible |
| 3 | Benchmarks | `func BenchmarkXxx(b *testing.B)` — measure performance. Run with `go test -bench=.`. Loop `b.N` times |
| 4 | Test Coverage | `go test -cover` shows percentage. `go test -coverprofile=c.out` + `go tool cover -html=c.out` for visual report |
| 5 | Linting | `golangci-lint` — runs 50+ linters in one tool. `go vet` for built-in static analysis. `staticcheck` for advanced checks |
| 6 | Project Layout | `cmd/` (entry points), `internal/` (private packages), `pkg/` (public libraries). Follow [golang-standards/project-layout](https://github.com/golang-standards/project-layout) |
| 7 | Subtests | `t.Run("subtest name", func(t *testing.T) {})` — group related tests, run individually with `-run TestXxx/subtest` |
| 8 | Test Helpers | `t.Helper()` marks a function as a test helper — error reports show the caller's line, not the helper's |

> [!IMPORTANT]
> **Table-driven tests** are the Go standard. Every Go developer writes tests this way:
> ```go
> func TestAdd(t *testing.T) {
>     tests := []struct {
>         name     string
>         a, b     int
>         expected int
>     }{
>         {"positive numbers", 2, 3, 5},
>         {"negative numbers", -1, -2, -3},
>         {"zero", 0, 0, 0},
>         {"mixed", -1, 5, 4},
>     }
>
>     for _, tt := range tests {
>         t.Run(tt.name, func(t *testing.T) {
>             result := Add(tt.a, tt.b)
>             if result != tt.expected {
>                 t.Errorf("Add(%d, %d) = %d, want %d",
>                     tt.a, tt.b, result, tt.expected)
>             }
>         })
>     }
> }
> ```
> Run a specific subtest: `go test -run TestAdd/positive_numbers`

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write table-driven tests with subtests for a utility function
- [ ] Run benchmarks and interpret the results
- [ ] Generate a coverage report and achieve 80%+ coverage on a package

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Ignoring errors with `_` | Hidden failures cause mysterious bugs downstream | Always handle errors: `if err != nil { return err }` |
| 2 | Using `panic` for error handling | `panic` crashes the program — it's not try/catch | Return `error` values and let the caller decide |
| 3 | Goroutine leaks | Goroutines that never exit waste memory and CPU forever | Always ensure goroutines can terminate — use `context` or `done` channels |
| 4 | Race conditions on shared data | Concurrent reads/writes cause unpredictable behavior | Use channels, `sync.Mutex`, or run `go test -race` to detect races |
| 5 | Nil pointer dereference | Accessing fields on a `nil` pointer causes a runtime panic | Check for `nil` before dereferencing. Return zero values instead of nil when possible |
| 6 | Not closing resources | Unclosed files, HTTP bodies, and database connections leak resources | Use `defer resource.Close()` immediately after opening |
| 7 | Mutating a slice passed to a function | Slices share underlying arrays — modifications affect the caller unexpectedly | Copy the slice with `copy()` or `append(slice[:0:0], slice...)` if mutation is unintended |
| 8 | Using `init()` for complex logic | `init()` runs implicitly, makes testing hard, hides dependencies | Pass dependencies explicitly. Use constructor functions like `NewServer(cfg Config)` |
| 9 | Overusing `interface{}` / `any` | Loses type safety — defeats the purpose of a typed language | Use generics (Go 1.18+) or define specific interfaces with the methods you need |
| 10 | Not running `go vet` and linters | Missed bugs that static analysis catches automatically | Run `go vet ./...` and `golangci-lint run` in CI and before every commit |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is Go and why was it created?**
   - Go is a statically typed, compiled language created at Google by Robert Griesemer, Rob Pike, and Ken Thompson. Designed for simplicity, fast compilation, built-in concurrency, and efficient networking. Solves problems of slow builds, complex dependencies, and difficulty writing concurrent code in C++ and Java.

2. **What are zero values in Go?**
   - Every type has a default value when uninitialized: `0` for integers, `0.0` for floats, `""` for strings, `false` for bools, `nil` for pointers, slices, maps, channels, interfaces, and functions. This eliminates uninitialized variable bugs.

3. **What is the difference between `var` and `:=`?**
   - `var x int = 5` is explicit — works everywhere, including package level. `:=` is short declaration with type inference — `x := 5` — only works inside functions. Use `:=` in functions for brevity, `var` at package level or when you need to specify the type.

4. **How does Go handle visibility (public/private)?**
   - Uppercase first letter = exported (visible outside the package). Lowercase = unexported (package-private). `User` is exported, `user` is not. No `public`/`private`/`protected` keywords. Applies to functions, types, variables, struct fields, and methods.

5. **What is `defer` and when do you use it?**
   - `defer` schedules a function call to run when the surrounding function returns. Used for cleanup: closing files, unlocking mutexes, flushing buffers. Multiple defers execute in LIFO (last-in, first-out) order. Runs even if the function panics.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain interfaces in Go. How are they different from other languages?**
   - Interfaces define a set of method signatures. They're satisfied implicitly — if a type has the right methods, it implements the interface without declaring it. This enables duck typing with compile-time safety. Keep interfaces small (1-3 methods). The `io.Reader` interface has just one method: `Read(p []byte) (int, error)`.

2. **Value receivers vs pointer receivers — when do you use each?**
   - Value receivers `(u User)` work on a copy — safe, can't modify original. Pointer receivers `(u *User)` work on the original — can modify fields, required for large structs to avoid copying. Rule: if any method uses a pointer receiver, all methods on that type should use pointer receivers for consistency.

3. **What are goroutines and how do they differ from OS threads?**
   - Goroutines are lightweight concurrent functions managed by the Go runtime. ~2KB initial stack (vs ~1MB per OS thread). The Go scheduler multiplexes thousands of goroutines onto a small number of OS threads (M:N scheduling). Created with `go func()`. Cost-effective: you can run millions.

4. **How do channels work? Buffered vs unbuffered.**
   - Channels are typed conduits for goroutine communication. Unbuffered (`make(chan int)`) blocks sender until receiver is ready and vice versa — guarantees synchronization. Buffered (`make(chan int, 10)`) holds N values — sender blocks only when full, receiver blocks only when empty. Close channels from the sender side.

5. **How does Go error handling work? Why no exceptions?**
   - Functions return `error` as the last return value. Callers check `if err != nil`. No exceptions, no try/catch — errors are values you handle explicitly. This forces you to consider every failure point. Use `fmt.Errorf("context: %w", err)` to wrap errors with context. Use `errors.Is`/`errors.As` to inspect the chain.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain Go's memory model and the `sync` package.**
   - Go's memory model defines when reads in one goroutine are guaranteed to observe writes from another. Without synchronization, there are no guarantees. Use `sync.Mutex` for mutual exclusion, `sync.RWMutex` for read-heavy workloads, `sync.Once` for one-time initialization, channels for communication. `go test -race` detects data races.

2. **How does the Go garbage collector work?**
   - Go uses a concurrent, tri-color mark-and-sweep GC. It runs concurrently with the program (low pause times, typically <1ms). Uses write barriers during the mark phase. Tunable with `GOGC` (default 100 = GC when heap doubles). Go 1.19+ added `GOMEMLIMIT` for soft memory limits. No generational collection — optimized for low latency over throughput.

3. **What are generics in Go and when should you use them?**
   - Added in Go 1.18. Type parameters: `func Map[T, U any](s []T, f func(T) U) []U`. Use when: writing data structures (trees, queues), utility functions that work on multiple types, avoiding `interface{}`. Don't use when: a concrete type works fine, or when an interface with methods is more readable. Constraint interfaces define type requirements.

4. **How would you design a concurrent pipeline in Go?**
   - Use the fan-out/fan-in pattern: Stage 1 produces work on a channel. Multiple goroutines (fan-out) read from that channel and write results to another. A single goroutine (fan-in) collects results. Use `context.WithCancel` for graceful shutdown. Close channels to signal completion. Use `errgroup` to propagate errors and manage goroutine lifecycles.

5. **Explain the `context` package and its role in production Go code.**
   - `context.Context` carries deadlines, cancellation signals, and request-scoped values across API boundaries. `context.WithTimeout` auto-cancels after a duration. `context.WithCancel` allows manual cancellation. Pass context as the first parameter to every function that does I/O or launches goroutines. Never store context in a struct — always pass it explicitly.

</details>

---

## Practice Projects

### Project 1: CLI Task Manager
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A command-line to-do app that reads and writes tasks to a JSON file. Add, list, complete, and delete tasks using command-line arguments and flags.

**Skills practiced:** Structs, slices, file I/O, JSON marshaling, error handling, `os.Args` or `flag` package.

---

### Project 2: URL Shortener
![Phase 4-6](https://img.shields.io/badge/After-Phase%204--6-yellow)

**What you'll build:** An HTTP service that shortens URLs, stores them in memory (or a file), and redirects short URLs to the original. Includes a JSON API and basic stats.

**Skills practiced:** `net/http`, structs, interfaces, maps, packages, JSON encoding/decoding, routing.

---

### Project 3: Concurrent Web Scraper
![Phase 7](https://img.shields.io/badge/After-Phase%207-orange)

**What you'll build:** A web scraper that fetches multiple URLs concurrently, extracts data, and writes results to a file. Configurable concurrency limit and timeout.

**Skills practiced:** Goroutines, channels, `WaitGroup`, `context.WithTimeout`, `net/http` client, error handling.

---

### Project 4: REST API with Database
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A full CRUD REST API for a bookstore or blog with SQLite or PostgreSQL. Includes JSON request/response handling, input validation, error wrapping, and middleware.

**Skills practiced:** `net/http`, `encoding/json`, `database/sql`, context, custom errors, middleware pattern.

---

### Project 5: Microservice with Full Test Suite
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A production-ready microservice with structured logging, graceful shutdown, health checks, configuration management, Docker support, and 80%+ test coverage.

**Skills practiced:** Everything from all phases — table-driven tests, benchmarks, linting, project layout, CI/CD.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [go.dev — Documentation](https://go.dev/doc/) | Official docs — language spec, effective Go, and standard library reference |
| [go.dev — Tour of Go](https://go.dev/tour/) | Interactive tutorial in the browser — the best first step for any Go learner |
| [go.dev — Effective Go](https://go.dev/doc/effective_go) | The official guide to writing idiomatic Go — read this after the Tour |
| [Go by Example](https://gobyexample.com/) | Annotated code examples for every Go concept — quick reference |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Go Tour](https://go.dev/tour/) | Official interactive tutorial. Covers basics through concurrency with runnable examples |
| [Exercism — Go Track](https://exercism.org/tracks/go) | 140+ exercises with mentorship. Practice Go idioms with real feedback |
| [Gophercises](https://gophercises.com/) | Free video course with coding exercises. Build real projects in Go |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Traversy Media — Go Crash Course](https://www.youtube.com/@TraversyMedia) | Great first Go video. Covers basics in ~1 hour |
| [Anthony GG — Go Projects](https://www.youtube.com/@anthonygg_) | Practical Go projects and patterns. Real-world focused |
| [Fireship — Go in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview of why Go matters |
| [NerdCademy — Go Tutorial](https://www.youtube.com/@NerdCademyDev) | Beginner-friendly, structured Go tutorials |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Go](https://roadmap.sh/golang) | Interactive learning path with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Go Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=golang.go) | Official Go extension — IntelliSense, debugging, testing, formatting |
| [GoLand](https://www.jetbrains.com/go/) | JetBrains IDE for Go — powerful refactoring, debugging, and code analysis |
| [golangci-lint](https://golangci-lint.run/) | Meta-linter — runs 50+ linters in one tool. Essential for CI |
| [Delve](https://github.com/go-delve/delve) | The Go debugger — breakpoints, step-through, goroutine inspection |
| [Air](https://github.com/cosmtrek/air) | Live reload for Go apps — auto-rebuild on file changes during development |

### Key Libraries

| Package | What It Does |
|---------|-------------|
| [gin](https://github.com/gin-gonic/gin) | Fast HTTP web framework with routing, middleware, and JSON validation |
| [chi](https://github.com/go-chi/chi) | Lightweight router compatible with `net/http` — idiomatic and composable |
| [sqlx](https://github.com/jmoiron/sqlx) | Extensions to `database/sql` — struct scanning, named parameters |
| [pgx](https://github.com/jackc/pgx) | PostgreSQL driver — faster than `lib/pq`, pure Go, connection pooling |
| [zap](https://github.com/uber-go/zap) | Blazing fast structured logging from Uber |
| [viper](https://github.com/spf13/viper) | Configuration management — env vars, config files, CLI flags, remote config |
| [cobra](https://github.com/spf13/cobra) | CLI framework — powers Docker CLI, Hugo, Kubernetes kubectl |
| [testify](https://github.com/stretchr/testify) | Testing toolkit — assertions, mocks, suites (though standard `testing` is often enough) |
| [wire](https://github.com/google/wire) | Compile-time dependency injection from Google |
| [grpc-go](https://github.com/grpc/grpc-go) | gRPC framework for Go — high-performance RPC |

---

[Back to Main Syllabus](../README.md)

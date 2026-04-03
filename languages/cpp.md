# C++ Syllabus

A complete, structured learning path for C++ — from your first `cout` to mastering templates, smart pointers, multithreading, and writing modern, production-grade C++17/20 code.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![C++: 17/20](https://img.shields.io/badge/C%2B%2B-17%2F20-00599C)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Types](#phase-2-variables--types)
- [Phase 3: Control Flow](#phase-3-control-flow)
- [Phase 4: Functions](#phase-4-functions)
- [Phase 5: Object-Oriented Programming](#phase-5-object-oriented-programming)
- [Phase 6: Memory Management](#phase-6-memory-management)
- [Phase 7: Standard Template Library (STL)](#phase-7-standard-template-library-stl)
- [Phase 8: Templates & Generics](#phase-8-templates--generics)
- [Phase 9: Advanced C++](#phase-9-advanced-c)
- [Phase 10: Build & Testing](#phase-10-build--testing)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> C++ is a powerful systems-level language used in game engines, embedded systems, operating systems, finance, and high-performance computing. It has a steeper learning curve than Python or JavaScript, but rewards you with fine-grained control over hardware and performance.

- Basic understanding of how computers work (memory, CPU)
- A text editor ([VS Code](https://code.visualstudio.com/) with the C/C++ extension recommended)
- A C++ compiler (GCC, Clang, or MSVC)
- Patience — C++ is deep, but every concept you learn makes you a stronger programmer

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write your first C++ program and understand the compilation model.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is C++ | A general-purpose, compiled language created by Bjarne Stroustrup. Used in games, OS kernels, browsers, databases, and anywhere performance matters |
| 2 | Compiler Setup | Install GCC (`g++`), Clang (`clang++`), or MSVC. Compile with `g++ -std=c++17 -o hello hello.cpp` |
| 3 | Hello World | `#include <iostream>` + `int main() { std::cout << "Hello, World!\n"; return 0; }` — every C++ program starts at `main()` |
| 4 | `cin` & `cout` | `std::cout <<` for output, `std::cin >>` for input. Use `std::endl` or `"\n"` for newlines (`"\n"` is faster) |
| 5 | Differences from C | C++ adds classes, templates, RAII, namespaces, `std::string`, smart pointers, references, and a massive standard library |
| 6 | Namespaces | `std::cout` vs `using namespace std;` — namespaces prevent name collisions. Avoid `using namespace std;` in headers |
| 7 | Comments | `//` for single-line, `/* */` for multi-line. Use comments to explain *why*, not *what* |
| 8 | Compilation Model | Preprocessor (`#include`) -> Compiler (`.cpp` -> `.o`) -> Linker (`.o` files -> executable). Understand headers vs source files |

> [!TIP]
> Always compile with warnings enabled — they catch bugs before they become runtime disasters:
> ```cpp
> // Compile with all warnings and C++17 standard
> // g++ -std=c++17 -Wall -Wextra -Wpedantic -o main main.cpp
>
> #include <iostream>
>
> int main() {
>     std::cout << "Hello, Modern C++!\n";
>     return 0;
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install a C++ compiler and compile a program from the terminal
- [ ] Write a program that reads user input with `cin` and prints with `cout`
- [ ] Explain the difference between a compiled and interpreted language

</details>

---

## Phase 2: Variables & Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Understand C++'s type system — the foundation of everything.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Primitive Types | `int`, `double`, `float`, `char`, `bool`, `long long` — sizes vary by platform, use `sizeof()` to check |
| 2 | `auto` Keyword | `auto x = 42;` — compiler deduces the type. Use when the type is obvious or complex (iterators, lambdas) |
| 3 | `std::string` vs `char[]` | `std::string` is safe, dynamic, and feature-rich. `char[]` is a C-style array — error-prone and fixed-size. Always prefer `std::string` |
| 4 | References | `int& ref = x;` — an alias to an existing variable. Cannot be null, cannot be reseated. Prefer over pointers when possible |
| 5 | Pointers | `int* ptr = &x;` — stores a memory address. Dereference with `*ptr`. Can be `nullptr`. Essential for dynamic memory |
| 6 | References vs Pointers | References are safer (no null, no arithmetic). Pointers are flexible (can be reassigned, can be null). Use references by default |
| 7 | `const` | `const int x = 10;` — immutable value. `const` references prevent modification: `const std::string& name` |
| 8 | `constexpr` | `constexpr int size = 100;` — evaluated at compile time. Faster than `const` for values known at compile time |
| 9 | Type Casting | `static_cast<int>(3.14)` — safe, explicit casting. Avoid C-style casts `(int)x`. Also: `dynamic_cast`, `reinterpret_cast` |

> [!IMPORTANT]
> **Always initialize your variables.** Uninitialized variables in C++ contain garbage values — this is undefined behavior and a common source of bugs:
> ```cpp
> int x;          // WRONG: uninitialized — contains garbage
> int x = 0;      // CORRECT: initialized
> int x{0};       // CORRECT: uniform initialization (preferred in modern C++)
> auto y = 3.14;  // CORRECT: auto with initializer
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables using primitive types, `auto`, and `std::string`
- [ ] Explain the difference between references and pointers
- [ ] Use `const` and `constexpr` correctly in a program

</details>

---

## Phase 3: Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make decisions and repeat actions with modern C++ constructs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `else if` / `else` | Conditional branching: `if (age >= 18) { ... }`. C++17 adds init-statements: `if (auto it = m.find(key); it != m.end())` |
| 2 | `switch` | Multi-way branching on integral/enum types. Always include `break` or use `[[fallthrough]]` attribute in C++17 |
| 3 | `for` Loops | Classic: `for (int i = 0; i < n; ++i)`. Prefer `++i` over `i++` for non-primitive iterators (avoids a copy) |
| 4 | Range-Based `for` | `for (const auto& item : container)` — iterate any STL container. Use `const auto&` to avoid copies |
| 5 | `while` & `do-while` | `while (condition) { ... }` checks first. `do { ... } while (condition);` executes at least once |
| 6 | `break` & `continue` | `break` exits the loop. `continue` skips to the next iteration. Use sparingly for readability |
| 7 | Structured Bindings | C++17: `auto [key, value] = pair;` — decompose pairs, tuples, and structs into named variables |
| 8 | Ternary Operator | `int result = (a > b) ? a : b;` — concise conditional expression. Don't nest them |

> [!TIP]
> **Structured bindings** (C++17) make working with pairs and tuples much cleaner:
> ```cpp
> #include <map>
> #include <string>
>
> std::map<std::string, int> scores = {{"Alice", 95}, {"Bob", 87}};
>
> for (const auto& [name, score] : scores) {
>     std::cout << name << ": " << score << "\n";
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a program using `if` with C++17 init-statements
- [ ] Use range-based `for` loops with `const auto&`
- [ ] Decompose a `std::pair` or `std::tuple` using structured bindings

</details>

---

## Phase 4: Functions

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable code with functions, overloading, and templates.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Basics | `int add(int a, int b) { return a + b; }` — declare return type, name, parameters. Declare before use or use prototypes |
| 2 | Function Overloading | Same name, different parameters: `print(int)`, `print(std::string)`. Compiler picks the right version at compile time |
| 3 | Default Arguments | `void greet(const std::string& name, const std::string& greeting = "Hello")` — defaults must be rightmost parameters |
| 4 | `inline` Functions | `inline int square(int x) { return x * x; }` — suggests inlining to avoid call overhead. Compiler may ignore the hint |
| 5 | Pass by Value | `void func(int x)` — copies the argument. Safe but expensive for large objects |
| 6 | Pass by Reference | `void func(int& x)` — modifies the original. No copy overhead. Use when you need to mutate the argument |
| 7 | Pass by `const` Reference | `void func(const std::string& s)` — no copy, no mutation. The **default choice** for objects |
| 8 | Function Templates Intro | `template <typename T> T max(T a, T b) { return (a > b) ? a : b; }` — write once, works for any type |
| 9 | `auto` Return Type | C++14: `auto add(int a, int b) { return a + b; }` — compiler deduces return type |

> [!IMPORTANT]
> **Pass objects by `const` reference by default.** Pass by value copies the entire object — expensive for strings, vectors, and custom types:
> ```cpp
> // WRONG: copies the entire string on every call
> void print(std::string s) { std::cout << s; }
>
> // CORRECT: no copy, no mutation — fast and safe
> void print(const std::string& s) { std::cout << s; }
>
> // CORRECT: pass by reference when you need to modify
> void uppercase(std::string& s) { /* modifies original */ }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write overloaded functions and explain how the compiler resolves calls
- [ ] Pass arguments by value, reference, and const reference — explain when to use each
- [ ] Write a simple function template that works with multiple types

</details>

---

## Phase 5: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Model real-world entities with classes, inheritance, and polymorphism.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Structs | `class` defaults to `private`, `struct` defaults to `public`. Use `struct` for plain data, `class` for behavior |
| 2 | Constructors | Default, parameterized, copy, and move constructors. Use member initializer lists: `User(std::string n) : name(std::move(n)) {}` |
| 3 | Destructors | `~ClassName()` — called when object goes out of scope. Essential for releasing resources (files, memory, locks) |
| 4 | Access Specifiers | `public` (anyone), `private` (class only), `protected` (class + derived). Default to `private`, expose minimally |
| 5 | Inheritance | `class Admin : public User { }` — `public` inheritance models "is-a". Avoid `protected`/`private` inheritance unless you know why |
| 6 | Virtual Functions | `virtual void speak()` — enables runtime polymorphism. Override in derived classes with `override` keyword |
| 7 | Pure Virtual & Abstract | `virtual void draw() = 0;` — makes the class abstract. Cannot be instantiated. Derived classes must implement it |
| 8 | Polymorphism | Base pointer/reference to derived object: `Shape* s = new Circle();` `s->draw();` calls `Circle::draw()` at runtime |
| 9 | Operator Overloading | `Vector operator+(const Vector& rhs) const { ... }` — define `+`, `==`, `<<`, `[]` for custom types |
| 10 | Rule of Five | If you define any of: destructor, copy constructor, copy assignment, move constructor, move assignment — define all five |

> [!TIP]
> Always mark overriding functions with `override` — it catches errors at compile time if the base class signature changes:
> ```cpp
> class Shape {
> public:
>     virtual double area() const = 0;      // pure virtual
>     virtual ~Shape() = default;           // virtual destructor!
> };
>
> class Circle : public Shape {
>     double radius;
> public:
>     Circle(double r) : radius(r) {}
>     double area() const override {        // override catches typos
>         return 3.14159 * radius * radius;
>     }
> };
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a class with constructors, destructor, and member initializer lists
- [ ] Implement an inheritance hierarchy with virtual functions and `override`
- [ ] Overload at least two operators (`<<` and `==`) for a custom class

</details>

---

## Phase 6: Memory Management

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Master memory management — the skill that separates C++ from other languages.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Stack vs Heap | Stack: automatic, fast, limited size. Heap: manual, slower, virtually unlimited. Objects on stack are destroyed automatically |
| 2 | `new` & `delete` | `int* p = new int(42);` allocates on heap. `delete p;` frees it. `new[]`/`delete[]` for arrays. **Never use raw `new`/`delete` in modern C++** |
| 3 | `std::unique_ptr` | `auto p = std::make_unique<Widget>();` — exclusive ownership. Cannot be copied, only moved. Use by default |
| 4 | `std::shared_ptr` | `auto p = std::make_shared<Widget>();` — reference-counted shared ownership. Use when multiple owners are necessary |
| 5 | `std::weak_ptr` | Non-owning reference to `shared_ptr`. Breaks circular references. Check with `.lock()` before use |
| 6 | RAII | Resource Acquisition Is Initialization — bind resource lifetime to object lifetime. Constructors acquire, destructors release |
| 7 | Move Semantics | `std::move(x)` transfers ownership instead of copying. `Widget(Widget&& other)` — move constructor steals resources |
| 8 | Copy vs Move | Copy duplicates data (expensive). Move transfers ownership (cheap). Return by value triggers move automatically (RVO/NRVO) |
| 9 | `std::move` & `std::forward` | `std::move` casts to rvalue. `std::forward` preserves value category in templates (perfect forwarding) |

> [!CAUTION]
> **Never use raw `new`/`delete` in modern C++.** Always use smart pointers — they automatically free memory when they go out of scope, preventing leaks:
> ```cpp
> // WRONG: raw new/delete — easy to leak memory
> Widget* w = new Widget();
> // ... if an exception is thrown here, memory leaks
> delete w;
>
> // CORRECT: smart pointer — automatic cleanup, exception-safe
> auto w = std::make_unique<Widget>();
> // w is automatically deleted when it goes out of scope
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the difference between stack and heap allocation
- [ ] Rewrite a program using raw pointers to use `unique_ptr` and `shared_ptr`
- [ ] Implement a class with proper move semantics (move constructor + move assignment)

</details>

---

## Phase 7: Standard Template Library (STL)

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master the STL — the most powerful standard library of any language.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `std::vector` | Dynamic array: `.push_back()`, `.emplace_back()`, `.size()`, `.at()`, `.reserve()`. Your default container |
| 2 | `std::map` | Ordered key-value pairs (red-black tree): O(log n) lookup. `map[key] = value`, `.find()`, `.count()` |
| 3 | `std::unordered_map` | Hash-based key-value pairs: O(1) average lookup. Faster than `map` when order doesn't matter |
| 4 | `std::set` & `std::unordered_set` | Unique elements. `set` is ordered (O(log n)), `unordered_set` is hashed (O(1) average) |
| 5 | `std::deque` | Double-ended queue: efficient push/pop at both ends. Use when you need front insertion |
| 6 | `std::stack` & `std::queue` | Adaptor containers: `stack` is LIFO (`.push()`, `.top()`, `.pop()`), `queue` is FIFO (`.push()`, `.front()`, `.pop()`) |
| 7 | Iterators | `begin()`, `end()`, `cbegin()`, `cend()`. Categories: input, output, forward, bidirectional, random access |
| 8 | Algorithms: Sort & Find | `std::sort(v.begin(), v.end())`, `std::find()`, `std::binary_search()`, `std::lower_bound()` |
| 9 | Algorithms: Transform & More | `std::transform()`, `std::accumulate()`, `std::count_if()`, `std::remove_if()`, `std::for_each()` |
| 10 | `std::array` | Fixed-size array: `std::array<int, 5> arr = {1, 2, 3, 4, 5};` — safer than C-style arrays, knows its size |

> [!TIP]
> Use `std::vector` as your default container — it's fast, cache-friendly, and covers 95% of use cases:
> ```cpp
> #include <vector>
> #include <algorithm>
>
> std::vector<int> nums = {5, 3, 8, 1, 9, 2};
>
> // Sort in-place
> std::sort(nums.begin(), nums.end());
>
> // Find an element
> auto it = std::find(nums.begin(), nums.end(), 8);
> if (it != nums.end()) {
>     std::cout << "Found: " << *it << "\n";
> }
>
> // Remove even numbers (erase-remove idiom)
> nums.erase(
>     std::remove_if(nums.begin(), nums.end(), [](int n) { return n % 2 == 0; }),
>     nums.end()
> );
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `vector`, `map`, `unordered_map`, and `set` in a program
- [ ] Apply `std::sort`, `std::find`, and `std::transform` with iterators
- [ ] Explain when to use `map` vs `unordered_map` vs `vector`

</details>

---

## Phase 8: Templates & Generics

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write generic, reusable code with templates — the backbone of the STL.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Templates | `template <typename T> T max(T a, T b)` — compiler generates type-specific code at compile time |
| 2 | Class Templates | `template <typename T> class Stack { std::vector<T> data; };` — generic data structures |
| 3 | Template Specialization | `template <> class Stack<bool> { ... };` — provide custom implementation for a specific type |
| 4 | Non-Type Template Parameters | `template <typename T, int N> class Array { T data[N]; };` — compile-time constants as parameters |
| 5 | Variadic Templates | `template <typename... Args> void print(Args... args)` — accept any number of arguments of any type |
| 6 | Fold Expressions (C++17) | `(std::cout << ... << args)` — expand variadic parameter packs concisely without recursion |
| 7 | `if constexpr` (C++17) | Compile-time `if` — branches are discarded at compile time. Replaces SFINAE for many use cases |
| 8 | Concepts (C++20) | `template <std::integral T> T add(T a, T b)` — constrain templates with readable requirements instead of SFINAE |
| 9 | `requires` Clause (C++20) | `requires (T a) { a + a; }` — ad-hoc constraints. Clearer error messages when template requirements aren't met |

> [!TIP]
> **Concepts** (C++20) make templates readable and give clear error messages:
> ```cpp
> #include <concepts>
>
> // Before concepts: cryptic error messages
> template <typename T>
> T add(T a, T b) { return a + b; }  // error: no match for operator+
>
> // With concepts: clear constraint
> template <typename T>
> requires std::integral<T> || std::floating_point<T>
> T add(T a, T b) { return a + b; }
>
> add(1, 2);       // OK: int is integral
> add(1.0, 2.0);   // OK: double is floating_point
> // add("a", "b"); // CLEAR ERROR: string doesn't satisfy constraint
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a function template and a class template with multiple type parameters
- [ ] Use `if constexpr` to branch at compile time based on type traits
- [ ] Define a C++20 concept and use it to constrain a template

</details>

---

## Phase 9: Advanced C++

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Master the features that make modern C++ expressive and powerful.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Lambdas | `[capture](params) { body }` — inline anonymous functions. Capture by value `[=]`, by reference `[&]`, or specific variables |
| 2 | `std::function` | `std::function<int(int, int)> op = add;` — type-erased callable wrapper. Store lambdas, functions, functors |
| 3 | Multithreading: `std::thread` | `std::thread t(func, args...);` — launch a thread. Always `.join()` or `.detach()`. Use RAII wrappers (C++20 `std::jthread`) |
| 4 | `std::mutex` & Locks | `std::mutex m; std::lock_guard<std::mutex> lock(m);` — protect shared data from data races |
| 5 | `std::async` & Futures | `auto future = std::async(std::launch::async, func);` — run tasks asynchronously. Get result with `future.get()` |
| 6 | RAII Patterns | Lock guards, file handles, database connections — wrap every resource in an object whose destructor cleans up |
| 7 | Exception Handling | `try { } catch (const std::exception& e) { }` — catch by const reference. Use `noexcept` for functions that never throw |
| 8 | `std::optional` (C++17) | `std::optional<int> find(...)` — explicitly represent "no value" without pointers or sentinel values |
| 9 | `std::variant` (C++17) | `std::variant<int, std::string> v;` — type-safe union. Use `std::visit` with a visitor pattern to handle alternatives |
| 10 | `std::any` (C++17) | Type-safe container for any single value. Use sparingly — prefer `variant` when possible types are known |

> [!IMPORTANT]
> **Always capture lambda variables explicitly** — avoid default captures `[=]` and `[&]` in non-trivial code. They can silently capture `this` or create dangling references:
> ```cpp
> int multiplier = 3;
> std::vector<int> nums = {1, 2, 3, 4, 5};
>
> // WRONG: captures everything by reference — fragile
> auto transform = [&](int x) { return x * multiplier; };
>
> // CORRECT: capture only what you need
> auto transform = [multiplier](int x) { return x * multiplier; };
>
> std::vector<int> result;
> std::transform(nums.begin(), nums.end(), std::back_inserter(result), transform);
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write lambdas with different capture modes and use them with STL algorithms
- [ ] Create a multithreaded program using `std::thread` and `std::mutex`
- [ ] Use `std::optional` and `std::variant` to handle nullable and union types

</details>

---

## Phase 10: Build & Testing

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build, test, and debug C++ projects professionally.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | CMake | `CMakeLists.txt` — the standard build system. `cmake -B build && cmake --build build`. Define targets, link libraries |
| 2 | Makefile | Manual build rules: `g++ -std=c++17 -o app main.cpp`. Good for small projects, CMake for larger ones |
| 3 | Google Test (GTest) | `TEST(SuiteName, TestName) { EXPECT_EQ(add(1, 2), 3); }` — industry-standard C++ testing framework |
| 4 | Test Fixtures | `class MyTest : public ::testing::Test { void SetUp() override { ... } };` — shared setup/teardown for related tests |
| 5 | Debugging with GDB/LLDB | Compile with `-g`. Set breakpoints, step through code, inspect variables: `gdb ./app`, `lldb ./app` |
| 6 | Address Sanitizer | `-fsanitize=address` — detects memory leaks, buffer overflows, use-after-free at runtime |
| 7 | Undefined Behavior Sanitizer | `-fsanitize=undefined` — catches signed integer overflow, null pointer dereference, misaligned access |
| 8 | Thread Sanitizer | `-fsanitize=thread` — detects data races in multithreaded code |
| 9 | Best Practices | Use `const` everywhere, prefer `make_unique`/`make_shared`, mark functions `noexcept`, use `[[nodiscard]]` |
| 10 | Modern C++ Idioms | RAII, Rule of Five/Zero, PIMPL, CRTP, type erasure, `std::string_view` for non-owning string references |

> [!TIP]
> A minimal **CMake** setup to get you started with Google Test:
> ```cmake
> cmake_minimum_required(VERSION 3.14)
> project(MyProject LANGUAGES CXX)
> set(CMAKE_CXX_STANDARD 17)
>
> add_executable(app src/main.cpp)
>
> # Testing
> include(FetchContent)
> FetchContent_Declare(
>     googletest
>     GIT_REPOSITORY https://github.com/google/googletest.git
>     GIT_TAG release-1.12.1
> )
> FetchContent_MakeAvailable(googletest)
>
> add_executable(tests tests/test_main.cpp)
> target_link_libraries(tests GTest::gtest_main)
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up a CMake project with source and test directories
- [ ] Write and run unit tests with Google Test
- [ ] Compile with sanitizers and fix any detected issues

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using raw `new`/`delete` | Memory leaks, double-free, use-after-free — the top source of C++ bugs | Use `std::make_unique` and `std::make_shared` |
| 2 | Forgetting virtual destructor | Deleting a derived object through a base pointer causes undefined behavior | Add `virtual ~Base() = default;` to any class with virtual functions |
| 3 | Passing objects by value | Copies entire object — expensive for strings, vectors, and custom types | Pass by `const&` for read-only, by `&` for mutation |
| 4 | Using `using namespace std;` in headers | Pollutes the global namespace for every file that includes the header | Use `std::` prefix explicitly, or limit `using` to `.cpp` files |
| 5 | Uninitialized variables | Contains garbage values — undefined behavior that may work "sometimes" | Always initialize: `int x = 0;` or `int x{};` |
| 6 | Dangling references/pointers | Returning a reference to a local variable — object is destroyed when function returns | Return by value (move semantics makes it cheap) or use smart pointers |
| 7 | Ignoring the Rule of Five | If you define a destructor but not copy/move operations, the compiler may generate broken defaults | Define all five (destructor, copy ctor, copy assign, move ctor, move assign) or use `= default`/`= delete` |
| 8 | Not using `override` | A typo in a virtual function silently creates a new function instead of overriding | Always add `override` — the compiler will catch mismatches |
| 9 | Catching exceptions by value | Slices derived exception objects — loses the actual exception type and message | Catch by `const` reference: `catch (const std::exception& e)` |
| 10 | Index out of bounds with `[]` | `vector[i]` does not check bounds — undefined behavior if `i >= size()` | Use `.at(i)` for bounds checking, or validate index manually |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between a reference and a pointer?**
   - A reference is an alias that must be initialized, cannot be null, and cannot be reseated. A pointer stores a memory address, can be null, can be reassigned, and supports arithmetic. Prefer references when you don't need null or reseating.

2. **What is the difference between `struct` and `class`?**
   - The only difference is default access: `struct` defaults to `public`, `class` defaults to `private`. By convention, `struct` is used for plain data aggregates and `class` for types with behavior and invariants.

3. **What does `const` mean in different contexts?**
   - `const int x` = immutable variable. `const int* p` = pointer to const int (can't modify value). `int* const p` = const pointer (can't change what it points to). `void f() const` = member function that doesn't modify the object.

4. **What is the difference between `++i` and `i++`?**
   - `++i` (pre-increment) increments and returns the new value. `i++` (post-increment) returns the old value, then increments. For iterators and non-trivial types, `++i` is more efficient because `i++` creates a temporary copy.

5. **What is `std::string` and why prefer it over `char[]`?**
   - `std::string` is a dynamic, bounds-checked, feature-rich string class. `char[]` is a fixed-size C-style array with no size tracking, manual memory management, and common buffer overflow vulnerabilities. Always use `std::string` in C++.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain RAII and give an example.**
   - Resource Acquisition Is Initialization: bind resource lifetime to object scope. Constructor acquires (opens file, allocates memory, locks mutex), destructor releases. `std::lock_guard` acquires a mutex on construction and releases on destruction — even if an exception is thrown.

2. **What is the Rule of Five?**
   - If a class manages a resource (raw pointer, file handle), you must define: destructor, copy constructor, copy assignment operator, move constructor, move assignment operator. If you don't need custom behavior, use the Rule of Zero — let the compiler generate all five by using smart pointers and standard containers.

3. **What are smart pointers and when do you use each?**
   - `unique_ptr`: sole ownership, zero overhead, default choice. `shared_ptr`: shared ownership with reference counting, use when multiple objects must co-own a resource. `weak_ptr`: non-owning observer of `shared_ptr`, breaks circular references. Never use raw `new`/`delete`.

4. **What is the difference between `std::map` and `std::unordered_map`?**
   - `map` uses a red-black tree: O(log n) operations, ordered keys, requires `operator<`. `unordered_map` uses a hash table: O(1) average operations, unordered, requires `std::hash`. Use `unordered_map` for speed when order doesn't matter.

5. **What are move semantics and why do they matter?**
   - Move semantics allow transferring ownership of resources (heap memory, file handles) instead of copying them. `std::move` casts to an rvalue reference. A move constructor "steals" the resources and leaves the source in a valid but unspecified state. Critical for performance with large objects and containers.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What are C++20 concepts and how do they improve templates?**
   - Concepts are named constraints on template parameters: `template <std::integral T>`. They replace SFINAE with readable requirements, produce clear error messages when constraints aren't met, and can be composed with `&&` and `||`. They make generic code self-documenting.

2. **Explain perfect forwarding and `std::forward`.**
   - Perfect forwarding preserves the value category (lvalue/rvalue) of arguments through template functions. `template <typename T> void wrapper(T&& arg) { inner(std::forward<T>(arg)); }`. Without `std::forward`, rvalue arguments would be passed as lvalues, preventing move optimization.

3. **What is the PIMPL idiom?**
   - Pointer to Implementation: hide implementation details behind an opaque pointer in the header. `class Widget { struct Impl; std::unique_ptr<Impl> pImpl; };`. Benefits: reduced compile times (changes to Impl don't trigger recompilation of dependents), ABI stability, true encapsulation.

4. **How do you prevent data races in multithreaded C++?**
   - Use `std::mutex` with `std::lock_guard` or `std::scoped_lock` (C++17) for RAII-based locking. Use `std::atomic` for lock-free operations on single variables. Use `std::async`/`std::future` for task-based parallelism. Compile with `-fsanitize=thread` to detect races. Minimize shared mutable state.

5. **What is CRTP (Curiously Recurring Template Pattern)?**
   - A class inherits from a template parameterized by itself: `class Derived : public Base<Derived>`. Enables static polymorphism (compile-time dispatch without virtual function overhead). Used in mixins, expression templates, and the `enable_shared_from_this` pattern in the standard library.

</details>

---

## Practice Projects

### Project 1: Student Grade Manager
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** CLI app to manage students, record grades, calculate GPA, sort by performance, and save/load from a CSV file.

**Skills practiced:** Variables, types, control flow, `cin`/`cout`, `std::string`, `std::vector`, file I/O.

---

### Project 2: Bank Account System with OOP
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** Object-oriented banking system: `Account` base class, `SavingsAccount` and `CheckingAccount` derived classes, transaction history, operator overloading for account comparisons.

**Skills practiced:** Classes, inheritance, polymorphism, virtual functions, operator overloading, const correctness.

---

### Project 3: Custom Smart Pointer
![Phase 6](https://img.shields.io/badge/After-Phase%206-orange)

**What you'll build:** Implement your own `UniquePtr<T>` and `SharedPtr<T>` with reference counting, move semantics, custom deleters, and RAII cleanup.

**Skills practiced:** Memory management, RAII, move semantics, templates, Rule of Five.

---

### Project 4: Generic Data Structures Library
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-orange)

**What you'll build:** Template library with `Stack<T>`, `Queue<T>`, `HashMap<K, V>`, iterators, and C++20 concepts for type constraints. Benchmarked against STL equivalents.

**Skills practiced:** Templates, specialization, variadic templates, concepts, iterators, STL algorithms.

---

### Project 5: Multithreaded Task Scheduler
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** Thread pool with a task queue, `std::async`-based task submission, `std::mutex`-protected shared state, priority scheduling, and comprehensive Google Test suite with sanitizer integration.

**Skills practiced:** Everything from all phases — lambdas, multithreading, RAII, templates, CMake, Google Test, sanitizers.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [cppreference.com](https://en.cppreference.com/) | The definitive C++ reference — every function, type, and feature with examples |
| [isocpp.org](https://isocpp.org/) | Official ISO C++ site — FAQs, guidelines, and news from the standards committee |
| [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/) | Best practices by Bjarne Stroustrup and Herb Sutter. The authoritative style guide |
| [cplusplus.com](https://cplusplus.com/reference/) | Beginner-friendly reference with clear examples for standard library functions |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [learncpp.com](https://www.learncpp.com/) | The most comprehensive free C++ tutorial site. Covers C++17/20 in depth |
| [Exercism — C++ Track](https://exercism.org/tracks/cpp) | 90+ exercises with free mentor feedback |
| [HackerRank — C++](https://www.hackerrank.com/domains/cpp) | Structured challenges from basic to advanced |
| [Codecademy — Learn C++](https://www.codecademy.com/learn/learn-c-plus-plus) | In-browser coding with instant feedback |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [The Cherno](https://www.youtube.com/@TheCherno) | Best C++ YouTube series — covers modern C++ from basics to engine development |
| [Jason Turner (C++ Weekly)](https://www.youtube.com/@caborern) | Weekly short videos on modern C++ features, tips, and best practices |
| [CppCon](https://www.youtube.com/@CppCon) | Conference talks from the world's top C++ experts |
| [Fireship — C++ in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview of C++ |
| [freeCodeCamp — C++ Full Course](https://www.youtube.com/@freecodecamp) | 4+ hour comprehensive beginner course |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — C++](https://roadmap.sh/cpp) | Interactive learning path with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [C/C++ Extension (Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) | Essential — IntelliSense, debugging, code navigation for VS Code |
| [clangd](https://clangd.llvm.org/) | Fast, accurate code completion and diagnostics based on LLVM |
| [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) | CMake integration for VS Code — configure, build, and debug |
| [Compiler Explorer (Godbolt)](https://godbolt.org/) | See assembly output of your code online — understand what the compiler does |
| [clang-format](https://clang.llvm.org/docs/ClangFormat.html) | Auto-format C++ code. Integrate with VS Code for format-on-save |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [C++ Reference Card](https://hackingcpp.com/cpp/cheat_sheets.html) | Visual, comprehensive C++ cheat sheets covering STL, algorithms, and modern features |
| [C++ Core Guidelines Quick Reference](https://isocpp.github.io/CppCoreGuidelines/) | Searchable best practices from the standards committee |

---

[Back to Main Syllabus](../README.md)
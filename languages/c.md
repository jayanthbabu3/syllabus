# C Programming Syllabus

A complete, structured learning path for C — from your first `printf()` to mastering pointers, memory management, and building efficient systems-level programs.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![C11/C17](https://img.shields.io/badge/C-C11%2FC17-00599C)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Data Types](#phase-2-variables--data-types)
- [Phase 3: Control Flow](#phase-3-control-flow)
- [Phase 4: Functions](#phase-4-functions)
- [Phase 5: Pointers & Memory](#phase-5-pointers--memory)
- [Phase 6: Arrays & Strings](#phase-6-arrays--strings)
- [Phase 7: Structures & Unions](#phase-7-structures--unions)
- [Phase 8: Dynamic Memory](#phase-8-dynamic-memory)
- [Phase 9: File I/O & Preprocessor](#phase-9-file-io--preprocessor)
- [Phase 10: Advanced Topics](#phase-10-advanced-topics)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> C requires **no prior programming experience**. It is one of the most foundational languages in computing — operating systems, embedded systems, and performance-critical software are built with it. An understanding of how computers work (CPU, memory, storage) is helpful but not required.

- A computer (Windows, Mac, or Linux)
- A C compiler ([GCC](https://gcc.gnu.org/) or [Clang](https://clang.llvm.org/))
- A text editor or IDE ([VS Code](https://code.visualstudio.com/) with C/C++ extension recommended)
- Willingness to think close to the hardware

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write your first C program and understand the compilation process.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is C | Low-level, compiled language created in 1972. Powers operating systems, databases, embedded systems — the backbone of modern computing |
| 2 | Compiler Setup | Install GCC (Linux/Mac: `gcc`, Windows: MinGW or WSL) or Clang. Verify with `gcc --version` |
| 3 | Hello World | `#include <stdio.h>` + `int main() { printf("Hello, World!\n"); return 0; }` — every C program starts with `main()` |
| 4 | Compilation Process | Four stages: **Preprocessing** (`#include` expansion) → **Compilation** (C to assembly) → **Assembly** (assembly to object code) → **Linking** (combine object files into executable) |
| 5 | IDE Setup | VS Code with C/C++ extension, or use terminal: `gcc hello.c -o hello && ./hello` |
| 6 | Basic I/O | `printf("Name: %s\n", name)` for output. `scanf("%d", &age)` for input — note the `&` (address-of) operator |
| 7 | Comments | `//` for single-line (C99+). `/* */` for multi-line. Document your code from day one |
| 8 | Return Values | `main()` returns `0` for success, non-zero for failure. The OS reads this exit code |

> [!TIP]
> Compile with warnings enabled from the start — they catch bugs before they become disasters:
> ```c
> gcc -Wall -Wextra -std=c17 program.c -o program
> // -Wall     : enable all common warnings
> // -Wextra   : enable extra warnings
> // -std=c17  : use C17 standard
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install GCC or Clang and compile a program from the terminal
- [ ] Write a program that takes user input with `scanf` and prints with `printf`
- [ ] Explain the four stages of compilation

</details>

---

## Phase 2: Variables & Data Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Understand how C stores data in memory with explicit types.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Basic Types | `int` (whole numbers), `char` (single character), `float` (decimal, 4 bytes), `double` (decimal, 8 bytes) |
| 2 | `sizeof` Operator | `sizeof(int)` returns the size in bytes. Sizes are platform-dependent — never assume |
| 3 | Type Modifiers | `short` (smaller), `long` (larger), `unsigned` (non-negative only), `signed` (default). Combine: `unsigned long int` |
| 4 | Constants | `const int MAX = 100;` — compiler-enforced immutability. Cannot be changed after initialization |
| 5 | `#define` Macros | `#define PI 3.14159` — preprocessor text replacement. No type checking, no memory allocation |
| 6 | Type Casting | Implicit: `int` to `double` (safe). Explicit: `(int)3.7` truncates to `3`. Casting pointers is dangerous |
| 7 | Format Specifiers | `%d` (int), `%f` (float), `%c` (char), `%s` (string), `%p` (pointer), `%ld` (long), `%u` (unsigned) |
| 8 | Overflow & Limits | `INT_MAX`, `INT_MIN` from `<limits.h>`. Overflow wraps around silently — a common source of bugs |

> [!IMPORTANT]
> **C does not initialize variables for you.** Uninitialized variables contain garbage values — whatever was in memory before:
> ```c
> int x;          // DANGER: x contains garbage
> printf("%d", x); // Undefined behavior!
>
> int y = 0;      // SAFE: always initialize your variables
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables of each basic type and print them with correct format specifiers
- [ ] Use `sizeof` to print the size of each data type on your system
- [ ] Demonstrate the difference between `const` and `#define`

</details>

---

## Phase 3: Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make decisions and repeat actions in your programs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `else if` / `else` | Conditional branching: `if (age >= 18) { ... }` — parentheses required, braces highly recommended |
| 2 | `switch` Statement | Multi-way branching: `switch (choice) { case 1: ... break; }` — don't forget `break` or you get fall-through |
| 3 | `for` Loop | `for (int i = 0; i < n; i++)` — initialization, condition, increment. The workhorse of C loops |
| 4 | `while` Loop | `while (condition) { ... }` — check condition first, then execute. Use when iteration count is unknown |
| 5 | `do-while` Loop | `do { ... } while (condition);` — execute first, then check. Guarantees at least one execution |
| 6 | `break` & `continue` | `break` exits the loop entirely. `continue` skips to the next iteration |
| 7 | `goto` (and When to Avoid) | `goto label;` — unconditional jump. Legitimate use: error cleanup in deeply nested code. Avoid everywhere else |
| 8 | Nested Loops | Loops inside loops: matrix traversal, pattern printing. Time complexity multiplies with each nesting level |
| 9 | Ternary Operator | `result = (a > b) ? a : b;` — compact `if/else` for simple assignments |
| 10 | Comma Operator | `for (i = 0, j = 10; i < j; i++, j--)` — evaluate multiple expressions where one is expected |

> [!CAUTION]
> **Always use braces `{}` with `if/else` and loops**, even for single statements. Omitting them is a notorious source of bugs:
> ```c
> // DANGEROUS — only the first line is inside the if
> if (loggedIn)
>     printf("Welcome\n");
>     showDashboard();  // ALWAYS executes — not part of the if!
>
> // SAFE — braces make the scope explicit
> if (loggedIn) {
>     printf("Welcome\n");
>     showDashboard();
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a program using `if/else if/else` with user input
- [ ] Implement a menu system using `switch` with a `do-while` loop
- [ ] Use nested `for` loops to print a multiplication table

</details>

---

## Phase 4: Functions

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write reusable, modular code with functions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Declaration | `int add(int a, int b);` — declares the function signature (prototype) before use |
| 2 | Function Definition | `int add(int a, int b) { return a + b; }` — the actual implementation with a body |
| 3 | Parameters (Pass by Value) | C copies argument values into function parameters. Modifying parameters inside the function does not affect the original |
| 4 | Return Types | Functions return one value: `int`, `float`, `char`, pointer, or `void` (no return). Always match the declared type |
| 5 | Function Prototypes | Declare prototypes at the top of the file or in header files so functions can be called before their definition |
| 6 | Recursion | A function calling itself: `factorial(n) = n * factorial(n-1)`. Always define a base case to stop recursion |
| 7 | Scope & Lifetime | Local variables live on the stack and die when the function returns. Global variables live for the entire program |
| 8 | `static` Keyword | `static int count = 0;` inside a function — retains value between calls. On a function — limits visibility to the file |
| 9 | `inline` Functions | `inline int square(int x) { return x * x; }` — hint to the compiler to insert the function body at the call site for speed |

> [!TIP]
> Use **function prototypes** in header files to organize multi-file programs:
> ```c
> // math_utils.h — declarations
> #ifndef MATH_UTILS_H
> #define MATH_UTILS_H
> int add(int a, int b);
> int multiply(int a, int b);
> #endif
>
> // math_utils.c — definitions
> #include "math_utils.h"
> int add(int a, int b) { return a + b; }
> int multiply(int a, int b) { return a * b; }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write functions with prototypes, definitions, and multiple parameters
- [ ] Implement a recursive function (factorial or Fibonacci)
- [ ] Demonstrate how `static` preserves a variable's value between function calls

</details>

---

## Phase 5: Pointers & Memory

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Master pointers — the most powerful and most misunderstood feature of C.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Pointer Basics | `int *p = &x;` — `&` gets the address, `*` dereferences (reads the value at that address) |
| 2 | Pointer Arithmetic | `p + 1` moves to the next element (advances by `sizeof(*p)` bytes). Foundation of array traversal |
| 3 | Pointers and Arrays | Array name is a pointer to the first element: `arr[i]` is the same as `*(arr + i)` |
| 4 | Pointers to Functions | `int (*fptr)(int, int) = &add;` — store functions in variables, pass them as arguments, build callbacks |
| 5 | NULL Pointer | `int *p = NULL;` — points to nothing. Always check for NULL before dereferencing: `if (p != NULL)` |
| 6 | Void Pointer | `void *p` — generic pointer that can hold any type's address. Must cast before dereferencing: `*(int *)p` |
| 7 | Double Pointers | `int **pp = &p;` — pointer to a pointer. Used for dynamic 2D arrays and modifying pointers inside functions |
| 8 | Pass by Reference | C simulates pass-by-reference using pointers: `void swap(int *a, int *b)` — modifies the original values |
| 9 | `const` with Pointers | `const int *p` (data is read-only), `int *const p` (pointer is read-only), `const int *const p` (both read-only) |

> [!CAUTION]
> **Dereferencing a NULL or uninitialized pointer is undefined behavior** — it can crash your program (segfault) or corrupt memory silently:
> ```c
> int *p;          // Uninitialized — points to random memory
> *p = 42;         // SEGFAULT or silent corruption!
>
> int *q = NULL;
> *q = 42;         // SEGFAULT — always check for NULL first
>
> int x = 10;
> int *r = &x;     // SAFE — r points to a valid variable
> *r = 42;         // x is now 42
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use pointers to swap two variables inside a function
- [ ] Traverse an array using pointer arithmetic instead of indexing
- [ ] Create a function pointer and use it to call different functions

</details>

---

## Phase 6: Arrays & Strings

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Work with collections of data and C-style strings.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | 1D Arrays | `int arr[5] = {1, 2, 3, 4, 5};` — fixed-size, contiguous memory. Index starts at 0, no bounds checking |
| 2 | 2D Arrays | `int matrix[3][4];` — rows and columns. Access: `matrix[row][col]`. Stored in row-major order in memory |
| 3 | String Basics | Strings are `char` arrays ending with `'\0'` (null terminator): `char name[] = "Alice";` is `{'A','l','i','c','e','\0'}` |
| 4 | String Functions | `strlen()` (length), `strcpy()` (copy), `strcat()` (concatenate), `strcmp()` (compare) — all from `<string.h>` |
| 5 | Character Arrays vs Pointers | `char s[] = "hello"` (mutable, on stack) vs `char *s = "hello"` (pointer to read-only string literal) |
| 6 | Array-Pointer Relationship | Array names decay to pointers when passed to functions. `sizeof(arr)` gives array size, `sizeof(ptr)` gives pointer size |
| 7 | Buffer Overflow Awareness | Writing past array bounds corrupts memory: `char buf[5]; strcpy(buf, "toolong");` — use `strncpy()` with size limits |
| 8 | Multi-dimensional Arrays | `int cube[2][3][4];` — arrays of arrays. Pass to functions with all dimensions except the first specified |

> [!IMPORTANT]
> **C does not check array bounds.** Writing past the end of an array is one of the most dangerous bugs in C — it causes buffer overflows, security vulnerabilities, and crashes:
> ```c
> char buffer[10];
> // DANGEROUS — "Hello, World!" is 13 chars + '\0' = 14 bytes
> strcpy(buffer, "Hello, World!");  // Buffer overflow!
>
> // SAFE — limit the copy to buffer size
> strncpy(buffer, "Hello, World!", sizeof(buffer) - 1);
> buffer[sizeof(buffer) - 1] = '\0';  // Ensure null-termination
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create and traverse 1D and 2D arrays with loops
- [ ] Use `strlen`, `strcpy`, `strcat`, and `strcmp` on C strings
- [ ] Explain why `strncpy` is safer than `strcpy`

</details>

---

## Phase 7: Structures & Unions

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Group related data together into custom types.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Struct Definition | `struct Point { int x; int y; };` — group related variables under one name. Access with `.` operator |
| 2 | `typedef` | `typedef struct { int x; int y; } Point;` — create a type alias so you can write `Point p;` instead of `struct Point p;` |
| 3 | Nested Structs | Structs inside structs: `struct Address` inside `struct Person` — model complex real-world entities |
| 4 | Unions | `union Data { int i; float f; char c; };` — all members share the same memory. Only one is valid at a time. Saves space |
| 5 | Bit Fields | `struct Flags { unsigned int active : 1; unsigned int role : 3; };` — pack data into individual bits for memory efficiency |
| 6 | Struct Pointers | `struct Point *p = &pt; p->x = 10;` — the `->` operator accesses members through a pointer |
| 7 | Structs and Functions | Pass structs by value (copies entire struct) or by pointer (efficient, allows modification). Prefer pointer for large structs |
| 8 | Linked List Introduction | `struct Node { int data; struct Node *next; };` — self-referential struct. Foundation of dynamic data structures |
| 9 | Enum | `enum Color { RED, GREEN, BLUE };` — named integer constants. More readable than `#define` for related values |

> [!TIP]
> Use `typedef` with structs to write cleaner code, and prefer passing structs by pointer for efficiency:
> ```c
> typedef struct {
>     char name[50];
>     int age;
>     float gpa;
> } Student;
>
> void printStudent(const Student *s) {
>     printf("Name: %s, Age: %d, GPA: %.2f\n",
>            s->name, s->age, s->gpa);
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Define a struct with `typedef` and access members with `.` and `->`
- [ ] Explain the difference between a struct and a union
- [ ] Implement a basic singly linked list with insert and print operations

</details>

---

## Phase 8: Dynamic Memory

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Allocate and manage memory at runtime — the heart of systems programming.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `malloc` | `int *p = malloc(n * sizeof(int));` — allocate `n` integers on the heap. Returns `NULL` on failure. Always check |
| 2 | `calloc` | `int *p = calloc(n, sizeof(int));` — like `malloc` but initializes all bytes to zero. Safer default |
| 3 | `realloc` | `p = realloc(p, new_size);` — resize previously allocated memory. May move the block. Assign to a temp pointer first |
| 4 | `free` | `free(p); p = NULL;` — release heap memory. Every `malloc`/`calloc` must have a matching `free`. Set pointer to NULL after |
| 5 | Memory Leaks | Allocated memory that is never freed. Grows over time, eventually exhausts system memory. Use tools to detect |
| 6 | Dangling Pointers | Pointer to memory that has been freed: `free(p); *p = 10;` — undefined behavior. Set to `NULL` after `free` |
| 7 | Memory Debugging (Valgrind) | `valgrind ./program` — detects leaks, invalid reads/writes, use-after-free. Essential tool for C developers |
| 8 | Heap vs Stack | Stack: automatic, fast, limited size, function-scoped. Heap: manual, slower, large, persists until freed |
| 9 | Dynamic Arrays | Grow arrays at runtime: allocate with `malloc`, resize with `realloc` when capacity is reached. Implement a vector |

> [!CAUTION]
> **Every `malloc` must have a matching `free`.** Memory leaks are silent killers — your program works fine until it runs out of memory:
> ```c
> // WRONG — memory leak
> int *data = malloc(100 * sizeof(int));
> data = malloc(200 * sizeof(int));  // Lost pointer to first allocation!
>
> // CORRECT — free before reassigning
> int *data = malloc(100 * sizeof(int));
> free(data);
> data = malloc(200 * sizeof(int));
> // ... use data ...
> free(data);
> data = NULL;
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Allocate, use, and free memory with `malloc` and `free`
- [ ] Use `realloc` to implement a dynamically growing array
- [ ] Run Valgrind on a program and fix all memory leaks it reports

</details>

---

## Phase 9: File I/O & Preprocessor

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-8 Hours](https://img.shields.io/badge/Time-7--8%20Hours-yellow)

> Read and write files, and master the C preprocessor.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `fopen` / `fclose` | `FILE *f = fopen("data.txt", "r");` — modes: `"r"` (read), `"w"` (write), `"a"` (append), `"rb"` (binary read) |
| 2 | `fprintf` / `fscanf` | `fprintf(f, "Score: %d\n", score);` — formatted file I/O. Same format specifiers as `printf`/`scanf` |
| 3 | `fread` / `fwrite` | `fread(buffer, size, count, f);` — binary file I/O. Read/write raw bytes. Use for structs, images, custom formats |
| 4 | Binary Files | Open with `"rb"`/`"wb"`. Store data in compact binary format. Not human-readable but efficient |
| 5 | `#include` | `#include <stdio.h>` (system headers) vs `#include "myheader.h"` (project headers). Pastes file contents |
| 6 | `#define` & Macros | `#define MAX(a,b) ((a) > (b) ? (a) : (b))` — text substitution. Wrap parameters in parentheses to avoid bugs |
| 7 | `#ifdef` / `#ifndef` | Conditional compilation: `#ifdef DEBUG printf("debug info"); #endif`. Include guards prevent double-inclusion |
| 8 | Header Files | `.h` files contain declarations, `.c` files contain definitions. Use include guards: `#ifndef HEADER_H` / `#define HEADER_H` / `#endif` |
| 9 | `#pragma` and Others | `#pragma once` (alternative include guard), `#error` (stop compilation), `#warning`, `__FILE__`, `__LINE__` |

> [!TIP]
> **Always check if `fopen` succeeded** — it returns `NULL` on failure:
> ```c
> FILE *f = fopen("config.txt", "r");
> if (f == NULL) {
>     perror("Error opening file");  // prints: "Error opening file: No such file..."
>     return 1;
> }
> // ... read from f ...
> fclose(f);  // Always close files when done
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read and write text files with `fprintf` and `fscanf`
- [ ] Write a struct to a binary file with `fwrite` and read it back with `fread`
- [ ] Create a multi-file project with header files and include guards

</details>

---

## Phase 10: Advanced Topics

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-12 Hours](https://img.shields.io/badge/Time-10--12%20Hours-yellow)

> Build data structures, automate builds, and debug like a professional.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Linked Lists | Singly and doubly linked lists: insert, delete, search, reverse. Dynamic size, O(1) insert at head |
| 2 | Stacks & Queues | Stack (LIFO): push/pop with array or linked list. Queue (FIFO): enqueue/dequeue. Foundation of many algorithms |
| 3 | Sorting Algorithms | Bubble sort, selection sort, insertion sort, merge sort, quicksort. Compare time complexity: O(n^2) vs O(n log n) |
| 4 | Makefile | `make` automates compilation: targets, dependencies, rules. `gcc -c file.c` compiles, `gcc *.o -o app` links |
| 5 | Debugging with GDB | `gcc -g program.c` + `gdb ./program` — set breakpoints, step through code, inspect variables, find segfaults |
| 6 | Static Libraries | `ar rcs libmath.a math.o` — archive object files. Link with `gcc main.c -L. -lmath`. Compiled into the executable |
| 7 | Shared Libraries | `gcc -shared -o libmath.so math.o` — loaded at runtime. Smaller executables, can update library without recompiling |
| 8 | Best Practices | Consistent naming, defensive programming, always compile with `-Wall -Wextra`, write documentation, keep functions small |
| 9 | Command-Line Arguments | `int main(int argc, char *argv[])` — `argc` is argument count, `argv[0]` is program name, `argv[1]` is first argument |

> [!TIP]
> Learn the basics of **GDB** — it will save you hours of debugging:
> ```bash
> gcc -g program.c -o program    # Compile with debug symbols
> gdb ./program                  # Start GDB
> (gdb) break main               # Set breakpoint at main
> (gdb) run                      # Run the program
> (gdb) next                     # Step to next line
> (gdb) print variable           # Inspect a variable's value
> (gdb) backtrace                # Show call stack (great for segfaults)
> (gdb) quit                     # Exit GDB
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Implement a linked list with insert, delete, and print operations
- [ ] Write a Makefile that compiles a multi-file project
- [ ] Debug a segfault using GDB breakpoints and backtrace

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Uninitialized variables | Contains garbage values — behavior is undefined and unpredictable | Always initialize: `int x = 0;`, `char *p = NULL;` |
| 2 | Buffer overflow | Writing past array bounds corrupts memory, causes crashes, and creates security vulnerabilities | Use `strncpy` instead of `strcpy`, always check array bounds |
| 3 | Missing `free()` | Memory leaks — allocated heap memory is never released, program consumes more and more RAM | Every `malloc`/`calloc` must have a matching `free`. Use Valgrind to verify |
| 4 | Dereferencing NULL/dangling pointers | Segfault or silent memory corruption — undefined behavior | Always check `if (ptr != NULL)` before dereferencing. Set to `NULL` after `free` |
| 5 | Forgetting `break` in `switch` | Fall-through executes all subsequent cases — usually not what you want | Add `break;` at the end of every `case` unless intentional fall-through |
| 6 | Using `=` instead of `==` | `if (x = 5)` assigns 5 to x (always true) instead of comparing | Use `==` for comparison: `if (x == 5)`. Some use `if (5 == x)` to catch this |
| 7 | Wrong format specifier in `printf`/`scanf` | `%d` for a `float` or `%f` for an `int` causes undefined behavior and wrong output | Match specifiers to types: `%d` (int), `%f` (float/double), `%s` (string), `%c` (char) |
| 8 | Returning address of local variable | Local variables are destroyed when the function returns — the pointer becomes dangling | Allocate on the heap with `malloc` or pass a buffer as a parameter |
| 9 | Forgetting `&` in `scanf` | `scanf("%d", x)` passes the value, not the address — undefined behavior, likely crash | Use address-of operator: `scanf("%d", &x)`. Exception: arrays decay to pointers automatically |
| 10 | Not checking `malloc` return value | `malloc` returns `NULL` when memory allocation fails — dereferencing `NULL` is a segfault | Always check: `if (ptr == NULL) { perror("malloc"); exit(1); }` |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between `=` and `==` in C?**
   - `=` is the assignment operator: `x = 5` stores 5 in `x`. `==` is the equality comparison operator: `x == 5` returns 1 (true) if `x` is 5, 0 (false) otherwise. Using `=` inside an `if` condition is a common bug.

2. **What is a pointer?**
   - A variable that stores the memory address of another variable. Declared with `*`: `int *p = &x;`. The `&` operator gets the address, the `*` operator dereferences (reads/writes the value at that address).

3. **What is the difference between `char s[]` and `char *s` when initialized with a string?**
   - `char s[] = "hello"` creates a mutable array on the stack containing a copy of the string. `char *s = "hello"` creates a pointer to a string literal stored in read-only memory — modifying it is undefined behavior.

4. **What does `sizeof` return?**
   - The size in bytes of a type or variable. `sizeof(int)` is typically 4 bytes. For arrays, `sizeof(arr)` gives total bytes; `sizeof(arr) / sizeof(arr[0])` gives the number of elements. For pointers, it gives the pointer size (4 or 8 bytes), not the data size.

5. **What is the null terminator `\0`?**
   - A character with value 0 that marks the end of a C string. All string functions (`strlen`, `printf %s`, etc.) rely on it. Forgetting the null terminator causes functions to read past the string into random memory.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain the difference between stack and heap memory.**
   - Stack: automatic allocation/deallocation, fast, limited size (typically 1-8 MB), stores local variables and function call frames. Heap: manual allocation (`malloc`/`free`), slower, much larger, persists until explicitly freed. Stack overflows cause crashes; heap leaks waste memory.

2. **What is a memory leak and how do you detect one?**
   - Memory allocated with `malloc`/`calloc` that is never `free`d. The program loses the pointer to the memory, so it can never be reclaimed. Detected with Valgrind: `valgrind --leak-check=full ./program`. Prevented by pairing every allocation with a free.

3. **What is the difference between `struct` and `union`?**
   - A `struct` allocates memory for all members — total size is the sum (plus padding). A `union` shares memory among all members — total size equals the largest member. In a union, only one member is valid at a time. Use unions to save memory when fields are mutually exclusive.

4. **How does pointer arithmetic work?**
   - Adding `n` to a pointer advances it by `n * sizeof(*ptr)` bytes. `int *p = arr; p + 3` points to `arr[3]`, which is 12 bytes ahead (if `int` is 4 bytes). Subtracting two pointers gives the number of elements between them. Only valid within the same array.

5. **What are include guards and why are they necessary?**
   - `#ifndef HEADER_H / #define HEADER_H / #endif` prevents a header from being included multiple times, which would cause duplicate definition errors. Without them, including `a.h` and `b.h` where both include `common.h` would define `common.h` contents twice.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What is undefined behavior in C? Give examples.**
   - Code whose behavior is not specified by the C standard — the compiler can do anything, including producing seemingly correct results. Examples: dereferencing NULL, signed integer overflow, accessing freed memory, reading uninitialized variables, buffer overflows. The compiler may optimize assuming UB never occurs.

2. **Explain `volatile` and when to use it.**
   - `volatile` tells the compiler that a variable's value may change at any time (by hardware, an interrupt handler, or another thread) and must not be cached in a register. Used in embedded systems for memory-mapped I/O registers and signal handlers. Does not provide atomicity or thread safety.

3. **What is the difference between `static` at file scope vs function scope?**
   - File scope `static`: limits the function or variable's visibility to the current translation unit (file) — internal linkage. Function scope `static`: the variable retains its value between function calls — it lives for the entire program but is only accessible inside the function.

4. **How do you handle memory management in a large C project?**
   - Establish clear ownership rules: whoever allocates is responsible for freeing. Use wrapper functions around `malloc`/`free` for centralized tracking. Use Valgrind and AddressSanitizer (`-fsanitize=address`) in CI. Consider arena/pool allocators for performance-critical paths. Document allocation lifetimes.

5. **Explain function pointers and their use cases.**
   - Variables that store the address of a function: `int (*cmp)(const void*, const void*)`. Used for callbacks (`qsort`), plugin systems, state machines, and implementing polymorphism in C. The standard library's `qsort` and `bsearch` use function pointers for custom comparison logic.

</details>

---

## Practice Projects

### Project 1: Student Grade Manager
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** CLI program that stores student names and grades in arrays, calculates averages, finds highest/lowest scores, and displays a formatted report.

**Skills practiced:** Variables, arrays, loops, conditionals, `printf`/`scanf` formatting.

---

### Project 2: Calculator with Function Pointers
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A calculator that maps operations (+, -, *, /) to functions via function pointers. Supports chained operations and handles division by zero.

**Skills practiced:** Functions, pointers, function pointers, error handling, `switch` statements.

---

### Project 3: Contact Book with Structs
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A contact management system using structs and arrays. Add, search, edit, delete contacts. Save/load contacts to/from a file.

**Skills practiced:** Structs, arrays, strings, string functions, file I/O, `typedef`.

---

### Project 4: Dynamic Memory Allocator
![Phase 8](https://img.shields.io/badge/After-Phase%208-orange)

**What you'll build:** Implement a dynamic array (vector) that grows automatically. Supports push, pop, insert at index, and automatic resizing with `realloc`.

**Skills practiced:** `malloc`, `calloc`, `realloc`, `free`, pointers, memory management, Valgrind.

---

### Project 5: Mini Database with Makefile
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A multi-file record management system with a linked list backend, binary file persistence, command-line argument parsing, Makefile build system, and GDB-debuggable code.

**Skills practiced:** Everything from all phases — data structures, dynamic memory, file I/O, multi-file compilation, debugging.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [cppreference.com (C)](https://en.cppreference.com/w/c) | The most accurate and detailed C reference — every function, header, and standard feature |
| [The C Programming Language (K&R)](https://en.wikipedia.org/wiki/The_C_Programming_Language) | The original C book by Kernighan and Ritchie. Still the gold standard for learning C |
| [C Standard Library Reference](https://www.cplusplus.com/reference/clibrary/) | Quick lookup for all standard library functions with examples |
| [GNU C Manual](https://www.gnu.org/software/gnu-c-manual/) | Free manual covering GCC-specific C features and extensions |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [CS50 — Harvard's Intro to CS](https://cs50.harvard.edu/x/) | World-class CS course that starts with C. Lectures, problem sets, and grading |
| [Learn-C.org](https://www.learn-c.org/) | Interactive browser-based C tutorials with exercises |
| [Exercism — C Track](https://exercism.org/tracks/c) | 80+ exercises with free mentor feedback and community solutions |
| [HackerRank — C](https://www.hackerrank.com/domains/c) | Structured C challenges from easy to hard with instant verification |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [CS50 — David Malan](https://www.youtube.com/@cs50) | Best CS lectures on the internet. Weeks 1-5 cover C in depth |
| [Jacob Sorber](https://www.youtube.com/@JacobSorber) | C and systems programming explained clearly with real examples |
| [CodeVault](https://www.youtube.com/@CodeVault) | Deep dives into pointers, threads, processes, and Linux system calls in C |
| [Neso Academy — C Programming](https://www.youtube.com/@nesaborad) | Structured C course with clear explanations for beginners |
| [freeCodeCamp — C Full Course](https://www.youtube.com/@freecodecamp) | Complete 4+ hour C course covering basics to advanced topics |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — C](https://roadmap.sh/c) | Interactive learning path for C with progress tracking |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [C/C++ Extension (Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) | Essential — IntelliSense, debugging, code navigation for VS Code |
| [GCC](https://gcc.gnu.org/) | The standard C compiler on Linux/Mac. Excellent warnings and optimizations |
| [Clang](https://clang.llvm.org/) | Modern C compiler with the best error messages. Drop-in GCC replacement |
| [Valgrind](https://valgrind.org/) | Memory debugger — finds leaks, invalid reads/writes, use-after-free |
| [GDB](https://www.gnu.org/software/gdb/) | The GNU Debugger — breakpoints, step execution, variable inspection |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [C Reference Card (ANSI)](https://users.ece.utexas.edu/~adnan/c-refcard.pdf) | Compact PDF with all C syntax, operators, and standard library functions |
| [GDB Quick Reference](https://darkdust.net/files/GDB%20Cheat%20Sheet.pdf) | PDF with essential GDB commands for debugging |

---

[Back to Main Syllabus](../README.md)

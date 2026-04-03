# Java Syllabus

A complete, structured learning path for Java — from your first program to building production APIs with Spring Boot, databases, multithreading, and testing.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Java: 17+](https://img.shields.io/badge/Java-17%2B-ED8B00)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Variables & Data Types](#phase-2-variables--data-types)
- [Phase 3: Control Flow](#phase-3-control-flow)
- [Phase 4: Object-Oriented Programming](#phase-4-object-oriented-programming)
- [Phase 5: Collections Framework](#phase-5-collections-framework)
- [Phase 6: Exception Handling & I/O](#phase-6-exception-handling--io)
- [Phase 7: Generics & Streams](#phase-7-generics--streams)
- [Phase 8: Multithreading](#phase-8-multithreading)
- [Phase 9: Spring Boot Basics](#phase-9-spring-boot-basics)
- [Phase 10: Testing & Build Tools](#phase-10-testing--build-tools)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Java is a **statically typed, object-oriented language** that runs on the JVM. No prior Java experience is needed, but basic programming concepts (variables, loops, functions) will help you move faster.

- Basic understanding of programming concepts (any language)
- Command line / terminal basics
- A text editor or IDE installed (IntelliJ IDEA recommended)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Java is and set up your development environment.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Java | A statically typed, object-oriented language that compiles to bytecode and runs on the JVM. "Write once, run anywhere" |
| 2 | JVM, JRE, and JDK | JVM executes bytecode, JRE = JVM + libraries, JDK = JRE + compiler + dev tools. You install the JDK to develop |
| 3 | Installation | Install JDK 17+ (LTS). Use `sdkman` to manage multiple Java versions. Verify with `java --version` and `javac --version` |
| 4 | IDE Setup | IntelliJ IDEA (recommended) or VS Code with Extension Pack for Java. Code completion, debugging, refactoring built-in |
| 5 | Hello World | `public class Main { public static void main(String[] args) { System.out.println("Hello, World!"); } }` |
| 6 | Packages | Organize code into packages: `package com.example.app;`. Convention: reverse domain name. Maps to folder structure |
| 7 | Compilation | `javac Main.java` produces `Main.class` (bytecode). `java Main` runs it on the JVM. IDEs handle this automatically |

> [!TIP]
> Use `sdkman` to install and switch between Java versions — it's the `nvm` of the Java world:
> ```bash
> # Install sdkman
> curl -s "https://get.sdkman.io" | bash
>
> # Install Java 21 LTS
> sdk install java 21.0.2-tem
>
> # Switch versions
> sdk use java 17.0.10-tem
> ```
> IntelliJ IDEA Community Edition is free and is the most popular Java IDE. VS Code works well too with the Java Extension Pack.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install JDK 17+ and verify with `java --version`
- [ ] Set up IntelliJ IDEA or VS Code with Java extensions
- [ ] Write, compile, and run a Hello World program

</details>

---

## Phase 2: Variables & Data Types

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn Java's type system — primitives, wrappers, strings, and type safety.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Primitive Types | 8 primitives: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean`. Stored on the stack, fast |
| 2 | Wrapper Classes | `Integer`, `Double`, `Boolean`, etc. Object versions of primitives. Needed for collections. Autoboxing/unboxing |
| 3 | String | Immutable sequence of characters. `String` pool for memory efficiency. Common methods: `length()`, `substring()`, `equals()`, `contains()` |
| 4 | StringBuilder | Mutable string manipulation. Use when concatenating in loops: `new StringBuilder().append("hello").append(" world").toString()` |
| 5 | Operators | Arithmetic (`+`, `-`, `*`, `/`, `%`), comparison (`==`, `!=`, `<`, `>`), logical (`&&`, `||`, `!`), bitwise (`&`, `|`, `^`) |
| 6 | `var` (Local Type Inference) | Java 10+: `var name = "Java";` — compiler infers the type. Only for local variables, not fields or parameters |
| 7 | `final` Keyword | `final int MAX = 100;` — constant, cannot be reassigned. Like `const` in JavaScript. Convention: UPPER_SNAKE_CASE |
| 8 | Type Casting | Widening (automatic): `int` to `long`. Narrowing (explicit): `double d = 9.7; int i = (int) d;` — truncates to 9 |

> [!WARNING]
> **Never compare strings with `==`.** Use `.equals()` instead. `==` compares object references (memory addresses), not the actual content:
> ```java
> String a = new String("hello");
> String b = new String("hello");
>
> System.out.println(a == b);      // false — different objects!
> System.out.println(a.equals(b)); // true  — same content
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Declare variables using all 8 primitive types
- [ ] Use wrapper classes and understand autoboxing
- [ ] Compare strings correctly with `.equals()` instead of `==`

</details>

---

## Phase 3: Control Flow

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Control how your program makes decisions and repeats actions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `if` / `else if` / `else` | Conditional branching: `if (age >= 18) { ... } else { ... }`. Curly braces always recommended |
| 2 | Enhanced `switch` | Java 14+: `switch` expressions with arrow syntax — no fall-through, can return values: `var result = switch(day) { case MONDAY -> "Start"; ... };` |
| 3 | `for` Loop | Classic: `for (int i = 0; i < 10; i++) { ... }`. Most common loop for counted iteration |
| 4 | `while` / `do-while` | `while`: checks condition first. `do-while`: runs at least once, then checks. Use when iteration count is unknown |
| 5 | Enhanced `for` (for-each) | `for (String item : list) { ... }` — iterate over arrays and collections without an index |
| 6 | `break` / `continue` | `break`: exit the loop entirely. `continue`: skip to the next iteration. Use with labels for nested loops |
| 7 | Ternary Operator | `String status = (age >= 18) ? "adult" : "minor";` — inline conditional, replaces simple if/else |

> [!TIP]
> Use enhanced `switch` expressions (Java 14+) instead of traditional switch statements. No `break` needed, no fall-through bugs, and they can return values:
> ```java
> String message = switch (statusCode) {
>     case 200 -> "OK";
>     case 404 -> "Not Found";
>     case 500 -> "Internal Server Error";
>     default -> "Unknown status: " + statusCode;
> };
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write programs using `if/else`, `switch`, and all loop types
- [ ] Use enhanced `switch` expressions with arrow syntax
- [ ] Iterate over arrays and collections with `for-each`

</details>

---

## Phase 4: Object-Oriented Programming

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master the core of Java — classes, objects, inheritance, and polymorphism.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Classes & Objects | Blueprint (class) vs instance (object). Fields store state, methods define behavior. `new` creates objects |
| 2 | Constructors | Initialize objects: `public User(String name) { this.name = name; }`. Default, parameterized, constructor chaining with `this()` |
| 3 | Access Modifiers | `public` (everywhere), `protected` (package + subclasses), default/package-private (same package), `private` (same class only) |
| 4 | Inheritance | `class Dog extends Animal { }` — reuse code from parent class. `super()` calls parent constructor. Java has single inheritance |
| 5 | Interfaces | `interface Drawable { void draw(); }` — define contracts. A class can implement multiple interfaces. Default methods (Java 8+) |
| 6 | Abstract Classes | `abstract class Shape { abstract double area(); }` — cannot be instantiated, can have both abstract and concrete methods |
| 7 | Polymorphism | One interface, many implementations. Method overriding (`@Override`) and method overloading (same name, different parameters) |
| 8 | Records (Java 16+) | `record Point(int x, int y) {}` — immutable data carriers. Auto-generates constructor, getters, `equals()`, `hashCode()`, `toString()` |
| 9 | Sealed Classes (Java 17+) | `sealed class Shape permits Circle, Square {}` — restrict which classes can extend a class. Exhaustive `switch` with pattern matching |

> [!IMPORTANT]
> **Prefer composition over inheritance.** Inheritance creates tight coupling. Use interfaces and composition for flexible designs:
> ```java
> // AVOID: Deep inheritance hierarchies
> class Animal { }
> class Dog extends Animal { }
> class GuideDog extends Dog { }  // Fragile!
>
> // PREFER: Composition with interfaces
> interface Walkable { void walk(); }
> interface Trainable { void train(); }
>
> record Dog(String name) implements Walkable, Trainable {
>     public void walk() { /* ... */ }
>     public void train() { /* ... */ }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create classes with constructors, fields, and methods
- [ ] Implement inheritance with `extends` and interfaces with `implements`
- [ ] Use records for immutable data classes and sealed classes for restricted hierarchies

</details>

---

## Phase 5: Collections Framework

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Store and manipulate groups of objects with Java's powerful collections library.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | ArrayList | Dynamic array: `List<String> names = new ArrayList<>()`. `.add()`, `.get()`, `.remove()`, `.size()`. Most-used collection |
| 2 | LinkedList | Doubly-linked list. Fast insertion/removal at ends, slow random access. Implements both `List` and `Deque` interfaces |
| 3 | HashMap | Key-value pairs: `Map<String, Integer> ages = new HashMap<>()`. `.put()`, `.get()`, `.containsKey()`. O(1) average lookup |
| 4 | HashSet | Unique elements, no duplicates: `Set<String> tags = new HashSet<>()`. `.add()`, `.contains()`. Backed by a HashMap internally |
| 5 | TreeMap | Sorted key-value pairs. Keys are in natural order (or custom `Comparator`). O(log n) operations. Implements `NavigableMap` |
| 6 | Queue & Deque | `Queue<Task> queue = new LinkedList<>()`. FIFO: `.offer()`, `.poll()`, `.peek()`. `ArrayDeque` for stack/queue operations |
| 7 | Iterator | `Iterator<String> it = list.iterator(); while (it.hasNext()) { it.next(); }` — safe removal during iteration with `it.remove()` |
| 8 | Comparable & Comparator | `Comparable<T>`: natural ordering (`compareTo`). `Comparator<T>`: custom ordering. `Comparator.comparing(User::getName)` |

> [!TIP]
> Use `List.of()`, `Map.of()`, and `Set.of()` (Java 9+) to create immutable collections. Use `List.copyOf()` to create an immutable copy of a mutable collection:
> ```java
> // Immutable collections — cannot add, remove, or modify
> var names = List.of("Alice", "Bob", "Charlie");
> var scores = Map.of("Alice", 95, "Bob", 87);
> var tags = Set.of("java", "spring", "backend");
>
> // Mutable when you need to modify
> var mutableNames = new ArrayList<>(List.of("Alice", "Bob"));
> mutableNames.add("Charlie"); // OK
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `ArrayList`, `HashMap`, and `HashSet` for common data operations
- [ ] Sort collections using `Comparable` and `Comparator`
- [ ] Choose the right collection for each use case (List vs Set vs Map vs Queue)

</details>

---

## Phase 6: Exception Handling & I/O

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Handle errors gracefully and work with files and user input.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `try` / `catch` / `finally` | Catch exceptions: `try { riskyCode(); } catch (IOException e) { handle(); } finally { cleanup(); }` |
| 2 | Checked vs Unchecked | Checked (`IOException`): must handle or declare with `throws`. Unchecked (`NullPointerException`): runtime errors, not forced to catch |
| 3 | Custom Exceptions | `class UserNotFoundException extends RuntimeException { }` — create domain-specific exceptions with meaningful messages |
| 4 | Try-with-Resources | `try (var reader = new BufferedReader(...)) { }` — auto-closes resources. Implements `AutoCloseable`. No more `finally` blocks for cleanup |
| 5 | `java.nio` File API | `Files.readString(Path.of("file.txt"))`, `Files.write()`, `Files.list()`, `Files.walk()` — modern file operations (Java 11+) |
| 6 | Scanner | `Scanner scanner = new Scanner(System.in)` — read user input. `.nextLine()`, `.nextInt()`, `.hasNext()` for console programs |
| 7 | Serialization | Convert objects to bytes (`Serializable`) or JSON (Jackson/Gson). JSON is the standard for APIs and config files |

> [!WARNING]
> **Never catch `Exception` or `Throwable` generically.** Catch specific exceptions so you know exactly what went wrong and can handle each case properly:
> ```java
> // WRONG — catches everything, hides bugs
> try {
>     processFile(path);
> } catch (Exception e) {
>     e.printStackTrace(); // Which exception? Who knows!
> }
>
> // CORRECT — specific handling for each case
> try {
>     processFile(path);
> } catch (FileNotFoundException e) {
>     System.err.println("File not found: " + path);
> } catch (IOException e) {
>     System.err.println("Error reading file: " + e.getMessage());
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Handle exceptions with `try/catch` and create custom exception classes
- [ ] Use try-with-resources for file and stream operations
- [ ] Read and write files using `java.nio.file.Files`

</details>

---

## Phase 7: Generics & Streams

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write type-safe reusable code and process data with functional-style operations.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Generics Basics | `class Box<T> { T value; }` — type parameters for classes and methods. Compile-time type safety without casting |
| 2 | Bounded Types | `<T extends Comparable<T>>` — restrict generic types. Upper bounds (`extends`), multiple bounds (`T extends A & B`) |
| 3 | Wildcards | `?` unknown type. `? extends Number` (read), `? super Integer` (write). PECS: Producer Extends, Consumer Super |
| 4 | Lambda Expressions | `(a, b) -> a + b` — anonymous functions. Replace verbose anonymous classes. Used with functional interfaces |
| 5 | Functional Interfaces | `Predicate<T>`, `Function<T,R>`, `Consumer<T>`, `Supplier<T>` — single abstract method interfaces. `@FunctionalInterface` annotation |
| 6 | Stream API | `list.stream().filter(...).map(...).collect(...)` — declarative data processing pipelines. Lazy evaluation, no mutation |
| 7 | Stream Operations | `filter()`, `map()`, `flatMap()`, `reduce()`, `collect()`, `forEach()`, `sorted()`, `distinct()`, `limit()`, `count()` |
| 8 | Optional | `Optional<User> user = findById(id)`. `.orElse()`, `.orElseThrow()`, `.map()`, `.ifPresent()` — eliminate null pointer exceptions |

> [!TIP]
> Combine streams with lambdas for clean, declarative data processing — Java's answer to functional programming:
> ```java
> List<String> activeUserEmails = users.stream()
>     .filter(user -> user.isActive())
>     .filter(user -> user.getAge() >= 18)
>     .map(User::getEmail)
>     .sorted()
>     .collect(Collectors.toList());
>
> // Optional — never return null
> Optional<User> user = repository.findById(id);
> String name = user.map(User::getName)
>     .orElse("Unknown");
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create generic classes and methods with bounded type parameters
- [ ] Process collections using the Stream API with `filter`, `map`, and `reduce`
- [ ] Use `Optional` instead of `null` to represent absent values

</details>

---

## Phase 8: Multithreading

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Run tasks concurrently — from basic threads to virtual threads.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Thread Basics | `new Thread(() -> doWork()).start()` — create and run threads. Thread lifecycle: NEW, RUNNABLE, BLOCKED, WAITING, TERMINATED |
| 2 | Runnable & Callable | `Runnable`: no return value. `Callable<T>`: returns a result via `Future<T>`. Prefer these over extending `Thread` |
| 3 | `synchronized` | `synchronized(lock) { ... }` — prevent race conditions. Synchronized methods and blocks. Only one thread enters at a time |
| 4 | ExecutorService | `Executors.newFixedThreadPool(4)` — manage a pool of reusable threads. `.submit()`, `.invokeAll()`, `.shutdown()` |
| 5 | CompletableFuture | `CompletableFuture.supplyAsync(() -> fetchData()).thenApply(data -> process(data))` — async pipelines with chaining |
| 6 | Concurrent Collections | `ConcurrentHashMap`, `CopyOnWriteArrayList`, `BlockingQueue` — thread-safe collections without external synchronization |
| 7 | Virtual Threads (Java 21+) | `Thread.ofVirtual().start(() -> doWork())` — lightweight threads managed by the JVM. Millions of threads, no thread pool tuning |

> [!CAUTION]
> **Never use `synchronized` on a public field or `this`.** Use a private lock object to prevent external code from interfering with your synchronization:
> ```java
> // WRONG — external code can lock on your object
> public synchronized void transfer() { ... }
>
> // CORRECT — private lock, only you control it
> private final Object lock = new Object();
>
> public void transfer(Account from, Account to, int amount) {
>     synchronized (lock) {
>         from.debit(amount);
>         to.credit(amount);
>     }
> }
> ```
> In Java 21+, prefer virtual threads over thread pools for I/O-bound workloads — they scale to millions of concurrent tasks with minimal overhead.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create and manage threads with `ExecutorService`
- [ ] Build async pipelines with `CompletableFuture`
- [ ] Use virtual threads (Java 21+) for high-concurrency I/O workloads

</details>

---

## Phase 9: Spring Boot Basics

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Build production-ready REST APIs with the most popular Java framework.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Spring Dependency Injection | `@Component`, `@Service`, `@Repository` — Spring creates and manages objects (beans) for you. `@Autowired` injects them |
| 2 | Spring Boot Setup | Use [start.spring.io](https://start.spring.io) to generate a project. Embedded Tomcat, auto-configuration, opinionated defaults |
| 3 | REST Controllers | `@RestController`, `@GetMapping("/users")`, `@PostMapping`, `@PathVariable`, `@RequestBody` — build REST endpoints |
| 4 | Annotations | `@SpringBootApplication`, `@Bean`, `@Configuration`, `@Value`, `@Qualifier` — configure behavior declaratively |
| 5 | `application.properties` | `server.port=8080`, `spring.datasource.url=...` — externalize configuration. Profiles for dev/staging/prod |
| 6 | JPA / Hibernate | `@Entity`, `@Id`, `@GeneratedValue`, `@OneToMany`, `@ManyToOne` — map Java objects to database tables. `JpaRepository` for CRUD |
| 7 | Validation | `@Valid`, `@NotBlank`, `@Email`, `@Min`, `@Max` — validate request bodies automatically. Returns 400 on validation failure |
| 8 | Error Handling | `@ControllerAdvice` + `@ExceptionHandler` — global error handling. Return consistent error responses across all endpoints |

> [!IMPORTANT]
> **Use constructor injection, not field injection.** Constructor injection makes dependencies explicit, enables immutability, and makes testing easy:
> ```java
> // WRONG — field injection hides dependencies
> @Service
> public class UserService {
>     @Autowired
>     private UserRepository repo; // Hidden dependency!
> }
>
> // CORRECT — constructor injection (Spring auto-wires)
> @Service
> public class UserService {
>     private final UserRepository repo;
>
>     public UserService(UserRepository repo) {
>         this.repo = repo;
>     }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Generate a Spring Boot project and run it with embedded Tomcat
- [ ] Build a full CRUD REST API with `@RestController` and `JpaRepository`
- [ ] Configure database connection and use JPA entities with validation

</details>

---

## Phase 10: Testing & Build Tools

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Test your code and package it for production.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | JUnit 5 | `@Test`, `@BeforeEach`, `@AfterEach`, `@DisplayName`. Assertions: `assertEquals()`, `assertThrows()`, `assertAll()` |
| 2 | Mockito | `@Mock`, `@InjectMocks`, `when(repo.findById(1)).thenReturn(user)` — mock dependencies for isolated unit tests |
| 3 | Integration Testing | `@SpringBootTest`, `@WebMvcTest`, `MockMvc` — test REST endpoints with the full Spring context |
| 4 | Maven | `pom.xml` for dependencies. `mvn clean install`, `mvn test`, `mvn package`. Lifecycle: compile, test, package, install |
| 5 | Gradle | `build.gradle` with Groovy or Kotlin DSL. `gradle build`, `gradle test`. Faster builds with incremental compilation and caching |
| 6 | Maven vs Gradle | Maven: XML-based, convention over configuration, widely adopted. Gradle: flexible, faster, preferred for new projects |
| 7 | JAR Packaging | `mvn package` creates `target/app.jar`. `java -jar app.jar` runs it. Spring Boot creates fat JARs with embedded server |
| 8 | CI/CD | GitHub Actions: run tests, build JARs, deploy on every push. `actions/setup-java@v4` with `distribution: 'temurin'` |

> [!TIP]
> Use `@WebMvcTest` for fast controller tests and `@SpringBootTest` for full integration tests. Keep unit tests fast and integration tests thorough:
> ```java
> @WebMvcTest(UserController.class)
> class UserControllerTest {
>
>     @Autowired
>     private MockMvc mockMvc;
>
>     @MockBean
>     private UserService userService;
>
>     @Test
>     @DisplayName("GET /api/users returns 200 with user list")
>     void getUsers_returnsUserList() throws Exception {
>         when(userService.findAll()).thenReturn(List.of(
>             new User(1L, "Alice"), new User(2L, "Bob")
>         ));
>
>         mockMvc.perform(get("/api/users"))
>             .andExpect(status().isOk())
>             .andExpect(jsonPath("$.length()").value(2));
>     }
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write unit tests with JUnit 5 and mock dependencies with Mockito
- [ ] Test REST endpoints with `MockMvc` and `@WebMvcTest`
- [ ] Build and package a Spring Boot app as a runnable JAR with Maven or Gradle

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Comparing strings with `==` | `==` compares object references, not content. Works sometimes due to string pool, but unreliable | Always use `.equals()` or `Objects.equals()` for string comparison |
| 2 | Ignoring checked exceptions | Empty `catch` blocks hide bugs and make debugging impossible | Handle or propagate exceptions with meaningful messages |
| 3 | Using raw types | `List list = new ArrayList()` loses type safety and requires casting | Use generics: `List<String> list = new ArrayList<>()` |
| 4 | Returning `null` instead of `Optional` | Callers forget to check for `null`, causing `NullPointerException` at runtime | Return `Optional<T>` and let callers handle absence explicitly |
| 5 | Mutable data classes | Public fields and setters everywhere lead to unpredictable state changes | Use records or immutable classes with `final` fields |
| 6 | `synchronized` on `this` | Any external code can lock on your object, causing deadlocks | Use a `private final Object lock` for synchronization |
| 7 | Not closing resources | File handles, DB connections, and streams leak if not closed | Use try-with-resources for all `AutoCloseable` objects |
| 8 | Using `float`/`double` for money | Floating point math is imprecise: `0.1 + 0.2 != 0.3` | Use `BigDecimal` for financial calculations |
| 9 | Field injection with `@Autowired` | Hides dependencies, prevents immutability, harder to test | Use constructor injection — Spring auto-wires single constructors |
| 10 | Catching `Exception` generically | Hides the actual error type, catches things you didn't intend to | Catch specific exceptions: `IOException`, `IllegalArgumentException`, etc. |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between JDK, JRE, and JVM?**
   - JVM (Java Virtual Machine) executes bytecode — it's the runtime engine. JRE (Java Runtime Environment) = JVM + standard libraries — enough to run Java programs. JDK (Java Development Kit) = JRE + compiler (`javac`) + dev tools — needed to develop Java programs.

2. **What are the 8 primitive data types in Java?**
   - `byte` (8-bit), `short` (16-bit), `int` (32-bit), `long` (64-bit), `float` (32-bit decimal), `double` (64-bit decimal), `char` (16-bit Unicode), `boolean` (true/false). Primitives are stored on the stack and are not objects.

3. **What is the difference between `==` and `.equals()`?**
   - `==` compares references (are they the same object in memory?). `.equals()` compares content (do they have the same value?). For primitives, `==` compares values. For objects (especially `String`), always use `.equals()`.

4. **What is the difference between an abstract class and an interface?**
   - Abstract classes can have state (fields), constructors, and both abstract and concrete methods. A class can only extend one abstract class. Interfaces define contracts with no state (before Java 8). A class can implement multiple interfaces. Java 8+ interfaces can have default and static methods.

5. **What is the `final` keyword used for?**
   - `final` variable: cannot be reassigned (constant). `final` method: cannot be overridden by subclasses. `final` class: cannot be extended (e.g., `String`). For reference types, `final` means the reference cannot change, but the object's contents still can.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain the Collections Framework hierarchy.**
   - `Iterable` > `Collection` > `List` (ordered, indexed: `ArrayList`, `LinkedList`), `Set` (unique: `HashSet`, `TreeSet`), `Queue` (FIFO: `LinkedList`, `ArrayDeque`). `Map` is separate (key-value: `HashMap`, `TreeMap`). Choose based on access pattern, ordering, and uniqueness needs.

2. **What are generics and why are they useful?**
   - Generics add compile-time type safety to collections and classes: `List<String>` instead of raw `List`. Benefits: no casting, compile-time error detection, code reuse. Type erasure means generic types are removed at runtime — this is why you can't do `new T()` or `instanceof T`.

3. **What is the Stream API and how does it differ from collections?**
   - Streams are a declarative pipeline for processing data: `filter`, `map`, `reduce`, `collect`. Unlike collections, streams are lazy (operations execute only when a terminal operation is called), don't store data, can be parallelized with `.parallelStream()`, and are consumed once.

4. **What is the difference between checked and unchecked exceptions?**
   - Checked exceptions (`IOException`, `SQLException`) must be caught or declared with `throws` — the compiler enforces this. Unchecked exceptions (`NullPointerException`, `IllegalArgumentException`) extend `RuntimeException` and don't require handling. Use unchecked for programming errors, checked for recoverable conditions.

5. **How does `HashMap` work internally?**
   - `HashMap` uses an array of buckets. `hashCode()` determines the bucket index. Collisions are handled with linked lists (or balanced trees when list length exceeds 8). `equals()` resolves collisions within a bucket. Load factor (0.75) triggers resizing to maintain O(1) average performance.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What are virtual threads (Java 21) and how do they differ from platform threads?**
   - Platform threads are OS threads — heavy (~1MB stack), limited to thousands. Virtual threads are JVM-managed, lightweight (~1KB), can scale to millions. They're ideal for I/O-bound tasks (HTTP calls, DB queries). Virtual threads mount/unmount from platform (carrier) threads automatically. Use `Thread.ofVirtual().start()` or `Executors.newVirtualThreadPerTaskExecutor()`.

2. **Explain the PECS principle (Producer Extends, Consumer Super).**
   - `? extends T`: read from it (producer) — safe to get `T` objects but can't add. `? super T`: write to it (consumer) — safe to add `T` objects but get returns `Object`. Example: `void copy(List<? extends T> src, List<? super T> dest)`. This maximizes API flexibility while maintaining type safety.

3. **How does Spring Dependency Injection work internally?**
   - Spring scans for `@Component`-annotated classes (component scanning), creates instances (beans), and stores them in the Application Context (IoC container). When a bean needs a dependency, Spring resolves it by type (and `@Qualifier` if ambiguous) and injects it via constructor, setter, or field. Beans are singletons by default (`@Scope("prototype")` for new instances).

4. **What is the Java Memory Model and how does `volatile` work?**
   - The JMM defines how threads interact through memory. Without synchronization, threads may see stale values due to CPU caching. `volatile` ensures visibility: writes to a volatile variable are immediately visible to all threads. It prevents instruction reordering around volatile access. However, `volatile` does not provide atomicity — use `AtomicInteger` or `synchronized` for compound operations.

5. **How would you design a thread-safe cache in Java?**
   - Use `ConcurrentHashMap` as the backing store for lock-free reads. For compute-if-absent patterns, use `computeIfAbsent()` which is atomic. For TTL-based expiration, use a `ScheduledExecutorService` to evict stale entries. For bounded caches, implement an LRU policy with `LinkedHashMap` (override `removeEldestEntry`) wrapped in `Collections.synchronizedMap()`, or use Caffeine library for production-grade caching.

</details>

---

## Practice Projects

### Project 1: CLI Task Manager
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A command-line task manager that lets users add, list, complete, and delete tasks. Saves tasks to a JSON file using `java.nio`.

**Skills practiced:** Variables, control flow, collections, file I/O, Scanner for user input.

---

### Project 2: Library Management System
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** An OOP-based library system with books, members, and borrowing logic. Uses inheritance, interfaces, and the Collections Framework for searching and sorting.

**Skills practiced:** Classes, inheritance, interfaces, polymorphism, ArrayList, HashMap, Comparable.

---

### Project 3: File Analyzer
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A tool that reads text files, counts word frequencies, finds the most common words, and generates statistics — all using the Stream API and proper exception handling.

**Skills practiced:** Exception handling, try-with-resources, `java.nio`, Stream API, lambdas, Optional, generics.

---

### Project 4: REST API with Spring Boot
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A full CRUD REST API for a bookstore or blog with Spring Boot, JPA/Hibernate, PostgreSQL, validation, global error handling, and pagination.

**Skills practiced:** Spring Boot, REST controllers, JPA entities, dependency injection, application.properties, CompletableFuture.

---

### Project 5: Production-Ready Microservice
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A fully tested Spring Boot microservice with JUnit 5, Mockito, Docker, CI/CD pipeline, health checks, structured logging, and 80%+ test coverage.

**Skills practiced:** Everything from all phases — your Java graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Oracle Java Documentation](https://docs.oracle.com/en/java/javase/21/docs/api/) | Official API docs for every class and method in the JDK |
| [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/) | Official guides: OOP, collections, concurrency, networking |
| [Spring Boot Reference](https://docs.spring.io/spring-boot/docs/current/reference/html/) | Official Spring Boot documentation — setup, configuration, deployment |
| [Baeldung](https://www.baeldung.com/) | In-depth Java and Spring tutorials with code examples for every topic |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Codecademy — Learn Java](https://www.codecademy.com/learn/learn-java) | Interactive, in-browser coding with instant feedback |
| [JetBrains Academy — Java Basics](https://www.jetbrains.com/academy/) | Project-based learning inside IntelliJ IDEA |
| [MOOC.fi — Java Programming](https://java-programming.mooc.fi/) | University of Helsinki's free Java course. Excellent exercises |
| [freeCodeCamp — Java Certification](https://www.freecodecamp.org/learn/) | Free certification with hands-on projects |

### YouTube

| Video / Channel | Why Watch |
|----------------|-----------|
| [Coding with John](https://www.youtube.com/@CodingWithJohn) | Clear, concise Java tutorials — perfect for individual topics |
| [Amigoscode](https://www.youtube.com/@amigoscode) | Full-length Java and Spring Boot courses, project-based |
| [Java Brains](https://www.youtube.com/@Java.Brains) | Excellent Spring and Java EE explanations for backend developers |
| [freeCodeCamp — Java Full Course](https://www.youtube.com/@freecodecamp) | 12-hour comprehensive Java course, completely free |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Java](https://roadmap.sh/java) | Interactive learning path with progress tracking |
| [roadmap.sh — Spring Boot](https://roadmap.sh/spring-boot) | Dedicated Spring Boot roadmap for backend development |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [IntelliJ IDEA](https://www.jetbrains.com/idea/) | The best Java IDE. Community Edition is free. Refactoring, debugging, code analysis |
| [VS Code Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack) | Lightweight alternative — Language Support, Debugger, Test Runner, Maven/Gradle |
| [Spring Initializr](https://start.spring.io/) | Generate Spring Boot projects with dependencies pre-configured |
| [sdkman](https://sdkman.io/) | Manage multiple JDK versions — install, switch, and update easily |
| [Postman](https://www.postman.com/) | Industry-standard API testing tool for REST endpoints |

### Cheat Sheets

| Resource | What It Covers |
|----------|---------------|
| [Java Cheat Sheet — Programming with Mosh](https://programmingwithmosh.com/java/java-cheat-sheet/) | Syntax, data types, OOP, collections — quick reference |
| [Spring Boot Annotations Cheat Sheet](https://www.baeldung.com/spring-boot-annotations) | Every Spring annotation explained with examples |
| [Maven Cheat Sheet](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) | Essential Maven commands and lifecycle phases |
| [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/) | Comprehensive reference for assertions, annotations, and test lifecycle |

---

[Back to Main Syllabus](../README.md)

# Angular Syllabus

A complete, structured learning path for Angular — from your first component to building enterprise-grade applications with Signals, RxJS, and server-side rendering.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Angular: v17+](https://img.shields.io/badge/Angular-v17%2B-DD0031)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Templates & Data Binding](#phase-2-templates--data-binding)
- [Phase 3: Components Deep Dive](#phase-3-components-deep-dive)
- [Phase 4: Directives & Pipes](#phase-4-directives--pipes)
- [Phase 5: Services & Dependency Injection](#phase-5-services--dependency-injection)
- [Phase 6: Routing & Navigation](#phase-6-routing--navigation)
- [Phase 7: Forms](#phase-7-forms)
- [Phase 8: HTTP & RxJS](#phase-8-http--rxjs)
- [Phase 9: Signals & Reactivity](#phase-9-signals--reactivity)
- [Phase 10: Testing, Performance & Deployment](#phase-10-testing-performance--deployment)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Angular uses **TypeScript** as its primary language. You must know TypeScript before learning Angular — not just JavaScript.

- HTML & CSS fundamentals
- JavaScript ES6+ (modules, classes, async/await, destructuring)
- TypeScript basics (types, interfaces, generics, decorators)
- Node.js and npm installed
- Complete the [TypeScript Syllabus](typescript.md) first

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what Angular is and create your first standalone component.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Angular | A full framework (not a library like React) — includes routing, forms, HTTP, DI, and testing out of the box |
| 2 | Angular vs AngularJS | AngularJS (v1) is dead. Modern Angular (v2+) is a complete rewrite — TypeScript-first, component-based |
| 3 | Angular CLI | `npm install -g @angular/cli` → `ng new my-app` — scaffolds a complete project with build, test, and dev server |
| 4 | Project Structure | `src/app/`, `angular.json`, `main.ts`, `app.component.ts` — where everything lives and why |
| 5 | Standalone Components | The default since Angular 17 — no `NgModule` needed. Components declare their own dependencies directly |
| 6 | Component Anatomy | `@Component({ selector, template, styles })` — decorator + class + template + styles = one component |
| 7 | Running the App | `ng serve` starts a dev server with hot reload. `ng build` creates the production bundle |

> [!TIP]
> When creating a new Angular project, Vite + esbuild is now the default build system (67% faster than the old Webpack setup):
> ```bash
> ng new my-app          # Standalone components by default (v17+)
> cd my-app
> ng serve               # Dev server at http://localhost:4200
> ng generate component header  # Generate a new component
> ```

<details>
<summary><strong>Quick Reference: Angular CLI Commands</strong></summary>

| Command | What It Does |
|---------|-------------|
| `ng new project-name` | Create a new Angular project |
| `ng serve` | Start dev server with live reload |
| `ng generate component name` | Create a new component |
| `ng generate service name` | Create a new service |
| `ng generate pipe name` | Create a new pipe |
| `ng generate directive name` | Create a new directive |
| `ng generate guard name` | Create a route guard |
| `ng build` | Build for production |
| `ng test` | Run unit tests |
| `ng e2e` | Run end-to-end tests |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create an Angular project with the CLI and run it
- [ ] Explain what a standalone component is and why NgModules are no longer needed
- [ ] Generate a component and render it in the app

</details>

---

## Phase 2: Templates & Data Binding

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Connect your component class to the template — display data, handle events, bind inputs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Interpolation | `{{ title }}` — display component data in the template with double curly braces |
| 2 | Property Binding | `[src]="imageUrl"` — bind component data to element properties (one-way, component → template) |
| 3 | Event Binding | `(click)="handleClick()"` — listen for DOM events and call component methods |
| 4 | Two-Way Binding | `[(ngModel)]="name"` — sync data both ways between input and component (banana-in-a-box syntax) |
| 5 | Template Variables | `#inputRef` — reference DOM elements directly in the template without going through the component |
| 6 | Class & Style Binding | `[class.active]="isActive"` and `[style.color]="textColor"` — dynamic CSS from component data |
| 7 | Safe Navigation | `{{ user?.name }}` — prevents "cannot read property of null" errors in templates |

> [!IMPORTANT]
> Angular has **four types of data binding**. Master this pattern — it's the core of every Angular template:
> ```
> Component → Template:  {{ value }}           Interpolation
> Component → Template:  [property]="value"    Property Binding
> Template → Component:  (event)="handler()"   Event Binding
> Both directions:       [(ngModel)]="value"   Two-Way Binding
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use all 4 types of data binding in a component
- [ ] Create a form input with two-way binding
- [ ] Use template reference variables to read input values

</details>

---

## Phase 3: Components Deep Dive

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master component communication, lifecycle, and projection patterns.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `@Input()` | Pass data from parent to child: `<child [title]="parentTitle" />` — child declares `@Input() title: string` |
| 2 | `@Output()` & EventEmitter | Child emits events to parent: `@Output() saved = new EventEmitter<Item>()` → `this.saved.emit(item)` |
| 3 | Lifecycle Hooks | `ngOnInit` (setup), `ngOnChanges` (input changes), `ngAfterViewInit` (DOM ready), `ngOnDestroy` (cleanup) |
| 4 | Content Projection | `<ng-content>` — pass HTML into a child component from the parent, like React's `children` prop |
| 5 | `@ViewChild` | `@ViewChild('ref') element: ElementRef` — access DOM elements or child components from the class |
| 6 | `@ContentChild` | Access projected content (passed via `<ng-content>`) from the component class |
| 7 | Change Detection | Default (checks everything) vs OnPush (checks only on @Input changes, events, or signal updates) |
| 8 | Smart vs Presentational | Smart components fetch data and manage state. Presentational components only display data via @Input |

> [!WARNING]
> **Don't access `@ViewChild` in the constructor or `ngOnInit`** — the view isn't rendered yet. Use `ngAfterViewInit` instead:
> ```typescript
> // WRONG — element is undefined here
> ngOnInit() { this.input.nativeElement.focus(); }
>
> // RIGHT — view is rendered
> ngAfterViewInit() { this.input.nativeElement.focus(); }
> ```

<details>
<summary><strong>Quick Reference: Lifecycle Hooks (in order)</strong></summary>

| Hook | When It Runs | Common Use |
|------|-------------|------------|
| `constructor` | Class instantiation | Inject dependencies only |
| `ngOnChanges` | Before `ngOnInit`, then on every `@Input` change | React to input changes |
| `ngOnInit` | Once, after first `ngOnChanges` | Fetch data, initialize logic |
| `ngAfterContentInit` | After `<ng-content>` is projected | Access `@ContentChild` |
| `ngAfterViewInit` | After the view (template) renders | Access `@ViewChild`, DOM |
| `ngOnDestroy` | Before the component is removed | Unsubscribe, cleanup timers |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Pass data between parent and child with `@Input` and `@Output`
- [ ] Use `ngOnInit` for initialization and `ngOnDestroy` for cleanup
- [ ] Implement content projection with `<ng-content>`

</details>

---

## Phase 4: Directives & Pipes

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Control rendering with directives and transform data with pipes.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `@if` / `@else` | `@if (isLoggedIn) { <Dashboard /> } @else { <Login /> }` — new built-in control flow (v17+) |
| 2 | `@for` with `track` | `@for (item of items; track item.id) { }` — loop with mandatory tracking for performance |
| 3 | `@switch` | `@switch (status) { @case ('active') { } @default { } }` — cleaner than chained `@if` |
| 4 | `@defer` | `@defer (on viewport) { <HeavyComponent /> }` — lazy-load components when they enter the viewport |
| 5 | Attribute Directives | `ngClass`, `ngStyle` — dynamically add classes and styles based on component data |
| 6 | Custom Directives | Create your own directive with `@Directive`, `HostListener`, `HostBinding`, `Renderer2` |
| 7 | Built-in Pipes | `date`, `currency`, `uppercase`, `lowercase`, `json`, `async`, `slice`, `keyvalue` |
| 8 | Custom Pipes | `@Pipe({ name: 'truncate' })` + `PipeTransform` — create reusable data transformations |

> [!TIP]
> The new `@for` syntax requires a `track` expression — this replaces the old `trackBy` function and is mandatory. It dramatically improves list performance:
> ```html
> <!-- New syntax (v17+) — track is required -->
> @for (user of users; track user.id) {
>   <user-card [user]="user" />
> } @empty {
>   <p>No users found.</p>
> }
> ```

<details>
<summary><strong>Quick Reference: Old vs New Control Flow</strong></summary>

| Old Syntax (v16-) | New Syntax (v17+) | Notes |
|-------------------|-------------------|-------|
| `*ngIf="condition"` | `@if (condition) { }` | Built-in, no imports needed |
| `*ngIf="x; else tmpl"` | `@if (x) { } @else { }` | Cleaner `else` handling |
| `*ngFor="let item of items; trackBy: trackFn"` | `@for (item of items; track item.id) { }` | `track` is mandatory |
| `[ngSwitch]` + `*ngSwitchCase` | `@switch (value) { @case (x) { } }` | Single block syntax |
| N/A | `@defer (on viewport) { }` | Entirely new — lazy component loading |

> Use the new syntax for all new projects. The old directives still work but are considered legacy.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `@if`, `@for`, and `@switch` in templates
- [ ] Create a custom directive that highlights elements on hover
- [ ] Create a custom pipe that truncates long text

</details>

---

## Phase 5: Services & Dependency Injection

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Share data and logic across components with services and Angular's powerful DI system.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Creating Services | `@Injectable({ providedIn: 'root' })` — a class that holds shared logic and data |
| 2 | `inject()` Function | `private http = inject(HttpClient)` — modern way to inject dependencies (no constructor boilerplate) |
| 3 | `providedIn: 'root'` | Makes the service a singleton — one instance shared across the entire app. Tree-shakeable |
| 4 | Constructor Injection | `constructor(private userService: UserService)` — classic approach, still valid |
| 5 | Hierarchical Injectors | Provide a service at component level for a fresh instance per component, or root for a singleton |
| 6 | `InjectionToken` | `new InjectionToken<string>('API_URL')` — inject non-class values (strings, configs, functions) |
| 7 | Factory Providers | `{ provide: Service, useFactory: () => new Service(config) }` — dynamic service creation |

> [!TIP]
> Use `inject()` instead of constructor injection — it's cleaner and works in standalone components, functions, and guards:
> ```typescript
> // Old way — constructor boilerplate
> constructor(private http: HttpClient, private router: Router) {}
>
> // Modern way — inject() function
> private http = inject(HttpClient);
> private router = inject(Router);
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a service and inject it using `inject()`
- [ ] Explain the difference between root-level and component-level providers
- [ ] Use `InjectionToken` to inject a configuration object

</details>

---

## Phase 6: Routing & Navigation

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build multi-page apps with client-side routing, guards, and lazy loading.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Router Setup | `provideRouter(routes)` in `app.config.ts` — configure routes for standalone apps |
| 2 | Basic Routes | `{ path: 'about', component: AboutComponent }` + `<router-outlet />` — URL maps to component |
| 3 | `routerLink` | `<a routerLink="/about">About</a>` — navigate without page reload. `routerLinkActive` for active styling |
| 4 | Route Parameters | `{ path: 'user/:id' }` + `inject(ActivatedRoute)` → `route.params` — dynamic URLs |
| 5 | Nested Routes | `children: [...]` + `<router-outlet />` in parent — shared layouts with changing content |
| 6 | Route Guards | `canActivate`, `canDeactivate`, `canMatch` — protect routes (auth check, unsaved changes warning) |
| 7 | Lazy Loading | `loadComponent: () => import('./page.component')` — load route components on demand, reducing initial bundle |
| 8 | Redirects & Wildcards | `{ path: '', redirectTo: '/home' }` and `{ path: '**', component: NotFoundComponent }` |
| 9 | Resolvers | Pre-fetch data before the route activates — the component receives data immediately, no loading state |

> [!IMPORTANT]
> **Lazy load every route** in a real app. It splits your bundle into chunks — users only download the code for the page they're visiting:
> ```typescript
> const routes: Routes = [
>   { path: '', component: HomeComponent },
>   {
>     path: 'dashboard',
>     loadComponent: () => import('./dashboard/dashboard.component')
>       .then(m => m.DashboardComponent)
>   }
> ];
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up routing with 4+ lazy-loaded routes
- [ ] Create a route guard that redirects unauthenticated users
- [ ] Use route parameters to load dynamic data

</details>

---

## Phase 7: Forms

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build forms with validation — template-driven for simple forms, reactive for complex ones.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Template-Driven Forms | `ngModel` + `ngForm` — quick forms with two-way binding. Good for simple forms |
| 2 | Reactive Forms | `FormGroup`, `FormControl`, `FormArray` — defined in TypeScript, full control over validation and state |
| 3 | `FormBuilder` | `fb.group({ name: ['', Validators.required] })` — shorthand for creating reactive forms |
| 4 | Built-in Validators | `Validators.required`, `.minLength()`, `.maxLength()`, `.email()`, `.pattern()` |
| 5 | Custom Validators | Write your own validation functions — sync and async (e.g., check if username is taken via API) |
| 6 | Cross-Field Validation | Validate fields against each other (e.g., "password" must match "confirm password") |
| 7 | Dynamic Forms | `FormArray` — add/remove form controls at runtime (e.g., add another phone number field) |
| 8 | Form State | `touched`, `dirty`, `valid`, `invalid`, `pristine` — track how the user has interacted with each field |

> [!TIP]
> **Reactive Forms > Template-Driven** for anything beyond a simple search box. They're type-safe, testable, and give you full control:
> ```typescript
> // Reactive Form — defined in the component class
> form = this.fb.group({
>   email: ['', [Validators.required, Validators.email]],
>   password: ['', [Validators.required, Validators.minLength(8)]]
> });
>
> // Template — clean, no validation logic
> <input formControlName="email" />
> @if (form.get('email')?.hasError('required')) {
>   <span>Email is required</span>
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a registration form with reactive forms and validation
- [ ] Create a custom validator (sync and async)
- [ ] Use `FormArray` for dynamic form fields

</details>

---

## Phase 8: HTTP & RxJS

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Make API calls, handle responses with Observables, and master the RxJS operators you'll use daily.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `HttpClient` | `provideHttpClient()` + `inject(HttpClient)` — typed GET, POST, PUT, DELETE requests |
| 2 | Observables vs Promises | Observables are lazy, cancellable, and emit multiple values over time. Promises are eager and emit once |
| 3 | Core RxJS Operators | `map`, `filter`, `tap`, `switchMap`, `mergeMap`, `catchError`, `retry`, `debounceTime` |
| 4 | `async` Pipe | `{{ data$ \| async }}` — subscribe in the template, auto-unsubscribe on destroy. Prevents memory leaks |
| 5 | Unsubscription Patterns | `takeUntilDestroyed()` (modern), `async` pipe, manual `unsubscribe()` — prevent memory leaks |
| 6 | HTTP Interceptors | Functional interceptors — add auth tokens, log requests, handle errors globally |
| 7 | Error Handling | `catchError()` operator, `HttpErrorResponse`, retry strategies, user-friendly error messages |
| 8 | Combining Streams | `combineLatest()`, `forkJoin()`, `merge()`, `concat()` — coordinate multiple async operations |

> [!CAUTION]
> **Every subscription is a potential memory leak.** If you subscribe in a component and don't unsubscribe when the component is destroyed, the subscription lives on forever. Use the `async` pipe or `takeUntilDestroyed()`:
> ```typescript
> // BEST — async pipe handles subscription and cleanup
> users$ = this.http.get<User[]>('/api/users');
> // In template: @for (user of users$ | async; track user.id) { }
>
> // GOOD — takeUntilDestroyed() auto-unsubscribes
> private destroyRef = inject(DestroyRef);
> ngOnInit() {
>   this.http.get('/api/data')
>     .pipe(takeUntilDestroyed(this.destroyRef))
>     .subscribe(data => this.data = data);
> }
> ```

<details>
<summary><strong>Quick Reference: Essential RxJS Operators</strong></summary>

| Operator | What It Does | When to Use |
|----------|-------------|-------------|
| `map(fn)` | Transform each emitted value | Reshape API response data |
| `filter(fn)` | Only pass values that match | Skip empty/invalid values |
| `tap(fn)` | Side effect without changing the stream | Logging, debugging |
| `switchMap(fn)` | Cancel previous, switch to new Observable | Search-as-you-type, route changes |
| `mergeMap(fn)` | Run Observables in parallel | Multiple concurrent requests |
| `catchError(fn)` | Handle errors, return fallback | API error handling |
| `debounceTime(ms)` | Wait for pause before emitting | Search input, form validation |
| `distinctUntilChanged()` | Skip consecutive duplicates | Avoid redundant API calls |
| `combineLatest([a$, b$])` | Latest value from each stream | Combine filter + search |
| `forkJoin([a$, b$])` | Wait for all to complete | Parallel API calls |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data from an API and display it with the `async` pipe
- [ ] Implement search-as-you-type with `debounceTime` and `switchMap`
- [ ] Create an HTTP interceptor that adds an auth token to every request

</details>

---

## Phase 9: Signals & Reactivity

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Angular's new reactivity system — simpler than RxJS for component state, better performance.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `signal()` | `count = signal(0)` — create reactive state. Read with `count()`, write with `count.set(5)` or `count.update(n => n + 1)` |
| 2 | `computed()` | `double = computed(() => this.count() * 2)` — derived state that auto-updates when dependencies change |
| 3 | `effect()` | `effect(() => console.log(this.count()))` — run side effects when signals change (logging, persistence) |
| 4 | Signal Inputs | `name = input<string>()` — signal-based `@Input()` replacement. Reactive, no `ngOnChanges` needed |
| 5 | Signal Outputs | `saved = output<Item>()` — signal-based `@Output()` replacement |
| 6 | Signals vs RxJS | Signals: synchronous, simple state, component-local. RxJS: async streams, complex flows, HTTP |
| 7 | Zoneless Change Detection | Signals enable removing Zone.js entirely — fine-grained reactivity without checking every component |

> [!TIP]
> **When to use Signals vs RxJS:**
> - **Signals** → Component state, derived values, simple shared state (like React's `useState`)
> - **RxJS** → HTTP requests, WebSockets, complex async flows, event streams, debouncing
> - **Both together** → Use Signals for UI state, RxJS for data streams. Convert between them with `toSignal()` and `toObservable()`

<details>
<summary><strong>Quick Reference: Signal API</strong></summary>

```typescript
// Create
const count = signal(0);

// Read
console.log(count()); // 0

// Write
count.set(5);                  // Set directly
count.update(n => n + 1);      // Update based on previous

// Derived
const double = computed(() => count() * 2);

// Side effect
effect(() => {
  console.log(`Count changed to ${count()}`);
});

// Convert RxJS → Signal
const users = toSignal(this.http.get<User[]>('/api/users'));

// Convert Signal → RxJS
const count$ = toObservable(count);
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Refactor a component from `@Input`/`@Output` to signal-based inputs/outputs
- [ ] Create derived state with `computed()`
- [ ] Explain when to use Signals vs RxJS Observables

</details>

---

## Phase 10: Testing, Performance & Deployment

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Test your app, optimize performance, and deploy to production.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Unit Testing | `TestBed.configureTestingModule({})` — configure the testing environment, create component fixtures |
| 2 | Component Testing | Render components, query the DOM, simulate events, assert on output. Use `fixture.detectChanges()` |
| 3 | Service Testing | Test services in isolation. Mock `HttpClient` with `HttpClientTestingModule` |
| 4 | E2E Testing | Playwright or Cypress — test real user flows across the full app in a browser |
| 5 | OnPush Strategy | `changeDetection: ChangeDetectionStrategy.OnPush` — skip re-rendering unless inputs/signals change |
| 6 | Lazy Loading & `@defer` | Lazy-load routes and components. `@defer (on viewport)` loads heavy components only when visible |
| 7 | SSR (Server-Side Rendering) | `ng add @angular/ssr` — pre-render pages on the server for SEO and faster initial load |
| 8 | Bundle Analysis | `ng build` + source-map-explorer — find what's bloating your bundle |
| 9 | Production Build | `ng build --configuration production` — AOT compilation, tree-shaking, minification |
| 10 | Deployment | Deploy to Vercel, Netlify, Firebase, AWS, or Docker. CI/CD with GitHub Actions |

> [!TIP]
> Use `@defer` to dramatically improve initial load time by lazy-loading heavy components:
> ```html
> <!-- Load the chart component only when it scrolls into view -->
> @defer (on viewport) {
>   <analytics-chart [data]="chartData" />
> } @placeholder {
>   <div class="skeleton-chart"></div>
> } @loading (minimum 500ms) {
>   <spinner />
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write unit tests for a component and a service
- [ ] Enable OnPush change detection across the app
- [ ] Deploy an Angular app with SSR to Vercel or Firebase

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most Angular developers:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Not unsubscribing | Subscriptions live forever → memory leaks, ghost behavior | Use `async` pipe, `takeUntilDestroyed()`, or unsubscribe in `ngOnDestroy` |
| 2 | Missing `track` in `@for` | Angular recreates all DOM elements on every change → terrible performance | Always provide `track item.id` — it's mandatory in the new syntax |
| 3 | Accessing `@ViewChild` too early | Accessing in `ngOnInit` or constructor — view isn't rendered yet | Use `ngAfterViewInit` for `@ViewChild` |
| 4 | Using `any` types | Defeats TypeScript's safety, hides bugs | Enable `strict: true` in `tsconfig.json`, type everything |
| 5 | Direct DOM manipulation | `document.querySelector()` breaks SSR and testing | Use `Renderer2`, template refs, or Angular bindings |
| 6 | Not using OnPush | Default change detection checks everything on every event — slow for large apps | Set `changeDetection: ChangeDetectionStrategy.OnPush` |
| 7 | Over-engineering state | Using NgRx for a to-do app — massive boilerplate for simple state | Start with services + Signals. Use NgRx only when complexity justifies it |
| 8 | Giant monolithic components | 500+ line components that do everything | Split into smart (data) + presentational (display) components |
| 9 | Ignoring `@defer` | Loading everything upfront, slow initial page load | Use `@defer (on viewport)` for below-fold and heavy components |
| 10 | Not handling HTTP errors | No `catchError` → unhandled errors crash the subscription silently | Use interceptors for global error handling, `catchError` per request |

---

## Interview Questions

Test your Angular knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is Angular and how does it differ from React?**
   - Angular is a full framework (routing, forms, HTTP, DI, testing included). React is a library (only the view layer — you add routing, state, etc. separately). Angular uses TypeScript by default, has opinionated structure, and is maintained by Google.

2. **What are standalone components?**
   - Components that don't require `NgModule`. They declare their own dependencies directly in the `@Component` decorator via `imports: []`. Default since Angular 17. Benefits: simpler, better tree-shaking, no module boilerplate.

3. **Explain the four types of data binding.**
   - Interpolation `{{ }}`: display data. Property binding `[prop]="value"`: component → template. Event binding `(event)="handler()"`: template → component. Two-way `[(ngModel)]="value"`: both directions.

4. **What is Dependency Injection?**
   - A design pattern where a class receives its dependencies from the outside (injected by Angular) instead of creating them itself. Benefits: loose coupling, testability (inject mocks), reusability. Angular's DI is hierarchical — root, component, and element-level injectors.

5. **Name 5 lifecycle hooks and when they run.**
   - `ngOnChanges`: when `@Input` values change. `ngOnInit`: after first render (initialization). `ngAfterViewInit`: after view renders (DOM access). `ngAfterContentInit`: after projected content renders. `ngOnDestroy`: before component is removed (cleanup).

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Observables vs Promises — what's the difference?**
   - Observables: lazy (don't execute until subscribed), cancellable, emit multiple values over time, support operators (map, filter, switchMap). Promises: eager (execute immediately), not cancellable, emit one value. Angular uses Observables for HTTP, routing, forms, and events.

2. **Explain OnPush change detection.**
   - Default strategy checks every component on every browser event. OnPush only checks when: (1) `@Input` reference changes, (2) an event fires within the component, (3) a signal updates, or (4) `async` pipe receives a new value. Dramatically improves performance in large apps.

3. **How do route guards work?**
   - Guards are functions (or classes) that return `true`, `false`, or a `UrlTree` (redirect). `canActivate`: before entering a route. `canDeactivate`: before leaving (unsaved changes). `canMatch`: before matching a route. Modern guards are just functions using `inject()`.

4. **Template-driven vs Reactive forms — when do you use each?**
   - Template-driven: simple forms, quick setup, `ngModel` in templates. Reactive: complex forms, validation logic in TypeScript, `FormGroup`/`FormControl`, testable, dynamic fields. Use Reactive for anything beyond a simple search box.

5. **How do you prevent memory leaks?**
   - Use `async` pipe (auto-unsubscribes). Use `takeUntilDestroyed()` for manual subscriptions. Clear `setInterval`/`setTimeout` in `ngOnDestroy`. Remove event listeners. Avoid storing references to destroyed components.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What are Signals and how do they change Angular?**
   - Signals are a synchronous, pull-based reactivity primitive. `signal(0)` creates reactive state, `computed()` derives values, `effect()` runs side effects. They enable fine-grained change detection without Zone.js. Simpler than RxJS for component state. Angular is moving toward Signals as the primary reactivity model.

2. **Explain NgZone and when to use `runOutsideAngular()`.**
   - NgZone patches browser APIs (setTimeout, addEventListener, etc.) to trigger change detection after each async operation. `runOutsideAngular()` runs code without triggering change detection — use for performance-critical operations (mousemove handlers, animations, third-party libraries). Re-enter with `run()` when you need Angular to detect changes.

3. **How does tree-shaking work in Angular?**
   - Tree-shaking removes unused code from the production bundle. Angular enables it through: `providedIn: 'root'` (services only bundled if imported), standalone components (no module pulling in unused code), ES modules (`import`/`export`). The Vite/esbuild bundler performs tree-shaking at build time.

4. **How would you build a custom structural directive?**
   - Inject `TemplateRef` and `ViewContainerRef`. Use `@Input` setter to conditionally create or clear the embedded view. Example: a `*appPermission="'admin'"` directive that only renders content if the user has the required role. Use `createEmbeddedView()` to render and `clear()` to remove.

5. **Signals vs RxJS — when do you use each?**
   - Signals: synchronous derived state, component-local state, simple shared state, UI reactivity (counters, toggles, form state). RxJS: HTTP requests, WebSocket streams, complex async orchestration (debounce, retry, combine streams), event-driven workflows. In practice: use `toSignal()` to convert HTTP Observables into Signals for template consumption.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Task Tracker
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** A task manager with add/edit/delete, category filters, and priority sorting. Uses `@if`, `@for`, `@Input`, `@Output`, and custom pipes.

**Skills practiced:** Components, data binding, directives, pipes, component communication.

---

### Project 2: Blog Platform with Routing
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** A multi-page blog with post listing, detail view, category pages, and admin area with route guards. Lazy-loaded routes.

**Skills practiced:** Services, DI, routing, route params, guards, lazy loading.

---

### Project 3: Registration System with Forms
![Phase 7](https://img.shields.io/badge/After-Phase%207-yellow)

**What you'll build:** A multi-step registration form with reactive forms, cross-field validation, dynamic fields, and a progress indicator.

**Skills practiced:** Reactive forms, FormBuilder, FormArray, custom validators, form state.

---

### Project 4: GitHub Explorer (API)
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** Search GitHub users and repos via API. Display results with Signals, implement search-as-you-type with RxJS, cache results, handle errors gracefully.

**Skills practiced:** HttpClient, RxJS operators, Signals, `computed()`, `async` pipe, error handling.

---

### Project 5: Full-Stack Dashboard
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** An admin dashboard with auth, charts, data tables, SSR, lazy-loaded sections, and 80%+ test coverage. OnPush everywhere, `@defer` for heavy widgets.

**Skills practiced:** Everything from all phases — your Angular graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [angular.dev](https://angular.dev/) | The official Angular docs — completely redesigned with interactive tutorials and modern content |
| [angular.dev — Essentials](https://angular.dev/essentials) | Start here. Covers standalone components, signals, templates, and DI |
| [angular.dev — Signals Guide](https://angular.dev/guide/signals) | Complete guide to Angular's new reactivity system |
| [angular.dev — API Reference](https://angular.dev/api) | Every decorator, class, function, and interface documented |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Angular.dev — Tutorial](https://angular.dev/tutorials) | Official interactive tutorial. Build a real app step by step in the browser |
| [freeCodeCamp — Angular Course](https://www.freecodecamp.org/news/tag/angular/) | Free full-length courses with projects |
| [Codecademy — Learn Angular](https://www.codecademy.com/learn/learn-angular) | In-browser coding with instant feedback |
| [Scrimba — Angular Basics](https://scrimba.com/learn/angular) | Interactive screencasts — pause and edit the instructor's code |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Decoded Frontend](https://www.youtube.com/@DecodedFrontend) | The best advanced Angular channel. Deep dives into DI, change detection, performance by Dmytro Mezhenskyi |
| [Angular University](https://www.youtube.com/@AngularUniversity) | In-depth courses on RxJS, NgRx, SSR, and enterprise patterns |
| [Traversy Media — Angular Crash Course](https://www.youtube.com/@TraversyMedia) | Best first Angular video — build a project in ~2 hours |
| [Fireship — Angular in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview before diving deep |
| [Joshua Morony](https://www.youtube.com/@JoshuaMorony) | Signals, modern Angular patterns, practical tutorials |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Angular](https://roadmap.sh/angular) | Interactive learning path — click each topic to see resources. Track your progress |

### Practice & Build Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional designs — build them with Angular |
| [DevChallenges](https://devchallenges.io/) | Full-stack challenges at varying difficulty levels |
| [Angular Challenges](https://angular-challenges.vercel.app/) | Angular-specific coding challenges by Thomas Laforge |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Angular Language Service](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template) | Official extension. Template IntelliSense, error detection, go-to-definition in templates |
| [Angular Essentials (John Papa)](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials) | Extension pack — includes Language Service, Prettier, Material icons, and more |
| [Angular Schematics](https://marketplace.visualstudio.com/items?itemName=cyrilletuzi.angular-schematics) | Right-click → generate component/service/pipe. No terminal needed |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Code quality with Angular-specific rules via `@angular-eslint` |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format HTML templates and TypeScript on save |
| [Angular DevTools](https://angular.dev/tools/devtools) | Chrome extension — inspect component tree, profile change detection, debug DI |

### RxJS Resources

| Resource | Why It's Great |
|----------|---------------|
| [RxJS Official Docs](https://rxjs.dev/) | Every operator documented with marble diagrams |
| [Learn RxJS](https://www.learnrxjs.io/) | Operator reference with real-world examples — the best RxJS learning site |
| [RxJS Marbles](https://rxmarbles.com/) | Interactive marble diagrams — visualize how operators transform streams |

### State Management

| Library | When to Use It |
|---------|---------------|
| Signals + Services | Simple to medium apps. Start here |
| [NgRx](https://ngrx.io/) | Large apps with complex state, many developers, strict architecture needs |
| [NGXS](https://www.ngxs.io/) | Simpler alternative to NgRx with less boilerplate |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [Angular Cheat Sheet (angular.dev)](https://angular.dev/guide/cheatsheet) | Official quick reference for template syntax, decorators, and DI |
| [RxJS Operator Decision Tree](https://rxjs.dev/operator-decision-tree) | "I want to..." → find the right operator |

---

[Back to Main Syllabus](../README.md)

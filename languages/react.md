# React Syllabus

A complete, structured learning path for React — from your first component to building production-ready applications with hooks, routing, state management, and testing.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 12-16 Weeks](https://img.shields.io/badge/Duration-12--16%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Components & Props](#phase-2-components--props)
- [Phase 3: State & Events](#phase-3-state--events)
- [Phase 4: Rendering & Lists](#phase-4-rendering--lists)
- [Phase 5: Effects & Lifecycle](#phase-5-effects--lifecycle)
- [Phase 6: React Hooks Deep Dive](#phase-6-react-hooks-deep-dive)
- [Phase 7: Context & State Management](#phase-7-context--state-management)
- [Phase 8: React Router](#phase-8-react-router)
- [Phase 9: Performance & Patterns](#phase-9-performance--patterns)
- [Phase 10: Testing & Best Practices](#phase-10-testing--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> React is a **JavaScript library**. You need solid JavaScript fundamentals before learning React — especially ES6+ features. Don't skip this.

- HTML & CSS fundamentals
- JavaScript essentials: arrow functions, destructuring, spread/rest, `map`/`filter`, promises, `async/await`, modules (`import`/`export`)
- Basic command line (terminal) usage
- Node.js and npm installed
- Complete the [JavaScript Syllabus](javascript.md) first

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what React is and build your first component.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is React | A JavaScript library for building UIs with reusable components — created by Meta, used everywhere |
| 2 | Why React | Declarative (describe what, not how), component-based, fast (virtual DOM), massive ecosystem |
| 3 | Setting Up a Project | `npm create vite@latest my-app -- --template react` — Vite is the modern standard (faster than CRA) |
| 4 | Project Structure | `src/`, `public/`, `index.html`, `main.jsx`, `App.jsx` — what each file does |
| 5 | JSX Fundamentals | HTML-like syntax in JavaScript — `{}` for expressions, `className` instead of `class`, self-closing tags |
| 6 | Your First Component | A function that returns JSX: `function App() { return <h1>Hello</h1> }` — must start with a capital letter |
| 7 | Rendering to the DOM | `createRoot(document.getElementById('root')).render(<App />)` — mounts your app |

> [!TIP]
> Use **Vite** for all new React projects. It's 10-20x faster than Create React App during development:
> ```bash
> npm create vite@latest my-app -- --template react
> cd my-app
> npm install
> npm run dev
> ```

<details>
<summary><strong>Quick Reference: JSX Rules</strong></summary>

| Rule | Wrong | Right |
|------|-------|-------|
| One root element | `return <h1>Hi</h1><p>Text</p>` | `return <><h1>Hi</h1><p>Text</p></>` |
| Close all tags | `<img>`, `<br>`, `<input>` | `<img />`, `<br />`, `<input />` |
| Use `className` | `<div class="box">` | `<div className="box">` |
| Use `htmlFor` | `<label for="name">` | `<label htmlFor="name">` |
| JS in curly braces | `<p>Hello name</p>` | `<p>Hello {name}</p>` |
| CamelCase events | `<button onclick={}>` | `<button onClick={}>` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a React project with Vite and run it locally
- [ ] Write a component that renders JSX with dynamic expressions
- [ ] Explain why React uses a virtual DOM

</details>

---

## Phase 2: Components & Props

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Break your UI into reusable pieces and pass data between them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Functional Components | Functions that return JSX — the only way to write components in modern React |
| 2 | Props | Pass data to components like HTML attributes: `<Card title="Hello" />` — accessed via `props.title` |
| 3 | Destructuring Props | `function Card({ title, description })` — cleaner than `props.title` |
| 4 | Props are Read-Only | Never modify props inside a component. Data flows down (parent → child), events flow up |
| 5 | `children` Prop | `<Card><p>Content</p></Card>` — `children` is whatever you put between the opening and closing tags |
| 6 | Component Composition | Build complex UIs from small components: `<Page>` contains `<Header>`, `<Sidebar>`, `<Content>` |
| 7 | Default Props | `function Button({ variant = "primary" })` — provide fallback values for optional props |
| 8 | Prop Drilling (Intro) | When you pass props through many levels just to reach a deep child — a problem you'll solve later |

> [!IMPORTANT]
> **Components are just functions.** If a function returns JSX, it's a component. There's nothing magical about them. Think of props as function arguments — that's literally what they are.

<details>
<summary><strong>Visual: Data Flow in React</strong></summary>

```
       ┌──────────┐
       │   App     │  ← State lives here
       └────┬─────┘
            │ props ↓
       ┌────┴─────┐
       │  Header   │  ← Receives data via props
       └──────────┘
            │ props ↓
       ┌────┴─────┐
       │  NavBar   │  ← Also receives via props
       └──────────┘

  Data flows DOWN (props)
  Events flow UP (callbacks)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create 3+ reusable components and compose them together
- [ ] Pass data via props and destructure them
- [ ] Use the `children` prop to create a wrapper component

</details>

---

## Phase 3: State & Events

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make components interactive — respond to clicks, inputs, and form submissions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `useState` Hook | `const [count, setCount] = useState(0)` — add state to a component. Calling the setter triggers a re-render |
| 2 | Event Handling | `onClick`, `onChange`, `onSubmit` — pass functions (not calls): `onClick={handleClick}` not `onClick={handleClick()}` |
| 3 | State Updates | State updates are async and batched. Use the updater function for consecutive updates: `setCount(prev => prev + 1)` |
| 4 | Controlled Components | Bind input values to state: `<input value={name} onChange={e => setName(e.target.value)} />` — React controls the input |
| 5 | Form Handling | Handle form submission with `onSubmit`, `e.preventDefault()`, collect values from state, validate, reset |
| 6 | Multiple State Variables | Use separate `useState` calls for independent values. Group related values in an object |
| 7 | Lifting State Up | When siblings need to share data, move the state to their common parent and pass it down as props |
| 8 | State Immutability | Never mutate state directly. For objects: `setState({...obj, key: newValue})`. For arrays: `setState([...arr, newItem])` |

> [!CAUTION]
> **Never mutate state directly.** This is the #1 React bug:
> ```javascript
> // WRONG — React won't detect the change, no re-render
> state.items.push(newItem);
> setState(state);
>
> // RIGHT — create a new array
> setState(prev => [...prev, newItem]);
> ```

<details>
<summary><strong>Quick Reference: Common Event Handlers</strong></summary>

| Event | Element | Use Case |
|-------|---------|----------|
| `onClick` | Buttons, divs | Button clicks, toggles |
| `onChange` | Inputs, selects, textareas | Form input changes |
| `onSubmit` | Forms | Form submission |
| `onFocus` / `onBlur` | Inputs | Focus/blur tracking |
| `onKeyDown` | Inputs, document | Keyboard shortcuts |
| `onMouseEnter` / `onMouseLeave` | Any | Hover effects |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a counter with increment/decrement buttons using `useState`
- [ ] Create a controlled form with multiple inputs
- [ ] Lift state up to share data between sibling components

</details>

---

## Phase 4: Rendering & Lists

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Show, hide, and repeat UI elements based on data and conditions.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Conditional Rendering | Ternary: `{isLoggedIn ? <Dashboard /> : <Login />}` — show different UI based on state |
| 2 | Short-Circuit (`&&`) | `{showModal && <Modal />}` — render something only when a condition is true |
| 3 | Rendering Lists | `{items.map(item => <Card key={item.id} data={item} />)}` — transform arrays into JSX |
| 4 | Keys | Every list item needs a unique `key` prop. React uses keys to track which items changed, were added, or removed |
| 5 | Filtering & Sorting | Filter before rendering: `{items.filter(i => i.active).map(...)}` — never mutate the original array |
| 6 | Empty States | Show a message when the list is empty: `{items.length === 0 ? <p>No items</p> : <List items={items} />}` |
| 7 | Fragments | `<>...</>` or `<React.Fragment>` — group elements without adding an extra DOM node |

> [!WARNING]
> **Never use array index as a key** when items can be reordered, added, or removed. It causes bugs — React will reuse the wrong component state:
> ```javascript
> // WRONG — index changes when list reorders
> items.map((item, index) => <Card key={index} />)
>
> // RIGHT — use a stable, unique identifier
> items.map(item => <Card key={item.id} />)
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Render a list of items with unique keys
- [ ] Implement filter and search on a list
- [ ] Use conditional rendering to show loading, error, and success states

</details>

---

## Phase 5: Effects & Lifecycle

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Run side effects — fetch data, set up subscriptions, interact with the browser.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What Are Side Effects | Anything outside React's render: API calls, timers, DOM manipulation, subscriptions |
| 2 | `useEffect` Basics | `useEffect(() => { /* runs after render */ })` — synchronize your component with external systems |
| 3 | Dependency Array | `[]` = run once on mount. `[value]` = run when `value` changes. No array = run after every render |
| 4 | Cleanup Function | `return () => { clearInterval(id) }` — runs when the component unmounts or before the effect re-runs |
| 5 | Data Fetching | Fetch API data inside `useEffect`, handle loading and error states, update state with the response |
| 6 | Avoiding Infinite Loops | Setting state inside `useEffect` without proper dependencies → infinite re-render loop |
| 7 | Multiple Effects | Use separate `useEffect` hooks for separate concerns — don't combine unrelated logic |
| 8 | Stale Closures | Effects capture variables from the render they were created in. Use the updater function or refs to get fresh values |

> [!CAUTION]
> The most common `useEffect` bug — an infinite loop:
> ```javascript
> // INFINITE LOOP — fetches on every render because no dependency array
> useEffect(() => {
>   fetch('/api/data').then(r => r.json()).then(setData);
> }); // Missing []!
>
> // CORRECT — runs only once on mount
> useEffect(() => {
>   fetch('/api/data').then(r => r.json()).then(setData);
> }, []); // Empty array = run once
> ```

<details>
<summary><strong>Quick Reference: useEffect Dependency Array</strong></summary>

| Dependency Array | When Effect Runs | Use Case |
|-----------------|------------------|----------|
| Not provided | After every render | Rarely needed — usually a mistake |
| `[]` | Once, on mount | Fetch initial data, set up subscriptions |
| `[a, b]` | When `a` or `b` changes | Re-fetch when filters change, sync with prop |
| Cleanup returned | On unmount / before re-run | Clear timers, remove listeners, cancel requests |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data from an API with `useEffect` and display loading/error states
- [ ] Write a cleanup function that clears a timer or cancels a subscription
- [ ] Explain what causes an infinite loop in `useEffect`

</details>

---

## Phase 6: React Hooks Deep Dive

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master the hooks beyond `useState` and `useEffect`.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `useRef` | Create a reference to a DOM element or store a mutable value that doesn't trigger re-renders |
| 2 | `useReducer` | `const [state, dispatch] = useReducer(reducer, initial)` — manage complex state with actions, like a mini Redux |
| 3 | `useMemo` | `useMemo(() => expensiveCalc(data), [data])` — cache the result of an expensive computation |
| 4 | `useCallback` | `useCallback(fn, [deps])` — cache a function definition so it doesn't change every render |
| 5 | Custom Hooks | Extract reusable logic into `useLocalStorage()`, `useFetch()`, `useDebounce()` — must start with `use` |
| 6 | `useId` | Generate unique IDs for accessibility attributes — connects labels to inputs without conflicts |
| 7 | Rules of Hooks | Only call hooks at the top level (never inside conditions/loops). Only call hooks from React functions |
| 8 | When to Use Which | `useState` for simple state, `useReducer` for complex state, `useMemo`/`useCallback` only after profiling |

> [!IMPORTANT]
> **Don't reach for `useMemo` or `useCallback` by default.** They add complexity. Only use them when you've confirmed a performance problem with React DevTools Profiler. Most components don't need them.

<details>
<summary><strong>Quick Reference: Hooks Comparison</strong></summary>

| Hook | Purpose | Returns | When to Use |
|------|---------|---------|-------------|
| `useState` | Simple state | `[value, setter]` | Counters, toggles, form inputs |
| `useReducer` | Complex state logic | `[state, dispatch]` | Multiple sub-values, complex transitions |
| `useEffect` | Side effects | Cleanup function | API calls, subscriptions, DOM interaction |
| `useRef` | Mutable reference | `{ current: value }` | DOM elements, previous values, timers |
| `useMemo` | Cache a value | Memoized value | Expensive calculations |
| `useCallback` | Cache a function | Memoized function | Stable callbacks for child components |
| `useContext` | Read context | Context value | Theme, auth, language (global state) |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `useRef` to focus an input programmatically
- [ ] Build a custom hook (e.g., `useLocalStorage` or `useFetch`)
- [ ] Refactor a complex `useState` into `useReducer`

</details>

---

## Phase 7: Context & State Management

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Share data across components without prop drilling.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Prop Drilling Problem | Passing props through 5 levels of components just so a deeply nested child can use it — painful to maintain |
| 2 | Context API | `createContext()` + `<Context.Provider value={data}>` — make data available to any descendant component |
| 3 | `useContext` Hook | `const value = useContext(MyContext)` — consume context anywhere without wrapping in a Consumer |
| 4 | Context Best Practices | Split contexts by concern (auth, theme, language). Don't put everything in one giant context |
| 5 | Context Limitations | Context re-renders every consumer when the value changes. Not ideal for frequently updating state |
| 6 | Zustand | Lightweight state management (3KB). Simple API: `const useStore = create(set => ({}))` — great for most apps |
| 7 | Redux (Overview) | Actions → Reducers → Store pattern. Use for large, complex apps with many developers. Redux Toolkit simplifies it |
| 8 | Choosing State Management | Local state (`useState`) → Shared state (lift up) → App-wide UI state (Context) → Complex global state (Zustand/Redux) |

> [!TIP]
> **State management decision guide:**
> - Simple local state → `useState`
> - Complex local state → `useReducer`
> - Theme/auth/language → Context API
> - Medium app, shared state → Zustand
> - Large team, complex flows → Redux Toolkit
> - Server data (API caching) → TanStack Query

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Implement dark/light mode with Context API
- [ ] Replace prop drilling with `useContext` in a project
- [ ] Build a small app using Zustand for global state

</details>

---

## Phase 8: React Router

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Build multi-page apps with client-side routing — no page reloads.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Router Setup | `npm install react-router-dom`, wrap app in `<BrowserRouter>`, define routes with `<Routes>` and `<Route>` |
| 2 | Basic Routes | `<Route path="/" element={<Home />} />` — map URLs to components |
| 3 | Navigation | `<Link to="/about">` (no reload) vs `<a href>` (full reload). `<NavLink>` adds active styling automatically |
| 4 | Route Parameters | `<Route path="/user/:id" />` + `const { id } = useParams()` — dynamic URLs |
| 5 | Nested Routes | Routes inside routes + `<Outlet />` — shared layouts (navbar stays, content changes) |
| 6 | Programmatic Navigation | `const navigate = useNavigate()` + `navigate('/dashboard')` — redirect after form submission or login |
| 7 | Protected Routes | Check auth status before rendering a route — redirect to login if not authenticated |
| 8 | 404 Page | `<Route path="*" element={<NotFound />} />` — catch all undefined routes |

> [!TIP]
> Use `<NavLink>` instead of `<Link>` for navigation menus. It automatically adds an `active` class to the current page link:
> ```jsx
> <NavLink
>   to="/about"
>   className={({ isActive }) => isActive ? "nav-active" : ""}
> >
>   About
> </NavLink>
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up React Router with 3+ routes and a shared layout
- [ ] Create a dynamic route with `useParams`
- [ ] Implement a protected route that redirects to login

</details>

---

## Phase 9: Performance & Patterns

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Optimize your app and learn advanced component patterns.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `React.memo` | Wrap a component to skip re-renders when props haven't changed (shallow comparison) |
| 2 | Code Splitting | `React.lazy(() => import('./Page'))` — load components only when needed, reducing initial bundle size |
| 3 | `Suspense` | `<Suspense fallback={<Spinner />}>` — show loading UI while lazy components or data load |
| 4 | Error Boundaries | Catch errors in the component tree and show a fallback UI instead of a white screen crash |
| 5 | React DevTools Profiler | Identify which components re-render and why. Measure render times. Find performance bottlenecks |
| 6 | Virtual Scrolling | Render only visible items in long lists (react-window, react-virtualized) — handles 10,000+ items smoothly |
| 7 | Compound Components | Build flexible APIs like `<Tabs><Tab>One</Tab><Tab>Two</Tab></Tabs>` — related components that share state implicitly |
| 8 | Render Props & HOCs | Share logic between components. Mostly replaced by hooks, but still used in libraries |

> [!IMPORTANT]
> **Profile before you optimize.** Open React DevTools → Profiler → record an interaction → see which components re-rendered and how long they took. Don't add `React.memo`, `useMemo`, or `useCallback` without evidence they'll help.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Lazy-load a route with `React.lazy` and `Suspense`
- [ ] Use React DevTools Profiler to identify unnecessary re-renders
- [ ] Add an Error Boundary to catch and display errors gracefully

</details>

---

## Phase 10: Testing & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Write tests that give confidence and follow industry best practices.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Testing Philosophy | Test behavior, not implementation. "Does the user see the right thing?" not "Did state update?" |
| 2 | Vitest Setup | Modern test runner (10-20x faster than Jest). Native ESM and TypeScript support. Vite-compatible |
| 3 | React Testing Library | `render(<App />)`, `screen.getByRole('button')`, `fireEvent.click()` — test like a user |
| 4 | Testing Components | Render, interact, assert: render the component → simulate user action → check the result |
| 5 | Testing Hooks | `renderHook(() => useCustomHook())` — test custom hooks independently |
| 6 | Mocking API Calls | MSW (Mock Service Worker) — intercept network requests at the service worker level. No mocking fetch |
| 7 | Accessibility Testing | `eslint-plugin-jsx-a11y` catches issues in code. `axe-core` catches issues in tests. Both together = accessible components |
| 8 | Component Organization | Feature-based folder structure, co-locate tests with components, separate concerns clearly |
| 9 | TypeScript with React | Type props with `interface`, type events with `React.ChangeEvent<HTMLInputElement>`, generic components |
| 10 | Production Checklist | Lighthouse audit (90+), error boundaries, loading states, accessibility, SEO meta tags |

> [!TIP]
> Use accessible queries in tests — they also verify your component is accessible:
> ```javascript
> // GOOD — tests accessibility AND functionality
> screen.getByRole('button', { name: 'Submit' })
>
> // BAD — bypasses accessibility, brittle
> screen.getByTestId('submit-btn')
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 5+ tests for a component using React Testing Library
- [ ] Mock an API call with MSW in a test
- [ ] Score 90+ on Lighthouse for a React project

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most React developers:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Mutating state directly | `state.items.push(x)` — React doesn't detect the change, no re-render | Create new arrays/objects: `setState([...items, x])` |
| 2 | Missing keys on lists | React can't track which items changed, causing bugs and lost state | Use unique IDs: `key={item.id}`, never array indices |
| 3 | `useEffect` infinite loops | Setting state inside `useEffect` without proper dependencies → infinite re-renders | Add a dependency array. Use `[]` for "run once" |
| 4 | Calling handler instead of passing | `onClick={handleClick()}` calls it immediately on render | Pass the function: `onClick={handleClick}` |
| 5 | Props drilling 10 levels deep | Passing data through components that don't use it — fragile, hard to refactor | Use Context API or Zustand for deeply shared state |
| 6 | Not cleaning up effects | Intervals, subscriptions, listeners keep running after unmount → memory leaks | Return a cleanup function from `useEffect` |
| 7 | `useCallback`/`useMemo` everywhere | Adds complexity and memory overhead without actual benefit in most cases | Profile first. Only optimize when you've measured a problem |
| 8 | Using `class` instead of `className` | `class` is a reserved JavaScript keyword — won't work in JSX | Always use `className` for CSS classes |
| 9 | Not using React DevTools | Debugging with `console.log` alone misses component state, props, and re-render info | Install React DevTools browser extension |
| 10 | Skipping JavaScript fundamentals | Confusing React problems with JavaScript gaps — closures, `this`, async, destructuring | Master vanilla JS before React |

---

## Interview Questions

Test your React knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is JSX?**
   - JSX is a syntax extension that lets you write HTML-like code in JavaScript. It compiles to `React.createElement()` calls. It's not valid JavaScript — Babel transpiles it. You can embed JS expressions with `{}`.

2. **What's the difference between props and state?**
   - Props are read-only data passed from parent to child (like function arguments). State is internal data managed by the component itself (like local variables). Props flow down, state can be updated and triggers re-renders.

3. **What is the virtual DOM?**
   - A lightweight JavaScript representation of the real DOM. When state changes, React creates a new virtual DOM, diffs it against the previous one (reconciliation), and only updates the changed parts in the real DOM. This is why React is fast.

4. **What is a controlled component?**
   - A form element whose value is driven by React state. The input's `value` is tied to state, and `onChange` updates that state. React is the "single source of truth" for the input's value. The alternative (uncontrolled) uses refs to read DOM values directly.

5. **Why do list items need keys?**
   - Keys help React identify which items changed, were added, or removed during re-renders. Without keys (or with index keys), React can't efficiently reconcile list changes and may reuse wrong component instances, causing state bugs.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain `useEffect` cleanup. When does it run?**
   - The cleanup function runs: (1) when the component unmounts, and (2) before the effect re-runs on subsequent renders. It's essential for clearing timers, removing event listeners, and canceling API requests to prevent memory leaks and stale updates.

2. **What are custom hooks and why would you create one?**
   - Custom hooks are functions starting with `use` that encapsulate reusable stateful logic. They let you share behavior (not UI) between components. Example: `useLocalStorage()` wraps `useState` + `localStorage` sync. They follow the same rules as built-in hooks.

3. **Context API vs Redux — when to use which?**
   - Context API: built-in, best for infrequent updates (theme, auth, language). Re-renders all consumers on change. Redux: external library, best for complex apps with frequent state updates, many developers, and need for middleware/devtools. Use Zustand as a simpler Redux alternative.

4. **What is `React.memo` and when should you use it?**
   - `React.memo` wraps a component to skip re-renders if props haven't changed (shallow comparison). Use it when a component is expensive to render AND receives the same props frequently. Don't use it everywhere — it adds overhead. Always profile first.

5. **How does `useReducer` differ from `useState`?**
   - `useReducer` manages state with a reducer function and dispatched actions — like a mini Redux. Use it when state logic is complex (multiple sub-values, transitions depending on previous state). `useState` is simpler and better for independent pieces of state.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain React's reconciliation algorithm.**
   - When state changes, React builds a new virtual DOM tree and diffs it against the old one. It compares elements by type: same type = update props/attributes, different type = unmount old and mount new. For lists, `key` props tell React which items to match. This "diffing" runs in O(n) time.

2. **What is React's Fiber architecture?**
   - Fiber is React's reconciliation engine (since React 16). It splits rendering work into units (fibers) that can be paused, resumed, and prioritized. This enables: interruptible rendering (user input gets priority), concurrent features (Suspense, transitions), and better performance for complex UIs.

3. **What are React Server Components?**
   - Server Components run on the server and send rendered HTML to the client — zero JavaScript shipped for these components. They can access databases and file systems directly. Client Components (`"use client"`) handle interactivity. This reduces bundle size and improves performance. Used in Next.js App Router.

4. **What is hydration in SSR?**
   - The server pre-renders HTML and sends it to the client (fast initial paint). Hydration is the process where React attaches event listeners and state to this pre-rendered HTML, making it interactive. Selective hydration (React 18+) prioritizes hydrating visible/interacted-with parts first.

5. **How do you prevent unnecessary re-renders in a large app?**
   - (1) Use React DevTools Profiler to identify slow components. (2) `React.memo` for pure components with stable props. (3) `useCallback`/`useMemo` to stabilize props passed to memoized children. (4) Split Context by concern so updates don't re-render unrelated consumers. (5) Use state colocation — keep state close to where it's used. (6) Virtual scrolling for long lists.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Recipe Finder App
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** Search recipes by ingredient, display results as cards, click for full details. Data from a local JSON array.

**Skills practiced:** Components, props, state, events, lists, keys, conditional rendering, controlled inputs.

---

### Project 2: Movie Database (API)
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** Search movies using the OMDB or TMDB API, display results, view details, save favorites. Handle loading, errors, and empty states.

**Skills practiced:** `useEffect`, data fetching, custom hooks (`useFetch`), `useRef`, loading/error states.

---

### Project 3: E-Commerce Store
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** Product listing, category filters, shopping cart (add/remove/quantity), checkout page. Multi-page with React Router.

**Skills practiced:** Context API for cart state, React Router (nested routes, params), `useReducer`, protected routes.

---

### Project 4: Real-Time Dashboard
![Phase 9](https://img.shields.io/badge/After-Phase%209-orange)

**What you'll build:** A dashboard with live-updating data cards, charts, lazy-loaded sections, and error boundaries. Smooth performance with 50+ components.

**Skills practiced:** `React.memo`, code splitting, `Suspense`, Error Boundaries, React DevTools profiling, virtual scrolling.

---

### Project 5: Full-Stack Social App
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** User auth, posts feed, comments, likes, profile pages, dark mode. Fully tested with 80%+ coverage and accessible.

**Skills practiced:** Everything from all phases — your React graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [react.dev — Learn React](https://react.dev/learn) | The official React docs. Completely rewritten in 2023 — interactive examples, modern patterns, hooks-first |
| [react.dev — API Reference](https://react.dev/reference/react) | Complete reference for every hook, component, and API. The source of truth |
| [MDN — React Getting Started](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started) | Mozilla's React intro — connects React to your existing JS/HTML knowledge |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Front End Libraries](https://www.freecodecamp.org/learn/front-end-development-libraries/) | Free certification. Build 5 projects including a random quote machine and a Pomodoro clock |
| [The Odin Project — React Course](https://www.theodinproject.com/paths/full-stack-javascript/courses/react) | Project-based. Teaches React the way you'd learn it on a team — build real things |
| [Codecademy — Learn React](https://www.codecademy.com/learn/react-101) | Interactive, in-browser lessons. Great for beginners who want guided, step-by-step learning |
| [Scrimba — Learn React](https://scrimba.com/learn/learnreact) | Pause any video and edit the instructor's code. 15+ hours of interactive content |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Traversy Media — React Crash Course](https://www.youtube.com/@TraversyMedia) | Best first React video. Build a project from scratch in ~2 hours |
| [The Net Ninja — Full React Tutorial](https://www.youtube.com/@NetNinja) | Well-paced playlist. Each video covers one concept with a mini project |
| [Codevolution — React Tutorial](https://www.youtube.com/@Codevolution) | Structured series — one of the most systematic React tutorials on YouTube |
| [Jack Herrington](https://www.youtube.com/@jherr) | Advanced React patterns, performance, and architecture for intermediate+ devs |
| [Fireship — React in 100 Seconds](https://www.youtube.com/@Fireship) | Fast, visual overview. Watch first to get the big picture before diving deep |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — React](https://roadmap.sh/react) | Interactive learning path — click each topic to see resources. Track your progress |

### Practice & Build Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional designs to build. Filter by "React" for framework-specific challenges |
| [DevChallenges](https://devchallenges.io/) | Full-stack project challenges. React-specific projects with varying difficulty |
| [React Projects Collection (GitHub)](https://github.com/vishal-dcode/100-React-Projects) | 100 React project ideas with increasing complexity |
| [JavaScript30](https://javascript30.com/) | 30 vanilla JS projects — rebuild them in React to practice thinking in components |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [ES7+ React Snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets) | Type `rafce` → full component boilerplate. Saves massive time |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Catches bugs and enforces rules. Install `eslint-plugin-react-hooks` for hook dependency warnings |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format on save. Consistent JSX formatting |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | Shows errors inline — see problems immediately without hovering |
| [Console Ninja](https://marketplace.visualstudio.com/items?itemName=niceplusplus.console-ninja) | See console output next to your code — faster debugging |
| [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) | Shows the size of imported packages inline — watch your bundle size |

### Component Libraries

| Library | Best For |
|---------|---------|
| [shadcn/ui](https://ui.shadcn.com/) | Copy-paste Tailwind components. Not a dependency — you own the code. Most popular choice in 2025+ |
| [Radix UI](https://www.radix-ui.com/) | Headless, accessible component primitives. Build your own design system on top |
| [Material UI (MUI)](https://mui.com/) | Google's Material Design. Huge component library, most mature option |
| [Mantine](https://mantine.dev/) | 100+ components with hooks. Great docs, active community |
| [Chakra UI](https://chakra-ui.com/) | Accessible, themeable. Good balance of flexibility and convenience |

### Development Tools

| Tool | What It Does |
|------|-------------|
| [React DevTools](https://react.dev/learn/react-developer-tools) | Browser extension. Inspect component tree, props, state, hooks. Profile performance |
| [Vite](https://vitejs.dev/) | Build tool. Instant dev server, fast HMR, optimized production builds |
| [TanStack Query](https://tanstack.com/query) | Server state management. Caching, background refetching, pagination — handles API data the right way |
| [React Router](https://reactrouter.com/) | Client-side routing. The standard for multi-page React apps |
| [Zustand](https://github.com/pmndrs/zustand) | Lightweight global state (3KB). Simple API, no boilerplate |
| [Vitest](https://vitest.dev/) | Test runner built for Vite. 10-20x faster than Jest, native ESM support |
| [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) | Test components by simulating user behavior, not implementation details |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [react.dev Quick Start](https://react.dev/learn) | Official guide — the best structured overview of core concepts |
| [React TypeScript Cheatsheet](https://react-typescript-cheatsheet.netlify.app/) | Community guide for typing React components, hooks, and patterns |
| [React Hooks Cheatsheet](https://react-hooks-cheatsheet.com/) | Interactive examples for every built-in hook |

---

[Back to Main Syllabus](../README.md)

# React Syllabus

A complete, structured learning path for React — your one-stop guide from your first component to building production-ready apps with hooks, routing, server state, Server Components, and the entire 2026 ecosystem (Next.js, shadcn/ui, TanStack Query, Tailwind, react-hook-form, Zustand, Vitest). Whether you have never touched React or you've been writing it for years and want to fill the gaps, this syllabus walks through every concept in the right order, explains *why* each matters, lists the **frameworks and libraries** you'll meet on the job, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 14-18 Weeks](https://img.shields.io/badge/Duration-14--18%20Weeks-blue)
![Topics: 15 Phases](https://img.shields.io/badge/Topics-15%20Phases-orange)
![React: 19+](https://img.shields.io/badge/React-19%2B-61DAFB)

---

## Table of Contents

- [What is React?](#what-is-react)
- [Why Learn React in 2026?](#why-learn-react-in-2026)
- [How React Works](#how-react-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: JSX, Components & Props](#phase-2-jsx-components--props)
- [Phase 3: State & Events](#phase-3-state--events)
- [Phase 4: Rendering, Lists & Conditional UI](#phase-4-rendering-lists--conditional-ui)
- [Phase 5: Effects & Lifecycle](#phase-5-effects--lifecycle)
- [Phase 6: Hooks Deep Dive](#phase-6-hooks-deep-dive)
- [Phase 7: Forms & Validation](#phase-7-forms--validation)
- [Phase 8: State Management](#phase-8-state-management)
- [Phase 9: Server State & Data Fetching](#phase-9-server-state--data-fetching)
- [Phase 10: Routing & Navigation](#phase-10-routing--navigation)
- [Phase 11: Performance, Suspense & Concurrent React](#phase-11-performance-suspense--concurrent-react)
- [Phase 12: Modern React — Server Components & Next.js](#phase-12-modern-react--server-components--nextjs)
- [Phase 13: Testing, TypeScript & Modern Tooling](#phase-13-testing-typescript--modern-tooling)
- [Phase 14: The React Ecosystem](#phase-14-the-react-ecosystem)
- [Phase 15: What's Next? (Specializations & Deploy)](#phase-15-whats-next-specializations--deploy)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is React?

**React is a JavaScript library for building user interfaces — based on the radical idea that UI is a function of state.** Type a value into a search box, the list filters. Click "like", the heart fills in. Add an item to your cart, the badge updates. In old-school JavaScript, you'd manually find each affected DOM element and patch it. In React, you change a value, and React figures out what to redraw.

Created by **Jordan Walke at Meta (Facebook) in 2011** and open-sourced in 2013, React rewrote the web app development playbook. Today it powers Facebook, Instagram, Netflix, Airbnb, Uber, Shopify, Discord, WhatsApp Web, the Anthropic Console — and roughly half of all new web apps shipping in 2026. Its sister project **React Native** powers Instagram, Discord, Bloomberg, and tens of thousands of mobile apps.

In simple words:

- **HTML** describes structure. **CSS** describes appearance. **React** describes behavior + structure together — as **components**.
- A **component** is a function that takes data (props) and returns JSX (HTML-like syntax inside JS).
- React keeps your UI in sync with your state. **You change the state; React updates the DOM.**

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 2013 | React 0.3 | Open-sourced at JSConf US. Skeptically received: "JavaScript inside HTML?!" |
| 2015 | React 0.14 | The split — `react` + `react-dom`. Sets up React Native (also 2015). |
| 2016 | React 15 | Stable. The class-component era. |
| 2017 | React 16 | **Fiber** — interruptible, prioritizable rendering. Error boundaries, fragments, portals. |
| 2019 | React 16.8 | **Hooks!** The biggest paradigm shift in React history. Classes are out. |
| 2022 | React 18 | **Concurrent React**: automatic batching, transitions, Suspense for data, `useDeferredValue`. |
| 2023 | RSC + Next.js App Router | **React Server Components** in production via Next.js 13/14. Server-rendered, zero-JS components. |
| 2024 | React 19 | `use()`, **Server Actions**, automatic memoization (React Compiler preview), form actions, `useOptimistic`. |
| 2025 | React 19 stable + Compiler | The 2026 default. Hooks + Server Components + Compiler-optimized. |

> [!IMPORTANT]
> "Modern React" in 2026 means **React 19 + hooks + functional components + Server Components (via Next.js or similar) + TypeScript**. If a tutorial uses class components, `componentDidMount`, or Create React App — it's outdated. Skip it.

### What Makes React Special

- **Declarative.** You describe *what the UI should look like* for any given state. React figures out the DOM updates.
- **Composable.** Build big UIs from small components. The `<Button>` you wrote on Tuesday gets reused for the next 5 years.
- **Just JavaScript.** No template language to learn — JSX is JS with HTML syntax. If you know JS, you can read React.
- **Massive ecosystem.** Whatever you need — auth, charts, drag-drop, animation, forms — has a battle-tested React library.
- **The hiring filter for frontend.** "React" appears on more frontend job postings than any other framework, by a wide margin.

---

## Why Learn React in 2026?

| Reason | What It Means |
|--------|---------------|
| **#1 frontend framework on Earth** | More open jobs than Vue, Angular, Svelte combined. |
| **Server Components changed full-stack** | Next.js App Router means React isn't just frontend — it's the rendering layer for full-stack apps too. |
| **Owns the AI app stack** | Vercel AI SDK, ChatGPT-style streaming UIs, every LLM playground — built in React. |
| **React Native = mobile** | Same skills ship to iOS + Android. Instagram, Discord, Bloomberg, Shopify, Microsoft Office mobile. |
| **shadcn/ui + Tailwind dominates UI** | The 2026 default React UI stack. Beautiful, accessible, copy-paste. |
| **Massive component library ecosystem** | Hundreds of mature libraries — charts, tables, forms, animation. You rarely build from scratch. |
| **TypeScript is standard** | React + TypeScript is the most-asked frontend skillset on job boards. |
| **Pays well** | Senior React/Next.js salaries in 2026: **$120k–$220k** (US), **₹15L–₹50L** (India). |
| **Job-portable** | Once you know React, switching companies takes a week, not a quarter. |

---

## How React Works

A high-level mental model — internalize this and the rest of the syllabus clicks.

```
       ┌───────────────────────┐
       │     Your component    │  function App() { return <h1>Hi</h1> }
       └───────────┬───────────┘
                   ▼
       ┌───────────────────────┐
       │   JSX → JS calls       │  React.createElement('h1', null, 'Hi')
       └───────────┬───────────┘
                   ▼
       ┌───────────────────────┐
       │      Virtual DOM       │  In-memory tree of React elements
       └───────────┬───────────┘
                   ▼ Reconciliation (diffing)
       ┌───────────────────────┐
       │  Fiber Reconciler     │  Splits work into units, prioritizes
       └───────────┬───────────┘
                   ▼
       ┌───────────────────────┐
       │      Real DOM          │  Browser updates the page
       └───────────────────────┘
```

**Three concepts to internalize:**

1. **Components are functions.** They take props (input), return JSX (output). Re-running a function with different props produces different UI.
2. **State triggers re-renders.** When state changes (`setCount(5)`), React re-runs the component function, gets new JSX, diffs against the old, and updates only the changed DOM nodes.
3. **Data flows down, events flow up.** Parents pass data to children via **props**. Children notify parents via **callback props** (function props). One-way data flow keeps things predictable.

---

## Pick Your Path

React is huge — most people don't need every phase equally. Pick the track that matches your goal. Each one tells you what to focus on, what to skip, and what to do next.

### Track 1 — Frontend Engineer (12–16 weeks)
**Goal:** ship React UIs in the browser. The default track for most React jobs.

Do every phase in order. Spend extra time on **Hooks**, **Forms**, **State Management**, **Server State** (TanStack Query), and **Performance**. Pair with the [JavaScript Syllabus](javascript.md) and [TypeScript Syllabus](typescript.md). Build all 8 [Practice Projects](#practice-projects) and deploy them to Vercel.

### Track 2 — Full-Stack Next.js Developer (16–20 weeks)
**Goal:** ship full-stack React apps with Next.js App Router, Server Components, Server Actions.

All phases, with extra depth on **Server Components & Next.js**, **Server State**, **Routing**, and **Testing**. Pair with the [Node.js Syllabus](nodejs.md) and [SQL Syllabus](sql.md). Master Next.js + Drizzle/Prisma + auth (Clerk/Auth.js) + Vercel deployment. Build the AI capstone project — most hireable demo in 2026.

### Track 3 — Mobile Developer (React Native) (12–16 weeks)
**Goal:** ship iOS + Android apps from a single React codebase.

Cover all React fundamentals through **Hooks Deep Dive**, then **Forms**, **State Management**, **Server State**. Skip the Next.js / RSC phase. Move to **Expo + React Native** — the React fundamentals transfer 95%. Different layout primitives, but the same component model.

### Track 4 — Modernize Your React (4–6 weeks)
**Goal:** you wrote React with classes / Redux / componentDidMount and stopped at React 16.

Skip the language fundamentals. Go straight to **Hooks Deep Dive**, **Server State**, **Performance & Concurrent React**, **Server Components**, and **Modern Tooling**. Replace your class instincts with hooks, Redux with Zustand or TanStack Query, Webpack with Vite, Jest with Vitest, CRA with Next.js or Vite.

### Track 5 — Interview Prep (4–6 weeks)
**Goal:** you already know React and have an interview coming up.

Drill: **Hooks** (especially `useEffect` rules), **State Management** (when to lift, when to context, when to global), **Performance** (memo, lazy, Suspense, when *not* to memoize), **Server Components** (the 2026 favorite topic). Re-read [Common Mistakes](#common-mistakes) and [Interview Questions](#interview-questions). Rebuild a debounced search and an infinite scroll from scratch.

> [!TIP]
> Whichever track you pick, **Phase 3 (State & Events)** and **Phase 5 (Effects & Lifecycle)** are the two phases every track depends on — read them carefully.

---

## Prerequisites

> [!IMPORTANT]
> React is **a JavaScript library — not a language**. You need solid JavaScript fundamentals first. The #1 reason new React devs struggle isn't React; it's the JavaScript underneath.

Before starting, you should be comfortable with:

- **HTML & CSS** — components, classes, semantic elements, Flexbox/Grid
- **JavaScript essentials** — `let`/`const`, arrow functions, destructuring, spread/rest, `map`/`filter`/`reduce`, promises, `async`/`await`, modules (`import`/`export`), `this` (well enough to know arrow functions don't have their own)
- **Closures and async** — they're at the heart of every `useEffect` bug you'll ever write
- **Terminal basics** — `cd`, `ls`, running `npm` commands
- **Node.js + npm** installed (LTS version)
- A code editor — [VS Code](https://code.visualstudio.com/) recommended
- A modern browser — [Chrome](https://www.google.com/chrome/) recommended for React DevTools
- A [GitHub account](https://github.com/) and [Vercel account](https://vercel.com/) (free, for deployments)

If any of the JS topics above feel shaky, do the [JavaScript Syllabus](javascript.md) first — especially Phases 4 (Functions), 5 (Arrays & Objects), 7 (Async). It will save you weeks.

---

## How to Use This Syllabus

1. **Don't skip phases.** Each builds on the last. If hooks (Phase 6) feel mysterious, the answer is almost always Phase 3 (State) or Phase 5 (Effects).
2. **Type the code yourself.** Copy-pasting gives the illusion of learning. Type every example.
3. **Use TypeScript from Phase 6+.** Almost every job uses TypeScript. Starting early is easier than retrofitting.
4. **Install React DevTools.** Browser extension — inspect component trees, props, state, profile renders. Non-negotiable.
5. **Build the project at the end of each phase block.** Reading is not the same as doing.
6. **Deploy every project.** Push to GitHub → Vercel auto-deploys. Free, instant, real.
7. **Read other people's React.** Browse the source of [shadcn/ui](https://github.com/shadcn-ui/ui), [TanStack Query](https://github.com/TanStack/query), Vercel templates. Pros read more code than they write.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Understand what React is and build your first component.

**What this phase is about.** Set up a real React project the modern way (**Vite**, not the deprecated Create React App), understand what each generated file does, write your first component, and render it. Plus the **mental model**: components are functions, JSX is just JS, and React keeps the DOM in sync with state.

**Why it matters.** Habits formed here (always Vite, always TypeScript-ready, components are functions, `index.html` is just an entry point) shape every project you build for years. Get them right now.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is React | A library for building UIs from reusable components. Created at Meta in 2013 |
| 2 | Why React | Declarative, component-based, predictable state, massive ecosystem |
| 3 | Setting Up with Vite | `npm create vite@latest my-app -- --template react-ts` — the 2026 standard |
| 4 | Why Not CRA? | Create React App is officially deprecated. Vite is faster, ESM-first, zero config |
| 5 | Project Structure | `src/`, `public/`, `index.html`, `main.tsx`, `App.tsx`, `vite.config.ts` |
| 6 | JSX Fundamentals | HTML-like syntax in JS. `{}` for expressions, `className` not `class`, self-closing tags |
| 7 | Your First Component | A function returning JSX. Must start with a capital letter |
| 8 | Rendering to the DOM | `createRoot(document.getElementById('root')).render(<App />)` |
| 9 | StrictMode | The double-invoke that catches side-effect bugs |
| 10 | React DevTools | Browser extension. Inspect tree, props, state, hooks, profiler |

> [!TIP]
> Use **Vite** + the **TypeScript template** for every new React project in 2026:

```bash
npm create vite@latest my-app -- --template react-ts
cd my-app
npm install
npm run dev
```

<details>
<summary><strong>Quick Reference: JSX Rules</strong></summary>

| Rule | Wrong | Right |
|------|-------|-------|
| One root element | `return <h1>Hi</h1><p>Text</p>` | `return <><h1>Hi</h1><p>Text</p></>` |
| Close all tags | `<img>`, `<br>`, `<input>` | `<img />`, `<br />`, `<input />` |
| Use `className` | `<div class="box">` | `<div className="box">` |
| Use `htmlFor` | `<label for="name">` | `<label htmlFor="name">` |
| JS in curly braces | `<p>Hello name</p>` | `<p>Hello {name}</p>` |
| camelCase events | `<button onclick={}>` | `<button onClick={}>` |
| Component = capital | `<button>` (HTML) vs `<Button>` (React) | Always capitalize React components |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a Vite + React + TS project, run it locally
- [ ] Install React DevTools and inspect a component
- [ ] Write a component that renders JSX with dynamic expressions
- [ ] Explain why React uses a virtual DOM

</details>

---

## Phase 2: JSX, Components & Props

![Phase](https://img.shields.io/badge/Phase-2%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Break your UI into reusable pieces and pass data between them.

**What this phase is about.** Components — the unit of React. **Props** are how parents pass data to children. **Composition** (small components inside bigger components) is how complex UIs are built without copy-pasting. The `children` prop turns components into wrappers (`<Card>...anything inside...</Card>`). Plus the **golden rule**: props are read-only.

**Why it matters.** "Think in components" is the React mindset. Once it clicks, every UI feels like Lego — you compose, never duplicate. Mid-level interviews ask "given this design, how would you split it into components?" Pass that and you pass interviews.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Function Components | The only kind in modern React. Functions returning JSX |
| 2 | Props | Pass data like HTML attributes: `<Card title="Hello" />`. Inside the component: `props.title` |
| 3 | Destructuring Props | `function Card({ title, description })` — cleaner than `props.title` |
| 4 | Default Values | `function Button({ variant = "primary" })` |
| 5 | Props are Read-Only | Never mutate `props.x = ...`. Data flows down only |
| 6 | The `children` Prop | `<Card><h2>Hi</h2></Card>` — `children` is whatever's between the tags |
| 7 | Component Composition | Build bigger from smaller. `<Page>` contains `<Header>`, `<Sidebar>`, `<Main>` |
| 8 | TypeScript Props | `interface ButtonProps { label: string; onClick: () => void; }` |
| 9 | Rendering Lists (intro) | `{items.map(item => <Item key={item.id} {...item} />)}` |
| 10 | Spread Props | `<Component {...props} />` — pass through. Use carefully |
| 11 | Component Naming & Files | One component per file usually. Match component name to file (PascalCase) |
| 12 | Prop Drilling (preview) | When you pass a prop through many layers — you'll fix this in Phase 8 |

> [!IMPORTANT]
> **Components are just functions.** If a function returns JSX and starts with a capital letter, it's a component. Props are function arguments. Nothing magical.

<details>
<summary><strong>Visual: Data Flow in React</strong></summary>

```
       ┌──────────┐
       │   App     │  ← state lives here
       └────┬─────┘
            │ props ↓
       ┌────┴─────┐
       │  Header   │  ← receives via props
       └──────────┘
            │ props ↓
       ┌────┴─────┐
       │  NavBar   │  ← also receives via props
       └──────────┘

  Data flows DOWN (props)
  Events flow UP   (callbacks)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create 5+ reusable components and compose them
- [ ] Pass and destructure props with TypeScript types
- [ ] Use the `children` prop to build a `<Card>` wrapper
- [ ] Render a list with unique keys

</details>

---

## Phase 3: State & Events

![Phase](https://img.shields.io/badge/Phase-3%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make components interactive — clicks, inputs, form submits, all driven by state.

**What this phase is about.** Components are static until they hold **state**. The `useState` hook gives them memory: a counter that ticks, a modal that opens, a search that filters. Event handlers (`onClick`, `onChange`, `onSubmit`) are how state changes happen. **Controlled components** mean React owns input values — the React way to handle forms.

**Why it matters.** Every interactive React app reduces to: *state + event handlers + re-renders*. Get this triangle right and you can build anything. Get it wrong and your app fights you.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `useState` | `const [count, setCount] = useState(0)`. Calling the setter re-renders |
| 2 | State is Per-Render Snapshot | Each render captures its own values. This trips up everyone — read it twice |
| 3 | Updater Functions | `setCount(prev => prev + 1)` — when next state depends on previous |
| 4 | Event Handling | `onClick`, `onChange`, `onSubmit`. Pass functions, never call them: `onClick={fn}` not `onClick={fn()}` |
| 5 | The Synthetic Event | React wraps native events. `e.target.value`, `e.preventDefault()` |
| 6 | Controlled Components | `<input value={text} onChange={e => setText(e.target.value)} />` — React owns the input |
| 7 | Multiple State Variables | Independent values → separate `useState`. Related values → one object |
| 8 | State Immutability | NEVER mutate. `setItems([...items, newItem])`, `setUser({...user, name: 'Bob'})` |
| 9 | Lifting State Up | When siblings share data, move state to their parent |
| 10 | Batching | React 18+ batches multiple `setState` calls in event handlers, promises, timeouts |
| 11 | When to Initialize Lazily | `useState(() => expensiveCalc())` runs the initializer once |
| 12 | TypeScript State | `useState<string>('')`, `useState<User \| null>(null)` |

> [!CAUTION]
> **Never mutate state directly.** This is the #1 React bug:

```jsx
// WRONG — React doesn't detect the change, no re-render
state.items.push(newItem);
setState(state);

// RIGHT — create a new array
setState(prev => [...prev, newItem]);
```

<details>
<summary><strong>Quick Reference: Common Event Handlers</strong></summary>

| Event | Element | Use Case |
|-------|---------|----------|
| `onClick` | Buttons, divs | Clicks, toggles |
| `onChange` | Inputs, selects, textareas | Input changes |
| `onSubmit` | Forms | Form submission |
| `onFocus` / `onBlur` | Inputs | Focus/blur |
| `onKeyDown` | Inputs, document | Keyboard shortcuts |
| `onMouseEnter` / `onMouseLeave` | Any | Hover effects |
| `onScroll` | Any scroll container | Scroll handlers |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a counter with `+`, `-`, reset, using updater function
- [ ] Build a controlled form with text, select, checkbox, radio, textarea
- [ ] Lift state up to share between sibling components
- [ ] Explain why mutating state breaks React

</details>

---

## Phase 4: Rendering, Lists & Conditional UI

![Phase](https://img.shields.io/badge/Phase-4%2F15-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Show, hide, and repeat UI based on data.

**What this phase is about.** Render different UI for different conditions (`isLoggedIn ? <Dashboard /> : <Login />`). Render lists from arrays (`items.map(...)`). Use **keys** so React tracks list items correctly across re-renders.

**Why it matters.** Every real app shows different things at different times — loading, error, success, empty. Master this here and you'll never write a `<div>{state.is_loading_now ? "..." : ...}</div>` mess again.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Conditional with Ternary | `{isLoggedIn ? <Dashboard /> : <Login />}` |
| 2 | Conditional with `&&` | `{showModal && <Modal />}` — render only when true |
| 3 | Multiple Branches | When ternaries get nested, extract to a function or use `if/return` |
| 4 | Rendering Lists | `{items.map(item => <Card key={item.id} {...item} />)}` |
| 5 | The `key` Prop | Stable, unique per sibling. **Never use array index** if items can move |
| 6 | Filtering & Sorting | `{items.filter(i => i.active).sort((a,b) => a.name.localeCompare(b.name)).map(...)}` |
| 7 | Empty States | `{items.length === 0 ? <Empty /> : <List items={items} />}` |
| 8 | Loading / Error / Success | The three-state UI pattern: loading → success or error |
| 9 | Fragments | `<>...</>` or `<React.Fragment key={id}>` — group without an extra DOM node |
| 10 | Why `&&` with numbers can bite you | `{count && <Foo />}` renders `0` if count is 0 |

> [!WARNING]
> **Never use the array index as a key** when items can be reordered, added, or removed:

```jsx
// WRONG — index changes when list reorders
items.map((item, i) => <Card key={i} />)

// RIGHT — stable, unique identifier
items.map(item => <Card key={item.id} />)
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Render a list with stable keys
- [ ] Implement a search/filter on a list
- [ ] Show loading, error, success, and empty states
- [ ] Use a Fragment to avoid an extra `<div>`

</details>

---

## Phase 5: Effects & Lifecycle

![Phase](https://img.shields.io/badge/Phase-5%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Run side effects — fetch data, set up subscriptions, talk to non-React code.

**What this phase is about.** Pure components (input → JSX) cover 80% of React. The other 20% is **side effects**: fetching from APIs, subscribing to events, integrating with third-party libraries, manipulating the DOM directly. The `useEffect` hook is how you do that — and how you safely *clean up* (cancel timers, unsubscribe, abort fetches) when the component unmounts.

**Why it matters.** Every "why does my data load 3 times?" / "why is my page leaking memory?" / "why doesn't this update?" question traces to `useEffect` mistakes. This phase is the gateway between "React beginner" and "React capable."

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What Are Side Effects | Anything outside pure render: API calls, timers, DOM, subscriptions, logging |
| 2 | `useEffect` Basics | `useEffect(() => { ... })` — runs *after* render |
| 3 | Dependency Array | `[]` = mount only. `[a, b]` = run when `a` or `b` changes. Missing = every render |
| 4 | Cleanup Function | `return () => { clearInterval(id); abort.abort(); }` |
| 5 | Data Fetching | `fetch` inside `useEffect`, handle loading/error/success — **but prefer TanStack Query (Phase 9)** |
| 6 | AbortController | Cancel fetches on unmount or re-fetch |
| 7 | Avoiding Infinite Loops | Setting state in `useEffect` without deps = infinite re-renders |
| 8 | Stale Closures | Effects capture variables from the render they ran in. Use updater fn or refs |
| 9 | StrictMode Double Invocation | Effects run twice in dev — exposes cleanup bugs early |
| 10 | When NOT to use Effects | Derived state? Compute during render. Event response? Use the handler. The 2024 React docs preach this |
| 11 | Multiple Effects | Separate concerns into separate effects |
| 12 | Effect → Subscription Pattern | `addEventListener` + cleanup `removeEventListener` |

> [!CAUTION]
> The classic infinite loop:

```jsx
// INFINITE — fetches on every render
useEffect(() => {
  fetch('/api/data').then(r => r.json()).then(setData);
}); // missing []!

// CORRECT — fetches once
useEffect(() => {
  fetch('/api/data').then(r => r.json()).then(setData);
}, []); // empty deps = once
```

> [!IMPORTANT]
> The 2024 React team's official guidance: **"You might not need an Effect."** If you're computing something from props/state, do it during render. If responding to a user event, do it in the handler. Effects are only for *synchronizing with external systems* (network, browser APIs, third-party libraries).

<details>
<summary><strong>Quick Reference: useEffect Dependency Array</strong></summary>

| Array | When Effect Runs | Use Case |
|-------|------------------|----------|
| Not provided | After every render | Almost always a mistake |
| `[]` | Once on mount, cleanup on unmount | Initial fetch, set up listeners |
| `[a, b]` | When `a` or `b` changes | Re-run when filters change |
| Cleanup returned | On unmount + before each re-run | Clear timers, abort fetches |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Fetch data in `useEffect` with loading + error states
- [ ] Cancel an in-flight fetch with `AbortController`
- [ ] Write cleanup for `setInterval` and a window event listener
- [ ] Identify a "you don't need an effect" case and refactor

</details>

---

## Phase 6: Hooks Deep Dive

![Phase](https://img.shields.io/badge/Phase-6%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Master every hook beyond `useState` and `useEffect` — and write your own.

**What this phase is about.** The full hooks toolkit: `useRef` (for DOM elements and mutable values), `useReducer` (for complex state), `useMemo` and `useCallback` (memoization — used carefully), `useId` (unique IDs for accessibility), `useLayoutEffect` (synchronous effect for layout reads), `useTransition` and `useDeferredValue` (concurrent React, Phase 11). Plus **custom hooks** — your own reusable stateful logic.

**Why it matters.** Custom hooks are the React superpower. `useFetch`, `useDebounce`, `useLocalStorage`, `useOnClickOutside` — once you can write these, your codebase shrinks dramatically.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `useRef` for DOM | Focus inputs, measure elements, integrate with non-React libs |
| 2 | `useRef` for Mutable Values | Holds a value across renders without causing re-renders. Timer IDs, previous values |
| 3 | `useReducer` | Action-dispatched state — like mini Redux for one component |
| 4 | When to Reach for `useReducer` | Complex transitions, related sub-state, easier testing |
| 5 | `useMemo` | `useMemo(() => expensiveCalc(deps), [deps])` |
| 6 | `useCallback` | `useCallback(fn, deps)` — stable function reference |
| 7 | When NOT to memoize | The 2024 React Compiler will memoize for you. Don't preemptively wrap everything |
| 8 | `useId` | Generate stable unique IDs across server + client render |
| 9 | `useLayoutEffect` vs `useEffect` | Sync vs async — almost always you want `useEffect` |
| 10 | `use()` (React 19) | Read promises and contexts during render. Replaces some `useEffect`+`useState` patterns |
| 11 | `useDebugValue` | Label custom hooks in DevTools |
| 12 | Rules of Hooks | Top level only — no conditionals, no loops, no early returns. Only inside React functions |
| 13 | Custom Hooks | Functions starting with `use` that call other hooks. The reuse mechanism |
| 14 | Common Custom Hooks | `useDebounce`, `useLocalStorage`, `useOnClickOutside`, `useMediaQuery`, `useIntersectionObserver` |
| 15 | TypeScript Hooks | Generic custom hooks: `function useLocalStorage<T>(key, init: T)` |

> [!IMPORTANT]
> **Don't reach for `useMemo` / `useCallback` by default.** They add complexity. Use them only when React DevTools Profiler shows a real bottleneck. The new **React Compiler** (in 19+) auto-memoizes — much of this becomes obsolete.

<details>
<summary><strong>Quick Reference: Hooks Comparison</strong></summary>

| Hook | Purpose | Returns | When |
|------|---------|---------|------|
| `useState` | Simple state | `[value, setter]` | Counters, toggles, inputs |
| `useReducer` | Complex state | `[state, dispatch]` | Multi-field state, transitions |
| `useEffect` | Side effects | Cleanup fn | API calls, subscriptions |
| `useLayoutEffect` | Sync side effects | Cleanup fn | DOM measurements before paint |
| `useRef` | Mutable container | `{ current: value }` | DOM, timers, latest value |
| `useMemo` | Memoize value | Memoized value | Expensive calc — measure first |
| `useCallback` | Memoize fn | Memoized fn | Stable callback for memoized children |
| `useContext` | Read context | Context value | Theme, auth, language |
| `useId` | Stable unique ID | string | A11y attributes, SSR-safe |
| `use()` | Read promise/context | unwrapped | Server Components, Suspense |
| `useTransition` | Mark non-urgent updates | `[isPending, startT]` | Big lists, slow filters |
| `useDeferredValue` | Defer a value | deferred value | Search input vs heavy result |
| `useOptimistic` (19) | Optimistic UI | `[optimistic, setOpt]` | Likes, sends, instant feedback |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `useRef` to focus an input on mount
- [ ] Refactor a complex `useState` to `useReducer`
- [ ] Write `useDebounce`, `useLocalStorage`, `useMediaQuery` from scratch
- [ ] Explain why hooks must run in the same order every render

</details>

---

## Phase 7: Forms & Validation

![Phase](https://img.shields.io/badge/Phase-7%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Forms in React, the right way. Controlled vs uncontrolled, validation, accessibility, file uploads.

**What this phase is about.** Forms are the highest-stakes UI in any app — login, signup, checkout, settings. React has two approaches: **controlled** (state owns the value) and **uncontrolled** (DOM owns the value, refs read it). For real apps, **react-hook-form + Zod** has become the 2026 default — fast, composable, type-safe validation.

**Why it matters.** Forms are an interview classic and a portfolio differentiator. A fluent, validated, accessible form takes a project from "tutorial" to "production."

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Controlled vs Uncontrolled | When to pick which (controlled is default, uncontrolled for huge perf-sensitive forms) |
| 2 | Manual Form State | One state per field with `useState`. OK for tiny forms |
| 3 | Single State Object | `useState({ name: '', email: '' })` + spread updates |
| 4 | Form Submit Handler | `onSubmit`, `e.preventDefault()`, validation, submit, reset |
| 5 | Native HTML5 Validation | `required`, `type="email"`, `minlength`, `pattern` — get it free |
| 6 | Accessible Forms | `<label>` for every input, `aria-describedby` for errors, `aria-invalid` |
| 7 | **react-hook-form** | The dominant form library. `useForm()`, `register`, `handleSubmit` — minimal re-renders |
| 8 | **Zod (or Valibot)** | Schema-first validation. Single source of truth for types and runtime checks |
| 9 | Combining RHF + Zod | `zodResolver(schema)` — type-safe, validated forms in <30 lines |
| 10 | Field Arrays | Dynamic forms with rows you can add/remove (`useFieldArray`) |
| 11 | File Uploads | `<input type="file">`, `FormData`, drag-and-drop with `react-dropzone` |
| 12 | Async Validation | "Is this email already taken?" — debounced server-side checks |
| 13 | Form Wizards | Multi-step forms with shared state |
| 14 | React 19 Form Actions | `<form action={serverAction}>` — server-driven forms in Next.js |
| 15 | `useOptimistic` | Optimistic UI updates while the server confirms |

> [!TIP]
> The 2026 default form stack:

```bash
npm install react-hook-form zod @hookform/resolvers
```

> Define schema once, get types + runtime validation everywhere.

<details>
<summary><strong>Quick Reference: react-hook-form + Zod Skeleton</strong></summary>

```tsx
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';

const schema = z.object({
  email: z.string().email('Invalid email'),
  password: z.string().min(8, 'Min 8 chars'),
});
type FormData = z.infer<typeof schema>;

export function LoginForm() {
  const { register, handleSubmit, formState: { errors, isSubmitting } } =
    useForm<FormData>({ resolver: zodResolver(schema) });

  return (
    <form onSubmit={handleSubmit(async data => { await login(data); })}>
      <input {...register('email')} />
      {errors.email && <p>{errors.email.message}</p>}
      <input type="password" {...register('password')} />
      {errors.password && <p>{errors.password.message}</p>}
      <button disabled={isSubmitting}>Sign in</button>
    </form>
  );
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a controlled form with native HTML5 validation
- [ ] Build the same form with react-hook-form + Zod
- [ ] Add accessible error messages with `aria-describedby`
- [ ] Build a multi-step wizard form
- [ ] Implement a file upload with progress

</details>

---

## Phase 8: State Management

![Phase](https://img.shields.io/badge/Phase-8%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Local state → lifted state → context → global store. Pick the right tool for each layer.

**What this phase is about.** Not all state is equal. Local component state (`useState`), parent-shared state (lift up), app-wide UI state (Context API), and complex global state (Zustand, Redux, Jotai). Plus **server state** (data from APIs) — *which is its own thing* and gets its own phase next.

**Why it matters.** "How do you manage state?" is the most common React design interview. Knowing **which layer goes where** is what separates juniors from mid-level. The 2026 answer is *not* "one big Redux store" — it's a layered stack.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The State Hierarchy | Local → Lifted → Context → Global. Pick the lowest level that works |
| 2 | Lift State Up | Move state to lowest common ancestor of components that need it |
| 3 | Prop Drilling | When lifting goes too far. Sign you need Context |
| 4 | **Context API** | `createContext()` + `<Provider value>` + `useContext()` |
| 5 | Splitting Contexts | One per concern (auth, theme, locale). Avoid one mega-context |
| 6 | Context Performance | Every consumer re-renders when value changes. Use `useMemo` for the value |
| 7 | When Context Isn't Enough | Frequent updates → drop in a global store |
| 8 | **Zustand** | Lightweight (~3KB) global store. The 2026 default for client state |
| 9 | **Jotai** | Atomic state — primitive units that compose |
| 10 | **Redux Toolkit** | Modern Redux — much less boilerplate than classic Redux. Use for huge apps with strict patterns |
| 11 | **Recoil / Valtio** | Other notable patterns (Valtio = mutable proxies) |
| 12 | TypeScript with State Stores | Type-safe Zustand / Redux slices |
| 13 | Persisting State | localStorage / sessionStorage middlewares |
| 14 | Devtools | Redux DevTools, Zustand DevTools middleware |

> [!TIP]
> The 2026 state management decision tree:
> - Single component value → `useState`
> - Multi-field connected state → `useReducer`
> - Theme / auth / locale → **Context API**
> - Cross-app client state (cart, drawer, filters) → **Zustand**
> - Atomic / dependency-graph state → **Jotai**
> - Big team / strict patterns / time-travel debugging → **Redux Toolkit**
> - **Server data → TanStack Query (Phase 9 — not state-management territory)**

<details>
<summary><strong>Quick Reference: Zustand Skeleton</strong></summary>

```ts
import { create } from 'zustand';

interface CartState {
  items: Item[];
  add: (item: Item) => void;
  remove: (id: string) => void;
  total: () => number;
}

export const useCart = create<CartState>((set, get) => ({
  items: [],
  add: item   => set(s => ({ items: [...s.items, item] })),
  remove: id  => set(s => ({ items: s.items.filter(i => i.id !== id) })),
  total: ()   => get().items.reduce((sum, i) => sum + i.price, 0),
}));

// In component:
const items = useCart(s => s.items);
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build dark mode with Context API
- [ ] Replace prop drilling with Context in an existing project
- [ ] Build a shopping cart with Zustand
- [ ] Pick the right state layer given a scenario (interview-style)

</details>

---

## Phase 9: Server State & Data Fetching

![Phase](https://img.shields.io/badge/Phase-9%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Data from your server is *not* the same as your client state. Treat it differently.

**What this phase is about.** Most "global state" in real apps is just *cached server data* — your user profile, the product list, search results. Trying to manage it with `useState` + `useEffect` leads to bugs (stale data, race conditions, cache invalidation, refetching, retries). **TanStack Query** (formerly React Query) solved this once and for all. SWR is the lighter alternative. In Next.js App Router, **Server Components fetch directly** — covered in Phase 12.

**Why it matters.** Senior frontend interviews now expect this distinction: "What's the difference between client state and server state?" If you can answer that and reach for TanStack Query without thinking, you've leveled up.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Client vs Server State | Server state is async, shared, can go stale, needs caching/refetching/retries |
| 2 | The Manual Fetch Pattern | `useEffect` + `useState` for loading/error/data. The pattern you should outgrow |
| 3 | Why Manual Fetching Fails | Race conditions, cache invalidation, refetch on focus, dedupe, loading states |
| 4 | **TanStack Query** | The dominant server-state library. Cache, retry, dedupe, refetch, mutation invalidation |
| 5 | `useQuery` | Read data with caching, refetching, and stale-while-revalidate baked in |
| 6 | Query Keys | The cache key — array-based, hierarchical, dependency-aware |
| 7 | `useMutation` | POST/PUT/DELETE with optimistic updates and cache invalidation |
| 8 | Cache Invalidation | `queryClient.invalidateQueries({ queryKey: ['users'] })` after a mutation |
| 9 | Optimistic Updates | Update UI before the server responds |
| 10 | Pagination | `useInfiniteQuery`, cursor-based, page-based |
| 11 | Suspense Mode | TanStack Query → Suspense boundaries (React 18+) |
| 12 | **SWR** | Vercel's lighter alternative. Same idea, smaller API |
| 13 | Auth + Tokens | Header injection, 401 handling, refresh tokens |
| 14 | DevTools | TanStack Query DevTools — see the entire cache live |
| 15 | When You DON'T Need It | Server Components fetch directly — sometimes simpler |

> [!IMPORTANT]
> **Server state is not state — it's a cache of server data.** Client state libs (Zustand, Redux) are the wrong tool. Use TanStack Query (or SWR) and your code shrinks 5×.

<details>
<summary><strong>Quick Reference: TanStack Query Skeleton</strong></summary>

```tsx
import { useQuery, useMutation, useQueryClient } from '@tanstack/react-query';

// READ
function UserList() {
  const { data, isLoading, error } = useQuery({
    queryKey: ['users'],
    queryFn: () => fetch('/api/users').then(r => r.json()),
  });
  if (isLoading) return <Spinner />;
  if (error)     return <Error err={error} />;
  return data.map(u => <UserCard key={u.id} user={u} />);
}

// WRITE
function AddUser() {
  const qc = useQueryClient();
  const { mutate, isPending } = useMutation({
    mutationFn: (user) => fetch('/api/users', { method: 'POST', body: JSON.stringify(user) }),
    onSuccess: () => qc.invalidateQueries({ queryKey: ['users'] }),
  });
  return <button onClick={() => mutate(newUser)}>{isPending ? 'Saving…' : 'Add'}</button>;
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Replace a manual `useEffect` fetch with `useQuery`
- [ ] Build a paginated list with `useInfiniteQuery`
- [ ] Add a mutation with optimistic updates and cache invalidation
- [ ] Wire TanStack Query DevTools and explore the cache

</details>

---

## Phase 10: Routing & Navigation

![Phase](https://img.shields.io/badge/Phase-10%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Multiple pages without page reloads. Plus the modern alternatives: Next.js App Router, TanStack Router.

**What this phase is about.** A single-page app needs **client-side routing** — change the URL, render a different component, no page reload. **React Router** is the classic. **TanStack Router** is the modern type-safe challenger. **Next.js App Router** does routing differently — file-system based, server-first — covered in Phase 12.

**Why it matters.** Every multi-page React app has a router. Knowing how to set up nested routes, dynamic segments, protected routes, and code splitting is a fundamental skill on every job.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Client-Side Routing | No page reloads, smooth transitions, shared layout |
| 2 | **React Router v6/v7** | The dominant library. `<BrowserRouter>`, `<Routes>`, `<Route>`, `<Link>` |
| 3 | Basic Routes | `<Route path="/" element={<Home />} />` |
| 4 | Navigation | `<Link>` (no reload), `<NavLink>` (active styling), `useNavigate()` (programmatic) |
| 5 | Route Parameters | `path="/user/:id"` + `useParams()` |
| 6 | Query Strings | `useSearchParams()` — read + write `?q=...&page=2` |
| 7 | Nested Routes | Routes inside routes + `<Outlet />` for shared layouts |
| 8 | Index Routes | The default child route at a parent path |
| 9 | Loaders & Actions (RR v6.4+) | Data loading at the route level, before render |
| 10 | Protected Routes | Auth guard component or loader-based redirect |
| 11 | 404 Catch-All | `<Route path="*" element={<NotFound />} />` |
| 12 | Code Splitting per Route | `lazy()` + `<Suspense>` — load page bundles on demand |
| 13 | **TanStack Router** | Type-safe, file-based or code-based — the modern challenger |
| 14 | **Next.js App Router (Preview)** | File-system routing, Server Components by default — Phase 12 |

> [!TIP]
> Use `<NavLink>` for nav menus — it auto-adds an `active` class:

```jsx
<NavLink
  to="/about"
  className={({ isActive }) => isActive ? 'nav-active' : ''}
>
  About
</NavLink>
```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up React Router with 5+ routes and nested layouts
- [ ] Use dynamic route params with `useParams`
- [ ] Implement a protected route that redirects to login
- [ ] Code-split a route with `lazy()` + `<Suspense>`

</details>

---

## Phase 11: Performance, Suspense & Concurrent React

![Phase](https://img.shields.io/badge/Phase-11%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Make your app fast — code splitting, memoization, transitions, virtualization, error boundaries.

**What this phase is about.** Performance levers from cheapest to most surgical: **code splitting** (don't ship code you don't need), **`Suspense`** (declarative loading states), **transitions** (`useTransition`, `useDeferredValue` — non-blocking updates for big lists / search), **`React.memo`** + `useMemo` + `useCallback` (cut unnecessary re-renders — used carefully), **virtualization** (render only visible rows in long lists). Plus **error boundaries** (don't let a bug whitescreen your app) and the **React DevTools Profiler** (measure before optimizing).

**Why it matters.** Anyone can write React that runs slowly. Writing React that stays smooth at 60fps under load — that's the senior interview filter.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The First Rule | **Profile, don't guess.** Use React DevTools Profiler before optimizing |
| 2 | Code Splitting | `lazy(() => import('./Page'))` — load components only when needed |
| 3 | `<Suspense>` | `<Suspense fallback={<Spinner />}>` — declarative loading boundaries |
| 4 | Suspense for Data | Suspense + TanStack Query (or RSC) — data dependencies become declarative |
| 5 | `React.memo` | Skip re-render if props are shallow-equal. Don't apply blindly |
| 6 | `useMemo` / `useCallback` | Stabilize values/functions for memoized children |
| 7 | The React Compiler (19+) | Auto-memoization at compile time. The future where you don't write `useMemo` |
| 8 | `useTransition` | Mark non-urgent updates so urgent ones (clicks, typing) stay snappy |
| 9 | `useDeferredValue` | Defer a value (search input → heavy results list) |
| 10 | Virtualization | `react-virtual`, `react-window` — render only visible rows. Handles 100k+ items |
| 11 | Error Boundaries | Class component (still — only way for now) that catches descendant errors |
| 12 | `react-error-boundary` (library) | Modern hook-friendly wrapper |
| 13 | Bundle Analysis | `vite-bundle-visualizer`, `source-map-explorer` — find what's bloating your build |
| 14 | Image Optimization | `next/image`, lazy-loading, modern formats (AVIF, WebP) |
| 15 | Production Builds | Tree-shaking, minification, gzip/brotli — done by Vite/Next automatically |

> [!IMPORTANT]
> **Profile before you optimize.** React DevTools → Profiler → record interaction → see which components re-rendered and how long. Don't add `React.memo`, `useMemo`, or `useCallback` without evidence.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Lazy-load a route with `lazy()` + `<Suspense>`
- [ ] Use the Profiler to find an unnecessary re-render
- [ ] Add an Error Boundary with `react-error-boundary`
- [ ] Render a 10,000-row list smoothly with `react-virtual`
- [ ] Use `useTransition` to keep an input snappy while filtering a big list

</details>

---

## Phase 12: Modern React — Server Components & Next.js

![Phase](https://img.shields.io/badge/Phase-12%2F15-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 10-14 Hours](https://img.shields.io/badge/Time-10--14%20Hours-yellow)

> The biggest React shift since hooks. Components that run on the server, ship zero JS, and fetch data directly.

**What this phase is about.** **React Server Components (RSC)** flip the model: instead of shipping JS to the browser to fetch data and render UI, **the server renders to HTML directly** — components can `await` a database query, hit an internal API, read environment variables, and ship zero JavaScript for that part of the page. **Next.js App Router** is the production way to use them. **Server Actions** let forms call server functions without writing an API route. This phase is the 2026 must-know.

**Why it matters.** In 2026, "Next.js" is on more job postings than "React" alone. Companies expect you to know Server Components, Server Actions, streaming, and `'use client'`. This phase is what separates "React dev" from "modern full-stack React dev."

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Server Components | Less JS shipped, direct DB access, secret keys safe, faster TTFB |
| 2 | RSC vs Client Components | Default = server. Add `'use client'` for interactivity (state, effects, browser APIs) |
| 3 | The `'use client'` Directive | Marks a file (and its imports) as client. Crosses are bridges, not boundaries |
| 4 | The `'use server'` Directive | Marks a function as a Server Action — callable from the client |
| 5 | **Next.js App Router** | File-system routing under `app/` — folders are routes, files have conventions |
| 6 | `page.tsx` / `layout.tsx` | The two main file conventions |
| 7 | `loading.tsx` & `error.tsx` | Co-located loading and error UIs (Suspense + Error Boundary) |
| 8 | Data Fetching in RSC | Just `await fetch(...)` or `await db.query(...)` directly in the component |
| 9 | `cache()` and Request Memoization | Dedupe identical fetches in the same render |
| 10 | Streaming & `<Suspense>` | Send HTML in chunks as data resolves — perceived speed |
| 11 | **Server Actions** | `<form action={createUser}>` — no API route needed |
| 12 | `useFormStatus`, `useFormState` | Form action helpers — pending state, server validation |
| 13 | `useOptimistic` | Optimistic UI before the server confirms |
| 14 | Revalidation | `revalidatePath()`, `revalidateTag()` — update the cache after mutations |
| 15 | Dynamic vs Static | Routes default to static. `dynamic = 'force-dynamic'` for per-request rendering |
| 16 | Partial Prerendering (PPR) | Static shell + streaming dynamic parts — Next 15 |
| 17 | Middleware | Edge-runtime functions before a request hits a route — auth, redirects, A/B |
| 18 | Auth Patterns | Auth.js (NextAuth), Clerk, server-side session checks |
| 19 | Route Handlers | `app/api/.../route.ts` — REST endpoints when you need them |
| 20 | Deploying to Vercel | Push to GitHub → auto-deploy. Free tier covers most projects |

> [!TIP]
> A minimal Server Component reading from a DB:

```tsx
// app/users/page.tsx — Server Component (no 'use client')
import { db } from '@/lib/db';

export default async function UsersPage() {
  const users = await db.user.findMany();
  return (
    <ul>
      {users.map(u => <li key={u.id}>{u.name}</li>)}
    </ul>
  );
}
```

> No `useEffect`, no API route, no fetch. The component runs on the server, hits the database, returns HTML.

<details>
<summary><strong>Quick Reference: Server vs Client Components</strong></summary>

| | Server Components | Client Components |
|--|------------------|-------------------|
| Default? | **Yes (in App Router)** | Add `'use client'` |
| Run where? | Server | Server (SSR) + Client |
| Use hooks? | No state hooks | Yes |
| Use browser APIs? | No (`window`, `document`) | Yes |
| Fetch data? | Direct (`await`) | TanStack Query / fetch |
| Access secrets? | Yes (env vars stay server-side) | No |
| Ship JS? | No (or minimal) | Yes |
| Use case | Data fetching, layouts, content | Interactivity, forms, animations |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a Next.js App Router app from `npx create-next-app@latest`
- [ ] Fetch data inside a Server Component with `await`
- [ ] Add a Server Action and call it from a `<form>`
- [ ] Use `useOptimistic` for a like button
- [ ] Stream a page with `<Suspense>` for the slow part
- [ ] Deploy to Vercel from GitHub

</details>

---

## Phase 13: Testing, TypeScript & Modern Tooling

![Phase](https://img.shields.io/badge/Phase-13%2F15-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Test like a user, type like a senior, set up your project the 2026 way.

**What this phase is about.** **Vitest** + **React Testing Library** + **Playwright** is the 2026 testing stack. **TypeScript** is the default — typing props, state, events, generic components. Plus modern tooling: **ESLint** (with `eslint-plugin-react-hooks`), **Prettier**, **Husky** + **lint-staged** for pre-commit, and the basics of **Storybook** for component-level dev.

**Why it matters.** Untested + untyped React doesn't ship to production at any serious company. Setting this stack up *once* lets you build it fast for every project after.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Testing Philosophy | Test behavior, not implementation. Test what users see and do |
| 2 | The Testing Pyramid | Unit (fast, many) → Integration → E2E (slow, few) |
| 3 | **Vitest** | Modern test runner. ESM-first. 10–20× faster than Jest. Vite-native |
| 4 | **React Testing Library** | `render`, `screen`, `userEvent` — query by accessible role/label |
| 5 | Common Queries | `getByRole`, `getByLabelText`, `findByText` — all accessibility-driven |
| 6 | Testing User Interactions | `userEvent.click`, `userEvent.type`, `userEvent.selectOptions` |
| 7 | Testing Async UI | `findBy*` (waits) vs `getBy*` (immediate). `waitFor` for assertions |
| 8 | Testing Custom Hooks | `renderHook(() => useMyHook())` |
| 9 | **Mock Service Worker (MSW)** | Mock HTTP at the network layer — same code in tests, dev, demos |
| 10 | **Playwright** | E2E tests in real browsers — Chromium, Firefox, WebKit |
| 11 | Visual Regression | Storybook + Chromatic for component-visual snapshots |
| 12 | A11y Testing | `vitest-axe`, `eslint-plugin-jsx-a11y` |
| 13 | **TypeScript Basics for React** | Props, state, events, refs, children, generic components |
| 14 | TypeScript Patterns | Discriminated unions, `Pick`/`Omit`, conditional rendering with type narrowing |
| 15 | **ESLint + Prettier** | `eslint-plugin-react`, `eslint-plugin-react-hooks`, Prettier auto-format |
| 16 | **Husky + lint-staged** | Run lint/test/format on `git commit` |
| 17 | **Storybook** | Visual workshop for components |
| 18 | CI/CD | GitHub Actions: lint → test → build → deploy |

<details>
<summary><strong>Quick Reference: A Real Component Test</strong></summary>

```tsx
import { render, screen } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { describe, test, expect, vi } from 'vitest';
import { Counter } from './Counter';

describe('Counter', () => {
  test('starts at 0 and increments on click', async () => {
    const user = userEvent.setup();
    render(<Counter />);

    expect(screen.getByText(/count: 0/i)).toBeInTheDocument();
    await user.click(screen.getByRole('button', { name: /increment/i }));
    expect(screen.getByText(/count: 1/i)).toBeInTheDocument();
  });

  test('calls onChange when value changes', async () => {
    const onChange = vi.fn();
    const user = userEvent.setup();
    render(<Counter onChange={onChange} />);
    await user.click(screen.getByRole('button', { name: /increment/i }));
    expect(onChange).toHaveBeenCalledWith(1);
  });
});
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up Vitest + RTL on a Vite project
- [ ] Write 10+ tests using `getByRole` and `userEvent`
- [ ] Mock a network call with MSW
- [ ] Write a Playwright E2E test that fills a form and asserts the result
- [ ] Type all components in a project with TypeScript

</details>

---

## Phase 14: The React Ecosystem

![Phase](https://img.shields.io/badge/Phase-14%2F15-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The libraries you'll meet on every job posting. Recognize them all; deeply learn 5–8.

**What this phase is about.** React's superpower is its ecosystem. Whatever you need — date picker, drag-and-drop, charts, animation, AI streaming, mobile — there's a battle-tested library. This phase is your **map**: what each does, when to pick which.

### 14.1 — Meta-Frameworks (Production React)

| Framework | What It Is | Best For |
|-----------|-----------|----------|
| **[Next.js](https://nextjs.org/)** | The React framework by Vercel. App Router + RSC + Server Actions | The 2026 default for full-stack React |
| **[Remix / React Router (v7)](https://remix.run/)** | Web-fundamentals-first React framework | Form-heavy apps, traditional web shape |
| **[Astro](https://astro.build/)** | Multi-framework, content-first, partial hydration | Marketing, docs, blogs |
| **[TanStack Start](https://tanstack.com/start)** | Type-safe full-stack React | Modern API-first apps |
| **[Gatsby](https://www.gatsbyjs.com/)** | Static-site generator | Content sites (less popular post-Next.js 13) |
| **[Vite + React](https://vitejs.dev/)** | Pure SPA toolchain | Internal dashboards, embedded apps |

### 14.2 — UI Component Libraries

| Library | What It Is |
|---------|-----------|
| **[shadcn/ui](https://ui.shadcn.com/)** | Copy-paste Tailwind components — the 2026 default |
| **[Radix UI](https://www.radix-ui.com/)** | Unstyled accessible primitives (the foundation of shadcn/ui) |
| **[Headless UI](https://headlessui.com/)** | Tailwind Labs' unstyled components |
| **[Material UI (MUI)](https://mui.com/)** | Google Material Design — most mature React UI library |
| **[Mantine](https://mantine.dev/)** | 100+ components + hooks, great DX |
| **[Chakra UI](https://chakra-ui.com/)** | Style-prop based components |
| **[Ant Design](https://ant.design/)** | Enterprise-grade (Alibaba) |
| **[Park UI](https://park-ui.com/)** | Ark UI + variants — multi-framework |
| **[Aria Components (React Aria)](https://react-spectrum.adobe.com/react-aria/)** | Adobe's accessibility primitives |

### 14.3 — Styling

| Tool | What It Does |
|------|-------------|
| **[Tailwind CSS](https://tailwindcss.com/)** | Utility-first CSS — the 2026 default |
| **[CSS Modules](https://github.com/css-modules/css-modules)** | Scoped class names (built into Vite/Next) |
| **[Vanilla Extract](https://vanilla-extract.style/)** | Type-safe CSS-in-TypeScript, zero runtime |
| **[styled-components](https://styled-components.com/)** | Tagged-template CSS-in-JS |
| **[Emotion](https://emotion.sh/)** | High-performance CSS-in-JS |
| **[Panda CSS](https://panda-css.com/)** | Modern zero-runtime CSS-in-JS |
| **[Open Props](https://open-props.style/)** | Design-token CSS variables |

### 14.4 — State Management

| Library | What It Does |
|---------|--------------|
| **[Zustand](https://zustand.docs.pmnd.rs/)** | Lightweight global store — 2026 default |
| **[Jotai](https://jotai.org/)** | Atomic state |
| **[Redux Toolkit](https://redux-toolkit.js.org/)** | Modern Redux — much less boilerplate |
| **[Recoil](https://recoiljs.org/)** | Meta's atomic state (less active in 2026) |
| **[Valtio](https://valtio.dev/)** | Mutable proxy state |
| **[XState](https://xstate.js.org/)** | Statecharts — for complex state machines |

### 14.5 — Server State / Data

| Library | What It Does |
|---------|--------------|
| **[TanStack Query](https://tanstack.com/query)** | The dominant server-state library |
| **[SWR](https://swr.vercel.app/)** | Vercel's lighter alternative |
| **[Apollo Client](https://www.apollographql.com/docs/react/)** | The GraphQL client |
| **[Relay](https://relay.dev/)** | Meta's GraphQL client |
| **[urql](https://formidable.com/open-source/urql/)** | Lightweight GraphQL client |
| **[tRPC](https://trpc.io/)** | End-to-end type-safe APIs (no GraphQL needed) |

### 14.6 — Forms

| Library | What It Does |
|---------|--------------|
| **[react-hook-form](https://react-hook-form.com/)** | The dominant form library — minimal re-renders |
| **[Formik](https://formik.org/)** | Older but widely used |
| **[TanStack Form](https://tanstack.com/form)** | Type-safe form state |
| **[Zod](https://zod.dev/)** | Schema validation — the 2026 default for runtime + types |
| **[Valibot](https://valibot.dev/)** | Tree-shakeable Zod alternative |
| **[Yup](https://github.com/jquense/yup)** | The classic validation library |

### 14.7 — Routing

| Library | What It Does |
|---------|--------------|
| **[React Router](https://reactrouter.com/)** | The classic SPA router |
| **[TanStack Router](https://tanstack.com/router)** | Type-safe modern router |
| **[Next.js App Router](https://nextjs.org/docs/app)** | File-system routing for Next.js |
| **[wouter](https://github.com/molefrog/wouter)** | Minimalist 1KB router |

### 14.8 — Animation

| Library | What It Does |
|---------|--------------|
| **[Framer Motion / Motion](https://motion.dev/)** | The dominant React animation library |
| **[react-spring](https://www.react-spring.dev/)** | Physics-based animations |
| **[GSAP](https://gsap.com/)** | The professional animation library |
| **[Auto-Animate (FormKit)](https://auto-animate.formkit.com/)** | Drop-in zero-config animations |
| **[react-transition-group](https://reactcommunity.org/react-transition-group/)** | Lightweight transitions |
| **[Tailwind Animate](https://github.com/jamiebuilds/tailwindcss-animate)** | Animation utilities for Tailwind |

### 14.9 — Charts & Data Viz

| Library | What It Does |
|---------|--------------|
| **[Recharts](https://recharts.org/)** | Composable React charts (built on D3) |
| **[Visx](https://airbnb.io/visx/)** | Airbnb's low-level D3 + React |
| **[Tremor](https://www.tremor.so/)** | Dashboard-first chart components |
| **[Chart.js + react-chartjs-2](https://react-chartjs-2.js.org/)** | The classic charting library |
| **[Nivo](https://nivo.rocks/)** | Beautiful, server-renderable charts |
| **[ECharts for React](https://github.com/hustcc/echarts-for-react)** | Apache ECharts wrapper |

### 14.10 — Tables & Data Grids

| Library | What It Does |
|---------|--------------|
| **[TanStack Table](https://tanstack.com/table)** | Headless, framework-agnostic, type-safe |
| **[AG Grid](https://www.ag-grid.com/react/)** | Enterprise data grid |
| **[Material React Table](https://www.material-react-table.com/)** | TanStack Table + Material UI |

### 14.11 — Drag and Drop

| Library | What It Does |
|---------|--------------|
| **[dnd-kit](https://dndkit.com/)** | Modern, accessible, performant DnD |
| **[react-dnd](https://react-dnd.github.io/react-dnd/)** | Older HTML5 drag-and-drop |
| **[react-beautiful-dnd](https://github.com/atlassian/react-beautiful-dnd)** | Atlassian's DnD (now archived; many migrating to dnd-kit) |

### 14.12 — AI / LLM SDKs (the 2026 frontier)

| Library | What It Is |
|---------|-----------|
| **[Vercel AI SDK](https://sdk.vercel.ai/)** | Streaming chat UIs, tool-calling, multi-provider — the 2026 default |
| **[Anthropic TypeScript SDK](https://github.com/anthropics/anthropic-sdk-typescript)** | Claude API |
| **[OpenAI Node SDK](https://github.com/openai/openai-node)** | GPT API |
| **[LangChain.js](https://js.langchain.com/)** | RAG, agents, chains |
| **[LlamaIndex.ts](https://ts.llamaindex.ai/)** | Data framework for LLMs |
| **[CopilotKit](https://www.copilotkit.ai/)** | Drop-in AI features for any React app |
| **[Assistant UI](https://www.assistant-ui.com/)** | shadcn/ui-style chat components |

### 14.13 — Auth

| Library | What It Does |
|---------|--------------|
| **[Clerk](https://clerk.com/)** | Drop-in auth — sign-in/up, MFA, organizations |
| **[Auth.js (NextAuth)](https://authjs.dev/)** | Open-source auth for Next.js |
| **[Supabase Auth](https://supabase.com/auth)** | Bundled with Supabase backend |
| **[Auth0](https://auth0.com/)** | Enterprise auth |
| **[Stack Auth](https://stack-auth.com/)** | Open-source Clerk alternative |
| **[Better Auth](https://www.better-auth.com/)** | TypeScript-first auth |

### 14.14 — Payments

| Library | What It Does |
|---------|--------------|
| **[Stripe React](https://docs.stripe.com/stripe-js/react)** | The default for payments |
| **[PayPal React](https://developer.paypal.com/sdk/js/reference/)** | PayPal SDK |
| **[Lemon Squeezy](https://www.lemonsqueezy.com/)** | Merchant of record (handles tax) |

### 14.15 — Real-time

| Library | What It Does |
|---------|--------------|
| **[socket.io-client](https://socket.io/docs/v4/client-api/)** | WebSockets with fallbacks |
| **[Pusher](https://pusher.com/)** | Hosted real-time |
| **[Ably](https://ably.com/)** | Hosted real-time |
| **[Liveblocks](https://liveblocks.io/)** | Multiplayer collaboration (cursors, presence, comments) |
| **[Yjs](https://yjs.dev/)** | CRDT for collaborative editing |
| **[PartyKit](https://www.partykit.io/)** | Real-time platform on Cloudflare |

### 14.16 — Mobile (React Native)

| Library | What It Does |
|---------|--------------|
| **[Expo](https://expo.dev/)** | The React Native framework — start here |
| **[React Native](https://reactnative.dev/)** | The core library |
| **[NativeWind](https://www.nativewind.dev/)** | Tailwind for React Native |
| **[Tamagui](https://tamagui.dev/)** | Universal UI for native + web |
| **[React Native Reanimated](https://docs.swmansion.com/react-native-reanimated/)** | Performant animations |
| **[React Navigation](https://reactnavigation.org/)** | The native router |

### 14.17 — Desktop

| Tool | What It Does |
|------|--------------|
| **[Electron](https://www.electronjs.org/)** | Cross-platform desktop apps with React |
| **[Tauri](https://tauri.app/)** | Rust-powered, lighter alternative to Electron |

### 14.18 — Utility Hooks

| Library | What It Does |
|---------|--------------|
| **[useHooks](https://usehooks.com/)** | Curated collection of common hooks |
| **[react-use](https://github.com/streamich/react-use)** | 100+ utility hooks |
| **[usehooks-ts](https://usehooks-ts.com/)** | Type-safe hook collection |
| **[ahooks](https://ahooks.js.org/)** | Alibaba's hook library |

### 14.19 — Dev Tools & Workshop

| Tool | What It Does |
|------|--------------|
| **[Storybook](https://storybook.js.org/)** | Component workshop, visual testing |
| **[Chromatic](https://www.chromatic.com/)** | Visual regression for Storybook |
| **[Ladle](https://ladle.dev/)** | Lightweight Storybook alternative (Vite-based) |
| **[React DevTools](https://react.dev/learn/react-developer-tools)** | Browser extension — non-negotiable |

> [!IMPORTANT]
> Don't learn all of these. **Recognize** all of them. **Deeply learn** the 2026 default stack: **Next.js + Tailwind + shadcn/ui + TanStack Query + Zustand + react-hook-form + Zod + Vitest + Playwright + Vercel AI SDK**. That's roughly what 70% of React jobs use.

---

## Phase 15: What's Next? (Specializations & Deploy)

![Phase](https://img.shields.io/badge/Phase-15%2F15-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You finished React. Now pick a specialization and ship.

**What this phase is about.** React opens more doors than almost any frontend skill. Pick a track that excites you, then go deep. Whatever you pick, **Git**, **a database (SQL)**, **Docker**, and **Vercel** travel with you.

### 15.1 — Pick a Specialization

| Track | What You Build | Key Tools |
|-------|---------------|-----------|
| **Frontend Engineer** | UIs, dashboards, marketing sites | React + Tailwind + shadcn/ui + TanStack Query |
| **Full-Stack Next.js** | End-to-end apps (frontend + backend in one repo) | Next.js + Drizzle/Prisma + Auth.js + Vercel |
| **AI Engineer (Frontend)** | LLM apps, agents, copilots | Vercel AI SDK + Anthropic/OpenAI + Pinecone/pgvector |
| **Mobile Engineer** | iOS + Android apps | Expo + React Native + NativeWind |
| **Design System Engineer** | Component libs powering whole products | Storybook + Radix + Tailwind + tokens |
| **Real-time / Collab** | Multiplayer apps, dashboards, editors | Liveblocks / Yjs + Socket.io / PartyKit |
| **Data Viz** | Dashboards, analytics, charts | Recharts / Visx / D3 + Tremor |
| **DevTools / Internal** | Internal tools, admin panels | Refine, Retool, custom Next.js + tRPC |

### 15.2 — Required Cross-cutting Skills

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every team. Every project. |
| **[TypeScript](typescript.md)** | The 2026 React default. Non-negotiable for senior roles. |
| **[SQL](sql.md)** | Every full-stack role. Pair with the SQL Syllabus. |
| **[Docker](docker.md)** | Containerize your Next.js app. |
| **CI/CD** (GitHub Actions) | Auto-test + auto-deploy on every push. |
| **Linux / terminal** | Every server runs Linux. |
| **A11y** ([axe DevTools](https://www.deque.com/axe/devtools/), [WAVE](https://wave.webaim.org/)) | Catch issues before users — and lawsuits. |

### 15.3 — Where to Deploy

| Target | Best For |
|--------|----------|
| **[Vercel](https://vercel.com/)** | The Next.js home. Free tier covers most projects |
| **[Netlify](https://www.netlify.com/)** | Vite + React SPAs, static sites |
| **[Cloudflare Pages](https://pages.cloudflare.com/)** | Edge-first, generous free tier |
| **[Render](https://render.com/)** | Full backend + DB if you don't use Vercel |
| **[Fly.io](https://fly.io/)** | Global edge with regions |
| **AWS Amplify / Azure / GCP** | Enterprise |
| **[Expo EAS](https://expo.dev/eas)** | React Native build + submit |

### 15.4 — Suggested Order After This Syllabus

```
TypeScript (deep) → Next.js (deep) → SQL → Build & deploy a real Next.js app → AI capstone → Repeat
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Mutating state directly | React doesn't detect the change → no re-render | Spread or use immer: `setState([...items, x])` |
| 2 | Index as `key` for dynamic lists | React reuses wrong components on reorder | Use a stable unique ID |
| 3 | `useEffect` infinite loops | Setting state with no dep array | Add `[]` (or correct deps) |
| 4 | Calling handlers immediately | `onClick={fn()}` fires on render | Pass the function: `onClick={fn}` |
| 5 | Prop-drilling 5 levels | Brittle, hard to refactor | Context API or Zustand |
| 6 | No cleanup in `useEffect` | Timers/listeners leak | `return () => cleanup()` |
| 7 | `useMemo` / `useCallback` everywhere | Adds complexity, not perf | Profile first; React Compiler will memo for you |
| 8 | `class` instead of `className` | `class` is reserved in JS | Always `className` |
| 9 | No React DevTools | Debugging blind | Install the extension |
| 10 | Skipping JS fundamentals | Confusing JS bugs as React bugs | Master JS first |
| 11 | Storing server data in Redux/Zustand | Wrong tool for cached server state | Use TanStack Query / SWR |
| 12 | Treating `useEffect` as lifecycle | Then you fight the docs | "You might not need an Effect" — derive in render |
| 13 | Single mega-Context | Every change re-renders the whole app | Split contexts by concern |
| 14 | Class components in new code | The class era ended in 2019 | Function components + hooks |
| 15 | CRA for new projects | Officially deprecated | Vite or Next.js |
| 16 | Not typing components | Refactors break, IDE can't help | TypeScript everywhere |
| 17 | Global CSS for components | Conflicts, specificity wars | CSS Modules or Tailwind |
| 18 | Stale closures in handlers | Reading old values inside async callbacks | Updater fns or refs |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is JSX?**
   - Syntax extension that lets you write HTML-like markup in JavaScript. It compiles to `React.createElement()` calls. Embed JS expressions with `{}`.

2. **Props vs state?**
   - Props are read-only inputs from the parent (like function arguments). State is internal data managed by the component itself. Props flow down, state can change and triggers re-renders.

3. **What is the virtual DOM?**
   - An in-memory tree of React elements. On state change, React builds a new tree, diffs against the previous, and updates only the changed nodes in the real DOM. Faster than naive DOM updates.

4. **What is a controlled component?**
   - A form element whose value is driven by React state — `<input value={x} onChange={...} />`. React is the single source of truth.

5. **Why do list items need `key`s?**
   - Keys let React match items between renders so it can update, add, or remove correctly. Without stable keys, list reorders cause bugs and lost component state.

6. **What's the difference between `useState` and `useReducer`?**
   - `useState` for simple, independent values. `useReducer` for complex state with multiple sub-fields and transitions, where actions describe *what happened* and the reducer decides the new state.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain `useEffect` cleanup.**
   - The cleanup function runs when the component unmounts AND before each subsequent re-run of the effect. Used to clear timers, abort fetches, remove listeners — prevents memory leaks and stale updates.

2. **What are custom hooks and when do you write one?**
   - Functions starting with `use` that call other hooks to encapsulate reusable stateful logic. Write one when the same `useState`+`useEffect` pattern shows up in 2+ components — `useLocalStorage`, `useDebounce`, `useFetch`.

3. **Context API vs Zustand vs Redux Toolkit?**
   - Context: built-in, best for infrequent updates (theme, auth). Zustand: tiny global store, great for client UI state. Redux Toolkit: opinionated, structured, best for big teams + complex flows + middleware needs.

4. **When and why use `React.memo`?**
   - Wraps a component to skip re-renders if shallow-compared props haven't changed. Use when (a) re-renders are expensive AND (b) the same props arrive often. Don't apply by default — measure first.

5. **What's the difference between client state and server state?**
   - Client state is owned by your app (filters, modals, form drafts). Server state is a *cache* of data living elsewhere — async, can go stale, needs refetching/retries. Use TanStack Query for server state, not Redux/Zustand.

6. **Implement a debounce hook.**
   - ```ts
     function useDebounce<T>(value: T, delay = 300): T {
       const [debounced, setDebounced] = useState(value);
       useEffect(() => {
         const id = setTimeout(() => setDebounced(value), delay);
         return () => clearTimeout(id);
       }, [value, delay]);
       return debounced;
     }
     ```

7. **Why do hooks need to run in the same order every render?**
   - React tracks hooks by call order — the 1st `useState` always corresponds to the same state slot. If hooks ran conditionally, the slots would shift and React would wire state to the wrong hook.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **Explain React's reconciliation.**
   - On state change, React builds a new virtual DOM and diffs it against the old. Same element type → update props. Different type → unmount old, mount new. For lists, `key`s match items. The whole diff runs in O(n).

2. **What is Fiber?**
   - React's reconciliation engine since v16. Splits work into units (fibers) that can be paused, resumed, and prioritized. Enables: interruptible rendering, concurrent features (Suspense, transitions), and selective hydration.

3. **What are React Server Components?**
   - Components that run on the server and ship their *output* (HTML + serialized data) to the client — no JS for that component. They can `await` databases or files directly. Client components (`'use client'`) handle interactivity. Used in Next.js App Router.

4. **What is hydration in SSR?**
   - The server pre-renders HTML and ships it. On the client, React attaches event listeners and state to that HTML, "hydrating" it into a fully interactive React tree. Selective hydration (React 18+) prioritizes visible/interacted-with parts.

5. **How do you prevent unnecessary re-renders in a large app?**
   - (1) Profile first. (2) Lift state down (state colocation). (3) Split contexts so unrelated consumers don't re-render. (4) `React.memo` for pure components with stable props. (5) `useMemo`/`useCallback` to stabilize props passed to memoized children. (6) Virtualization for long lists. (7) The React Compiler (19+) auto-memoizes much of this.

6. **What is `useTransition` and when would you use it?**
   - Marks state updates as **non-urgent**. Urgent updates (typing, clicks) preempt them. Use to keep an input snappy while a heavy filter/search updates the list — `startTransition(() => setFilter(query))`.

7. **Server Actions — what are they and what do they replace?**
   - Functions marked `'use server'` that can be called directly from the client (often via `<form action={fn}>`). They replace bespoke API routes for form submissions. Implement mutations + revalidation in one call.

8. **Why is "you might not need an Effect" the official guidance?**
   - Effects are for synchronizing with *external systems*. State derived from props/state should be computed during render. Event responses belong in handlers. Following this eliminates a huge class of bugs.

</details>

---

## Practice Projects

You don't truly know React until you've shipped real projects. Each builds on multiple phases.

> [!TIP]
> Push every project to GitHub and deploy it (Vercel auto-deploys Next.js from a GitHub repo for free). 5 polished, deployed projects beat any tutorial certificate.

### Project 1: Recipe Finder
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** Search recipes by ingredient. Filter by category. View detail. Static JSON data.

**Skills:** Components, props, state, events, lists, keys, conditional rendering, controlled inputs.

**Stretch:** Save favorites to `localStorage`. Dark mode toggle.

---

### Project 2: Movie Browser (TMDB API)
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** Search movies via [TMDB](https://www.themoviedb.org/documentation/api), grid of results, detail pages, custom `useDebounce` + `useFetch` hooks. Loading/error/empty states.

**Skills:** `useEffect`, data fetching, custom hooks, `useRef`, `AbortController`.

**Stretch:** Infinite scroll with `IntersectionObserver`.

---

### Project 3: Production Forms
![Phase 7](https://img.shields.io/badge/After-Phase%207-yellow)

**What you'll build:** A multi-step signup form with **react-hook-form + Zod**: email/password, profile, plan selection. Async username availability check. Accessible error messages. Resume after refresh.

**Skills:** react-hook-form, Zod, multi-step state, async validation, accessibility.

**Stretch:** Persist progress to `localStorage`.

---

### Project 4: E-commerce with Cart & Routing
![Phase 8-10](https://img.shields.io/badge/After-Phase%208--10-yellow)

**What you'll build:** Product catalog (TanStack Query), category filters, cart (Zustand), checkout, react-router with protected routes. shadcn/ui components.

**Skills:** Zustand, TanStack Query, React Router, protected routes, shadcn/ui.

**Stretch:** Stripe Checkout integration.

---

### Project 5: Real-time Chat
![Phase 9-11](https://img.shields.io/badge/After-Phase%209--11-red)

**What you'll build:** Multi-room chat with WebSockets, optimistic message sending, virtualized message list (10k+ messages stay smooth), error boundaries, code-split routes.

**Skills:** WebSockets, optimistic UI (`useOptimistic`), virtualization, error boundaries, transitions.

**Stretch:** Typing indicators. File uploads. End-to-end encryption.

---

### Project 6: Full-Stack Next.js App (Server Components + Server Actions)
![Phase 12](https://img.shields.io/badge/After-Phase%2012-red)

**What you'll build:** A complete app — user auth (Clerk or Auth.js), dashboard with Server Components fetching from Postgres (Drizzle/Prisma), Server Actions for mutations, streaming with Suspense, deployed on Vercel.

**Skills:** Next.js App Router, RSC, Server Actions, Drizzle/Prisma, auth, Vercel deploy.

**Stretch:** Switch to PPR (Partial Prerendering). Add real-time with channels.

---

### Project 7: Tested + Typed Component Library
![Phase 13](https://img.shields.io/badge/After-Phase%2013-red)

**What you'll build:** A small library of 10 reusable components (Button, Input, Modal, Tabs, etc.) with **TypeScript**, **Storybook**, **Vitest + RTL** unit tests, **Playwright** visual checks, published to npm.

**Skills:** TypeScript, Storybook, Vitest, RTL, Playwright, npm publishing.

**Stretch:** Visual regression with Chromatic.

---

### Project 8: AI-Powered App with Streaming (Capstone)
![Phase 14](https://img.shields.io/badge/After-Phase%2014-red)

**What you'll build:** Your graduation project. A Next.js app where users upload PDFs / paste URLs, ask questions, and get streamed answers via Claude (Anthropic SDK) using **Vercel AI SDK**, with **RAG** (pgvector or chromadb), auth (Clerk), tested with Vitest + Playwright, deployed to Vercel. Add **`useOptimistic`**, **prompt caching**, multi-turn memory, and a **tool-calling** demo (LLM calls a server action).

**Skills:** Everything from all 15 phases — RSC, Server Actions, AI streaming, RAG, optimistic UI, auth, deploy. **This is portfolio gold for any 2026 React/AI interview.**

**Stretch:** Voice input. Multi-document RAG. Eval suite.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [react.dev — Learn React](https://react.dev/learn) | The official React docs, completely rewritten in 2023. Hooks-first, modern patterns |
| [react.dev — Reference](https://react.dev/reference/react) | Every hook, component, API |
| [Next.js Docs](https://nextjs.org/docs) | The full-stack React framework — learn this if you go full-stack |
| [Vercel AI SDK Docs](https://sdk.vercel.ai/docs) | LLM streaming, tool calling, generative UI |
| [TanStack Query Docs](https://tanstack.com/query/latest) | The server-state library |
| [shadcn/ui Docs](https://ui.shadcn.com/) | The UI component reference |

### Books & Long-form Reads

| Book | Why Read |
|------|---------|
| [The React Beta Docs (now react.dev)](https://react.dev/) | Better than any book — interactive, exhaustive |
| [Patterns.dev](https://www.patterns.dev/) | Free book on modern web patterns including React |
| [Epic React (Kent C. Dodds)](https://epicreact.dev/) | Paid, deep, opinionated |
| [Fullstack React](https://www.fullstackreact.com/) | Project-based |
| [Robin Wieruch's React Books](https://www.robinwieruch.de/) | Free + paid books on React, Hooks, TS |
| [Refactoring UI (Wathan & Schoger)](https://refactoringui.com/) | Design fundamentals — pairs with Tailwind/shadcn |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [react.dev tutorial](https://react.dev/learn/tutorial-tic-tac-toe) | Official tic-tac-toe tutorial — the canonical first project |
| [The Odin Project — React](https://www.theodinproject.com/paths/full-stack-javascript/courses/react) | Project-based |
| [Scrimba — Learn React](https://scrimba.com/learn/learnreact) | Edit instructor's code in-browser |
| [Codecademy — Learn React](https://www.codecademy.com/learn/react-101) | In-browser, guided |
| [freeCodeCamp — Front End Libraries](https://www.freecodecamp.org/learn/front-end-development-libraries/) | Free certification, 5 projects |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Theo (t3.gg)](https://www.youtube.com/@t3dotgg) | Modern React/Next/TS opinions, what to use today |
| [Jack Herrington](https://www.youtube.com/@jherr) | Advanced patterns, performance, architecture |
| [Lee Robinson](https://www.youtube.com/@leerob) | VP of Vercel — Next.js deep dives |
| [Web Dev Cody](https://www.youtube.com/@WebDevCody) | Project-based, modern stack |
| [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified) | Clear, focused per-topic |
| [Codevolution](https://www.youtube.com/@Codevolution) | Structured React tutorials |
| [The Net Ninja](https://www.youtube.com/@NetNinja) | Well-paced playlists |
| [Fireship](https://www.youtube.com/@Fireship) | Fast visual overviews |

### Practice & Build

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Real Figma designs to build |
| [DevChallenges](https://devchallenges.io/) | Project challenges by difficulty |
| [Build UI](https://buildui.com/) | Modern React patterns + projects |
| [JS Mastery Pro](https://jsmastery.pro/) | Project-based React courses |
| [Sam Selikoff Courses](https://buildui.com/courses) | Beautiful real projects |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — React](https://roadmap.sh/react) | Interactive React roadmap |
| [roadmap.sh — Next.js](https://roadmap.sh/nextjs) | Modern full-stack track |
| [roadmap.sh — AI Engineer](https://roadmap.sh/ai-engineer) | If you're heading into AI apps |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [VS Code](https://code.visualstudio.com/) | Free, fast, the standard |
| [ES7+ React Snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets) | Type `rafce` → full functional component |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Bug + style enforcement (with `eslint-plugin-react-hooks`) |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format on save |
| [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) | Tailwind autocomplete + previews |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | Inline error display |
| [Console Ninja](https://marketplace.visualstudio.com/items?itemName=niceplusplus.console-ninja) | Console output beside your code |
| [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) | Bundle-size hints inline |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [react.dev Quick Start](https://react.dev/learn) | Official structured overview |
| [React TypeScript Cheatsheet](https://react-typescript-cheatsheet.netlify.app/) | Comprehensive TS + React patterns |
| [TanStack Query Cheatsheet](https://tkdodo.eu/blog/practical-react-query) | TkDodo's series on TanStack Query |
| [react-hook-form Cheatsheet](https://react-hook-form.com/get-started) | Get started fast |

### Newsletters & Podcasts

| Resource | Format |
|----------|--------|
| [Bytes](https://bytes.dev/) | Weekly React/JS newsletter — fun, sharp |
| [This Week in React](https://thisweekinreact.com/) | Weekly newsletter — comprehensive |
| [React Status](https://react.statuscode.com/) | Weekly newsletter |
| [JavaScript Jabber](https://devchat.tv/podcasts/js-jabber/) | Weekly JS/React podcast |
| [Syntax.fm](https://syntax.fm/) | Wes Bos & Scott Tolinski |
| [PodRocket](https://podrocket.logrocket.com/) | Frontend deep dives |

---

[Back to Main Syllabus](../README.md)

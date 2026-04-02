# Vue.js Syllabus

A complete, structured learning path for Vue.js — from your first `.vue` file to building production apps with the Composition API, Pinia, and Vue Router.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 10-14 Weeks](https://img.shields.io/badge/Duration-10--14%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Vue: 3.x](https://img.shields.io/badge/Vue-3.x-42b883)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Reactivity & State](#phase-2-reactivity--state)
- [Phase 3: Components & Props](#phase-3-components--props)
- [Phase 4: Directives & Rendering](#phase-4-directives--rendering)
- [Phase 5: Events & Forms](#phase-5-events--forms)
- [Phase 6: Composables & Lifecycle](#phase-6-composables--lifecycle)
- [Phase 7: Routing](#phase-7-routing)
- [Phase 8: State Management with Pinia](#phase-8-state-management-with-pinia)
- [Phase 9: Advanced Patterns](#phase-9-advanced-patterns)
- [Phase 10: Testing & Best Practices](#phase-10-testing--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Vue 3 uses the **Composition API** with `<script setup>` as the default. This syllabus focuses entirely on the modern approach — not the Options API.

- HTML & CSS fundamentals
- JavaScript ES6+ (modules, destructuring, arrow functions, promises)
- TypeScript basics (recommended but not required)
- Node.js and npm installed
- Complete the [JavaScript Syllabus](javascript.md) first

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what Vue is and create your first reactive component.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Vue.js | A progressive JavaScript framework — use it for a widget or a full SPA. Reactive, component-based, fast |
| 2 | Vue 3 vs Vue 2 | Vue 3: Composition API, `<script setup>`, Proxy-based reactivity, Pinia, Vite. Vue 2 is legacy |
| 3 | Project Setup | `npm create vue@latest` — scaffolds a Vite-powered project with TypeScript, Router, and Pinia options |
| 4 | Single-File Components | `.vue` files have three sections: `<template>`, `<script setup>`, `<style scoped>` — everything in one file |
| 5 | Template Syntax | `{{ message }}` for text, `:src="url"` for attribute binding, `@click="handler"` for events |
| 6 | Your First Component | A function-like `<script setup>` block + a template. Variables declared in setup are automatically available in the template |
| 7 | Dev Server & Build | `npm run dev` (Vite dev server with HMR), `npm run build` (production bundle) |

> [!TIP]
> Use `npm create vue@latest` (not Vite directly) for the best Vue starter — it gives you options for TypeScript, Router, Pinia, Vitest, and ESLint:
> ```bash
> npm create vue@latest my-app
> cd my-app
> npm install
> npm run dev     # http://localhost:5173
> ```

<details>
<summary><strong>Quick Reference: .vue File Structure</strong></summary>

```vue
<script setup lang="ts">
import { ref } from 'vue'

const message = ref('Hello, Vue!')
const count = ref(0)
</script>

<template>
  <h1>{{ message }}</h1>
  <button @click="count++">Count: {{ count }}</button>
</template>

<style scoped>
h1 { color: #42b883; }
</style>
```

> Everything in `<script setup>` is automatically available in the template. No `return` statement needed.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a Vue 3 project and run the dev server
- [ ] Write a `.vue` component with `<script setup>`
- [ ] Explain the three sections of a Single-File Component

</details>

---

## Phase 2: Reactivity & State

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make your data reactive — when it changes, the UI updates automatically.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `ref()` | `const count = ref(0)` — reactive primitive. Access with `.value` in JS, auto-unwrapped in templates |
| 2 | `reactive()` | `const state = reactive({ name: '', age: 0 })` — reactive object. Access directly: `state.name` |
| 3 | `ref` vs `reactive` | Use `ref()` by default (works with any type). Use `reactive()` only for grouped object state |
| 4 | `computed()` | `const double = computed(() => count.value * 2)` — cached derived state, recalculates only when dependencies change |
| 5 | `watch()` | `watch(count, (newVal, oldVal) => {})` — run side effects when reactive data changes |
| 6 | `watchEffect()` | `watchEffect(() => console.log(count.value))` — auto-tracks dependencies, runs immediately |
| 7 | Template Refs | `const input = ref(null)` + `<input ref="input">` — access DOM elements directly |
| 8 | Reactivity Utilities | `toRef()`, `toRefs()`, `unref()`, `isRef()` — helpers for working with reactive data |

> [!CAUTION]
> **Destructuring `reactive()` objects breaks reactivity.** The destructured values are plain, non-reactive copies:
> ```javascript
> const state = reactive({ count: 0, name: 'Vue' })
>
> // WRONG — count is now a plain number, not reactive
> const { count } = state
>
> // RIGHT — use toRefs() to maintain reactivity
> const { count, name } = toRefs(state)
> // Now count.value is reactive
> ```

<details>
<summary><strong>Quick Reference: ref() vs reactive()</strong></summary>

| Feature | `ref()` | `reactive()` |
|---------|---------|-------------|
| Works with | Any type (primitives + objects) | Objects only |
| Access in JS | `.value` required | Direct access |
| Access in template | Auto-unwrapped | Direct access |
| Can be destructured | Yes (it's a ref) | No (loses reactivity) |
| Can be reassigned | Yes: `myRef.value = newObj` | No: `state = newObj` breaks it |
| Default choice | Yes — use this | Only for grouped related data |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `ref()` and `reactive()` and explain when to use each
- [ ] Create a `computed()` property that derives from reactive state
- [ ] Set up a `watch()` that calls an API when a search term changes

</details>

---

## Phase 3: Components & Props

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build reusable components and pass data between them.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Defining Components | Import and use components directly in `<script setup>` — no registration needed |
| 2 | `defineProps()` | `const props = defineProps<{ title: string; count?: number }>()` — typed props with TypeScript |
| 3 | `defineEmits()` | `const emit = defineEmits<{ update: [value: string] }>()` — type-safe events from child to parent |
| 4 | `v-model` on Components | `defineModel()` — two-way binding between parent and child with zero boilerplate |
| 5 | Slots | `<slot />` for default content, `<slot name="header" />` for named slots, scoped slots for passing data back |
| 6 | `provide()` / `inject()` | Skip prop drilling — parent provides data, any descendant injects it (like React Context) |
| 7 | Fallthrough Attributes | `$attrs` — attributes passed to a component that aren't declared as props flow through to the root element |
| 8 | `defineExpose()` | `defineExpose({ reset })` — explicitly expose methods/refs for parent to access via template refs |

> [!TIP]
> `defineModel()` (Vue 3.4+) replaces the verbose `modelValue` + `update:modelValue` pattern. Two-way binding in one line:
> ```vue
> <!-- Child component -->
> <script setup>
> const model = defineModel<string>()
> </script>
> <template>
>   <input :value="model" @input="model = $event.target.value" />
> </template>
>
> <!-- Parent — just use v-model -->
> <SearchInput v-model="searchQuery" />
> ```

<details>
<summary><strong>Visual: Component Communication</strong></summary>

```
Parent ──── props ────→ Child          (data down)
Parent ←── emits ────── Child          (events up)
Parent ←─ v-model ───→ Child          (two-way)
Ancestor ── provide ──→ Descendant    (skip levels)
Parent ←─ template ref → Child        (direct access)
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a component with typed `defineProps()` and `defineEmits()`
- [ ] Use `defineModel()` for two-way binding
- [ ] Skip prop drilling with `provide()` and `inject()`

</details>

---

## Phase 4: Directives & Rendering

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Control what renders and how — conditionals, loops, dynamic styling.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `v-if` / `v-else-if` / `v-else` | Conditionally render elements — adds/removes from the DOM |
| 2 | `v-show` | Toggle visibility with CSS `display: none` — element stays in DOM. Faster for frequent toggling |
| 3 | `v-for` | `v-for="item in items" :key="item.id"` — render lists. `:key` is mandatory for correct behavior |
| 4 | `v-bind` (`:`) | `:src="imageUrl"`, `:class="{ active: isActive }"`, `:style="{ color: textColor }"` |
| 5 | `v-on` (`@`) | `@click="handler"`, `@submit.prevent="onSubmit"` — event modifiers: `.stop`, `.prevent`, `.once` |
| 6 | `v-model` | Two-way binding for inputs: `<input v-model="name">` — modifiers: `.lazy`, `.number`, `.trim` |
| 7 | Custom Directives | `const vFocus = { mounted: (el) => el.focus() }` — create your own `v-focus` directive |

> [!IMPORTANT]
> **`v-if` vs `v-show` — when to use each:**
> - `v-if`: Use when the condition rarely changes. Removes/adds elements from the DOM (lazy)
> - `v-show`: Use when toggling frequently. Only toggles CSS `display` (always renders)
> - `v-if` has higher toggle cost, `v-show` has higher initial render cost

<details>
<summary><strong>Quick Reference: Directive Shorthand</strong></summary>

| Full Syntax | Shorthand | Example |
|-------------|-----------|---------|
| `v-bind:src` | `:src` | `:src="imageUrl"` |
| `v-on:click` | `@click` | `@click="handleClick"` |
| `v-bind:class` | `:class` | `:class="{ active: isActive }"` |
| `v-on:submit.prevent` | `@submit.prevent` | `@submit.prevent="onSubmit"` |
| `v-slot:header` | `#header` | `<template #header>` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `v-if`, `v-for`, and `v-bind` in a component
- [ ] Explain the difference between `v-if` and `v-show`
- [ ] Create a custom directive (e.g., `v-focus`)

</details>

---

## Phase 5: Events & Forms

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Handle user interactions and build forms with validation.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Event Handling | `@click`, `@input`, `@submit`, `@keydown` — handle any DOM event with inline or method handlers |
| 2 | Event Modifiers | `.prevent` (preventDefault), `.stop` (stopPropagation), `.once`, `.self`, `.passive` |
| 3 | Key Modifiers | `@keydown.enter`, `@keydown.esc`, `@keydown.ctrl.s` — listen for specific keys |
| 4 | Form Inputs with `v-model` | Text, textarea, checkbox, radio, select, multi-select — all two-way bound with `v-model` |
| 5 | `v-model` Modifiers | `.lazy` (sync on change, not input), `.number` (cast to number), `.trim` (strip whitespace) |
| 6 | Form Validation | Watch inputs, show errors conditionally, disable submit until valid, integrate Zod/Valibot for schemas |
| 7 | Complex Forms | Multi-step forms, dynamic fields, nested objects, handling file uploads |

> [!TIP]
> Debounce search inputs with `watchEffect` and a timeout — don't make an API call on every keystroke:
> ```javascript
> const search = ref('')
> const results = ref([])
>
> watchEffect((onCleanup) => {
>   const timer = setTimeout(async () => {
>     if (search.value) {
>       results.value = await fetchResults(search.value)
>     }
>   }, 300)
>   onCleanup(() => clearTimeout(timer))
> })
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a form with multiple input types bound with `v-model`
- [ ] Add client-side validation with error messages
- [ ] Use event modifiers (`@submit.prevent`, `@keydown.enter`)

</details>

---

## Phase 6: Composables & Lifecycle

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Extract reusable logic into composables — Vue's most powerful pattern.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Lifecycle Hooks | `onMounted()` (DOM ready), `onUnmounted()` (cleanup), `onUpdated()`, `onBeforeMount()` |
| 2 | What Are Composables | Functions named `useXxx()` that encapsulate reactive state and logic — Vue's answer to React hooks |
| 3 | Creating `useFetch()` | A composable that handles data fetching, loading state, errors, and cleanup |
| 4 | Creating `useLocalStorage()` | Sync a `ref()` with `localStorage` — persists across page reloads |
| 5 | VueUse Library | 200+ pre-built composables: `useMouse()`, `useWindowSize()`, `useIntersectionObserver()`, `useDark()` |
| 6 | Composable Design Rules | Must start with `use`, call at top level (not conditionally), return refs (not raw values) |
| 7 | Testing Composables | Test composables in isolation with Vitest — assert reactive state changes |

> [!IMPORTANT]
> **Composables replace mixins** (which are problematic). A composable is just a function that uses Vue's reactivity:
> ```javascript
> // composables/useCounter.ts
> export function useCounter(initial = 0) {
>   const count = ref(initial)
>   const increment = () => count.value++
>   const decrement = () => count.value--
>   const reset = () => count.value = initial
>   return { count, increment, decrement, reset }
> }
>
> // In any component:
> const { count, increment } = useCounter(10)
> ```

<details>
<summary><strong>Quick Reference: Lifecycle Hooks</strong></summary>

| Hook | When It Runs | Common Use |
|------|-------------|------------|
| `onBeforeMount()` | Before DOM is created | Rarely needed |
| `onMounted()` | After DOM is created | Fetch data, access DOM, set up listeners |
| `onBeforeUpdate()` | Before re-render | Access DOM before changes |
| `onUpdated()` | After re-render | Access DOM after changes |
| `onBeforeUnmount()` | Before removal | Final cleanup |
| `onUnmounted()` | After removal | Clear timers, remove listeners, cancel requests |
| `onActivated()` | `<KeepAlive>` reactivated | Resume paused operations |
| `onDeactivated()` | `<KeepAlive>` deactivated | Pause operations |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a `useFetch()` composable with loading/error states
- [ ] Use 3+ VueUse composables in a project
- [ ] Test a composable in isolation with Vitest

</details>

---

## Phase 7: Routing

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Build multi-page applications with Vue Router 4.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Router Setup | `createRouter({ history: createWebHistory(), routes })` — configure routes and register with the app |
| 2 | Basic Routes | `{ path: '/about', component: () => import('./About.vue') }` + `<RouterView />` |
| 3 | `<RouterLink>` | `<RouterLink to="/about">About</RouterLink>` — navigation without page reload. Active class auto-applied |
| 4 | Route Parameters | `{ path: '/user/:id' }` + `const route = useRoute()` → `route.params.id` |
| 5 | Nested Routes | `children: [...]` + `<RouterView />` in parent — shared layouts |
| 6 | Navigation Guards | `router.beforeEach((to, from) => {})` — protect routes, check auth, redirect |
| 7 | Lazy Loading | `component: () => import('./views/Dashboard.vue')` — code-split per route, reduce initial bundle |
| 8 | Programmatic Navigation | `const router = useRouter()` → `router.push('/dashboard')`, `router.replace()`, `router.back()` |

> [!TIP]
> **Always lazy-load route components** — it splits your bundle so users only download the page they're visiting:
> ```typescript
> const routes = [
>   { path: '/', component: () => import('./views/Home.vue') },
>   { path: '/about', component: () => import('./views/About.vue') },
>   { path: '/user/:id', component: () => import('./views/User.vue') },
>   { path: '/:pathMatch(.*)*', component: () => import('./views/NotFound.vue') }
> ]
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up Vue Router with 4+ lazy-loaded routes
- [ ] Create a navigation guard that protects authenticated routes
- [ ] Use `useRoute()` and `useRouter()` in a component

</details>

---

## Phase 8: State Management with Pinia

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Manage global state with Pinia — Vue's official state management library (replaces Vuex).

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Pinia | Simpler than Vuex — no mutations, full TypeScript support, modular by design, devtools integration |
| 2 | `defineStore()` | `defineStore('counter', () => { const count = ref(0); return { count } })` — setup syntax (preferred) |
| 3 | State | `ref()` values inside the store — the reactive data. Modify directly, no mutations needed |
| 4 | Getters | `computed()` values inside the store — derived state. Cached, recalculates only when dependencies change |
| 5 | Actions | Functions inside the store — modify state, call APIs, handle async logic |
| 6 | Using Stores | `const store = useCounterStore()` — access state, getters, and actions in any component |
| 7 | `storeToRefs()` | `const { count } = storeToRefs(store)` — destructure reactive state without losing reactivity |
| 8 | Plugins | Persist state to `localStorage`, add logging, extend all stores with custom behavior |

> [!IMPORTANT]
> **Use `storeToRefs()` when destructuring store state**, otherwise you get plain non-reactive values:
> ```javascript
> const store = useUserStore()
>
> // WRONG — name is a plain string, not reactive
> const { name } = store
>
> // RIGHT — name is a ref, stays reactive
> const { name } = storeToRefs(store)
>
> // Actions don't need storeToRefs — they're just functions
> const { fetchUser } = store
> ```

<details>
<summary><strong>Quick Reference: Pinia Store (Setup Syntax)</strong></summary>

```typescript
// stores/counter.ts
import { defineStore } from 'pinia'
import { ref, computed } from 'vue'

export const useCounterStore = defineStore('counter', () => {
  // State (ref)
  const count = ref(0)

  // Getters (computed)
  const doubleCount = computed(() => count.value * 2)

  // Actions (functions)
  function increment() {
    count.value++
  }

  async function fetchCount() {
    const res = await fetch('/api/count')
    count.value = await res.json()
  }

  return { count, doubleCount, increment, fetchCount }
})
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a Pinia store with state, getters, and actions
- [ ] Use the store in a component with `storeToRefs()`
- [ ] Add a plugin that persists state to `localStorage`

</details>

---

## Phase 9: Advanced Patterns

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master built-in components, transitions, and advanced composition patterns.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `<Teleport>` | `<Teleport to="body">` — render a modal/tooltip outside the component tree (like React Portal) |
| 2 | `<Suspense>` | `<Suspense>` with `#default` and `#fallback` slots — show loading UI while async components load |
| 3 | Async Components | `defineAsyncComponent(() => import('./Heavy.vue'))` — lazy-load components on demand |
| 4 | `<Transition>` | Animate elements entering/leaving the DOM — CSS classes: `v-enter-from`, `v-enter-active`, `v-leave-to` |
| 5 | `<TransitionGroup>` | Animate list items being added, removed, or reordered — with FLIP-based move transitions |
| 6 | `<KeepAlive>` | `<KeepAlive><component :is="currentTab" /></KeepAlive>` — cache component instances instead of destroying them |
| 7 | Render Functions | `h('div', { class: 'box' }, 'Hello')` — programmatic rendering for maximum flexibility (rare, library use) |
| 8 | Plugin Architecture | `app.use(myPlugin)` — create plugins that add global functionality (custom directives, composables, components) |

> [!TIP]
> `<Teleport>` is perfect for modals — it renders the modal at `<body>` level, avoiding CSS `overflow: hidden` and `z-index` issues from parent containers:
> ```vue
> <Teleport to="body">
>   <div v-if="showModal" class="modal-overlay">
>     <div class="modal">
>       <h2>Modal Title</h2>
>       <button @click="showModal = false">Close</button>
>     </div>
>   </div>
> </Teleport>
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a modal with `<Teleport>`
- [ ] Add enter/leave animations with `<Transition>`
- [ ] Use `<Suspense>` with an async component

</details>

---

## Phase 10: Testing & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write tests, optimize performance, and prepare for production.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Vitest Setup | Fast test runner built for Vite. `npm install -D vitest` — runs your tests 10-20x faster than Jest |
| 2 | Vue Test Utils | `mount(MyComponent, { props: { title: 'Test' } })` — render components in tests, find elements, trigger events |
| 3 | Component Testing | Render → interact → assert: mount the component, simulate clicks/input, check the DOM output |
| 4 | Testing Composables | `const { result } = renderHook(() => useCounter())` — test composable logic in isolation |
| 5 | E2E Testing | Playwright or Cypress — test real user flows in a browser (login, checkout, navigation) |
| 6 | Performance | Lazy-load routes and components, use `v-once` for static content, avoid unnecessary watchers, profile with Vue DevTools |
| 7 | Nuxt Overview | `npx nuxi@latest init my-nuxt-app` — meta-framework for SSR, file-based routing, auto-imports. Vue's equivalent of Next.js |
| 8 | Production Checklist | Error handling, loading states, accessibility, SEO meta tags, bundle analysis, environment variables |

> [!TIP]
> Test behavior, not implementation. Use accessible queries that also verify your component is accessible:
> ```javascript
> import { mount } from '@vue/test-utils'
>
> test('increments counter on click', async () => {
>   const wrapper = mount(Counter)
>   await wrapper.find('button').trigger('click')
>   expect(wrapper.text()).toContain('Count: 1')
> })
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write 5+ component tests with Vue Test Utils and Vitest
- [ ] Test a Pinia store (state, getters, actions)
- [ ] Run a Lighthouse audit and score 90+ on a Vue project

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most Vue developers:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Mutating props | Props are read-only. Mutating them breaks one-way data flow | Emit an event: `emit('update:value', newValue)` |
| 2 | Using `reactive()` for primitives | `reactive('hello')` doesn't work — it only accepts objects | Use `ref()` for primitives (strings, numbers, booleans) |
| 3 | Destructuring `reactive()` | `const { count } = reactive({count: 0})` loses reactivity | Use `toRefs()` or just use `ref()` instead |
| 4 | Missing `:key` in `v-for` | Vue can't track which items changed — causes bugs with reordering and component state | Always use a unique ID: `:key="item.id"` |
| 5 | Forgetting `.value` in setup | `count` instead of `count.value` in JavaScript (templates auto-unwrap, JS doesn't) | Always use `.value` in `<script>`, never in `<template>` |
| 6 | Side effects at top level | Fetching data outside lifecycle hooks can break SSR and cause race conditions | Put side effects in `onMounted()` or `watchEffect()` |
| 7 | Not using `storeToRefs()` | Destructuring a Pinia store gives non-reactive plain values | `const { name } = storeToRefs(store)` for state/getters |
| 8 | Options API + Composition API mix | Mixing `data()` and `ref()` in the same component causes confusion | Use `<script setup>` exclusively for new code |
| 9 | Giant components | 500+ line components that handle everything | Split into small, focused components with clear responsibilities |
| 10 | Not cleaning up in `onUnmounted` | Event listeners, timers, and subscriptions keep running → memory leaks | Always clean up in `onUnmounted()` |

---

## Interview Questions

Test your Vue knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is Vue.js and why use it?**
   - Vue is a progressive JavaScript framework for building UIs. "Progressive" means you can use it for a single widget or a full SPA. Benefits: reactive data binding, component-based architecture, great documentation, small bundle size, gentle learning curve.

2. **What's the difference between `ref()` and `reactive()`?**
   - `ref()`: works with any type (primitives + objects), requires `.value` in JS, auto-unwrapped in templates. `reactive()`: only for objects, direct property access, can't be reassigned, loses reactivity when destructured. Default choice: `ref()`.

3. **Options API vs Composition API — what's the difference?**
   - Options API organizes by option type (`data`, `methods`, `computed`). Composition API organizes by logical concern using functions. Composition API is better for large components, code reuse (composables), and TypeScript. Vue 3 recommends Composition API.

4. **What's the difference between `v-if` and `v-show`?**
   - `v-if`: conditionally adds/removes elements from the DOM (lazy, higher toggle cost). `v-show`: toggles CSS `display` property (element always in DOM, higher initial cost). Use `v-if` for rarely changing conditions, `v-show` for frequent toggling.

5. **How do you pass data between components?**
   - Parent → Child: props (`defineProps()`). Child → Parent: events (`defineEmits()`). Two-way: `v-model` (`defineModel()`). Skip levels: `provide()` / `inject()`. Global: Pinia stores.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What are composables and how do they differ from mixins?**
   - Composables are `useXxx()` functions that encapsulate reactive logic. Unlike mixins: no naming conflicts, explicit dependencies, type-safe, testable in isolation, clear data flow. Composables completely replace mixins in Vue 3.

2. **Pinia vs Vuex — why is Pinia preferred?**
   - Pinia: no mutations (modify state directly), full TypeScript inference, modular by design, setup syntax, smaller bundle (1KB), devtools support. Vuex: requires mutations, weaker TypeScript, module-based, more boilerplate. Pinia is the official recommendation.

3. **`computed()` vs `watch()` — when do you use each?**
   - `computed()`: for derived values (cached, declarative). Use when you need a value that depends on other reactive data. `watch()`: for side effects (imperative). Use when you need to run code when data changes (API calls, logging, localStorage sync).

4. **How does `provide`/`inject` work?**
   - Parent calls `provide('key', value)`. Any descendant calls `inject('key')`. Skips intermediate components (no prop drilling). Use `ref()` values to make injected data reactive. Use `Symbol` keys for safety in large apps.

5. **How do navigation guards work in Vue Router?**
   - `router.beforeEach((to, from) => {})` — runs before every route change. Return `true` (allow), `false` (block), or a route object (redirect). Use for auth checks, loading data, confirming unsaved changes. Can be global, per-route, or per-component.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How does Vue's Proxy-based reactivity system work?**
   - Vue 3 wraps objects with JavaScript `Proxy`. When you read a property, Vue tracks it as a dependency. When you write a property, Vue triggers re-renders for all components that depend on it. This is automatic — no `setState()` needed. Limitations: doesn't track property deletion or addition on non-proxied objects.

2. **Explain Vue's virtual DOM and rendering pipeline.**
   - Template → compile → render function → virtual DOM tree. On state change: new virtual DOM is created, diffed against the old one, and only changed nodes are patched in the real DOM. Vue's compiler applies static hoisting and patch flags to skip unchanged parts, making it faster than React's diffing.

3. **What is hydration in SSR and how do you handle mismatches?**
   - SSR renders HTML on the server for fast initial load and SEO. Hydration is when Vue attaches event listeners and reactivity to the pre-rendered HTML. Mismatch = server HTML differs from client render → broken app. Fix: avoid browser-only APIs (`window`, `localStorage`) in server-rendered code, use `onMounted()` for client-only logic.

4. **How does `<Suspense>` work with async components?**
   - `<Suspense>` waits for all async dependencies (async `setup()`, `defineAsyncComponent`) to resolve. Shows `#fallback` slot while loading, switches to `#default` when ready. Can handle nested async components. Still experimental but widely used with Nuxt.

5. **What is Vapor Mode and why does it matter?**
   - Vapor Mode is an upcoming Vue compilation strategy that skips the virtual DOM entirely. It compiles templates to direct DOM operations (like Svelte/Solid). Result: smaller runtime, faster updates, less memory. It's opt-in per component — existing apps don't need changes. Expected to be a major performance leap for Vue.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Notes App
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** Create, edit, delete notes with search and category filters. Persist to `localStorage`. Uses `ref()`, `computed()`, `v-for`, `v-if`, `v-model`.

**Skills practiced:** Reactivity, components, props, directives, local storage.

---

### Project 2: Movie Search (API)
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** Search movies via OMDB/TMDB API, view details, save favorites. Debounced search with a `useFetch()` composable. Loading and error states.

**Skills practiced:** Composables, lifecycle hooks, events, forms, API calls, VueUse.

---

### Project 3: Blog with Vue Router
![Phase 7](https://img.shields.io/badge/After-Phase%207-yellow)

**What you'll build:** Multi-page blog with post listing, detail view, category pages, and a 404 page. Lazy-loaded routes with navigation guards.

**Skills practiced:** Vue Router, route params, nested routes, guards, lazy loading.

---

### Project 4: E-Commerce Store
![Phase 8](https://img.shields.io/badge/After-Phase%208-orange)

**What you'll build:** Product listing, shopping cart (add/remove/quantity), checkout page. Cart persisted with Pinia + localStorage plugin.

**Skills practiced:** Pinia stores, `storeToRefs()`, actions with API calls, computed getters.

---

### Project 5: Full-Stack Dashboard
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** Admin dashboard with auth, data tables, charts, modals via `<Teleport>`, animated transitions, and 80%+ test coverage.

**Skills practiced:** Everything from all phases — your Vue graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [vuejs.org — Guide](https://vuejs.org/guide/introduction.html) | The official Vue 3 docs. Exceptionally well-written with interactive examples |
| [vuejs.org — Tutorial](https://vuejs.org/tutorial/) | Interactive step-by-step tutorial — write code directly in the browser |
| [vuejs.org — API Reference](https://vuejs.org/api/) | Complete reference for every function, directive, and component option |
| [Vue Router Docs](https://router.vuejs.org/) | Official routing library documentation |
| [Pinia Docs](https://pinia.vuejs.org/) | Official state management documentation |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Vue Mastery — Intro to Vue 3](https://www.vuemastery.com/courses/intro-to-vue-3-comp-api/introduction-comp-api/) | Free intro course. Interactive, Composition API-first |
| [Vue School — Vue 3 Fundamentals](https://vueschool.io/courses/vue-js-fundamentals-with-the-composition-api) | Free course covering Composition API fundamentals |
| [vuejs.org Tutorial](https://vuejs.org/tutorial/) | Official interactive tutorial — practice in the browser |
| [freeCodeCamp — Vue Course](https://www.freecodecamp.org/news/tag/vue/) | Free full-length courses with projects |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Traversy Media — Vue 3 Crash Course](https://www.youtube.com/@TraversyMedia) | Best first Vue video — build a project in ~2 hours |
| [The Net Ninja — Vue 3 Tutorial](https://www.youtube.com/@NetNinja) | Well-paced playlist. Each video covers one concept |
| [Program with Erik](https://www.youtube.com/@ProgramWithErik) | Vue-focused channel with practical tutorials |
| [Fireship — Vue in 100 Seconds](https://www.youtube.com/@Fireship) | Quick visual overview before diving deep |
| [LearnVue](https://www.youtube.com/@LearnVue) | Deep dives into Vue 3 patterns and Composition API |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Vue](https://roadmap.sh/vue) | Interactive learning path — click each topic to see resources |

### Practice & Challenges

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional designs — build them with Vue |
| [DevChallenges](https://devchallenges.io/) | Full-stack challenges with varying difficulty |
| [VueUse — Challenge Yourself](https://vueuse.org/) | Explore 200+ composables — try building your own first |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Vue — Official (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) | The official Vue extension. TypeScript, template IntelliSense, error highlighting |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) | Use with `eslint-plugin-vue` for Vue-specific linting rules |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format `.vue` files on save |
| [Vue DevTools](https://devtools.vuejs.org/) | Chrome/Firefox extension — inspect components, Pinia stores, routes, and performance |

### Key Ecosystem Libraries

| Library | What It Does |
|---------|-------------|
| [VueUse](https://vueuse.org/) | 200+ composables: `useMouse`, `useLocalStorage`, `useDark`, `useFetch`, and many more |
| [Pinia](https://pinia.vuejs.org/) | Official state management — simple, type-safe, modular |
| [Vue Router](https://router.vuejs.org/) | Official routing library |
| [Nuxt](https://nuxt.com/) | Meta-framework for SSR, file-based routing, auto-imports — Vue's Next.js |
| [Vitest](https://vitest.dev/) | Fast test runner built for Vite |
| [Vue Test Utils](https://test-utils.vuejs.org/) | Official component testing library |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [Vue 3 Cheat Sheet (Vue Mastery)](https://www.vuemastery.com/vue-cheat-sheet/) | Visual quick reference for Composition API |
| [Vue.js Style Guide](https://vuejs.org/style-guide/) | Official best practices and naming conventions |

---

[Back to Main Syllabus](../README.md)

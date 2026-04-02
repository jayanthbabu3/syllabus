# CSS Syllabus

A complete, structured learning path for CSS — from styling your first element to building responsive, animated, production-ready layouts.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 8-12 Weeks](https://img.shields.io/badge/Duration-8--12%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Box Model & Layout Basics](#phase-2-box-model--layout-basics)
- [Phase 3: Typography & Colors](#phase-3-typography--colors)
- [Phase 4: Flexbox](#phase-4-flexbox)
- [Phase 5: CSS Grid](#phase-5-css-grid)
- [Phase 6: Responsive Design](#phase-6-responsive-design)
- [Phase 7: Transitions & Animations](#phase-7-transitions--animations)
- [Phase 8: Advanced Selectors & Pseudo-classes](#phase-8-advanced-selectors--pseudo-classes)
- [Phase 9: CSS Architecture & Methodologies](#phase-9-css-architecture--methodologies)
- [Phase 10: Modern CSS & Best Practices](#phase-10-modern-css--best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> You should know **basic HTML** before starting CSS. If you haven't already, complete the [HTML Syllabus](html.md) first.

- HTML fundamentals (elements, attributes, document structure)
- A code editor ([VS Code](https://code.visualstudio.com/) recommended)
- A web browser (Chrome recommended for DevTools)

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what CSS is and write your first styles.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is CSS | Cascading Style Sheets — the language that controls how HTML looks on screen |
| 2 | Three Ways to Add CSS | Inline (`style=""`), internal (`<style>`), and external (`.css` file) — and why external wins |
| 3 | CSS Syntax | Selectors, properties, and values — the `selector { property: value; }` pattern |
| 4 | Basic Selectors | Type (`p`), class (`.intro`), ID (`#header`), and universal (`*`) selectors |
| 5 | Combining Selectors | Descendant (space), child (`>`), adjacent sibling (`+`), general sibling (`~`) |
| 6 | Your First Styles | Change text color, background color, font size, and text alignment |
| 7 | CSS Comments | `/* comment */` — document your code without affecting the output |

> [!TIP]
> Always use **external CSS files** (`<link rel="stylesheet" href="style.css">`). Inline and internal styles are harder to maintain and don't scale.

<details>
<summary><strong>Quick Reference: Selector Types</strong></summary>

| Selector | Syntax | What It Selects |
|----------|--------|-----------------|
| Type | `p` | All `<p>` elements |
| Class | `.card` | All elements with `class="card"` |
| ID | `#header` | The one element with `id="header"` |
| Universal | `*` | Every element on the page |
| Descendant | `div p` | `<p>` inside any `<div>` (any depth) |
| Child | `div > p` | `<p>` directly inside `<div>` (one level) |
| Adjacent | `h1 + p` | First `<p>` immediately after `<h1>` |
| General Sibling | `h1 ~ p` | All `<p>` elements after `<h1>` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the three ways to add CSS and when to use each
- [ ] Write CSS rules using type, class, and ID selectors
- [ ] Style text color, background, font size, and alignment

</details>

---

## Phase 2: Box Model & Layout Basics

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Understand how every element is a box and how to control its size and spacing.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Box Model | Every element is a box: content → padding → border → margin (from inside out) |
| 2 | `box-sizing` | `content-box` (default, confusing) vs `border-box` (intuitive, always use this) |
| 3 | Margin & Padding | Shorthand syntax, individual sides, and why vertical margins collapse |
| 4 | Borders & Outlines | Border width/style/color, `border-radius` for rounded corners, outline vs border |
| 5 | Display Property | `block` (full width), `inline` (flows with text), `inline-block` (hybrid), `none` (hidden) |
| 6 | Width & Height | `width`, `height`, `min-width`, `max-width`, `min-height`, `max-height` |
| 7 | Overflow | `visible`, `hidden`, `scroll`, `auto` — what happens when content doesn't fit |
| 8 | Positioning | `static` (default), `relative`, `absolute`, `fixed`, `sticky` — and how they interact |

> [!IMPORTANT]
> Add this to the top of every project. It makes sizing intuitive — `width: 200px` means the element is actually 200px wide, including padding and border:
> ```css
> *, *::before, *::after {
>   box-sizing: border-box;
> }
> ```

<details>
<summary><strong>Visual: The Box Model</strong></summary>

```
┌─────────────────────────────────────┐
│              MARGIN                 │
│   ┌─────────────────────────────┐   │
│   │          BORDER             │   │
│   │   ┌─────────────────────┐   │   │
│   │   │      PADDING        │   │   │
│   │   │   ┌─────────────┐   │   │   │
│   │   │   │   CONTENT   │   │   │   │
│   │   │   └─────────────┘   │   │   │
│   │   └─────────────────────┘   │   │
│   └─────────────────────────────┘   │
└─────────────────────────────────────┘
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Draw the box model from memory (content → padding → border → margin)
- [ ] Explain why `box-sizing: border-box` is essential
- [ ] Use positioning to place elements precisely on the page

</details>

---

## Phase 3: Typography & Colors

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Make text beautiful and master the CSS color systems.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Font Families | Generic families (serif, sans-serif, monospace), font stacks, and fallback fonts |
| 2 | Web Fonts | Load custom fonts with `@font-face` or Google Fonts — beyond system defaults |
| 3 | Font Properties | `font-size` (px, rem, em), `font-weight` (400, 700), `font-style`, `line-height` |
| 4 | Text Styling | `text-align`, `text-transform`, `text-decoration`, `letter-spacing`, `word-spacing`, `text-indent` |
| 5 | Color Systems | Named colors, hex (`#FF5733`), `rgb()`, `rgba()`, `hsl()`, `hsla()` — and when to use each |
| 6 | Backgrounds | `background-color`, `background-image`, gradients (`linear-gradient`, `radial-gradient`) |
| 7 | Text Shadows | `text-shadow` for depth and glow effects |
| 8 | Accessible Typography | Minimum font sizes, sufficient line-height (1.5+), color contrast for readability |

> [!TIP]
> Use `rem` for font sizes, not `px`. `rem` respects the user's browser font size settings — better for accessibility. Set `html { font-size: 62.5%; }` so that `1rem = 10px` for easy math.

<details>
<summary><strong>Quick Reference: Color Formats</strong></summary>

| Format | Syntax | Best For |
|--------|--------|----------|
| Named | `red`, `blue` | Quick prototyping |
| Hex | `#FF5733` | Most common in code |
| RGB | `rgb(255, 87, 51)` | When you need numeric values |
| RGBA | `rgba(255, 87, 51, 0.5)` | Colors with transparency |
| HSL | `hsl(14, 100%, 60%)` | Easiest to adjust hue/saturation |
| HSLA | `hsla(14, 100%, 60%, 0.5)` | HSL with transparency |

> **Pro tip:** Use **HSL** when designing. It's the easiest format to adjust — change the first number to shift the color, second for saturation, third for lightness.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add custom fonts with Google Fonts or `@font-face`
- [ ] Style text with proper sizing, spacing, and alignment
- [ ] Use HSL colors and create gradient backgrounds

</details>

---

## Phase 4: Flexbox

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master one-dimensional layouts — the most used CSS layout system.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Flexbox Basics | `display: flex` turns a container into a flex layout — items line up automatically |
| 2 | Main & Cross Axis | `flex-direction: row` (horizontal) vs `column` (vertical) — changes how items flow |
| 3 | Justify Content | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` — main axis alignment |
| 4 | Align Items | `stretch`, `center`, `flex-start`, `flex-end`, `baseline` — cross axis alignment |
| 5 | Gap | `gap`, `row-gap`, `column-gap` — clean spacing between items without margin hacks |
| 6 | Flex Grow, Shrink, Basis | `flex-grow` (expand), `flex-shrink` (compress), `flex-basis` (starting size) — how items share space |
| 7 | Flex Wrap | `flex-wrap: wrap` — items move to the next line instead of overflowing |
| 8 | Align Self & Order | Override alignment per item (`align-self`), change visual order without touching HTML (`order`) |
| 9 | Common Patterns | Navigation bars, centering anything, card layouts, sticky footers, holy grail layout |

> [!TIP]
> The fastest way to center anything vertically and horizontally:
> ```css
> .parent {
>   display: flex;
>   justify-content: center;
>   align-items: center;
> }
> ```

<details>
<summary><strong>Visual: Flexbox Axes</strong></summary>

```
flex-direction: row (default)
┌──────────────────────────────────────────┐
│  ┌──────┐  ┌──────┐  ┌──────┐           │
│  │Item 1│  │Item 2│  │Item 3│           │
│  └──────┘  └──────┘  └──────┘           │
│  ← ─ ─ ─ ─ MAIN AXIS ─ ─ ─ ─ ─ ─ → │
└──────────────────────────────────────────┘
       ↑ CROSS AXIS ↓

flex-direction: column
┌──────────────┐
│  ┌──────────┐│  ↑
│  │  Item 1  ││  │
│  └──────────┘│  │
│  ┌──────────┐│  MAIN
│  │  Item 2  ││  AXIS
│  └──────────┘│  │
│  ┌──────────┐│  │
│  │  Item 3  ││  ↓
│  └──────────┘│
│← CROSS AXIS →│
└──────────────┘
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a navigation bar using flexbox
- [ ] Center content both horizontally and vertically
- [ ] Use `flex-grow` and `flex-shrink` to distribute space

</details>

---

## Phase 5: CSS Grid

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master two-dimensional layouts — rows AND columns at the same time.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Grid Basics | `display: grid` creates a 2D layout — define rows and columns explicitly |
| 2 | Defining Columns & Rows | `grid-template-columns`, `grid-template-rows`, and the `fr` (fraction) unit |
| 3 | Gap | `gap`, `column-gap`, `row-gap` — spacing between grid cells |
| 4 | Placing Items | `grid-column: 1 / 3`, `grid-row: 1 / 2` — place items across specific cells |
| 5 | Named Grid Areas | `grid-template-areas` — visually lay out your page in CSS like a blueprint |
| 6 | Auto Fit & Auto Fill | `auto-fit` and `auto-fill` with `minmax()` — responsive grids without media queries |
| 7 | Implicit vs Explicit Grids | What happens when you have more items than defined cells |
| 8 | Grid Alignment | `justify-items`, `align-items`, `justify-content`, `align-content` — control placement |
| 9 | Common Patterns | Page layouts, image galleries, dashboard grids, card grids |

> [!IMPORTANT]
> **Flexbox vs Grid** — Use Flexbox for 1D layouts (nav bars, single rows/columns). Use Grid for 2D layouts (page structure, galleries). They work great together.

<details>
<summary><strong>Quick Reference: Grid Template Areas</strong></summary>

```css
.container {
  display: grid;
  grid-template-areas:
    "header  header  header"
    "sidebar content content"
    "footer  footer  footer";
  grid-template-columns: 200px 1fr 1fr;
  grid-template-rows: auto 1fr auto;
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer  { grid-area: footer; }
```

> This reads like a visual blueprint of your page layout — one of the most powerful features in CSS.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a page layout using `grid-template-areas`
- [ ] Create a responsive card grid with `auto-fit` and `minmax()`
- [ ] Explain the difference between Flexbox and Grid

</details>

---

## Phase 6: Responsive Design

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make your designs work beautifully on every screen size.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Mobile-First Approach | Write CSS for mobile first, then add styles for larger screens — not the other way around |
| 2 | Media Queries | `@media (min-width: 768px) { }` — apply styles only when the screen is wide enough |
| 3 | Common Breakpoints | Mobile (<768px), Tablet (768-1024px), Desktop (>1024px) — and why exact pixels don't matter |
| 4 | Responsive Units | `rem`, `em`, `%`, `vw`, `vh`, `vmin`, `vmax` — stop using `px` for everything |
| 5 | Fluid Typography | `clamp(1rem, 2.5vw, 2rem)` — font sizes that smoothly scale with the viewport |
| 6 | Responsive Images | `max-width: 100%`, `object-fit`, `object-position` — images that adapt to any container |
| 7 | `calc()` Function | `width: calc(100% - 2rem)` — do math in CSS for dynamic sizing |
| 8 | Container Queries | `@container` — responsive styles based on the parent element's size, not the viewport |

> [!WARNING]
> Never use `px` for font sizes in production. Users who've increased their browser's default font size (for accessibility) will see no effect. Use `rem` instead.

<details>
<summary><strong>Quick Reference: Responsive Units</strong></summary>

| Unit | Relative To | Best For |
|------|-------------|----------|
| `px` | Nothing (absolute) | Borders, shadows, tiny details |
| `rem` | Root font size (16px default) | Font sizes, spacing, padding |
| `em` | Parent element's font size | Scaling within components |
| `%` | Parent element's size | Widths, heights |
| `vw` | 1% of viewport width | Full-width sections |
| `vh` | 1% of viewport height | Full-height hero sections |
| `clamp()` | Min/preferred/max | Fluid font sizes and spacing |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a layout that works on mobile, tablet, and desktop
- [ ] Write mobile-first media queries with `min-width`
- [ ] Use `clamp()` for fluid typography

</details>

---

## Phase 7: Transitions & Animations

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Add smooth motion and life to your designs.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Transitions | `transition: property duration easing delay` — smoothly animate property changes |
| 2 | Easing Functions | `ease`, `ease-in`, `ease-out`, `ease-in-out`, `cubic-bezier()` — control the speed curve |
| 3 | Transform: 2D | `translate()`, `rotate()`, `scale()`, `skew()` — move, spin, resize, and tilt elements |
| 4 | Transform: 3D | `rotateX()`, `rotateY()`, `perspective` — add depth to your transforms |
| 5 | `@keyframes` Animations | Define multi-step animations: `from/to` or percentage-based keyframes |
| 6 | Animation Properties | `animation-name`, `duration`, `delay`, `iteration-count`, `direction`, `fill-mode` |
| 7 | Performance | Only animate `transform` and `opacity` — they're GPU-accelerated. Avoid animating `width`, `height`, `top`, `left` |
| 8 | `prefers-reduced-motion` | Respect users who have motion sensitivity — wrap animations in this media query |

> [!CAUTION]
> Never animate `width`, `height`, `margin`, or `top`/`left` — they cause layout recalculations and will feel janky. Use `transform: translate()` and `transform: scale()` instead — they're GPU-accelerated and silky smooth.

<details>
<summary><strong>Quick Reference: Transition vs Animation</strong></summary>

| Feature | Transition | Animation |
|---------|-----------|-----------|
| Trigger | Needs a state change (`:hover`, class toggle) | Runs automatically or on trigger |
| Steps | Only A → B (two states) | Multiple steps with `@keyframes` |
| Repeat | Once per trigger | Can loop infinitely |
| Control | Simple | Full control (pause, reverse, delay) |
| Best For | Hover effects, button states | Loading spinners, attention-grabbers |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add smooth hover transitions to buttons and cards
- [ ] Create a `@keyframes` animation (loading spinner, fade-in)
- [ ] Use `transform` instead of position properties for animations

</details>

---

## Phase 8: Advanced Selectors & Pseudo-classes

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Target elements with precision using advanced selectors.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Attribute Selectors | `[href]`, `[type="email"]`, `[class*="btn"]` — select elements by their attributes |
| 2 | State Pseudo-classes | `:hover`, `:active`, `:focus`, `:focus-visible`, `:visited` — style interactive states |
| 3 | Structural Pseudo-classes | `:first-child`, `:last-child`, `:nth-child(2n)`, `:nth-of-type()` — select by position |
| 4 | Form Pseudo-classes | `:checked`, `:disabled`, `:valid`, `:invalid`, `:required`, `:placeholder-shown` |
| 5 | Pseudo-elements | `::before`, `::after` (insert content), `::first-letter`, `::selection`, `::placeholder` |
| 6 | Modern Selectors | `:is()` (matches any), `:where()` (zero specificity), `:has()` (parent selector!), `:not()` |

> [!TIP]
> `:has()` is the "parent selector" CSS developers waited 20 years for. You can now style a parent based on its children:
> ```css
> /* Style a card differently if it contains an image */
> .card:has(img) {
>   grid-template-rows: 200px 1fr;
> }
> ```

<details>
<summary><strong>Quick Reference: nth-child Patterns</strong></summary>

| Pattern | Selects |
|---------|---------|
| `:nth-child(odd)` | 1st, 3rd, 5th... (alternating rows) |
| `:nth-child(even)` | 2nd, 4th, 6th... |
| `:nth-child(3)` | Only the 3rd child |
| `:nth-child(3n)` | Every 3rd child (3, 6, 9...) |
| `:nth-child(n+4)` | 4th child and everything after |
| `:nth-child(-n+3)` | Only the first 3 children |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Style form inputs differently based on validation state (`:valid`, `:invalid`)
- [ ] Use `::before` and `::after` to add decorative elements
- [ ] Use `:has()` to style a parent based on its children

</details>

---

## Phase 9: CSS Architecture & Methodologies

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Write CSS that scales — organize, name, and structure your styles for real projects.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Cascade | How browsers decide which styles win: position, specificity, origin, `!important` |
| 2 | Specificity | ID (1-0-0) > class (0-1-0) > element (0-0-1) — why your styles sometimes don't apply |
| 3 | Inheritance | Which properties inherit from parents (`color`, `font`) and which don't (`margin`, `padding`) |
| 4 | BEM Naming | Block-Element-Modifier: `.card`, `.card__title`, `.card--featured` — predictable CSS naming |
| 5 | CSS Custom Properties | `--primary: #3498db;` and `var(--primary)` — variables that cascade and can change at runtime |
| 6 | Theming with Variables | Dark mode, light mode, brand themes — swap entire color systems by changing a few variables |
| 7 | `@layer` (Cascade Layers) | Organize CSS into layers with explicit priority — no more specificity wars |
| 8 | Code Organization | Split CSS into files (reset, layout, components, utilities), plan your architecture |

> [!IMPORTANT]
> **`!important` is almost never the answer.** If you need it, your specificity is out of control. Fix the root cause: simplify your selectors, use BEM naming, or use `@layer`.

<details>
<summary><strong>Quick Reference: BEM Naming Convention</strong></summary>

```css
/* Block — standalone component */
.card { }

/* Element — part of the block (double underscore) */
.card__title { }
.card__image { }
.card__body { }

/* Modifier — variation or state (double hyphen) */
.card--featured { }
.card--dark { }
.card__title--large { }
```

> **Why BEM?** Every class is flat (no nesting), specificity stays low, and the name tells you exactly what it styles and where it belongs.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Calculate specificity for any CSS selector
- [ ] Refactor a project to use BEM naming
- [ ] Implement dark/light mode with CSS custom properties

</details>

---

## Phase 10: Modern CSS & Best Practices

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Use cutting-edge CSS features and write production-quality code.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | CSS Filters | `blur()`, `brightness()`, `contrast()`, `grayscale()`, `hue-rotate()`, `saturate()` — image effects in CSS |
| 2 | Blend Modes | `mix-blend-mode`, `background-blend-mode` — Photoshop-style layer blending |
| 3 | Clip Path | `clip-path: polygon()` / `circle()` / `ellipse()` — crop elements into custom shapes |
| 4 | Backdrop Filter | `backdrop-filter: blur(10px)` — frosted glass effect behind elements |
| 5 | CSS Nesting | Native nesting without preprocessors: `& .child { }` — cleaner, DRY stylesheets |
| 6 | Subgrid | `grid-template-columns: subgrid` — child grids that align with the parent grid |
| 7 | Scroll Snap | `scroll-snap-type`, `scroll-snap-align` — smooth, app-like scrolling sections |
| 8 | Performance | Critical CSS, unused CSS removal, `will-change`, `content-visibility` — make your CSS fast |
| 9 | `@supports` | Feature detection: `@supports (display: grid) { }` — use modern CSS with fallbacks |
| 10 | Cross-Browser Testing | Test in Chrome, Firefox, Safari. Check [Can I Use](https://caniuse.com/) before shipping |

> [!TIP]
> The frosted glass effect is just two lines of CSS:
> ```css
> .glass {
>   background: rgba(255, 255, 255, 0.1);
>   backdrop-filter: blur(10px);
> }
> ```

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create a frosted glass effect with `backdrop-filter`
- [ ] Use `clip-path` to create a non-rectangular section
- [ ] Implement CSS nesting in a real project
- [ ] Run a Lighthouse audit and score 90+ on performance

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most CSS learners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `!important` everywhere | Breaks the cascade, makes debugging a nightmare | Fix specificity issues at the source — simplify selectors |
| 2 | Using `px` for font sizes | Ignores user accessibility settings (browser zoom) | Use `rem` for font sizes, `px` only for borders/shadows |
| 3 | Forgetting `box-sizing: border-box` | Width calculations become confusing (padding adds to width) | Set `* { box-sizing: border-box; }` globally |
| 4 | Overly specific selectors | `div.container > ul.nav > li.nav-item > a.link` — impossible to override | Use flat class selectors: `.nav-link` |
| 5 | Not using a CSS reset | Different browsers have different default styles | Use Normalize.css or a modern CSS reset |
| 6 | Animating layout properties | Animating `width`, `height`, `top`, `left` causes janky performance | Animate `transform` and `opacity` only |
| 7 | Hardcoding colors everywhere | Changing a brand color means find-and-replace across files | Use CSS custom properties (`--primary-color`) |
| 8 | Using floats for layout | Floats were a hack — they cause clearing issues and headaches | Use Flexbox or Grid |
| 9 | Ignoring mobile from the start | Retrofitting responsive design is painful and error-prone | Start mobile-first, enhance with `min-width` queries |
| 10 | One giant CSS file | Impossible to find anything, merge conflicts, slow loading | Split into component files or use a methodology (BEM) |

---

## Interview Questions

Test your CSS knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the CSS Box Model?**
   - Every element is a box made of 4 layers: content (innermost) → padding → border → margin (outermost). `box-sizing: border-box` makes width/height include padding and border.

2. **What's the difference between `margin` and `padding`?**
   - `padding` is space inside the border (part of the element). `margin` is space outside the border (between elements). Vertical margins collapse; padding never does.

3. **What are the differences between `block`, `inline`, and `inline-block`?**
   - `block`: takes full width, starts on a new line, respects all margin/padding. `inline`: only takes needed width, ignores vertical margin/padding. `inline-block`: flows inline but respects all box model properties.

4. **How do you center a div horizontally?**
   - Block element: `margin: 0 auto;` with a set width. Or use flexbox: `display: flex; justify-content: center;` on the parent.

5. **What is the difference between `class` and `id` selectors?**
   - Classes (`.name`) can be reused on multiple elements. IDs (`#name`) must be unique per page. IDs have higher specificity (1-0-0 vs 0-1-0). Use classes for styling, IDs for JavaScript hooks.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain CSS Specificity. How is it calculated?**
   - Specificity determines which CSS rule wins when multiple rules target the same property. Calculated as: inline styles (1-0-0-0) > ID (1-0-0) > class/attribute/pseudo-class (0-1-0) > element/pseudo-element (0-0-1). Higher specificity always wins; equal specificity goes to the last rule.

2. **What's the difference between Flexbox and Grid?**
   - Flexbox is 1D (row OR column) — best for components like navbars, card rows, centering. Grid is 2D (rows AND columns) — best for page layouts, dashboards, galleries. Use both together: Grid for the page structure, Flexbox for components within it.

3. **What is `position: sticky` and how does it work?**
   - An element with `position: sticky` behaves like `relative` until you scroll past a threshold (e.g., `top: 0`), then it becomes `fixed`. Commonly used for sticky headers. It only works within its parent container.

4. **What are CSS Custom Properties and how do they differ from Sass variables?**
   - CSS Custom Properties (`--name`) are runtime variables that cascade and can be changed with JavaScript. Sass variables (`$name`) are compiled away at build time and don't exist in the browser. CSS variables can be scoped, inherited, and toggled dynamically (great for theming).

5. **How do media queries work? What's the mobile-first approach?**
   - Media queries apply CSS rules conditionally: `@media (min-width: 768px) { }`. Mobile-first means your base CSS is for mobile; you add `min-width` queries to enhance for larger screens. This results in simpler base styles and better mobile performance.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What is the Stacking Context and why does `z-index` sometimes not work?**
   - A stacking context is a 3D layer group. `z-index` only compares elements within the same stacking context. New contexts are created by: positioned elements with `z-index`, `opacity < 1`, `transform`, `filter`. If `z-index` isn't working, the element is probably in a different stacking context than you think.

2. **Explain `::before` and `::after`. When would you use them?**
   - Pseudo-elements that insert content before/after an element's content without adding HTML. Require the `content` property. Use for: decorative elements (lines, icons), tooltips, clearfix, custom list markers, overlay effects. They're style-only — don't use them for meaningful content.

3. **How would you implement dark mode with CSS?**
   - Define colors as CSS custom properties. Use `@media (prefers-color-scheme: dark) { }` to detect OS preference and override the variables. Or toggle a `.dark` class on `<html>` via JavaScript. Store user preference in `localStorage`.

4. **What properties are safe to animate for 60fps performance?**
   - Only `transform` and `opacity` are GPU-composited. Animating `width`, `height`, `margin`, `top`, `left` triggers layout recalculation (expensive). Use `transform: translate()` instead of `left/top`, and `transform: scale()` instead of `width/height`. Use `will-change` sparingly for hints.

5. **What is the `:has()` selector and why is it revolutionary?**
   - `:has()` is the first true "parent selector" in CSS. It lets you style an element based on its children: `.card:has(img)` styles cards that contain images. It enables logic that previously required JavaScript. Supported in all modern browsers since late 2023.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Styled Bio Page
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** Take your HTML bio page and make it beautiful — custom fonts, colors, spacing, and a polished layout.

**Skills practiced:** Selectors, box model, typography, colors, backgrounds.

---

### Project 2: Flexbox Navigation & Card Layout
![Phase 4](https://img.shields.io/badge/After-Phase%204-green)

**What you'll build:** A responsive navigation bar with logo, links, and a CTA button + a row of feature cards that wrap on smaller screens.

**Skills practiced:** Flexbox container/item properties, gap, wrapping, alignment.

---

### Project 3: Grid-Based Landing Page
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** A full landing page with hero section, feature grid, testimonials, and footer — fully responsive across all devices.

**Skills practiced:** CSS Grid, media queries, responsive units, mobile-first approach.

---

### Project 4: Animated Portfolio
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-yellow)

**What you'll build:** A personal portfolio with smooth hover effects, page transitions, animated skill bars, and interactive cards.

**Skills practiced:** Transitions, transforms, keyframe animations, pseudo-elements, advanced selectors.

---

### Project 5: Production Dashboard
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** A dashboard with sidebar navigation, data cards, dark/light mode toggle, and modern visual effects. BEM naming, CSS variables, and Lighthouse score 90+.

**Skills practiced:** Everything from all phases — your CSS graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [MDN — Learn CSS](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics) | The gold standard. Structured modules from basics to advanced, written by Mozilla |
| [web.dev — Learn CSS](https://web.dev/learn/css) | Google's modern CSS course. 25 modules covering every topic with interactive examples |
| [W3Schools CSS Tutorial](https://www.w3schools.com/css/) | "Try It Yourself" editor on every page — great for quick experimentation |
| [CSS-Tricks](https://css-tricks.com/) | In-depth guides on Flexbox, Grid, and modern CSS. The [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) and [Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/) are legendary |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 100% free. Build 5 certification projects. Learn by writing code, not watching videos |
| [The Odin Project — CSS](https://www.theodinproject.com/paths/full-stack-javascript/courses/intermediate-html-and-css) | Project-based. Teaches you how to think about CSS, not just memorize properties |
| [Codecademy — Learn CSS](https://www.codecademy.com/learn/learn-css) | In-browser coding with instant feedback. Step-by-step lessons |
| [Flexbox Froggy](https://flexboxfroggy.com/) | Learn Flexbox by guiding frogs to their lily pads. 24 levels, surprisingly addictive |
| [Grid Garden](https://cssgridgarden.com/) | Learn CSS Grid by watering a garden. 28 levels from basic to advanced |
| [CSS Battle](https://cssbattle.dev/) | Competitive CSS challenges — replicate designs with the least code possible |

### YouTube (Specific Courses)

| Video / Channel | Why Watch |
|----------------|-----------|
| [Kevin Powell](https://www.youtube.com/@KevinPowell) | The best CSS educator on YouTube. 1000+ videos covering everything from basics to bleeding-edge features |
| [Traversy Media — CSS Crash Course](https://www.youtube.com/@TraversyMedia) | Best first CSS video. Covers fundamentals in ~1 hour with practical examples |
| [Web Dev Simplified — Learn CSS](https://www.youtube.com/@WebDevSimplified) | Clear, concise explanations. Great for specific topics (Grid, Flexbox, animations) |
| [Josh W. Comeau — Interactive Guides](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/) | Not YouTube, but the best interactive visual guides to [Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/) and [Grid](https://www.joshwcomeau.com/css/interactive-guide-to-grid/) |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — CSS](https://roadmap.sh/css) | Interactive learning path — click each topic to see resources. Track your progress |

### Practice & Build Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional Figma designs to build. Real-world workflow. Community code reviews |
| [freeCodeCamp Projects](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 5 certification projects — build them to earn a free certificate |
| [DevChallenges](https://devchallenges.io/) | Front-end projects with varying difficulty. Great for portfolio building |
| [100 Days CSS](https://100dayscss.com/) | Daily CSS challenges to sharpen skills — small, focused exercises |
| [Frontend Practice](https://www.frontendpractice.com/) | Recreate real, beautifully designed websites. Learn by reverse-engineering |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) | Auto-refreshes the browser on save. Essential for CSS development |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-formats your CSS on save. Consistent code every time |
| [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek) | Ctrl+click a class name in HTML to jump to its CSS definition |
| [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info) | Hover over any color value to see a visual preview and format conversions |
| [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) | Autocompletes class names in HTML from your CSS files |

### CSS Generators (Save Time)

| Tool | What It Generates |
|------|-------------------|
| [CSSGradient.io](https://cssgradient.io/) | Visual gradient builder — linear, radial, conic gradients with live preview |
| [Neumorphism.io](https://neumorphism.io/) | Soft UI / neumorphic shadow generator |
| [Clippy](https://bennettfeely.com/clippy/) | Interactive `clip-path` builder — create custom shapes visually |
| [Grid Generator (Layoutit)](https://grid.layoutit.com/) | Visual CSS Grid builder — drag and drop, export clean code |
| [Flexbox Generator](https://www.cssportal.com/css-flexbox-generator/) | Visual Flexbox builder with live preview |
| [Cubic Bezier](https://cubic-bezier.com/) | Custom animation easing curve builder — visualize your timing functions |
| [Haikei](https://haikei.app/) | Generate SVG backgrounds, waves, blobs — copy the CSS directly |

### Validation & Testing

| Tool | What It Checks |
|------|---------------|
| [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) | Official CSS validator — finds syntax errors and invalid properties |
| [Can I Use](https://caniuse.com/) | Check if a CSS feature works in all browsers before using it |
| [CSS Stats](https://cssstats.com/) | Analyze any site's CSS — number of selectors, colors, font sizes, specificity graph |
| [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/) | Built into Chrome DevTools. Scores your page on performance, accessibility, SEO |
| [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) | Check if your text/background color combination meets WCAG standards |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [CSS-Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) | The definitive visual Flexbox reference — bookmark this |
| [CSS-Tricks Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/) | The definitive visual Grid reference — bookmark this too |
| [MDN CSS Cheatsheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cheatsheet) | Official Mozilla quick reference |
| [htmlcheatsheet.com/css](https://htmlcheatsheet.com/css/) | Interactive — edit CSS in the cheat sheet and see live results |

---

[Back to Main Syllabus](../README.md)

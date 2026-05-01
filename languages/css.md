# CSS Syllabus

A complete, structured learning path for CSS — your one-stop guide from styling your first paragraph to building responsive, animated, accessible, theme-aware production interfaces. Whether you have never written a line of CSS or you've been writing it for years and want to fill the gaps, this syllabus walks you through every concept in the right order, explains *why* each matters, lists the **frameworks and tools** you'll meet on the job, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 8-12 Weeks](https://img.shields.io/badge/Duration-8--12%20Weeks-blue)
![Topics: 13 Phases](https://img.shields.io/badge/Topics-13%20Phases-orange)

---

## Table of Contents

- [What is CSS?](#what-is-css)
- [Why Learn CSS in 2026?](#why-learn-css-in-2026)
- [How CSS Works](#how-css-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Selectors & The Cascade](#phase-2-selectors--the-cascade)
- [Phase 3: Box Model, Display & Positioning](#phase-3-box-model-display--positioning)
- [Phase 4: Typography & Color](#phase-4-typography--color)
- [Phase 5: Flexbox](#phase-5-flexbox)
- [Phase 6: CSS Grid](#phase-6-css-grid)
- [Phase 7: Responsive Design](#phase-7-responsive-design)
- [Phase 8: Transitions, Animations & Transforms](#phase-8-transitions-animations--transforms)
- [Phase 9: Modern CSS Features](#phase-9-modern-css-features)
- [Phase 10: CSS Architecture & Theming](#phase-10-css-architecture--theming)
- [Phase 11: CSS Frameworks & Tooling](#phase-11-css-frameworks--tooling)
- [Phase 12: Performance, Accessibility & Best Practices](#phase-12-performance-accessibility--best-practices)
- [Phase 13: What's Next? (JS, Frameworks, Design Systems)](#phase-13-whats-next-js-frameworks--design-systems)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## What is CSS?

**CSS (Cascading Style Sheets) is the language that controls how web pages look.** Every color you've seen on the web, every font, every spacing, every animation, every responsive layout that adapts to your phone — all CSS. HTML decides *what* is on the page; CSS decides *how it looks*.

Created by **Håkon Wium Lie at CERN in 1994** and standardized by the W3C, CSS solved a real crisis: in the early web, styling was tangled into HTML (`<font color="red">`, `<center>`), making sites unmaintainable. CSS separated structure (HTML) from presentation (CSS) — a clean line that the entire modern web is built on.

In simple words:

- **HTML** is the *structure* of a web page (the skeleton).
- **CSS** is the *style* (the look — colors, layout, motion).
- **JavaScript** is the *behavior* (the brain — interactivity).

You can build a web page with HTML alone. It will look like a 1992 government website. Add CSS and suddenly it looks like a real product.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 1996 | CSS1 | First spec. Selectors, fonts, colors, basic positioning. |
| 1998 | CSS2 | Floats, positioning, media types. The version that ran the web for ~15 years. |
| 2011+ | CSS3 (modular) | Spec broke into modules. Border-radius, gradients, transitions, animations, transforms, media queries. |
| 2017 | Flexbox + Grid | The biggest layout upgrade in CSS history. No more float hacks. |
| 2020+ | Custom properties, `clamp()`, modern color | The "modern CSS" era kicks off. |
| 2022–2026 | `:has()`, `@layer`, `@scope`, `@property`, nesting, container queries, view transitions, anchor positioning | Things that used to need JavaScript or preprocessors are now native CSS. |

> [!IMPORTANT]
> "CSS3" is no longer a meaningful version number — CSS is now developed as **independent modules**, each at its own version. When people say "modern CSS," they mean the post-2020 wave: Flexbox, Grid, custom properties, container queries, `:has()`, and the new color/layout features landing every quarter.

### What Makes CSS Special

- **Declarative.** You describe what you want (`color: red`); the browser figures out how to draw it.
- **Cascading.** Multiple rules can target the same element — CSS has well-defined rules for which one wins.
- **Forgiving.** Invalid CSS doesn't crash the page; the browser just ignores what it doesn't understand. Great for progressive enhancement.
- **Surprisingly powerful.** Modern CSS handles layout, animation, theming, responsive design, even logic (`:has()`) — things that used to require JavaScript.
- **The most-underestimated language in dev.** Senior CSS engineers are rare and well-paid.

---

## Why Learn CSS in 2026?

| Reason | What It Means |
|--------|---------------|
| **Mandatory for every web job** | Frontend, full-stack, designer-developer, design-system engineer — they all need CSS. |
| **Modern CSS replaces JavaScript** | Nesting, `:has()`, `@scope`, `@layer`, container queries, view transitions — all native now. Fewer libraries, faster pages. |
| **Tailwind owns the job market** | Most React/Vue/Next jobs in 2026 list Tailwind CSS. Knowing the underlying CSS makes you 10× faster with Tailwind. |
| **Design systems are a profession** | Companies like Stripe, GitHub, Shopify employ entire teams to build CSS-driven design systems. |
| **Accessibility law** | ADA (US), EAA (EU), AODA (Canada) — companies are sued for inaccessible CSS (bad contrast, missing focus styles, motion that triggers vertigo). |
| **The frontend interview filter** | "Center a div" / "BEM" / "specificity" / "Flexbox vs Grid" / "explain `:has()`" — every frontend interview tests CSS. |
| **Pays well** | Senior frontend / design-system roles in 2026: **$100k–$200k** (US), **₹10L–₹40L** (India). |

---

## How CSS Works

When the browser loads a page, it builds two trees in parallel: the **DOM** (from HTML) and the **CSSOM** (from CSS). It then merges them into the **render tree**, which is what gets painted to the screen.

```
   ┌────────────┐         ┌────────────┐
   │   HTML     │         │    CSS     │
   └─────┬──────┘         └─────┬──────┘
         ▼                      ▼
   ┌────────────┐         ┌────────────┐
   │    DOM     │         │   CSSOM    │
   └─────┬──────┘         └─────┬──────┘
         └──────────┬───────────┘
                    ▼
              ┌──────────┐
              │  Render  │
              │   Tree   │
              └────┬─────┘
                   ▼
       Layout → Paint → Composite
                   ▼
            Pixels on screen
```

Three things to internalize:

1. **The Cascade.** Multiple CSS rules can match the same element. CSS resolves conflicts using *origin*, *specificity*, and *order*.
2. **Inheritance.** Some properties (like `color`, `font-family`) inherit from parent to child. Others (like `margin`, `padding`) don't.
3. **Box Model.** Every visible element is a rectangle made of *content + padding + border + margin*. Layout = arranging boxes.

That's the entire mental model. The rest is vocabulary.

---

## Pick Your Path

CSS is huge — most people don't need every phase equally. Pick the track that matches your goal. Each one tells you what to focus on, what to skip, and what to do next.

### Track 1 — Frontend Engineer (8–12 weeks)
**Goal:** ship beautiful, responsive, accessible UIs alongside HTML and JavaScript.

Do every phase in order. Spend extra time on **Selectors & Cascade**, **Flexbox**, **Grid**, **Responsive Design**, and **Architecture**. Build all 6 [Practice Projects](#practice-projects). Pair with the [HTML Syllabus](html.md) and the [JavaScript Syllabus](javascript.md). After Phase 11, learn **Tailwind** — most job postings expect it.

### Track 2 — Design System Engineer (10–14 weeks)
**Goal:** build the CSS that powers a whole product (tokens, themes, components).

All phases, with extra depth on **Architecture & Theming** (custom properties, `@layer`), **Modern CSS** (`@scope`, `@property`), **Frameworks & Tooling**, and **Accessibility**. Study public design systems: [GitHub Primer](https://primer.style/), [Adobe Spectrum](https://spectrum.adobe.com/), [Shopify Polaris](https://polaris.shopify.com/), [Atlassian Design](https://atlassian.design/).

### Track 3 — Modernize Your CSS (3–5 weeks)
**Goal:** you've been writing CSS for years but stopped at Flexbox. Catch up to 2026.

Skim Phases 1–8 (you know it). Focus on **Modern CSS Features** (`:has()`, `@layer`, `@scope`, nesting, container queries, view transitions), **Architecture & Theming**, and **Frameworks** (Tailwind if you haven't tried it, Open Props for design tokens). Replace your float/clearfix instincts with Grid, your BEM with `@layer`, your Sass with native nesting.

### Track 4 — Tailwind-First Developer (4–6 weeks)
**Goal:** ship Tailwind-based UIs in React/Vue/Next/Astro.

You still need the underlying CSS — Tailwind is just CSS shorthand. Drill **Selectors**, **Box Model**, **Flexbox**, **Grid**, **Responsive**, and **Architecture**. Then go through the Tailwind docs in Phase 11. The CSS knowledge makes you 10× faster with Tailwind because you understand what each utility actually does.

### Track 5 — Interview Prep (2–4 weeks)
**Goal:** you already know CSS and have a frontend interview coming up.

Drill: **The Cascade**, **Specificity**, **Box Model**, **Flexbox vs Grid**, **Positioning** (especially stacking contexts and `z-index`), **Custom Properties**, **`:has()`**. Re-read [Common Mistakes](#common-mistakes) and [Interview Questions](#interview-questions). Be ready to write "center a div" in 5 ways and explain BEM.

> [!TIP]
> Whichever track you pick, **Phase 2 (Selectors & The Cascade)** and **Phase 5/6 (Flexbox & Grid)** are the three phases every track depends on — read them carefully.

---

## Prerequisites

> [!NOTE]
> You should know **basic HTML** before starting CSS. CSS without HTML is like paint without a wall — there's nothing to apply it to. If you haven't already, complete the [HTML Syllabus](html.md) first (or do the first 4 phases of it in parallel).

- HTML fundamentals (elements, attributes, `id` and `class`, document structure)
- A code editor — [VS Code](https://code.visualstudio.com/) recommended (free, best CSS support via the Live Server extension)
- A modern browser — [Chrome](https://www.google.com/chrome/) recommended for the best DevTools
- A [GitHub account](https://github.com/) to store and deploy your work from day one

---

## How to Use This Syllabus

1. **Don't skip phases.** CSS is one of those subjects where gaps haunt you forever. If Phase 2 (Cascade) is shaky, every later debugging session feels like guesswork.
2. **Type the code yourself.** Copy-pasting gives the illusion of learning. Type every example.
3. **Inspect everything.** Right-click any element on any website → "Inspect" → look at the CSS. Reading other people's CSS is the fastest way to learn.
4. **Build with the cascade, not against it.** Your goal is to *use* specificity intentionally, not fight it with `!important`.
5. **Build the project after every 2–3 phases** — reading is not the same as doing. Deploy each one (Vercel/Netlify/Cloudflare Pages, all free).
6. **Run Lighthouse** on every project. Aim 90+ on Performance and Accessibility before calling it done.
7. **Commit to GitHub** from day one.

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. There is no rush — depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what CSS is and write your first styles.

**What this phase is about.** Before you can style anything, you need to know **how to attach CSS to HTML** (three ways — but only one is right), the **anatomy of a CSS rule** (selector + property + value), and the **basic selectors** that 80% of CSS uses. You'll write your first stylesheet, link it to a page, and see styles applied.

**Why it matters.** This phase looks trivial but the habits formed here (always external CSS, always classes over IDs, always lowercase) carry through your entire career. Skipping the basics here means rewriting your first 10 projects later.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is CSS | Cascading Style Sheets — the language that controls how HTML looks. Created in 1996 |
| 2 | Three Ways to Add CSS | Inline (`style=""`), internal (`<style>`), external (`.css` file) — and why external wins for everything |
| 3 | CSS Syntax | The `selector { property: value; }` pattern. Every line ends in `;`. Comments use `/* */` |
| 4 | Basic Selectors | Type (`p`), class (`.intro`), ID (`#header`), universal (`*`) — and why classes beat IDs for styling |
| 5 | Combining Selectors | Descendant (space), child (`>`), adjacent sibling (`+`), general sibling (`~`), grouped (`a, b`) |
| 6 | Your First Styles | `color`, `background-color`, `font-size`, `text-align`, `padding`, `margin` |
| 7 | DevTools Inspection | Right-click → Inspect — see, edit, and debug CSS live in the browser |
| 8 | Linking CSS Files | `<link rel="stylesheet" href="style.css">` — the only correct way in 2026 |

> [!TIP]
> Always use **external CSS files**. Inline (`style="..."`) and internal (`<style>...</style>`) are harder to maintain, can't be cached by the browser, and don't scale. The single `<link>` tag is the right answer 99% of the time.

<details>
<summary><strong>Quick Reference: Selector Types</strong></summary>

| Selector | Syntax | What It Selects |
|----------|--------|-----------------|
| Type | `p` | All `<p>` elements |
| Class | `.card` | All elements with `class="card"` |
| ID | `#header` | The one element with `id="header"` |
| Universal | `*` | Every element on the page |
| Descendant | `div p` | `<p>` inside any `<div>` (any depth) |
| Child | `div > p` | `<p>` directly inside `<div>` (one level only) |
| Adjacent sibling | `h1 + p` | First `<p>` immediately after `<h1>` |
| General sibling | `h1 ~ p` | All `<p>` after `<h1>` (same parent) |
| Grouped | `h1, h2, h3` | All headings 1, 2, 3 |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the three ways to add CSS and why external wins
- [ ] Write CSS rules using type, class, and ID selectors
- [ ] Use descendant and child combinators correctly
- [ ] Inspect any page's CSS using Chrome DevTools

</details>

---

## Phase 2: Selectors & The Cascade

![Phase](https://img.shields.io/badge/Phase-2%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> The single most important phase in this syllabus. If you skip one, don't let it be this one.

**What this phase is about.** When two CSS rules target the same element, **which one wins?** That single question is what makes CSS feel mysterious to beginners. The answer is the **Cascade** — a deterministic algorithm using *origin* (browser, user, author), *specificity* (the rule's "weight"), and *order* (later rules win on ties). You'll also learn **inheritance** (which properties pass from parent to child), **pseudo-classes** (`:hover`, `:focus`, `:nth-child`, `:has()`), **pseudo-elements** (`::before`, `::after`), and **attribute selectors**.

**Why it matters.** "Why isn't my style applying?" is the #1 CSS frustration. The answer is *always* one of: specificity, order, or inheritance. Once this phase clicks, CSS stops feeling random.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Cascade | How browsers decide which rule wins: origin → importance → specificity → order |
| 2 | Specificity | Inline (1-0-0-0) > ID (1-0-0) > class/attr/pseudo (0-1-0) > element (0-0-1). Calculate it for any rule |
| 3 | Inheritance | `color`, `font`, `line-height` inherit. `margin`, `padding`, `border` don't |
| 4 | `inherit`, `initial`, `unset`, `revert` | Force inheritance, reset to default, undo author styles |
| 5 | `!important` | The nuclear option. Why you should almost never use it |
| 6 | Pseudo-classes (state) | `:hover`, `:active`, `:focus`, `:focus-visible`, `:focus-within`, `:visited`, `:disabled` |
| 7 | Pseudo-classes (structural) | `:first-child`, `:last-child`, `:nth-child(2n+1)`, `:nth-of-type()`, `:only-child`, `:empty` |
| 8 | Pseudo-classes (form) | `:checked`, `:disabled`, `:valid`, `:invalid`, `:required`, `:placeholder-shown`, `:user-invalid` |
| 9 | Pseudo-elements | `::before`, `::after` (insert content), `::first-letter`, `::first-line`, `::selection`, `::placeholder`, `::marker` |
| 10 | Attribute Selectors | `[href]`, `[type="email"]`, `[class*="btn"]`, `[href^="https"]`, `[src$=".svg"]` |
| 11 | `:is()` and `:where()` | `:is(h1, h2, h3) { ... }` reduces repetition. `:where()` does the same with **zero specificity** |
| 12 | `:not()` | Negation: `button:not(.primary)` |
| 13 | `:has()` (the parent selector!) | Style an element based on its children. Game-changing — landed in all browsers in 2023 |
| 14 | Specificity Wars | What to do when your styles don't apply: simplify, refactor, use `@layer` (Phase 9) |

> [!IMPORTANT]
> **Calculating specificity** — count the categories from left to right, biggest beats next:
> ```
> #header .nav a:hover     →  (0, 1, 2, 1)  →  0 IDs, 1 ID + 2 classes/pseudo, 1 element
> .button.primary          →  (0, 0, 2, 0)
> button                   →  (0, 0, 0, 1)
> ```
> The rule with the highest specificity wins. On ties, the rule that appears *later* in the stylesheet wins.

> [!TIP]
> `:has()` is the "parent selector" CSS developers waited 20 years for. Style a parent based on its children:
> ```css
> /* Style a card differently if it contains an image */
> .card:has(img) { grid-template-rows: 200px 1fr; }
>
> /* Style a form when it has invalid inputs */
> form:has(:invalid) .submit-btn { opacity: 0.5; }
> ```

<details>
<summary><strong>Quick Reference: nth-child Patterns</strong></summary>

| Pattern | Selects |
|---------|---------|
| `:nth-child(odd)` | 1st, 3rd, 5th… (zebra rows) |
| `:nth-child(even)` | 2nd, 4th, 6th… |
| `:nth-child(3)` | Only the 3rd child |
| `:nth-child(3n)` | Every 3rd (3, 6, 9…) |
| `:nth-child(3n+1)` | Every 3rd starting from 1 (1, 4, 7…) |
| `:nth-child(n+4)` | 4th and everything after |
| `:nth-child(-n+3)` | Only the first 3 |
| `:nth-last-child(1)` | Same as `:last-child` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Calculate specificity for any selector
- [ ] Predict which rule wins given two competing CSS rules
- [ ] Explain which properties inherit and which don't
- [ ] Style form inputs based on validation state (`:valid`, `:invalid`, `:user-invalid`)
- [ ] Use `:has()` to style a parent based on its children
- [ ] Refactor a stylesheet that has too many `!important` declarations

</details>

---

## Phase 3: Box Model, Display & Positioning

![Phase](https://img.shields.io/badge/Phase-3%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Every element is a box. This phase teaches you how to size, space, and place those boxes.

**What this phase is about.** The **Box Model** says every element on a page is a rectangle made of four concentric rings: *content → padding → border → margin*. The `display` property decides whether the box stacks vertically (block), flows with text (inline), or sits in between (inline-block). The `position` property decides whether the box is in the normal flow or floating somewhere specific. Together these three concepts let you control where everything lives.

**Why it matters.** 90% of "why is my layout broken?" questions trace back to the box model, display, or positioning. Get this phase right and Flexbox + Grid (next two phases) feel obvious.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Box Model | Every element: content → padding → border → margin (inside out) |
| 2 | `box-sizing` | `content-box` (default, confusing) vs `border-box` (intuitive — always set this globally) |
| 3 | Margin | Shorthand, individual sides, `auto`, **why vertical margins collapse** |
| 4 | Padding | Inside spacing — never collapses |
| 5 | Borders | `border-width`, `-style`, `-color`, `border-radius` for rounded corners |
| 6 | Outline vs Border | Outline doesn't take up space, doesn't follow `border-radius`. Use for focus rings |
| 7 | `display: block / inline / inline-block` | How elements flow. Block stacks; inline flows with text; inline-block hybrid |
| 8 | `display: none` vs `visibility: hidden` | One removes from layout, one keeps the space |
| 9 | Width & Height | `width`, `height`, `min-width`, `max-width`, `min-height`, `max-height`, `aspect-ratio` |
| 10 | Overflow | `visible`, `hidden`, `scroll`, `auto`, `clip` |
| 11 | Positioning: `static` | The default — element flows normally |
| 12 | Positioning: `relative` | Element nudged from its normal position. Other elements still see its original spot |
| 13 | Positioning: `absolute` | Pulled out of normal flow, positioned relative to the nearest *positioned* ancestor |
| 14 | Positioning: `fixed` | Positioned relative to the viewport — stays put on scroll |
| 15 | Positioning: `sticky` | Acts `relative` until you scroll past a threshold, then becomes `fixed` |
| 16 | `z-index` & Stacking Contexts | What controls layer order. Why your z-index sometimes doesn't work (different stacking context) |
| 17 | Logical Properties | `margin-inline`, `padding-block`, `inset` — direction-aware (RTL/LTR safe) |

> [!IMPORTANT]
> Add this to the top of every CSS file. It makes sizing intuitive: `width: 200px` actually means 200px wide, including padding and border:
> ```css
> *, *::before, *::after { box-sizing: border-box; }
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
<summary><strong>Quick Reference: When `z-index` Doesn't Work</strong></summary>

`z-index` only compares elements inside the **same stacking context**. New stacking contexts are created by:
- A positioned element (`relative`, `absolute`, `fixed`, `sticky`) with a `z-index` value
- `opacity < 1`
- `transform` (any non-`none` value)
- `filter`, `backdrop-filter`
- `will-change`
- `isolation: isolate`

If your `z-index: 9999` isn't winning, the element is in a different stacking context than you think.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Draw the box model from memory
- [ ] Explain why `box-sizing: border-box` is essential
- [ ] Explain margin collapsing and how to prevent it
- [ ] Use all 5 `position` values correctly
- [ ] Debug a `z-index` issue caused by stacking contexts
- [ ] Use logical properties (`margin-inline`, `padding-block`)

</details>

---

## Phase 4: Typography & Color

![Phase](https://img.shields.io/badge/Phase-4%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make text beautiful and master the modern color systems.

**What this phase is about.** Most of what users *read* is text — typography is 80% of design quality. This phase covers font loading (system fonts, Google Fonts, `@font-face`), the type scale (sizes, weights, line-height), and accessible defaults. It also covers CSS's color systems — old (named, hex, RGB) and new (HSL, **OKLCH**, `color-mix()`, relative color syntax) — plus gradients and shadows.

**Why it matters.** Bad typography makes good content unreadable. Bad color makes a great UI fail accessibility. These two areas are the difference between "looks designed" and "looks like a junior project."

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Font Families | Generic families (serif, sans-serif, monospace), font stacks, system font stack |
| 2 | Web Fonts | `@font-face`, Google Fonts, self-hosting, `font-display: swap` for performance |
| 3 | Variable Fonts | One file, infinite weights/widths — modern, lighter, more flexible |
| 4 | Font Properties | `font-size`, `font-weight`, `font-style`, `font-variant`, `line-height`, `letter-spacing`, `word-spacing` |
| 5 | The `font` Shorthand | `font: 1rem/1.5 system-ui, sans-serif;` |
| 6 | Text Properties | `text-align`, `text-transform`, `text-decoration`, `text-indent`, `text-shadow`, `white-space` |
| 7 | Modern Text Wrapping | `text-wrap: balance` for headings, `text-wrap: pretty` for paragraphs |
| 8 | Fluid Typography | `clamp(1rem, 2.5vw, 2rem)` — sizes that smoothly scale with viewport |
| 9 | Named Colors & Hex | `red`, `#FF5733`, short `#F53` |
| 10 | RGB / RGBA | `rgb(255 87 51 / 0.5)` — modern space-separated syntax |
| 11 | HSL / HSLA | Hue (0–360), Saturation, Lightness — easier to reason about and tweak |
| 12 | **OKLCH (modern default in 2026)** | Perceptually uniform colors. Better gradients, accessible by default |
| 13 | `color-mix()` | `color-mix(in oklch, blue 60%, red)` — blend two colors at runtime |
| 14 | Relative Color Syntax | `oklch(from var(--accent) calc(l - 0.1) c h)` — derive variants from a base color |
| 15 | Gradients | `linear-gradient`, `radial-gradient`, `conic-gradient`, multiple color stops |
| 16 | Box & Text Shadows | `box-shadow` for elevation, `text-shadow` for depth |
| 17 | Accessible Typography | Min font size (≥16px body), line-height (1.5+), max line length (60–80ch), contrast ratios |

> [!TIP]
> Use `rem` for font sizes — never `px`. `rem` respects the user's browser font-size setting (an accessibility setting). And in 2026, prefer **OKLCH** for new projects:
> ```css
> :root {
>   --brand: oklch(64% 0.22 245);  /* perceptually uniform blue */
>   --brand-hover: oklch(from var(--brand) calc(l - 0.05) c h);
> }
> body { font-family: system-ui, sans-serif; line-height: 1.6; }
> ```

<details>
<summary><strong>Quick Reference: Color Formats</strong></summary>

| Format | Syntax | Best For |
|--------|--------|----------|
| Named | `red`, `tomato` | Quick prototyping |
| Hex | `#FF5733` | Most common in legacy code |
| RGB / RGBA | `rgb(255 87 51 / 0.5)` | Numeric values |
| HSL / HSLA | `hsl(14 100% 60% / 0.5)` | Easy to tweak |
| **OKLCH** | `oklch(64% 0.22 245)` | **Modern default — perceptually uniform** |
| `color-mix()` | `color-mix(in oklch, red, blue 30%)` | Blend two colors |
| `currentColor` | `border-color: currentColor` | Inherit `color` value |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add a Google Font (or self-host) with `font-display: swap`
- [ ] Use `clamp()` for fluid font sizing
- [ ] Use `text-wrap: balance` on a heading
- [ ] Define a color palette using OKLCH custom properties
- [ ] Verify all text passes WCAG AA contrast (4.5:1)
- [ ] Build a multi-stop gradient with `linear-gradient`

</details>

---

## Phase 5: Flexbox

![Phase](https://img.shields.io/badge/Phase-5%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master one-dimensional layouts — the most-used CSS layout system.

**What this phase is about.** Flexbox is for **one-dimensional layouts** — arranging items in a single row or column. Navigation bars, button groups, card rows, sticky footers, "center this thing" — all Flexbox. You'll learn the **container properties** (`flex-direction`, `justify-content`, `align-items`, `flex-wrap`, `gap`) and the **item properties** (`flex-grow`, `flex-shrink`, `flex-basis`, `align-self`, `order`).

**Why it matters.** Before Flexbox (2017), CSS layout was a hack — floats, `inline-block`, table layouts. Flexbox made layout declarative and predictable. It's what most components use most of the time.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Flexbox? | Replaces float-based layouts. Built for components, not full pages |
| 2 | `display: flex` | Turn a container into a flex layout — items line up automatically |
| 3 | Main vs Cross Axis | `flex-direction: row` (horizontal main) vs `column` (vertical main) |
| 4 | `justify-content` | Main-axis alignment: `flex-start`, `center`, `space-between`, `space-around`, `space-evenly` |
| 5 | `align-items` | Cross-axis alignment: `stretch` (default), `center`, `flex-start`, `flex-end`, `baseline` |
| 6 | `gap`, `row-gap`, `column-gap` | Clean spacing between items — no margin hacks needed |
| 7 | `flex-wrap` | `wrap` so items move to a new line instead of overflowing |
| 8 | `flex-grow` / `flex-shrink` / `flex-basis` | How items share space when there's extra (or not enough) |
| 9 | `flex` Shorthand | `flex: 1` is `1 1 0%`. Most-common pattern |
| 10 | `align-self` | Override alignment per item |
| 11 | `order` | Visually reorder items without changing HTML |
| 12 | Common Patterns | Centering anything, navbars, sticky footers, holy-grail layout, equal-height cards |

> [!TIP]
> The fastest "center anything" pattern in CSS:
> ```css
> .center {
>   display: flex;
>   justify-content: center;
>   align-items: center;
>   min-height: 100vh;
> }
> ```

<details>
<summary><strong>Visual: Flexbox Axes</strong></summary>

```
flex-direction: row (default)
┌──────────────────────────────────────────┐
│  ┌──────┐  ┌──────┐  ┌──────┐            │
│  │Item 1│  │Item 2│  │Item 3│            │
│  └──────┘  └──────┘  └──────┘            │
│  ← ─ ─ ─ ─ MAIN AXIS ─ ─ ─ ─ ─ ─ →       │
└──────────────────────────────────────────┘
       ↑ CROSS AXIS ↓
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a navigation bar using Flexbox
- [ ] Center content both horizontally and vertically
- [ ] Use `flex-grow` and `flex-shrink` to distribute space
- [ ] Build a sticky footer that stays at the bottom
- [ ] Build equal-height cards in a row

</details>

---

## Phase 6: CSS Grid

![Phase](https://img.shields.io/badge/Phase-6%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 7-9 Hours](https://img.shields.io/badge/Time-7--9%20Hours-yellow)

> Master two-dimensional layouts — rows AND columns at the same time.

**What this phase is about.** Grid is for **two-dimensional layouts** — anywhere you need control over both rows *and* columns simultaneously. Page structures, dashboards, image galleries, magazine layouts. You'll learn explicit grids (`grid-template-columns/rows`), implicit grids (auto-generated tracks), the `fr` unit, named grid areas (the most readable layout syntax in CSS), `auto-fit` / `auto-fill` for responsive grids without media queries, and the new **subgrid**.

**Why it matters.** Grid is the most powerful layout tool in CSS, period. Once you internalize it, you stop reaching for libraries to do simple layouts. Combined with Flexbox (Grid for the page structure, Flexbox for components inside), you can build *any* layout.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Grid? | True 2D layout. Replaces table layouts, complex float hacks, and most layout libraries |
| 2 | `display: grid` | Turn a container into a grid |
| 3 | `grid-template-columns/rows` | Define track sizes: `1fr 2fr 1fr`, `repeat(3, 1fr)`, `200px auto 1fr` |
| 4 | The `fr` unit | Fraction of available space — Grid's killer feature |
| 5 | `gap`, `row-gap`, `column-gap` | Spacing between cells |
| 6 | Placing Items by Line | `grid-column: 1 / 3`, `grid-row: 1 / span 2` |
| 7 | **Named Grid Areas** | `grid-template-areas: "header header" "sidebar main"` — the most readable layout in CSS |
| 8 | `minmax()` | `minmax(200px, 1fr)` — flexible tracks with limits |
| 9 | `auto-fit` & `auto-fill` | `repeat(auto-fit, minmax(250px, 1fr))` — responsive grids without media queries |
| 10 | Implicit vs Explicit Grids | What happens when you have more items than defined cells. `grid-auto-rows`, `grid-auto-flow` |
| 11 | Grid Alignment | `justify-items`, `align-items`, `justify-content`, `align-content` |
| 12 | **Subgrid** | Child grids that align with the parent grid — finally lands in 2024 |
| 13 | Grid + Flexbox Together | Grid for the page, Flexbox for the components inside. The 2026 standard |
| 14 | Common Patterns | Page layout, card galleries, dashboards, magazine layouts |

> [!IMPORTANT]
> **Flexbox vs Grid** — pick by *dimensionality*:
> - **Flexbox** for 1D (one row OR one column): navbars, button groups, single-row cards.
> - **Grid** for 2D (rows AND columns at the same time): page layouts, dashboards, galleries.
> - **Use both together.** Grid for the outer page structure, Flexbox for the components inside it.

<details>
<summary><strong>Quick Reference: Grid Template Areas</strong></summary>

```css
.layout {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header  header"
    "sidebar main"
    "footer  footer";
  min-height: 100vh;
  gap: 1rem;
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

That ASCII map IS the page layout. Reads like a blueprint.

</details>

<details>
<summary><strong>Quick Reference: Responsive Card Grid (no media queries needed)</strong></summary>

```css
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}
```

Cards automatically wrap based on available width. **One line** replaces dozens of media queries.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a page layout using `grid-template-areas`
- [ ] Build a responsive card grid with `auto-fit` + `minmax()`
- [ ] Combine Grid (page) + Flexbox (component) in one layout
- [ ] Use `subgrid` to align child grids with a parent
- [ ] Explain when to use Grid vs Flexbox

</details>

---

## Phase 7: Responsive Design

![Phase](https://img.shields.io/badge/Phase-7%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make your designs work beautifully on every screen size — from a 320px Android to a 4K monitor.

**What this phase is about.** Mobile-first design (write CSS for the smallest screen, enhance for bigger), **media queries** (the classic responsive tool), **container queries** (the 2023 game-changer — respond to a *parent's* size, not the viewport), responsive units (`rem`, `em`, `%`, `vw`, `vh`, `dvh`, `clamp()`), and responsive images. You'll also meet **logical properties** that automatically flip for right-to-left languages.

**Why it matters.** Over 60% of web traffic is mobile. A site that works on desktop but breaks on a phone has lost more than half its audience. In 2026, **responsive is the default**, not a bonus feature.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Mobile-First Approach | Write base CSS for mobile, enhance up with `min-width` queries — never the other way around |
| 2 | The Viewport Meta Tag | `<meta name="viewport" content="width=device-width, initial-scale=1">` — without it, mobile is broken |
| 3 | Media Queries | `@media (min-width: 768px) { … }` |
| 4 | Common Breakpoints | Mobile (<768px), tablet (768–1024), desktop (>1024). Pick by *content*, not by device |
| 5 | Media Features | `min-width`, `max-width`, `orientation`, `prefers-color-scheme`, `prefers-reduced-motion` |
| 6 | **Container Queries** | `@container (min-width: 400px)` — respond to a parent's size, not the viewport. Component-level responsiveness |
| 7 | Responsive Units | `rem`, `em`, `%`, `vw`, `vh`, `vmin`, `vmax`, `dvh`/`svh`/`lvh` (mobile-safe heights) |
| 8 | `clamp()` for Fluid Sizes | `font-size: clamp(1rem, 2vw + 1rem, 2rem)` — min, fluid middle, max |
| 9 | Responsive Images | `max-width: 100%; height: auto`, `object-fit`, `object-position` |
| 10 | `<picture>` and `srcset` | Different image files per screen size or pixel density |
| 11 | `aspect-ratio` | Reserve space before image loads (prevents layout shift) |
| 12 | Logical Properties | `margin-inline`, `padding-block`, `inset` — work in RTL languages too |
| 13 | `calc()` | `width: calc(100% - 2rem)` — math in CSS |
| 14 | Testing Responsively | DevTools device toolbar, real devices, BrowserStack |

> [!WARNING]
> **Never use `px` for font sizes.** Users who increase their browser's default font size for accessibility will see no effect. Use `rem`. Same for `100vh` on mobile (the bottom URL bar moves) — use `100dvh` (dynamic viewport height) for true mobile-safe full height.

<details>
<summary><strong>Quick Reference: Responsive Units</strong></summary>

| Unit | Relative To | Best For |
|------|-------------|----------|
| `px` | Nothing (absolute) | Borders, shadows, tiny fixed details |
| `rem` | Root font size (16px default) | **Font sizes, spacing, padding** — your default |
| `em` | Parent's font size | Component-internal scaling |
| `%` | Parent's size | Widths, heights |
| `vw` | 1% of viewport width | Full-width sections |
| `vh` | 1% of viewport height | Old way — breaks on mobile |
| `dvh` / `svh` / `lvh` | Dynamic / Small / Large viewport height | **Modern mobile-safe full height** |
| `ch` | Width of "0" character | Max line length (e.g. `max-width: 65ch`) |
| `clamp()` | Min / preferred / max | **Fluid font sizes & spacing** |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a layout that works at 320px, 768px, 1024px, and 1440px
- [ ] Write mobile-first media queries with `min-width`
- [ ] Use `clamp()` for fluid typography
- [ ] Use `100dvh` instead of `100vh` for full-screen sections
- [ ] Use a container query to make a component responsive
- [ ] Use `<picture>` + `srcset` to serve format/size variants

</details>

---

## Phase 8: Transitions, Animations & Transforms

![Phase](https://img.shields.io/badge/Phase-8%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Add smooth, purposeful motion — without breaking performance or triggering vertigo.

**What this phase is about.** **Transforms** (move, rotate, scale, skew without affecting layout), **transitions** (smooth between two states — perfect for hovers), **keyframe animations** (multi-step sequences — perfect for loaders, attention), and **scroll-driven animations** (the 2024 newcomer that lets you animate on scroll without JavaScript). Plus the most-overlooked rule: **respect `prefers-reduced-motion`**.

**Why it matters.** Motion is *the* modern UI signal — used right, it makes interfaces feel responsive and alive. Used wrong, it tanks performance and triggers motion-sickness in real users.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `transition` | `transition: property duration easing delay` — smooth animation between two states |
| 2 | Easing Functions | `ease`, `ease-in`, `ease-out`, `ease-in-out`, `linear`, `cubic-bezier()`, `steps()` |
| 3 | Transform: 2D | `translate()`, `rotate()`, `scale()`, `skew()` |
| 4 | Transform: 3D | `rotateX/Y/Z()`, `translateZ()`, `perspective`, `transform-style: preserve-3d` |
| 5 | `transform-origin` | Set the pivot point for rotations and scales |
| 6 | `@keyframes` | Multi-step animations: `from/to` or percentage-based |
| 7 | `animation` Properties | `animation-name`, `-duration`, `-delay`, `-iteration-count`, `-direction`, `-fill-mode`, `-play-state` |
| 8 | Performance Rule | Animate only `transform` and `opacity` — they're GPU-composited. Never animate `width`, `height`, `top`, `left` |
| 9 | `will-change` | Hint the browser to optimize. Use sparingly |
| 10 | **Scroll-Driven Animations** | `animation-timeline: scroll()` — animate on scroll without JavaScript (2024+) |
| 11 | **View Transitions API** | `view-transition-name` + JS — smooth page-to-page transitions |
| 12 | `prefers-reduced-motion` | **Mandatory** — respect users with vestibular sensitivity |
| 13 | Common Patterns | Hover effects, loading spinners, slide-ins, fade-ins, scroll reveals, page transitions |

> [!CAUTION]
> Never animate `width`, `height`, `margin`, `top`, `left` — they cause layout recalculations and feel janky. Use `transform: translate()` and `transform: scale()` — they're GPU-accelerated and silky-smooth at 60fps.

> [!IMPORTANT]
> Always respect `prefers-reduced-motion`. Wrap any animation that moves significant distance:
> ```css
> @media (prefers-reduced-motion: no-preference) {
>   .reveal { animation: slide-up 0.6s ease-out; }
> }
> ```

<details>
<summary><strong>Quick Reference: Transition vs Animation</strong></summary>

| Feature | Transition | Animation |
|---------|-----------|-----------|
| Trigger | Needs a state change (`:hover`, class toggle) | Runs automatically (or on trigger) |
| Steps | Two states (A → B) | Multiple keyframes |
| Repeat | Once per trigger | Can loop infinitely |
| Control | Simple | Full control (pause, reverse, delay, fill) |
| Best for | Hovers, button states, toggles | Loaders, attention-grabbers, scroll reveals |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add hover transitions to buttons and cards
- [ ] Build a loading spinner using `@keyframes`
- [ ] Use only `transform` and `opacity` for all animations
- [ ] Wrap animations in `prefers-reduced-motion: no-preference`
- [ ] Build a scroll-driven animation with `animation-timeline: scroll()`

</details>

---

## Phase 9: Modern CSS Features

![Phase](https://img.shields.io/badge/Phase-9%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> The 2022–2026 wave that replaces preprocessors and JavaScript libraries.

**What this phase is about.** CSS shipped more new features in the last 4 years than the previous 15. **Native nesting** kills the case for Sass. **`@layer`** ends specificity wars. **`@scope`** isolates styles to a subtree. **`@property`** lets you register custom property types. **Anchor positioning** (2024+) replaces popper.js. **View transitions** replace 90% of GSAP page-transition code.

**Why it matters.** Knowing modern CSS in 2026 lets you delete entire libraries and write less code. Hiring managers can spot a junior dev by what they reach for: `:has()` and `@layer`, or jQuery and Bootstrap?

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | **Native CSS Nesting** | `& { ... }` — Sass-style nesting in plain CSS, no preprocessor |
| 2 | **`@layer`** | Cascade layers — explicit priority order. Ends specificity wars |
| 3 | **`@scope`** | Style only inside a specific subtree. Component-level isolation |
| 4 | **`@property`** | Register custom property types — animatable, validated, with fallbacks |
| 5 | **`@container`** | Container queries (component-level responsive). See Phase 7 |
| 6 | **`:has()` (parent selector)** | Style based on children. Replaces 50% of "I need JavaScript for this" |
| 7 | **`:is()` and `:where()`** | Group selectors. `:where()` adds zero specificity — useful for resets |
| 8 | **Logical Properties** | `margin-block`, `padding-inline`, `inset` — RTL-safe |
| 9 | **OKLCH + `color-mix()` + Relative Color** | Modern color (Phase 4 recap) |
| 10 | **`text-wrap: balance / pretty`** | Better headings + paragraphs |
| 11 | **Anchor Positioning** | `position-anchor`, `inset-area` — popovers + tooltips without JS |
| 12 | **View Transitions API** | Smooth page-to-page transitions, declaratively |
| 13 | **`@starting-style`** | Animate elements *as they enter* the page |
| 14 | **Subgrid** | Child grids align with parent grids (Phase 6 recap) |
| 15 | **Scroll-Driven Animations** | `animation-timeline` (Phase 8 recap) |
| 16 | **`@supports`** | Feature detection: `@supports (container-type: inline-size) { … }` |

> [!TIP]
> Native nesting + `@layer` together replace ~80% of Sass:
> ```css
> @layer reset, base, components, utilities;
>
> @layer components {
>   .card {
>     padding: 1rem;
>     border-radius: 8px;
>
>     & .title { font-weight: 700; }
>     &:hover  { transform: translateY(-2px); }
>     & + & { margin-top: 1rem; }   /* sibling card */
>   }
> }
> ```

<details>
<summary><strong>Quick Reference: `@layer` (Cascade Layers)</strong></summary>

```css
/* Define layer order — earlier layers have LOWER priority */
@layer reset, base, components, utilities;

@layer reset {
  * { margin: 0; padding: 0; box-sizing: border-box; }
}
@layer base {
  body { font-family: system-ui; line-height: 1.6; }
}
@layer components {
  .button { padding: 0.5rem 1rem; border-radius: 4px; }
}
@layer utilities {
  .mt-4 { margin-top: 1rem; }   /* always wins over components */
}
```

A utility class beats any component class — without `!important`. That's the magic.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Refactor a stylesheet using native nesting
- [ ] Replace specificity hacks with `@layer`
- [ ] Use `@scope` to isolate component styles
- [ ] Use `:has()` to style a form based on its inputs' validity
- [ ] Build a popover with anchor positioning (no JavaScript)
- [ ] Use the View Transitions API for a smooth page transition

</details>

---

## Phase 10: CSS Architecture & Theming

![Phase](https://img.shields.io/badge/Phase-10%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Write CSS that scales — organize, name, theme, and version your styles for real production projects.

**What this phase is about.** Naming conventions (**BEM** still dominates), organizing files (component-based vs ITCSS vs Atomic), **CSS custom properties** (variables that work at runtime, scope, inherit, and can be changed via JavaScript), **theming** (dark mode, brand themes, multi-tenant white-labeling), and the basics of **design tokens** (the values that power a design system).

**Why it matters.** Anyone can write CSS for a one-page site. Writing CSS for a 100-page app, with five team members, that ships dark mode without breaking — that's the senior frontend role. This phase is where you become hireable for those.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Cascade (Recap) | Why architecture matters — specificity wars are predictable now |
| 2 | BEM Naming | `Block__Element--Modifier` — flat, low-specificity, predictable. Still dominates |
| 3 | OOCSS, SMACSS, ITCSS | Older methodologies you'll meet in legacy code |
| 4 | Atomic / Utility-First CSS | The "Tailwind" philosophy — covered in Phase 11 |
| 5 | **CSS Custom Properties** | `--brand: #3498db` and `var(--brand)`. Cascade, scope, fallback, runtime change |
| 6 | Property Scope | Define on `:root` for global, on `.component` for local |
| 7 | Fallbacks | `var(--brand, navy)` — fallback when undefined |
| 8 | **Dark Mode** | Theme via `[data-theme="dark"]` or `prefers-color-scheme` |
| 9 | **Multi-theme Systems** | Brand themes, white-label, density modes (compact/cozy/comfortable) |
| 10 | **Design Tokens** | The values that drive a design system: colors, spacing, typography, radii, shadows, durations |
| 11 | File Organization | `reset.css`, `tokens.css`, `base.css`, components per file, utilities last |
| 12 | `@layer` for Architecture | The 2026 way to enforce architecture (Phase 9 recap) |
| 13 | CSS Reset / Normalize | Modern resets: [Andy Bell's](https://piccalil.li/blog/a-more-modern-css-reset/), [Josh Comeau's](https://www.joshwcomeau.com/css/custom-css-reset/) |
| 14 | Style Guides & Linting | Stylelint, conventions, code review |

> [!IMPORTANT]
> **`!important` is almost never the answer.** If you need it, your specificity is out of control. Fix the root cause: simplify selectors, use BEM, or layer properly with `@layer`.

<details>
<summary><strong>Quick Reference: BEM Naming</strong></summary>

```css
/* Block — standalone component */
.card { }

/* Element — part of the block (double underscore) */
.card__title { }
.card__image { }
.card__body  { }

/* Modifier — variation or state (double hyphen) */
.card--featured       { }
.card--dark           { }
.card__title--large   { }
```

Why BEM? Every class is flat (no descendant chains), specificity stays at 0-1-0, and the name tells you exactly what styles what.

</details>

<details>
<summary><strong>Quick Reference: Dark Mode in 10 Lines</strong></summary>

```css
:root {
  --bg:   white;
  --text: #111;
}
[data-theme="dark"] {
  --bg:   #111;
  --text: #f5f5f5;
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg:   #111;
    --text: #f5f5f5;
  }
}
body { background: var(--bg); color: var(--text); }
```

OS preference + manual override + persistence (localStorage) — that's a complete dark-mode system in ~15 lines.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Refactor a project to use BEM naming
- [ ] Build a dark/light mode toggle with CSS custom properties
- [ ] Define a design-token file (`tokens.css`) with colors, spacing, typography
- [ ] Use `@layer` to organize reset / base / components / utilities
- [ ] Apply a modern CSS reset (Andy Bell or Josh Comeau)

</details>

---

## Phase 11: CSS Frameworks & Tooling

![Phase](https://img.shields.io/badge/Phase-11%2F13-blue)
![Difficulty: Reference](https://img.shields.io/badge/Difficulty-Reference-purple)
![Time: Pick & Learn](https://img.shields.io/badge/Time-Pick%20%26%20Learn-yellow)

> The frameworks, preprocessors, and tools you'll see in every job posting.

**What this phase is about.** Vanilla CSS is enough — but most teams use frameworks and tooling to ship faster. **Tailwind CSS** dominates the 2026 job market. **Sass / PostCSS** are still everywhere. **CSS Modules** scope styles in component frameworks. **Open Props** gives you design tokens without the framework lock-in. This phase is your **map** — what each does, when to pick which.

**Why it matters.** When a job listing says "Tailwind, Sass, Storybook, Vanilla Extract," you should know what every one of those is without Googling. Pick one or two for deep mastery — recognize the rest.

### 11.1 — Utility-First Frameworks

| Framework | What It Is | Best For |
|-----------|-----------|----------|
| **[Tailwind CSS](https://tailwindcss.com/)** | The dominant utility-first framework. `class="flex items-center px-4 py-2 bg-blue-500"` | New React/Vue/Next/Astro projects, any team that values shipping speed |
| **[UnoCSS](https://unocss.dev/)** | Tailwind-compatible engine, faster, more flexible | Modern Vite projects |
| **[Open Props](https://open-props.style/)** | Design tokens (CSS variables) without lock-in. Works alongside any approach | Vanilla CSS projects with design-token discipline |
| **[Pico CSS](https://picocss.com/)** | Class-less semantic CSS — "just write HTML" | Prototypes, simple sites |
| **[Tachyons](https://tachyons.io/)** | Original utility-first framework (pre-Tailwind) | Legacy maintenance |

### 11.2 — Component Frameworks

| Framework | What It Is | Best For |
|-----------|-----------|----------|
| **[Bootstrap](https://getbootstrap.com/)** | The classic component framework. Pre-built nav, modals, cards | Server-rendered apps, fast prototypes |
| **[Bulma](https://bulma.io/)** | Modern CSS-only Bootstrap alternative | Class-based component systems |
| **[Foundation](https://get.foundation/)** | Email + web components | Email developers |

### 11.3 — Component Libraries (React/Vue/Solid/Svelte)

| Library | What It Is |
|---------|-----------|
| **[shadcn/ui](https://ui.shadcn.com/)** | Copy-paste Tailwind components — the 2026 default for React/Next |
| **[Radix UI](https://www.radix-ui.com/)** | Unstyled accessible primitives (the foundation under shadcn/ui) |
| **[Headless UI](https://headlessui.com/)** | Tailwind Labs' unstyled components |
| **[Material UI (MUI)](https://mui.com/)** | Google Material Design — React |
| **[Chakra UI](https://chakra-ui.com/)** | Style-prop based React components |
| **[Mantine](https://mantine.dev/)** | Full-featured React UI library |
| **[Ant Design](https://ant.design/)** | Enterprise-grade React UI (Alibaba) |
| **[Vuetify](https://vuetifyjs.com/)** | Material Design for Vue |

### 11.4 — Preprocessors & PostCSS

| Tool | What It Does |
|------|--------------|
| **[Sass / SCSS](https://sass-lang.com/)** | The classic preprocessor — variables, nesting, mixins, functions. Less needed in 2026 (native CSS now does most of it) |
| **[Less](https://lesscss.org/)** | Older preprocessor (used by Bootstrap 3, Ant Design) |
| **[Stylus](https://stylus-lang.com/)** | Whitespace-sensitive preprocessor |
| **[PostCSS](https://postcss.org/)** | Plugin-based CSS transformer. Tailwind, autoprefixer, nesting all run on PostCSS |
| **[Autoprefixer](https://github.com/postcss/autoprefixer)** | Adds vendor prefixes automatically |

### 11.5 — CSS-in-JS (React/Vue/etc.)

| Library | What It Does |
|---------|--------------|
| **[CSS Modules](https://github.com/css-modules/css-modules)** | Scoped class names per component. Built into Next.js, Vite |
| **[Vanilla Extract](https://vanilla-extract.style/)** | Type-safe CSS-in-TypeScript. Zero runtime |
| **[styled-components](https://styled-components.com/)** | Tagged-template CSS-in-JS for React |
| **[Emotion](https://emotion.sh/)** | High-performance CSS-in-JS |
| **[Stitches](https://stitches.dev/)** | CSS-in-JS with variants (now archived; many teams migrated to Vanilla Extract) |
| **[Panda CSS](https://panda-css.com/)** | Modern zero-runtime CSS-in-JS (by Chakra team) |

### 11.6 — Build Tools

| Tool | What It Does |
|------|--------------|
| **[Vite](https://vitejs.dev/)** | The modern bundler default. CSS Modules, PostCSS, Sass — built-in |
| **[Webpack](https://webpack.js.org/)** | The classic bundler. Most legacy projects |
| **[esbuild](https://esbuild.github.io/)** | Fastest bundler. Often used inside Vite |
| **[Lightning CSS](https://lightningcss.dev/)** | Rust-based CSS bundler/transformer. Replaces PostCSS for speed |

### 11.7 — Linting & Formatting

| Tool | What It Does |
|------|--------------|
| **[Stylelint](https://stylelint.io/)** | The standard CSS linter. Catches mistakes, enforces conventions |
| **[Prettier](https://prettier.io/)** | Auto-formats CSS / SCSS / Tailwind |
| **[Tailwind ESLint Plugin](https://github.com/francoismassart/eslint-plugin-tailwindcss)** | Sorts utility classes, catches typos |

### 11.8 — Design System Tools

| Tool | What It Does |
|------|--------------|
| **[Storybook](https://storybook.js.org/)** | Visual workshop for UI components |
| **[Chromatic](https://www.chromatic.com/)** | Visual regression testing for Storybook |
| **[Figma Tokens / Style Dictionary](https://amzn.github.io/style-dictionary/)** | Sync design tokens between Figma and code |

> [!IMPORTANT]
> Don't learn all of these. **Recognize** all of them (so you can read job descriptions). **Deeply learn** maybe 3 — for most React shops in 2026 that's: **Tailwind CSS + shadcn/ui + Storybook**. For vanilla projects: **Open Props + native nesting + `@layer`**.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build the same component in vanilla CSS, Tailwind, and CSS Modules
- [ ] Set up a Vite project with Tailwind + Stylelint + Prettier
- [ ] Install and use 3 shadcn/ui components in a Next.js project
- [ ] Define a design-token file with Open Props
- [ ] Set up Storybook for one component

</details>

---

## Phase 12: Performance, Accessibility & Best Practices

![Phase](https://img.shields.io/badge/Phase-12%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Write CSS that's fast, accessible, and shippable to real users.

**What this phase is about.** **Performance** (Critical CSS, unused-CSS removal, `content-visibility`, animation performance), **Accessibility** (focus rings, contrast, motion preferences, reduced-motion), and **the practices that separate junior CSS from senior CSS** (resets, file organization, browser testing, validation, Lighthouse).

**Why it matters.** Slow CSS hurts Core Web Vitals (and SEO). Inaccessible CSS is illegal in many countries. This is the phase that turns a "looks nice" portfolio into a "ships to production" portfolio.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Critical Rendering Path | How CSS blocks rendering. Where to inline/defer |
| 2 | Critical CSS | Inline above-the-fold styles in `<head>`; defer the rest |
| 3 | Unused CSS Removal | PurgeCSS, Tailwind's JIT — ship only what you use |
| 4 | `content-visibility: auto` | Skip rendering offscreen sections — instant perf wins |
| 5 | `will-change` | Hint the browser. Use sparingly — it costs memory |
| 6 | Animation Performance | Animate only `transform` + `opacity` (Phase 8 recap) |
| 7 | `aspect-ratio` for CLS | Reserve image space — eliminates layout shift |
| 8 | Font Performance | `font-display: swap`, preload critical fonts, self-host vs CDN |
| 9 | Core Web Vitals (CSS side) | LCP, INP, CLS — what CSS contributes |
| 10 | **Focus Indicators** | Visible focus rings (`:focus-visible`). **Never `outline: none` without a replacement** |
| 11 | **Color Contrast** | WCAG AA: 4.5:1 normal text, 3:1 large. Use a contrast checker |
| 12 | **Reduced Motion** | `@media (prefers-reduced-motion)` — Phase 8 recap |
| 13 | **Reduced Transparency** | `prefers-reduced-transparency` — fall back from glass effects |
| 14 | **Color Scheme Preference** | `prefers-color-scheme` for dark mode |
| 15 | High-Contrast Mode | Windows High Contrast — use `forced-colors` media query |
| 16 | **Don't rely on color alone** | Pair color with icons / labels for color-blind users |
| 17 | CSS Validation | [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) — catches typos browsers ignore |
| 18 | Cross-Browser Testing | Chrome, Firefox, Safari (the big 3). Mobile Safari is its own beast |
| 19 | Lighthouse | Built into Chrome DevTools. Aim 90+ on Performance and Accessibility |
| 20 | Browser Support | Check [Can I Use](https://caniuse.com/) before adopting new features |

> [!CAUTION]
> **Never `outline: none` without replacing the focus ring.** It's the single most common accessibility violation. Keyboard-only users (and most power users) rely on visible focus to know where they are:
> ```css
> /* WRONG */
> button:focus { outline: none; }
>
> /* CORRECT */
> button:focus-visible {
>   outline: 2px solid var(--accent);
>   outline-offset: 2px;
> }
> ```

<details>
<summary><strong>Quick Reference: A Modern Reset for Production</strong></summary>

```css
/* Andy Bell's modern CSS reset (excerpt) */
*, *::before, *::after { box-sizing: border-box; }
* { margin: 0; }
body { line-height: 1.5; -webkit-font-smoothing: antialiased; }
img, picture, video, canvas, svg { display: block; max-width: 100%; }
input, button, textarea, select { font: inherit; }
p, h1, h2, h3, h4, h5, h6 { overflow-wrap: break-word; }

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Score 90+ on Lighthouse Performance and Accessibility
- [ ] Replace every `outline: none` with `:focus-visible` + visible ring
- [ ] Verify all text passes WCAG AA contrast
- [ ] Wrap all motion in `prefers-reduced-motion: no-preference`
- [ ] Use `aspect-ratio` on every image to prevent CLS
- [ ] Run Stylelint and W3C CSS Validator with zero errors

</details>

---

## Phase 13: What's Next? (JS, Frameworks & Design Systems)

![Phase](https://img.shields.io/badge/Phase-13%2F13-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You finished CSS. Now combine it with JavaScript and a framework to build real apps.

**What this phase is about.** CSS plus HTML gets you static pages. Adding JavaScript gets you interactive sites. Adding a framework (React, Vue, Next, Astro) gets you full applications. This phase maps where to go from here.

### 13.1 — Add Interactivity: JavaScript

CSS handles the look. JavaScript handles the behavior. Together with HTML, that's the full web platform.

➡️ Continue with the [JavaScript Syllabus](javascript.md).

### 13.2 — Pick a Framework

Frameworks change how you write HTML/CSS — they introduce **components** (re-usable HTML+CSS+JS bundles).

| Framework | CSS Story | Best For |
|-----------|-----------|----------|
| **[React](react.md)** + Next.js | Tailwind + CSS Modules + shadcn/ui | The dominant 2026 choice |
| **[Vue](vuejs.md)** + Nuxt | Single-File Components with scoped styles | Gentle learning curve |
| **[Angular](angular.md)** | View Encapsulation, SCSS | Enterprise apps |
| **[Astro](https://astro.build/)** | Component-scoped CSS, Tailwind, MDX | Content-driven sites — blogs, marketing, docs |
| **[Svelte / SvelteKit](https://svelte.dev/)** | Component-scoped CSS by default | Smaller bundles |

### 13.3 — Become a Design Systems Engineer

If you fell in love with CSS architecture and theming (Phase 10), this is a *career*. Study public design systems:

| System | What's Special |
|--------|---------------|
| [GitHub Primer](https://primer.style/) | Comprehensive — components, tokens, guidance |
| [Adobe Spectrum](https://spectrum.adobe.com/) | Massive scale, multi-platform |
| [Shopify Polaris](https://polaris.shopify.com/) | Merchant-first design |
| [Atlassian Design](https://atlassian.design/) | Cross-product consistency |
| [IBM Carbon](https://carbondesignsystem.com/) | Open source, enterprise |
| [Mailchimp Pattern Library](https://ux.mailchimp.com/patterns) | Marketing tone |

### 13.4 — Real-World Add-Ons

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every team. Every project. |
| **Figma / Penpot** | Where designs come from. Learn to inspect and translate. |
| **Deployment** ([Vercel](https://vercel.com/), [Netlify](https://www.netlify.com/), [Cloudflare Pages](https://pages.cloudflare.com/)) | Free hosting for static sites |
| **A11y Testing** ([axe DevTools](https://www.deque.com/axe/devtools/), [WAVE](https://wave.webaim.org/)) | Catch issues before users do |
| **Design Tokens** ([Style Dictionary](https://amzn.github.io/style-dictionary/)) | Sync designers ↔ developers |

### 13.5 — Suggested Order After This Syllabus

```
JavaScript → React (or Vue) → Tailwind → Git → Build & deploy a real project
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

Avoid these pitfalls that trip up most CSS learners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Using `!important` everywhere | Breaks the cascade, makes debugging a nightmare | Fix specificity — simplify selectors, use BEM, use `@layer` |
| 2 | `px` for font sizes | Ignores user's accessibility settings (browser zoom) | Use `rem` for font sizes, `px` only for borders/shadows |
| 3 | Forgetting `box-sizing: border-box` | Width math becomes confusing | Set `* { box-sizing: border-box; }` globally |
| 4 | Overly specific selectors | `div.container > ul.nav > li > a` — impossible to override | Flat class selectors: `.nav-link` |
| 5 | No CSS reset | Different browsers have different defaults | Use Andy Bell's or Josh Comeau's modern reset |
| 6 | Animating `width`/`height`/`top`/`left` | Causes layout recalc — janky 60fps | Animate `transform` + `opacity` only |
| 7 | Hardcoded colors everywhere | Theme changes = find-and-replace nightmare | Use CSS custom properties (`--brand`) |
| 8 | Using floats for layout | Floats are a pre-2017 hack | Use Flexbox or Grid |
| 9 | Desktop-first responsive | Adding mobile styles afterward is painful | Mobile-first with `min-width` queries |
| 10 | `outline: none` on focus | Major a11y violation — keyboard users lose focus indicators | Replace with `:focus-visible` + visible ring |
| 11 | One giant CSS file | Impossible to find anything | Split into component files; use `@layer` |
| 12 | Not respecting `prefers-reduced-motion` | Triggers vertigo in users with vestibular disorders | Wrap motion in `@media (prefers-reduced-motion: no-preference)` |
| 13 | Animating layout properties | Janky frame rate | Animate compositor properties (transform, opacity) |
| 14 | `100vh` on mobile | URL bar makes it wrong | Use `100dvh` (dynamic viewport height) |
| 15 | Setting fixed widths on flex/grid items | Defeats the purpose of flex/grid | Use `flex: 1`, `minmax()`, `fr` units |
| 16 | Using `id` selectors for styling | High specificity, hard to override | Use classes for styling, `id` only as JS hook |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the CSS Box Model?**
   - Every element is a box: content (innermost) → padding → border → margin (outermost). `box-sizing: border-box` makes width/height include padding and border.

2. **`margin` vs `padding`?**
   - `padding` is space inside the border (part of the element). `margin` is space outside the border (between elements). Vertical margins **collapse**; padding never does.

3. **Differences between `block`, `inline`, `inline-block`?**
   - `block`: full width, new line, respects all box-model. `inline`: only needed width, ignores vertical margin/padding. `inline-block`: flows inline, respects all box-model.

4. **How do you center a div horizontally?**
   - Block element: `margin: 0 auto;` with a width. Or Flexbox on parent: `display: flex; justify-content: center;`. Or Grid: `place-items: center;`.

5. **`class` vs `id`?**
   - Classes (`.name`) are reusable on many elements. IDs (`#name`) must be unique per page. IDs have higher specificity (1-0-0 vs 0-1-0). Use classes for styling, IDs as JS hooks.

6. **Why does `==` between two elements with the same `class` not exist in CSS?**
   - CSS doesn't compare elements — it just selects them. The browser uses `class` to apply rules.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Explain CSS Specificity. How is it calculated?**
   - Inline styles (1-0-0-0) > IDs (1-0-0) > classes/attributes/pseudo-classes (0-1-0) > elements/pseudo-elements (0-0-1). Higher specificity always wins; equal specificity → last rule wins.

2. **Flexbox vs Grid?**
   - Flexbox is 1D (one row OR one column). Grid is 2D (rows AND columns). Use Flexbox for components (navbars, button rows), Grid for page layout. Use them together.

3. **How does `position: sticky` work?**
   - Behaves like `relative` until you scroll past a threshold (`top: 0`), then becomes `fixed`. Only sticks within its parent's bounds.

4. **CSS Custom Properties vs Sass variables?**
   - Custom properties (`--name`) are runtime, cascade, can be changed via JS, work in `var()`. Sass variables (`$name`) are compile-time and don't exist in the browser. Custom properties enable theming.

5. **What's the mobile-first approach and why?**
   - Write base styles for mobile, layer on `min-width` media queries for larger screens. Simpler base, better mobile performance, easier to enhance than to remove.

6. **How does `z-index` actually work?**
   - It only compares elements within the same stacking context. New contexts are created by positioned elements with `z-index`, `opacity < 1`, `transform`, `filter`, `isolation: isolate`.

7. **What does `:focus-visible` do that `:focus` doesn't?**
   - `:focus` matches whenever something has focus (including mouse clicks). `:focus-visible` only matches when focus is visible — typically keyboard navigation. Lets you remove the click outline without breaking keyboard users.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What is the Stacking Context and why does `z-index` sometimes fail?**
   - A stacking context is a 3D layer group. `z-index` only compares within the same context. New contexts are created by positioned elements with `z-index`, `opacity < 1`, `transform`, `filter`, `backdrop-filter`, `isolation: isolate`. If `z-index: 9999` isn't winning, the element is in a different context.

2. **Explain `::before` and `::after`. When would you use them?**
   - Pseudo-elements that insert content before/after an element's content, without HTML. Need the `content` property. Use for: decorative shapes, tooltips, icons, custom list markers, clearfix. Style-only — never use for meaningful content.

3. **How would you implement dark mode?**
   - Define colors as custom properties on `:root`. Use `prefers-color-scheme: dark` media query *and* a `[data-theme]` attribute for manual override. Persist user choice in `localStorage`.

4. **Which properties are GPU-accelerated for animation?**
   - Only `transform` and `opacity`. Animating those triggers only the compositor (no layout, no paint). Animating `width`, `height`, `top`, `left` triggers layout recalculation — expensive. Use `transform: translate()` instead of `top/left`.

5. **What is `:has()` and why is it revolutionary?**
   - The "parent selector" — style an element based on its descendants: `.card:has(img)` styles cards with images. Replaces logic that previously required JavaScript. Supported in all modern browsers since late 2023.

6. **What does `@layer` solve?**
   - Specificity wars. Layers have explicit priority — a class in a higher layer beats an ID in a lower layer. Lets you organize CSS into reset → base → components → utilities without `!important`.

7. **What's the difference between `:where()` and `:is()`?**
   - Both group selectors. `:is()` takes the highest specificity of its arguments. `:where()` always has *zero* specificity — useful for resets and base styles you want trivially overridable.

8. **Container queries vs media queries?**
   - Media queries respond to the **viewport**. Container queries respond to a specific **parent element**. Container queries enable true component-level responsive design — same component, different sizes in different parts of the page.

</details>

---

## Practice Projects

Build these projects as you progress through the syllabus. Each one is portfolio-worthy. **Push every project to GitHub and deploy live** (Vercel/Netlify/Cloudflare Pages — all free).

### Project 1: Styled Bio Page
![Phase 1-4](https://img.shields.io/badge/After-Phase%201--4-green)

**What you'll build:** Take your HTML bio page from the [HTML Syllabus](html.md) and make it beautiful. Custom fonts, OKLCH color palette, careful typography (line-height, max-width, fluid sizing), hover effects.

**Skills practiced:** Selectors, cascade, box model, typography, color, custom properties.

**Stretch goal:** Add a print stylesheet (`@media print`) so the page can be saved as a PDF resume.

---

### Project 2: Flexbox Component Kit
![Phase 5](https://img.shields.io/badge/After-Phase%205-green)

**What you'll build:** A component playground — navbar with logo + links + CTA, button row, equal-height card row, sticky footer. All Flexbox, all responsive (start with mobile-first).

**Skills practiced:** Flexbox container/item properties, gap, wrap, alignment, mobile-first responsive.

**Stretch goal:** Replicate Twitter/Notion's top nav exactly.

---

### Project 3: Grid-Based Landing Page
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A full SaaS marketing landing page — hero, feature grid (`auto-fit` + `minmax`), pricing comparison, testimonials, footer. Fully responsive across mobile/tablet/desktop. **No media queries for the card grids** — use auto-fit.

**Skills practiced:** Grid template areas, `auto-fit`/`minmax`, container queries, fluid typography (`clamp()`), `aspect-ratio`.

**Stretch goal:** Pass Lighthouse Performance + Accessibility 95+.

---

### Project 4: Animated Portfolio
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-yellow)

**What you'll build:** A personal portfolio with: hero with subtle scroll-driven animations, project cards with hover transforms, animated skill bars, page transitions via the **View Transitions API**, dark/light mode. **All animations wrapped in `prefers-reduced-motion`**.

**Skills practiced:** Transitions, transforms, keyframes, scroll-driven animations, View Transitions API, custom properties for theming, `:has()`.

**Stretch goal:** Replace at least 3 things you'd normally use JavaScript for with pure CSS (`:has()`, `:focus-within`, scroll snap).

---

### Project 5: Production Dashboard with Theming
![Phase 10-11](https://img.shields.io/badge/After-Phase%2010--11-red)

**What you'll build:** A dashboard with sidebar nav, KPI cards, data tables, dark/light mode toggle (persists), brand-theme switcher (3 themes via custom properties). BEM naming throughout. Use `@layer` for architecture.

**Skills practiced:** BEM, CSS custom properties, `@layer`, multi-theme system, dark mode, design tokens, modern CSS reset.

**Stretch goal:** Rebuild it once with vanilla CSS, once with Tailwind. Compare your DX.

---

### Project 6: Real-World Audit & Refactor (Capstone)
![Phase 12](https://img.shields.io/badge/Capstone-Interview%20Ready-purple)

**What you'll build:** Pick an existing public site (small business, charity, school) with mediocre CSS. Refactor — without changing the visual design — to: pass Lighthouse 95+ on Performance and Accessibility, eliminate `!important`, use `@layer`, replace any float layouts with Grid/Flexbox, fix focus indicators, respect `prefers-reduced-motion`, pass W3C CSS validation. Write a 1-page audit report explaining each change with measurable improvements.

**Skills practiced:** All architecture + accessibility + performance phases. **Portfolio gold — every frontend interview wants to see this.**

**Stretch goal:** Submit a Pull Request to the original site (if open source).

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [MDN — Learn CSS](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics) | The gold standard. Structured Mozilla curriculum |
| [MDN — CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) | Every property, value, selector, and at-rule |
| [web.dev — Learn CSS](https://web.dev/learn/css) | Google's modern course. 30 modules with interactive examples |
| [CSS-Tricks](https://css-tricks.com/) | The "manual" of modern CSS — guides on Flexbox, Grid, animations |
| [W3C CSS Specs](https://www.w3.org/Style/CSS/) | The official specs — the definitive answer for edge cases |
| [Can I Use](https://caniuse.com/) | Browser support tables |

### Books & Long-form Reads

| Book | Why Read |
|------|---------|
| [CSS in Depth (Keith J. Grant)](https://www.manning.com/books/css-in-depth) | The book to read at year 2. Cascade, layout, modern features |
| [Every Layout (Bell & Andrew)](https://every-layout.dev/) | Composable layout primitives. Changes how you think about layout |
| [Smashing CSS (Vitaly Friedman)](https://smashingmagazine.com/category/css) | Article archive on modern techniques |
| [Josh W. Comeau — Interactive Guides](https://www.joshwcomeau.com/) | Visual interactive guides for [Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/), [Grid](https://www.joshwcomeau.com/css/interactive-guide-to-grid/), and more |
| [A More Modern CSS Reset (Andy Bell)](https://piccalil.li/blog/a-more-modern-css-reset/) | The 2024 modern reset |
| [Refactoring UI (Adam Wathan & Steve Schoger)](https://refactoringui.com/) | Design fundamentals for developers — pairs perfectly with Tailwind |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | Free certification with 5 projects |
| [The Odin Project — CSS](https://www.theodinproject.com/paths/full-stack-javascript/courses/intermediate-html-and-css) | Project-based curriculum |
| [Codecademy — Learn CSS](https://www.codecademy.com/learn/learn-css) | In-browser with instant feedback |
| [Flexbox Froggy](https://flexboxfroggy.com/) | Learn Flexbox by guiding frogs to lily pads |
| [Grid Garden](https://cssgridgarden.com/) | Learn CSS Grid by watering a garden |
| [CSS Battle](https://cssbattle.dev/) | Replicate designs in the fewest characters |
| [100 Days CSS](https://100dayscss.com/) | Daily focused exercises |

### YouTube

| Channel / Video | Why Watch |
|----------------|-----------|
| [Kevin Powell](https://www.youtube.com/@KevinPowell) | The best CSS educator on YouTube. 1000+ videos |
| [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified) | Clear, focused explanations |
| [Josh W. Comeau](https://www.youtube.com/@JoshWComeau) | Deep, beautifully visual |
| [Bramus](https://www.youtube.com/@Bramus) | Modern CSS deep dives (Google's CSS evangelist) |
| [Una Kravets](https://www.youtube.com/@unakravets) | Modern CSS — Chrome team |
| [Traversy Media — CSS Crash Course](https://www.youtube.com/@TraversyMedia) | Best first CSS video |

### Practice & Build Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional Figma designs to build |
| [DevChallenges](https://devchallenges.io/) | Project challenges by difficulty |
| [100 Days CSS](https://100dayscss.com/) | Daily CSS challenges |
| [Frontend Practice](https://www.frontendpractice.com/) | Recreate real production sites |
| [CSSBattle](https://cssbattle.dev/) | Code golf for CSS |
| [Codrops](https://tympanus.net/codrops/) | Inspiration + tutorials for advanced effects |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — CSS](https://roadmap.sh/css) | Interactive CSS path |
| [roadmap.sh — Frontend](https://roadmap.sh/frontend) | Where CSS fits in the full stack |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [VS Code](https://code.visualstudio.com/) | Free, fast, huge ecosystem |
| [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) | Auto-refresh on save |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-format CSS on save |
| [Stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint) | Lint as you type |
| [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek) | Ctrl+click class to jump to its CSS |
| [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight) | See color values in your editor |
| [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) | If using Tailwind — autocomplete + previews |
| [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) | Class autocomplete from CSS |

### CSS Generators (Save Time)

| Tool | What It Generates |
|------|-------------------|
| [CSSGradient.io](https://cssgradient.io/) | Visual gradient builder |
| [Clippy](https://bennettfeely.com/clippy/) | Visual `clip-path` builder |
| [Grid Generator (Layoutit)](https://grid.layoutit.com/) | Drag-and-drop Grid builder |
| [Flexbox Generator](https://www.cssportal.com/css-flexbox-generator/) | Visual Flexbox builder |
| [Cubic Bezier](https://cubic-bezier.com/) | Custom easing curves |
| [Haikei](https://haikei.app/) | SVG backgrounds, waves, blobs |
| [Smooth Shadow](https://shadows.brumm.af/) | Realistic layered shadows |
| [Easing Functions](https://easings.net/) | Catalog of named easings |

### Validation, Performance, A11y Tools

| Tool | What It Does |
|------|--------------|
| [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) | Official CSS validator |
| [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/) | Built into Chrome DevTools — Perf / A11y / SEO scores |
| [PageSpeed Insights](https://pagespeed.web.dev/) | Lighthouse + real-world Core Web Vitals |
| [axe DevTools](https://www.deque.com/axe/devtools/) | A11y issues with one click |
| [WAVE](https://wave.webaim.org/) | Highlights a11y issues on the page |
| [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) | WCAG color contrast check |
| [CSS Stats](https://cssstats.com/) | Analyze any site's CSS at a glance |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [CSS-Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) | The definitive visual Flexbox reference |
| [CSS-Tricks Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/) | The definitive visual Grid reference |
| [MDN CSS Cheatsheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cheatsheet) | Official Mozilla reference |
| [Modern CSS Cheatsheet](https://github.com/AllThingsSmitty/css-protips) | 50+ modern CSS tips |
| [State of CSS](https://stateofcss.com/) | Yearly survey — what's new and what's used |

### Newsletters & Podcasts

| Resource | Format |
|----------|--------|
| [CSS Weekly](https://css-weekly.com/) | Weekly newsletter |
| [Frontend Focus](https://frontendfoc.us/) | Weekly newsletter — broader frontend |
| [Smashing Magazine](https://www.smashingmagazine.com/category/css) | Long-form CSS articles |
| [Syntax.fm](https://syntax.fm/) | Wes Bos & Scott Tolinski — fun, opinionated |

---

[Back to Main Syllabus](../README.md)

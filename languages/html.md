# HTML Syllabus

A complete, structured learning path for HTML — your one-stop guide from your very first `<h1>` to building accessible, SEO-friendly, performance-tuned web pages. Whether you have never opened a code editor or you have been writing markup for years and want to fill the gaps, this syllabus walks you through every concept in the right order, explains *why* each matters, and gives you real projects to prove you actually learned it.

![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 4-6 Weeks](https://img.shields.io/badge/Duration-4--6%20Weeks-blue)
![Topics: 11 Phases](https://img.shields.io/badge/Topics-11%20Phases-orange)

---

## Table of Contents

- [What is HTML?](#what-is-html)
- [Why Learn HTML in 2026?](#why-learn-html-in-2026)
- [How a Browser Renders HTML](#how-a-browser-renders-html)
- [Who This Syllabus Is For](#who-this-syllabus-is-for)
- [Learning Paths](#learning-paths)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: HTML Basics](#phase-2-html-basics)
- [Phase 3: Links, Images & Media](#phase-3-links-images--media)
- [Phase 4: Lists & Tables](#phase-4-lists--tables)
- [Phase 5: Forms & User Input](#phase-5-forms--user-input)
- [Phase 6: Semantic HTML](#phase-6-semantic-html)
- [Phase 7: HTML Head, Meta Tags & Resource Hints](#phase-7-html-head-meta-tags--resource-hints)
- [Phase 8: Advanced HTML](#phase-8-advanced-html)
- [Phase 9: Accessibility](#phase-9-accessibility)
- [Phase 10: SEO, Structured Data & Performance](#phase-10-seo-structured-data--performance)
- [Phase 11: What's Next? (CSS, JavaScript, Frameworks)](#phase-11-whats-next-css-javascript-frameworks)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](../interviews/html.md)
- [Practice Projects](#practice-projects)
- [Final Outcome Checklist](#final-outcome-checklist-jobproject-ready)
- [Resources](#resources)

---

## What is HTML?

**HTML (HyperText Markup Language) is the language used to describe the structure of every web page on the internet.** Every headline, paragraph, link, button, image, form field, and video you have ever seen on the web started life as an HTML tag. It is the *skeleton* of the web — the very first thing the browser downloads, parses, and turns into the page in front of you.

In simple words:

- **HTML** is the *structure* of a web page (the skeleton — what content exists and how it is organized).
- **CSS** is the *style* of a web page (the look — colors, spacing, layout, typography).
- **JavaScript** is the *behavior* of a web page (the brain — interactivity, data fetching, animations).

You can build a website with HTML alone. You cannot build one without it.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 1991 | HTML (Tim Berners-Lee) | The original 18 tags — born at CERN to share research papers. |
| 1995 | HTML 2.0 | First IETF standard. Added forms. |
| 1997 | HTML 3.2 / 4.0 | Tables, scripts, style sheets. |
| 2000 | XHTML 1.0 | Stricter, XML-based syntax. Eventually abandoned. |
| 2014 | **HTML5** | Semantic tags, audio/video, canvas, forms, offline support. The version we use today. |
| 2019+ | **HTML Living Standard** | Maintained by [WHATWG](https://html.spec.whatwg.org/) — no more numbered versions. The spec evolves continuously. |

> [!IMPORTANT]
> When people say "HTML" today, they mean the **HTML Living Standard**. There is no "HTML 6" coming. The spec ships features as they are ready; browsers implement them; you use them.

### What Makes HTML Special

- **It's declarative.** You describe *what* the content is (`<button>`, `<nav>`, `<article>`), not how to draw it.
- **It's forgiving.** Forget a closing tag, the browser still tries to render the page. Great for beginners — bad if you don't know the rules.
- **It's universal.** The same HTML runs on a $50 phone in Lagos and a Mac Studio in Tokyo. No installation, no compilation.
- **It's the foundation of every web framework.** React, Vue, Angular, Svelte — they all eventually output HTML.

---

## Why Learn HTML in 2026?

| Reason | What It Means |
|--------|---------------|
| **The bedrock of every web job** | Frontend, full-stack, mobile (PWA), email designer, content engineer, technical writer — all need HTML. |
| **Required for accessibility (a11y)** | Laws like ADA (US), EAA (EU), and AODA (Canada) require accessible websites. Companies get sued for inaccessible HTML. |
| **Required for SEO** | Google ranks pages partly based on semantic structure. Bad HTML = low ranking = no traffic. |
| **Required for AI** | Large language models, screen scrapers, and search crawlers all read HTML. Semantic tags + structured data = better AI understanding of your content. |
| **Email developers earn good money** | HTML emails (Mailchimp, Klaviyo, SendGrid templates) are still mostly hand-written `<table>`-based HTML. Niche, in-demand skill. |
| **Foundation for every JavaScript framework** | You cannot debug a React app's hydration mismatch if you do not understand the underlying HTML it produces. |

---

## How a Browser Renders HTML

Understanding *what the browser does* with your HTML makes everything else easier.

```
   ┌─────────────────────────┐
   │   You write HTML file   │  index.html
   └────────────┬────────────┘
                │ User visits the URL
                ▼
   ┌─────────────────────────┐
   │   Browser downloads it  │  Bytes over HTTP
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │     Parses HTML →       │  Tokens → Nodes → DOM tree
   │   Builds the DOM tree   │
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │     Loads CSS  →        │  Builds the CSSOM tree
   │      Loads JS  →        │  Runs scripts (may modify the DOM)
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │       Render Tree       │  DOM + CSSOM = what to paint
   └────────────┬────────────┘
                ▼
   ┌─────────────────────────┐
   │   Layout → Paint →      │  Pixels on the screen
   │      Composite          │
   └─────────────────────────┘
```

Every tag you write becomes a **node** in the DOM (Document Object Model). JavaScript and CSS both target this tree. **Good HTML = good DOM = fast, accessible, SEO-friendly site.** Bad HTML = pain at every layer above it.

---

## Who This Syllabus Is For

| You Are | What You Get |
|---------|--------------|
| **Absolute beginner** — never coded before | Start at Phase 1. Each tag is explained from scratch, every example runnable. |
| **College student / fresher** prepping for first internship | Do all 11 phases. Build at least 3 projects. Pair with the [Interview Questions](../interviews/html.md). |
| **Career switcher** moving into web dev | Skim Phase 1–4, focus on Phases 5 (forms), 6 (semantics), 9 (a11y), 10 (SEO) — these decide who is hired. |
| **Self-taught dev with gaps** | Use [Common Mistakes](#common-mistakes) as a self-audit, then re-do whichever phase you flunk. |
| **Backend / framework dev** weak on markup | Phase 6 (semantics) + Phase 9 (a11y) + Phase 10 (SEO/perf) — the highest-leverage 3 phases. |
| **Email / template developer** | Phase 4 (tables — yes, real ones), Phase 7 (head/meta), Phase 8 (responsive images), Phase 9 (a11y for email). |
| **Experienced frontend dev** | [Interview Questions](../interviews/html.md) + Phase 8 (`<dialog>`, popover, `inert`) + Phase 10 (Core Web Vitals, JSON-LD). |

---

## Learning Paths

Pick the path that matches your goal. Each path tells you which phases to do, in what order, and roughly how long it takes.

### Path A — Zero to First Web Page (1–2 weeks)
You want to put something on the internet, fast.

```
Phase 1 → 2 → 3 → 4 → Project 1 (Profile site)
```
- Goal: a deployed personal page with your name, bio, links, photo.
- Deploy free on [GitHub Pages](https://pages.github.com/) or [Netlify Drop](https://app.netlify.com/drop).

### Path B — Job-Ready Frontend (4–6 weeks)
Target: pass a junior frontend HTML/CSS/JS interview.

```
All 10 phases → Phase 11 (CSS + JS bridge) → Build Projects 1, 3, 5, 7
```
- Pair with the [CSS Syllabus](css.md) starting after Phase 4.
- Run every project through the [W3C Validator](https://validator.w3.org/) and [Lighthouse](https://developer.chrome.com/docs/lighthouse/).

### Path C — Accessibility & SEO Specialist (3–5 weeks)
You already know HTML basics; you want to stand out.

```
Phase 6 → 7 → 9 → 10 → Project 5 (a11y portal) → Project 4 (SEO blog)
```
- Read the [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/).
- Pass [Lighthouse](https://developer.chrome.com/docs/lighthouse/) Accessibility & SEO scores 95+.

### Path D — Email / Template Developer (2–3 weeks)
HTML emails are still mostly inline-styled `<table>` layouts.

```
Phase 1 → 2 → 3 → 4 (yes, tables for layout — exception for email!) → 7 → 9
```
- Practice on [Litmus](https://www.litmus.com/) or [Email on Acid](https://www.emailonacid.com/) free tiers.
- Read [Can I Email](https://www.caniemail.com/) before using any modern feature.

---

## Prerequisites

> [!NOTE]
> HTML requires **zero programming experience**. It is the perfect starting point for anyone entering web development.

- A computer (Windows, Mac, or Linux)
- A web browser ([Chrome](https://www.google.com/chrome/) recommended for the best DevTools)
- A text editor — [VS Code](https://code.visualstudio.com/) recommended (free, the industry default)
- Curiosity and willingness to practice
- A [GitHub account](https://github.com/) to store and share your code (you'll need it eventually anyway)

---

## How to Use This Syllabus

1. **Don't skip phases.** Each one builds on the last. If Phase 2 (basics) is shaky, Phase 6 (semantics) will feel arbitrary.
2. **Type the code yourself.** Copy-pasting from tutorials gives the illusion of learning. Type every example by hand.
3. **Build the project after every 2–3 phases.** Reading is not the same as doing.
4. **Validate every page** with the [W3C Validator](https://validator.w3.org/) — it catches errors browsers silently ignore.
5. **Test keyboard-only navigation** for every project. If you can't reach a button without a mouse, your HTML is broken.
6. **Keep an "HTML pattern notebook"** — reusable snippets for forms, tables, semantic layouts, head/meta templates. You'll use them forever.
7. **Commit every project to GitHub** from day one. Future you (and future employers) will thank you.

### Recommended Pace

| Track | Time | Phases | Projects |
|-------|------|--------|----------|
| **Fast (experienced dev)** | 2–3 weeks | Phases 5–11 | 2 capstones |
| **Regular (student / fresher)** | 4–6 weeks | All 11 phases | 3 projects |
| **Deep (job-ready)** | 6–8 weeks | All 11 phases | 5+ projects + interview prep |

> [!TIP]
> Estimated times in each phase assume ~2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F11-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what HTML is and write your first web page.

**What this phase is about.** Before you can build anything useful, you need to know *what HTML is*, *where it lives*, and *how to make a browser display it*. This phase covers the history of the web (so the rest of the syllabus has context), sets up your editor and browser DevTools, walks through the document structure (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>` — the skeleton of every page), and ends with you saving your first `.html` file and seeing it open in a browser.

**Why it matters.** Every concept in the next 10 phases assumes you can create a file, write the boilerplate, save it, and open it. Skipping or rushing this guarantees frustration in Phase 5 when you can't figure out why your form won't appear.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is HTML | What HTML stands for, why every website needs it, and how it fits with CSS & JavaScript |
| 2 | History of HTML | The evolution from HTML4 → XHTML → HTML5 → Living Standard, and why HTML5 is the modern baseline |
| 3 | How the Web Works | The browser-server model — what happens when you type a URL and hit Enter (DNS → HTTP → HTML → render) |
| 4 | Setting Up Your Editor | Install VS Code, enable Emmet shortcuts, install Live Server extension, open Chrome DevTools (F12) |
| 5 | HTML Document Structure | `<!DOCTYPE html>`, `<html lang="en">`, `<head>`, `<body>` — the skeleton of every page and why each piece exists |
| 6 | Your First HTML Page | Create, save (`.html`), and open a file in the browser — see your code come alive |
| 7 | Reading HTML in DevTools | Right-click → Inspect — see the live DOM tree of any page on the internet |

> [!TIP]
> In VS Code, type `!` and press Tab to instantly generate the full HTML5 boilerplate. This single shortcut will save you hours over the next 10 phases.

<details>
<summary><strong>HTML5 Boilerplate Reference</strong></summary>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is my first HTML page.</p>
</body>
</html>
```

Every line earns its place:
- `<!DOCTYPE html>` — tells the browser to use modern (standards) mode.
- `lang="en"` — tells screen readers and search engines what language the content is in.
- `charset="UTF-8"` — supports every character in every language (emoji, accents, Chinese, Arabic).
- `viewport` — tells mobile browsers not to render at desktop size and zoom out.
- `<title>` — the browser tab text and Google search result heading.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain what HTML is and its role in web development to a non-technical friend
- [ ] Set up VS Code, install Live Server, open Chrome DevTools (F12)
- [ ] Write and view a complete HTML page from scratch (no copy-paste)
- [ ] Inspect any live website's HTML using DevTools

</details>

---

## Phase 2: HTML Basics

![Phase](https://img.shields.io/badge/Phase-2%2F11-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the fundamental building blocks of every web page.

**What this phase is about.** Every HTML page is just elements stacked and nested inside other elements. This phase teaches the **vocabulary** — what an element, tag, and attribute actually are — and the most common content tags: headings (`<h1>`–`<h6>`), paragraphs (`<p>`), and inline text formatting (`<strong>`, `<em>`, `<code>`, etc.). It also introduces the single most important categorization in HTML: **block vs inline** elements, which decides how content flows on the page.

**Why it matters.** These 7 topics are 80% of what you'll write daily. Get them wrong (use `<b>` instead of `<strong>`, skip from `<h1>` straight to `<h4>`, mix up block and inline) and the rest of the syllabus — semantics, accessibility, SEO — collapses on top.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Elements, Tags & Attributes | Opening tags, closing tags, void elements (`<img>`, `<br>`, `<hr>`), and attribute syntax (`name="value"`) |
| 2 | Headings | `<h1>` through `<h6>` — heading hierarchy, when to use each level, and why skipping levels hurts SEO |
| 3 | Paragraphs & Spacing | `<p>` for paragraphs, `<br>` for line breaks (sparingly!), `<hr>` for thematic breaks |
| 4 | Text Formatting | `<strong>` vs `<b>`, `<em>` vs `<i>`, `<u>`, `<del>`, `<sub>`, `<sup>`, `<code>`, `<pre>`, `<kbd>`, `<samp>`, `<var>` |
| 5 | Quotations & Citations | `<blockquote>`, `<q>`, `<cite>` — semantic ways to mark up quoted material |
| 6 | Comments | `<!-- -->` — hide notes in your code that don't show on the page (but still ship to users — never put secrets here) |
| 7 | Block vs Inline Elements | Block (`<div>`, `<p>`) takes full width and stacks vertically. Inline (`<span>`, `<a>`) flows with text |
| 8 | Nesting Elements | How to properly nest tags inside each other without breaking the structure (the "first-in, last-out" rule) |
| 9 | The `id` and `class` Attributes | Hooks for CSS and JavaScript. `id` is unique per page; `class` is reusable |

> [!IMPORTANT]
> `<strong>` means **semantically important** (screen readers can emphasize it). `<b>` is just **visual bold**. Same for `<em>` (emphasized) vs `<i>` (italic styling). Always prefer the semantic tag when the meaning matches.

<details>
<summary><strong>Quick Reference: Text Formatting Tags</strong></summary>

| Tag | Purpose | Example |
|-----|---------|---------|
| `<strong>` | Important text (bold by default) | **important** |
| `<em>` | Emphasized text (italic by default) | *emphasized* |
| `<mark>` | Highlighted/marked text | highlighted |
| `<del>` | Deleted text | ~~deleted~~ |
| `<ins>` | Inserted text | underlined |
| `<sub>` | Subscript | H₂O |
| `<sup>` | Superscript | x² |
| `<code>` | Inline code | `code` |
| `<kbd>` | Keyboard input | `Ctrl+C` |
| `<samp>` | Sample output | computer output |
| `<var>` | Variable name | `x` in math |
| `<pre>` | Preformatted text | preserves spacing |
| `<small>` | Side-comments (fine print) | © 2026 Acme Co. |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Identify HTML elements, tags, and attributes in any code sample
- [ ] Use headings, paragraphs, and text formatting correctly
- [ ] Explain the difference between `<strong>` and `<b>` (and `<em>` vs `<i>`)
- [ ] Explain the difference between block and inline elements with examples
- [ ] Explain the difference between `id` and `class`

</details>

---

## Phase 3: Links, Images & Media

![Phase](https://img.shields.io/badge/Phase-3%2F11-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Connect pages together and add visual content.

**What this phase is about.** The "HT" in HTML stands for **HyperText** — text with links to other text. The `<a>` tag is what made the web *the web* in 1991, and it's still the most-used interactive element on every site. This phase covers links (internal, external, anchor, email, phone), images (`<img>` with `alt`, formats, sizing), and embedded audio/video — the core of every page that isn't pure prose.

**Why it matters.** Links and images make up 60–80% of what users actually click and look at. Bad alt text breaks accessibility. Wrong image format triples your page weight. Missing `rel="noopener"` opens you to a real security exploit. Get the small details right here and you ship faster, safer, more accessible pages forever.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Hyperlinks (`<a>`) | Link to other pages with `href`, open in new tabs with `target="_blank"`, anchor to page sections with `#id` |
| 2 | Email & Phone Links | Create clickable email (`mailto:`) and phone (`tel:`) links — and how to add subject/body to mailto |
| 3 | Download Links | The `download` attribute — force a file download instead of opening in the browser |
| 4 | Images (`<img>`) | Add images with `src` and `alt`, set `width`/`height` to prevent layout shift, choose JPEG/PNG/WebP/AVIF/SVG/GIF |
| 5 | Image Loading | `loading="lazy"` (don't load offscreen images), `decoding="async"` (don't block the parser) |
| 6 | Audio (`<audio>`) | Embed sound files with player controls, support multiple formats with `<source>` |
| 7 | Video (`<video>`) | Embed videos with `controls`, `poster` image, multiple formats, captions/subtitles with `<track>` |
| 8 | File Paths | Absolute vs relative paths, navigating directories with `../`, root-relative paths (`/images/...`) |
| 9 | Link Best Practices | Descriptive link text ("Read the report" not "Click here"), `rel="noopener noreferrer"`, `aria-label` for icon-only links |

> [!WARNING]
> Always add `rel="noopener noreferrer"` when using `target="_blank"`. Without it, the opened page can hijack your tab via `window.opener`. Modern browsers add `noopener` by default, but writing it explicitly is the safe habit.

<details>
<summary><strong>Quick Reference: Image Formats</strong></summary>

| Format | Best For | Transparency | Animation | File Size |
|--------|----------|:------------:|:---------:|:---------:|
| JPEG | Photos, complex images | No | No | Medium |
| PNG | Graphics, screenshots, transparency | Yes | No | Larger |
| GIF | Simple animations (legacy) | Yes | Yes | Large |
| **WebP** | Modern replacement for JPEG/PNG | Yes | Yes | Small |
| **AVIF** | Newest, smallest, best quality | Yes | Yes | Smallest |
| SVG | Icons, logos, illustrations | Yes | Yes | Tiny (scalable) |

> **In 2026, default to AVIF or WebP** for photos and PNG for screenshots. Use SVG for anything that needs to scale (icons, logos, charts).

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create hyperlinks to external sites, internal pages, and page sections
- [ ] Add images with proper, meaningful alt text
- [ ] Set `width` and `height` on every image to prevent layout shift
- [ ] Embed audio and video with multiple format fallbacks
- [ ] Explain why `<a target="_blank" rel="noopener">` matters for security

</details>

---

## Phase 4: Lists & Tables

![Phase](https://img.shields.io/badge/Phase-4%2F11-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Organize and display structured data.

**What this phase is about.** Lists and tables are how HTML expresses *structured information* — sequences (steps, todos, navigation menus) and grids (schedules, comparisons, financial reports). This phase covers all three list types (`<ul>`, `<ol>`, `<dl>`) and the full table model (`<thead>`, `<tbody>`, `<tfoot>`, `<caption>`, `colspan`, `rowspan`).

**Why it matters.** Real apps have nav menus, settings pages, comparison tables, pricing tables, dashboards — all built on lists and tables. Use the wrong tag (a `<div>` for a nav menu, a `<table>` for layout) and you tank both accessibility and SEO. Use the right tag and you get correct keyboard navigation, screen-reader announcements, and search-engine understanding *for free*.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Unordered Lists | Bullet-point lists with `<ul>` and `<li>` |
| 2 | Ordered Lists | Numbered lists with `<ol>`, `<li>`, custom numbering (`type="A"`, `start="5"`, `reversed`) |
| 3 | Nested Lists | Lists inside lists — for menus, outlines, and hierarchical data |
| 4 | Description Lists | Key-value pairs with `<dl>`, `<dt>`, `<dd>` — perfect for glossaries, FAQs, metadata |
| 5 | Table Basics | Build tables with `<table>`, `<tr>`, `<td>`, and `<th>` for headers |
| 6 | Table Structure | Organize with `<thead>`, `<tbody>`, `<tfoot>`, and add titles with `<caption>` |
| 7 | Merging Cells | Span columns with `colspan` and rows with `rowspan` for complex layouts |
| 8 | Table Accessibility | `scope="col"`/`scope="row"` on headers, `<caption>`, summary patterns for screen readers |
| 9 | Column Styling | `<colgroup>` and `<col>` — apply styles or widths to entire columns at once |

> [!CAUTION]
> Never use `<table>` for page layout. Tables are for **tabular data only** (spreadsheets, schedules, comparisons). Use CSS Flexbox or Grid for layout. **Exception:** HTML emails — most email clients (Outlook!) still don't support modern CSS, so emails are written with table-based layouts. Outside of email, never.

<details>
<summary><strong>Quick Reference: Anatomy of an Accessible Table</strong></summary>

```html
<table>
    <caption>Q4 2025 Sales by Region</caption>
    <thead>
        <tr>
            <th scope="col">Region</th>
            <th scope="col">Revenue</th>
            <th scope="col">Growth</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">North America</th>
            <td>$2.4M</td>
            <td>+12%</td>
        </tr>
        <tr>
            <th scope="row">Europe</th>
            <td>$1.8M</td>
            <td>+8%</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th scope="row">Total</th>
            <td>$4.2M</td>
            <td>+10%</td>
        </tr>
    </tfoot>
</table>
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create ordered, unordered, and description lists
- [ ] Build a fully-structured table with `<thead>`, `<tbody>`, `<tfoot>`, and `<caption>`
- [ ] Use `scope` attributes on `<th>` for screen-reader accessibility
- [ ] Merge table cells using `colspan` and `rowspan`

</details>

---

## Phase 5: Forms & User Input

![Phase](https://img.shields.io/badge/Phase-5%2F11-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build interactive forms to collect user data.

**What this phase is about.** Forms are how the web becomes a two-way street — search bars, login pages, sign-ups, checkouts, contact forms, file uploads, settings panels. HTML5 ships with **22+ input types** and **a full validation system built in**, no JavaScript needed for basic checks. This phase covers every input type, every validation attribute, label/fieldset patterns, and the `GET` vs `POST` decision.

**Why it matters.** Forms are the highest-stakes part of any site — broken signup form = no users, broken checkout = no revenue, inaccessible form = lawsuit. Forms are also the #1 source of UX complaints and the #1 thing employers test in interviews. Master forms and you instantly look senior.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The `<form>` Element | `action` (where data goes), `method` (`GET` vs `POST`), `enctype`, and how forms submit |
| 2 | Labels | `<label>` with `for` attribute — connects text to inputs for accessibility, UX, and click target size |
| 3 | Text Inputs | `text`, `password`, `email`, `number`, `tel`, `url`, `search` — each has built-in validation and mobile keyboards |
| 4 | Date & Time Inputs | `date`, `time`, `datetime-local`, `month`, `week` — native browser pickers |
| 5 | Selection Inputs | `checkbox` (multi-select), `radio` (single-select), `<select>` dropdowns, `<datalist>` autocomplete, `<optgroup>` |
| 6 | File, Range, & Color | `file` (uploads, with `accept` and `multiple`), `range` (sliders), `color` (color picker), `hidden` (invisible data) |
| 7 | Textarea & Buttons | `<textarea>` for multi-line text, `<button>` vs `<input type="submit">`, `formaction` to override `<form>` action |
| 8 | Grouping Fields | `<fieldset>` and `<legend>` — visually and semantically group related inputs (radio groups, address blocks) |
| 9 | HTML5 Validation | `required`, `minlength`, `maxlength`, `min`, `max`, `step`, `pattern` (regex), `placeholder` (and the `:invalid` CSS state) |
| 10 | Input Attributes | `name`, `value`, `id`, `disabled`, `readonly`, `autofocus`, `autocomplete`, `inputmode`, `accept` |
| 11 | Mobile Keyboard Hints | `inputmode="numeric"`, `inputmode="email"`, `inputmode="decimal"` — show the right keyboard on phones |
| 12 | Output & Progress | `<output>` (live form result display), `<progress>` (loading bars), `<meter>` (gauges) |

> [!TIP]
> Always wrap or link every input with a `<label>`. Clicking the label focuses the input — better UX for everyone, mandatory for screen-reader users, and the click target gets bigger on mobile (touch-target accessibility).

<details>
<summary><strong>Quick Reference: All HTML5 Input Types</strong></summary>

| Input Type | Purpose | Example Use |
|------------|---------|-------------|
| `text` | Single-line text | Name, username |
| `password` | Hidden text | Password fields |
| `email` | Email with validation + mobile keyboard | Email address |
| `number` | Numeric input + spinner | Age, quantity |
| `tel` | Phone number + numeric mobile keyboard | Contact number |
| `url` | URL with validation | Website link |
| `search` | Search field (with built-in clear button on iOS) | Search bar |
| `date` | Date picker | Birth date |
| `time` | Time picker | Appointment time |
| `datetime-local` | Date + time | Event scheduling |
| `month` | Month + year | Card expiry |
| `week` | Week of year | Scheduling |
| `checkbox` | Multiple selections | Preferences, T&Cs |
| `radio` | Single selection from a group | Plan type, gender |
| `file` | File upload (use `accept` + `multiple`) | Profile picture, documents |
| `range` | Slider | Volume, rating |
| `color` | Color picker | Theme color |
| `hidden` | Hidden data | CSRF tokens, IDs |

</details>

<details>
<summary><strong>Quick Reference: GET vs POST</strong></summary>

| | `GET` | `POST` |
|--|-------|--------|
| Data location | URL (query string) | Request body |
| Visible to user? | Yes — bookmark-able, shareable | No |
| Cacheable? | Yes | No |
| Idempotent? | Yes (safe to repeat) | No |
| Use for | Search, filters, navigation | Forms that change data (login, sign-up, payment) |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a complete form with at least 8 different input types
- [ ] Apply HTML5 validation (`required`, `pattern`, `min`/`max`, `minlength`/`maxlength`)
- [ ] Group related fields with `<fieldset>` and `<legend>` (especially radio buttons)
- [ ] Set `inputmode` and `autocomplete` correctly for mobile UX
- [ ] Explain `GET` vs `POST` and pick the right one for a use case

</details>

---

## Phase 6: Semantic HTML

![Phase](https://img.shields.io/badge/Phase-6%2F11-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write meaningful HTML that browsers, screen readers, AI, and search engines understand.

**What this phase is about.** Before HTML5 (2014), every page was a forest of `<div>` tags with `class="header"`, `class="nav"`, `class="footer"`. Browsers had no idea which `<div>` was the navigation and which was the article. HTML5 introduced **semantic elements** — `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`, `<figure>`, `<time>`, etc. — that tell every consumer (browser, screen reader, search crawler, AI scraper) what each chunk of the page *means*.

**Why it matters.** Semantic HTML is the single highest-leverage skill in this entire syllabus. It costs nothing extra to write — `<nav>` is the same number of characters as `<div>` — and it improves accessibility, SEO, and code readability all at once. Most "senior frontend" interview questions are really just "do you know your semantics?".

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Semantics Matter | How semantic HTML improves accessibility, SEO, AI parsing, and code readability — and reduces ARIA you'd otherwise need |
| 2 | `<header>` & `<footer>` | Page/section introductions and footer content (contact, copyright, sitemap) |
| 3 | `<nav>` | Wraps your navigation links — tells browsers and screen readers "this is a menu" |
| 4 | `<main>` | The primary content of the page (only **one** per page — exactly one) |
| 5 | `<section>` & `<article>` | `<section>` groups related content with a heading; `<article>` is self-contained (blog post, card, comment) |
| 6 | `<aside>` | Sidebar content, related links, supplementary information, ad slots |
| 7 | `<figure>` & `<figcaption>` | Images, diagrams, code snippets, or quotes with a descriptive caption |
| 8 | `<details>` & `<summary>` | Native collapsible/expandable sections — no JavaScript needed |
| 9 | Other Semantic Tags | `<time>`, `<mark>`, `<progress>`, `<meter>`, `<address>`, `<blockquote>`, `<cite>`, `<abbr>`, `<dfn>` |
| 10 | Document Outline | How heading levels (`<h1>`–`<h6>`) and sections form an implicit document tree |
| 11 | `<div>` vs Semantic Tags | When `<div>` is okay (pure styling hook) and when a semantic element is required |

> [!IMPORTANT]
> Think of `<div>` as a last resort — a styling hook with no meaning. If a semantic element describes your content (`<nav>`, `<article>`, `<aside>`, `<button>`), always use that instead. The single biggest semantic upgrade for any site: replace `<div onclick="...">` with `<button>`.

<details>
<summary><strong>Visual: Semantic Page Structure</strong></summary>

```
┌──────────────────────────────────┐
│            <header>              │
│   ┌──────────────────────────┐   │
│   │          <nav>           │   │
│   └──────────────────────────┘   │
├──────────────────────────────────┤
│            <main>                │
│   ┌───────────────┐ ┌────────┐   │
│   │  <article>    │ │<aside> │   │
│   │  ┌─────────┐  │ │        │   │
│   │  │<section>│  │ │        │   │
│   │  └─────────┘  │ │        │   │
│   │  ┌─────────┐  │ │        │   │
│   │  │<section>│  │ │        │   │
│   │  └─────────┘  │ │        │   │
│   └───────────────┘ └────────┘   │
├──────────────────────────────────┤
│            <footer>              │
└──────────────────────────────────┘
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Replace generic `<div>` elements with proper semantic tags in any page
- [ ] Structure a page using `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- [ ] Explain the difference between `<section>` and `<article>` with examples
- [ ] Explain how semantic HTML improves SEO and accessibility (specific reasons, not "it's better")

</details>

---

## Phase 7: HTML Head, Meta Tags & Resource Hints

![Phase](https://img.shields.io/badge/Phase-7%2F11-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Control how your page appears in browsers, search engines, social media, and AI tools.

**What this phase is about.** The `<head>` is the invisible but enormously important part of every HTML page. Nothing inside it shows up to the user — yet what you put there decides how Google ranks you, how your page looks when shared on Twitter or Slack, what icon shows in the browser tab, what fonts and stylesheets load, and how fast the page paints. This phase covers every essential meta tag, the Open Graph protocol, favicons, and **resource hints** (`preload`, `preconnect`, `dns-prefetch`, `prefetch`, `modulepreload`) — small `<link>` tags that can shave whole seconds off your load time.

**Why it matters.** Two pages with identical visible content can rank totally differently on Google, share differently on social media, and load 3× faster — based purely on what's in their `<head>`. Marketing teams obsess over this. So should you.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The `<head>` Section | What goes inside `<head>` — none of it is visible on the page, but all of it matters |
| 2 | `<title>` Tag | Sets the browser tab text and the title shown in Google search results |
| 3 | Essential Meta Tags | `charset`, `viewport`, `description`, `author`, `robots`, `theme-color` |
| 4 | Open Graph Tags | `og:title`, `og:description`, `og:image`, `og:url`, `og:type` — control how your page looks when shared on social media, Slack, Discord, iMessage |
| 5 | Twitter Card Tags | `twitter:card`, `twitter:image`, `twitter:site` — Twitter/X-specific previews |
| 6 | Favicon | `<link rel="icon">`, multi-resolution favicons, Apple touch icons, Android Chrome icons |
| 7 | External Resources | `<link rel="stylesheet">` for CSS, `<link rel="canonical">` for SEO |
| 8 | **Resource Hints — `preload`** | Tell the browser "load this critical resource ASAP" (above-the-fold fonts, hero images) |
| 9 | **Resource Hints — `preconnect`** | Open the TCP+TLS connection early to a domain you'll fetch from soon (CDN, API) |
| 10 | **Resource Hints — `dns-prefetch`** | Just resolve DNS early (cheaper than `preconnect`, useful when you have many third-party domains) |
| 11 | **Resource Hints — `prefetch`** | Fetch low-priority resources for *the next* navigation (cache them now, use them later) |
| 12 | **Resource Hints — `modulepreload`** | Like `preload` but for ES modules — preloads + parses them |
| 13 | Script Loading | `<script>` placement, `defer` vs `async` vs `type="module"` |
| 14 | PWA Manifest Link | `<link rel="manifest" href="/manifest.json">` — declares your site as a Progressive Web App |
| 15 | Multilingual / `hreflang` | `<link rel="alternate" hreflang="es">` — tell Google about translated versions |

> [!TIP]
> Always include these 4 tags in every page — they are non-negotiable:
> ```html
> <meta charset="UTF-8">
> <meta name="viewport" content="width=device-width, initial-scale=1.0">
> <meta name="description" content="A clear, 150-character description of this page">
> <link rel="canonical" href="https://yoursite.com/this-page">
> ```

<details>
<summary><strong>Quick Reference: Open Graph Starter Block</strong></summary>

```html
<!-- Essentials -->
<title>Your Page Title — Brand</title>
<meta name="description" content="A clear description for search results.">
<link rel="canonical" href="https://yoursite.com/page">

<!-- Open Graph (Facebook, LinkedIn, Slack, Discord, iMessage) -->
<meta property="og:type" content="website">
<meta property="og:title" content="Your Page Title">
<meta property="og:description" content="A clear description for social shares.">
<meta property="og:image" content="https://yoursite.com/og.png">
<meta property="og:url" content="https://yoursite.com/page">

<!-- Twitter / X -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://yoursite.com/og.png">

<!-- PWA / theme -->
<meta name="theme-color" content="#0a0a0a">
<link rel="manifest" href="/manifest.json">

<!-- Favicons -->
<link rel="icon" href="/favicon.ico">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
```

</details>

<details>
<summary><strong>Quick Reference: Script Loading — defer vs async vs module</strong></summary>

| Attribute | HTML Parsing | Script Download | Script Execution |
|-----------|:------------:|:---------------:|:----------------:|
| `<script>` | **Pauses** | Downloads | Runs immediately |
| `<script defer>` | Continues | In parallel | After HTML parsed (in order) |
| `<script async>` | Continues | In parallel | As soon as downloaded (any order) |
| `<script type="module">` | Continues | In parallel | After HTML parsed (deferred by default) |

**Rule of thumb:** Use `defer` for app code. Use `async` only for independent scripts (analytics, ads). Use `type="module"` for modern ESM code.

</details>

<details>
<summary><strong>Quick Reference: Resource Hints Decision Tree</strong></summary>

| You want to... | Use |
|---------------|-----|
| Preload a critical font/image *for this page* | `<link rel="preload">` |
| Connect to a domain early (TCP + TLS handshake) | `<link rel="preconnect">` |
| Just resolve DNS early (lighter than preconnect) | `<link rel="dns-prefetch">` |
| Cache a resource for the *next* page navigation | `<link rel="prefetch">` |
| Preload an ES module | `<link rel="modulepreload">` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Configure essential meta tags (charset, viewport, description, canonical) on every page
- [ ] Set up complete Open Graph + Twitter card tags and verify with [OpenGraph.xyz](https://www.opengraph.xyz/)
- [ ] Use `defer` vs `async` correctly
- [ ] Use `<link rel="preconnect">` to your CDN and `<link rel="preload">` for an above-the-fold font

</details>

---

## Phase 8: Advanced HTML

![Phase](https://img.shields.io/badge/Phase-8%2F11-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Explore features beyond the basics — modern modal dialogs, popovers, responsive images, Web Components, embedded content.

**What this phase is about.** HTML did not stop evolving in 2014. Modern HTML ships features that used to require thousands of lines of JavaScript: **`<dialog>`** (native modals with focus trapping), the **Popover API** (`popovertarget`, the `inert` attribute), **`<picture>` + `srcset`** (responsive images that serve the right format and size to every device), **`<template>`/`<slot>`** (the foundation of Web Components), **inline SVG**, **`<canvas>`**, and proper iframe sandboxing. This phase covers what separates "I know HTML" from "I keep up with HTML".

**Why it matters.** Every one of these features replaces a popular JavaScript library — and runs faster, weighs less, and is more accessible than the library it replaces. Senior frontend roles expect you to reach for the platform first, libraries second.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Iframes (`<iframe>`) | Embed external content (maps, videos, payments), use `sandbox` for security, `loading="lazy"` for speed |
| 2 | HTML Entities & Symbols | Special characters: `&amp;`, `&lt;`, `&gt;`, `&nbsp;`, `&copy;`, numeric refs (`&#169;`), and when each is required |
| 3 | Data Attributes (`data-*`) | Store custom data on any element, access in JavaScript with `element.dataset`, use as CSS selectors |
| 4 | Responsive Images | `<picture>` with `<source>`, `srcset` and `sizes` — serve the right image format and size for every screen |
| 5 | Lazy-Loading Images & Iframes | `loading="lazy"`, `decoding="async"`, `fetchpriority` — defer offscreen content |
| 6 | Canvas (`<canvas>`) | Draw graphics, build games, create visualizations (requires JavaScript) |
| 7 | SVG (`<svg>`) | Inline vs `<img>`, basic shapes (circle, rect, path), styling with CSS — always sharp at any size |
| 8 | **Native Dialogs (`<dialog>`)** | Modal and non-modal dialogs, `dialog.showModal()`, form submission with `method="dialog"`, focus trap and Escape-to-close behavior |
| 9 | **Popover API** | The `popover` attribute and `popovertarget` button attribute — declarative tooltips and menus, top-layer rendering |
| 10 | **`inert` Attribute** | Make a section completely non-interactive (background while a modal is open) — replaces complex focus-trap libraries |
| 11 | HTML Templates | `<template>` (parsed but not rendered) and `<slot>` — reusable markup for Web Components |
| 12 | Web Components Intro | Custom Elements, Shadow DOM — framework-agnostic reusable UI (`<my-button>`) |
| 13 | Progressive Enhancement | `hidden`, `<noscript>`, fallback content — letting HTML work *before* JavaScript loads or *if* it fails |
| 14 | Microdata & RDFa | `itemscope`, `itemtype`, `itemprop` — inline structured data (JSON-LD is preferred today, but you'll see this in legacy code) |

> [!WARNING]
> Always use the `sandbox` attribute on iframes embedding third-party content. Without it, the embedded page can run scripts, submit forms, set cookies, and break out of the iframe via `window.top`. Start with `sandbox=""` (most restrictive) and only add what you need (`allow-scripts`, `allow-same-origin`).

<details>
<summary><strong>Quick Reference: Canvas vs SVG</strong></summary>

| Feature | Canvas | SVG |
|---------|--------|-----|
| Type | Raster (pixels) | Vector (math) |
| Scaling | Gets blurry | Always sharp |
| Performance | Better for many objects | Better for few objects |
| Interaction | Manual (JavaScript hit-testing) | Built-in (DOM events on every shape) |
| Best for | Games, dense data viz, image filters | Icons, logos, charts, illustrations |
| Accessibility | Poor (just pixels) | Good (each shape is a DOM element) |
| File-based usage | No | Yes (`<img src="logo.svg">`) |

</details>

<details>
<summary><strong>Quick Reference: Native `<dialog>` Modal</strong></summary>

```html
<dialog id="confirmDialog">
    <form method="dialog">
        <h2>Delete this item?</h2>
        <p>This action cannot be undone.</p>
        <button value="cancel">Cancel</button>
        <button value="confirm">Delete</button>
    </form>
</dialog>

<button onclick="confirmDialog.showModal()">Delete</button>

<script>
  confirmDialog.addEventListener('close', () => {
    if (confirmDialog.returnValue === 'confirm') deleteItem();
  });
</script>
```

> Native `<dialog>` gives you focus trap, Escape-to-close, backdrop, and accessible name — for free.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Embed external content safely with sandboxed iframes
- [ ] Use data attributes (`data-*`) to pass values from HTML to JavaScript and CSS
- [ ] Implement responsive images with `<picture>`, `srcset`, and `sizes`
- [ ] Build a native `<dialog>` modal with `showModal()` and `method="dialog"`
- [ ] Use `inert` to disable a background section while a modal is open
- [ ] Explain when to use Canvas vs SVG

</details>

---

## Phase 9: Accessibility

![Phase](https://img.shields.io/badge/Phase-9%2F11-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-7 Hours](https://img.shields.io/badge/Time-5--7%20Hours-yellow)

> Make your web pages usable by everyone — including blind users, motor-impaired users, and the 1.3 billion people worldwide with some form of disability.

**What this phase is about.** Accessibility (a11y — `a` + 11 letters + `y`) is the practice of building pages that work for users with screen readers, keyboard-only navigation, voice control, low-vision settings, motor impairments, and cognitive differences. This phase covers the four WCAG principles (Perceivable, Operable, Understandable, Robust), `alt` text done right, the `ARIA` attribute system (and when to *not* use it), keyboard navigation, and how to test with real screen readers.

**Why it matters.** Three reasons, in order of how the business will phrase them:
1. **Legal.** ADA (US), EAA (EU), AODA (Canada). Companies are sued every week for inaccessible sites.
2. **Reach.** ~15% of the world has a disability — that's hundreds of millions of paying customers.
3. **Better UX for everyone.** Captions help everyone in noisy environments. High contrast helps everyone in sunlight. Keyboard nav helps power users.

And the secret: **most a11y is just semantic HTML done correctly** (Phase 6). You're already 80% of the way there.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Accessibility Matters | Legal requirements, audience reach, better UX, and the moral case |
| 2 | WCAG 2.2 Principles | **Perceivable**, **Operable**, **Understandable**, **Robust** — the 4 pillars (POUR) |
| 3 | WCAG Levels | A (minimum), AA (industry standard), AAA (highest — rarely required for whole sites) |
| 4 | Semantic HTML (Recap) | How using the right elements (`<nav>`, `<main>`, `<button>`) makes pages accessible *by default* |
| 5 | Image Accessibility | Meaningful `alt` text, decorative images (`alt=""`), long descriptions for complex images, captions on videos |
| 6 | ARIA Basics | `role`, `aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`, `aria-live` |
| 7 | When NOT to Use ARIA | Native HTML always wins — `<button>` beats `<div role="button">` every time |
| 8 | Keyboard Navigation | `tabindex`, focus management, skip-to-content links — your site must work without a mouse |
| 9 | Focus Indicators | Visible focus rings (`:focus-visible`) — never `outline: none` without a replacement |
| 10 | Form Accessibility | Labels for every input, error messages tied with `aria-describedby`, required-field indicators |
| 11 | Language & Direction | `lang` for screen-reader pronunciation, `dir="rtl"` for Arabic / Hebrew |
| 12 | Color & Contrast | WCAG AA contrast ratios (4.5:1 normal, 3:1 large), don't rely on color alone |
| 13 | Reduced Motion | Respect `prefers-reduced-motion` — millions of users get vertigo from animations |
| 14 | Screen Reader Testing | Test with VoiceOver (Mac, free), NVDA (Windows, free), TalkBack (Android, free) |

> [!IMPORTANT]
> The #1 rule of ARIA: **don't use ARIA if you can use a native HTML element instead.** A `<button>` is always better than `<div role="button">`. Native elements get keyboard support, focus styles, and screen-reader names for free. ARIA is a patch — patches are second-best.

<details>
<summary><strong>Quick Reference: Writing Good Alt Text</strong></summary>

| Image Type | Alt Text Approach | Example |
|-----------|-------------------|---------|
| Informative | Describe the content | `alt="Golden retriever playing fetch in a park"` |
| Functional (link/button) | Describe the action | `alt="Search"` or `alt="Go to homepage"` |
| Decorative | Leave empty | `alt=""` |
| Complex (charts/graphs) | Summarize + provide long description | `alt="Sales chart showing 30% growth in Q4"` (with a longer text version nearby) |
| Text in image | Repeat the text exactly | `alt="Sale: 50% off all items"` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Apply WCAG POUR principles to any web page
- [ ] Write effective alt text for 5 different image types
- [ ] Use ARIA attributes correctly (and identify cases where ARIA is unnecessary)
- [ ] Navigate one of your pages using only the keyboard (no mouse)
- [ ] Test a page with a screen reader (VoiceOver, NVDA, or browser extension)
- [ ] Run [axe DevTools](https://www.deque.com/axe/devtools/) and resolve every flagged issue

</details>

---

## Phase 10: SEO, Structured Data & Performance

![Phase](https://img.shields.io/badge/Phase-10%2F11-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Write clean, performant, search-engine-friendly HTML that ranks high and loads fast.

**What this phase is about.** Two topics that decide whether anyone ever sees your beautiful HTML: **SEO** (will Google show this page?) and **performance** (will the user wait long enough for it to load?). This phase covers the HTML side of both — heading hierarchy, descriptive titles, **Schema.org structured data with JSON-LD** (the way to get rich results in Google), sitemaps, robots, lazy-loading, preloading, and **Core Web Vitals** (LCP, INP, CLS) — Google's ranking metrics.

**Why it matters.** "I built a great site, but no one visits it" is the #1 silent killer of side projects. Most of the fix is in the HTML. Get this phase right and your project ranks, loads fast, and shows recipe cards / product cards / FAQ accordions directly in Google search results.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Code Quality | Consistent indentation, meaningful class/ID names, proper tag nesting |
| 2 | Heading Hierarchy | One `<h1>` per page, logical `<h2>` → `<h3>` → `<h4>` structure (no skipping levels) |
| 3 | SEO Meta Tags | Descriptive `<title>` (50–60 chars) and `<meta description>` (150–160 chars) that earn the click |
| 4 | **Structured Data — JSON-LD** | The modern way: `<script type="application/ld+json">` with Schema.org vocabularies |
| 5 | **Schema.org Types** | `Article`, `Product`, `Recipe`, `Event`, `FAQPage`, `Breadcrumb`, `Organization`, `LocalBusiness` |
| 6 | Sitemap & robots.txt | Tell search engines what to crawl (`sitemap.xml`) and what to skip (`robots.txt`, `meta robots`) |
| 7 | Canonical URLs | `<link rel="canonical">` — prevent duplicate content penalties |
| 8 | Lazy Loading | `loading="lazy"` on images and iframes — only load what the user can see |
| 9 | Preloading | `<link rel="preload">` for critical fonts, hero images, scripts |
| 10 | Core Web Vitals (HTML side) | LCP (Largest Contentful Paint), INP (Interaction to Next Paint), CLS (Cumulative Layout Shift) |
| 11 | Preventing CLS | Always set `width` and `height` on images and embeds; reserve space for ads/dynamic content |
| 12 | DOM Performance | Minimize nesting depth, remove unnecessary wrapper `<div>`s |
| 13 | HTML Validation | Use the [W3C Validator](https://validator.w3.org/) to catch errors browsers silently ignore |
| 14 | Cross-Browser Testing | Test in Chrome, Firefox, Safari. Use [Can I Use](https://caniuse.com/) before adopting new features |
| 15 | Lighthouse Audits | Built into Chrome DevTools — scores Performance, Accessibility, Best Practices, SEO out of 100 |

> [!TIP]
> Run every page through the [W3C Validator](https://validator.w3.org/) and Chrome [Lighthouse](https://developer.chrome.com/docs/lighthouse/) before considering it "done." Aim for: HTML validation = 0 errors, Lighthouse Performance ≥ 90, Accessibility ≥ 95, SEO ≥ 95.

<details>
<summary><strong>Quick Reference: JSON-LD for an Article (paste into `<head>`)</strong></summary>

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Your Article Title",
  "image": ["https://example.com/photo.jpg"],
  "datePublished": "2026-05-01T08:00:00+00:00",
  "dateModified": "2026-05-02T09:30:00+00:00",
  "author": [{
    "@type": "Person",
    "name": "Jane Doe",
    "url": "https://example.com/jane"
  }],
  "publisher": {
    "@type": "Organization",
    "name": "Your Site",
    "logo": {
      "@type": "ImageObject",
      "url": "https://example.com/logo.png"
    }
  }
}
</script>
```

> Test with [Google Rich Results Test](https://search.google.com/test/rich-results) before deploying.

</details>

<details>
<summary><strong>Quick Reference: Core Web Vitals — What Each Metric Means</strong></summary>

| Metric | Measures | Good Threshold | HTML Fix |
|--------|----------|---------------|----------|
| **LCP** (Largest Contentful Paint) | When the biggest visible element appears | ≤ 2.5s | Preload hero image, optimize images, server-side rendering |
| **INP** (Interaction to Next Paint) | Responsiveness to clicks/taps | ≤ 200ms | Reduce JS work, defer non-critical scripts |
| **CLS** (Cumulative Layout Shift) | How much content jumps around | ≤ 0.1 | Set `width`/`height` on images, reserve space for ads/embeds |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Validate every page using the [W3C Validator](https://validator.w3.org/) (zero errors)
- [ ] Add JSON-LD structured data for at least one Schema.org type and verify with [Rich Results Test](https://search.google.com/test/rich-results)
- [ ] Score 95+ on Lighthouse SEO and Accessibility
- [ ] Add `width` and `height` to every image to eliminate CLS
- [ ] Optimize one page's LCP by preloading the hero image
- [ ] Generate a `sitemap.xml` and a `robots.txt`

</details>

---

## Phase 11: What's Next? (CSS, JavaScript, Frameworks)

![Phase](https://img.shields.io/badge/Phase-11%2F11-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You've finished the structure. Now style it, animate it, and make it interactive.

**What this phase is about.** HTML alone is enough for documents — resumes, blog posts, docs, simple landing pages. To build *applications* (anything with state, interaction, data fetching, animation), you need CSS for styling and JavaScript for behavior. This phase is your runway from "I write HTML" to "I build web apps" — pointing at the right next syllabus for each track.

**Why it matters.** This is the gap most self-taught learners hit. They know HTML, build a static site, then freeze when faced with "make this button submit a form to an API and update the UI without reloading." Now you have a map.

### 11.1 — Style It: CSS

CSS controls how every HTML element *looks* — colors, fonts, spacing, layout, animations, responsive design. Modern CSS (Flexbox, Grid, Container Queries, custom properties, `:has()`) is genuinely powerful — most "I'll just use Bootstrap" reflexes are obsolete.

➡️ Continue with the [CSS Syllabus](css.md).

### 11.2 — Make It Interactive: JavaScript

JavaScript is the only language native to every browser. It's what powers: clicking a button to show a menu, fetching data from an API, validating forms, building entire SPAs.

➡️ Continue with the [JavaScript Syllabus](javascript.md).

### 11.3 — Pick a Frontend Framework

Once you know HTML/CSS/JS, frameworks make building large apps faster and more maintainable:

| Framework | Best For | Companies |
|-----------|----------|-----------|
| **[React](react.md)** (most popular, recommended) | Job market, ecosystem, hiring | Meta, Netflix, Airbnb, Uber, Shopify |
| **[Vue](vuejs.md)** | Gentle learning curve, great docs | Alibaba, GitLab, Nintendo |
| **[Angular](angular.md)** | Large enterprise apps, opinionated | Google, Microsoft, Deutsche Bank |

**Recommendation for 2026:** Start with **React** + Next.js. Most job postings, most ecosystem, best AI tooling.

### 11.4 — Real-World Add-Ons

| Skill | Why It Matters |
|-------|----------------|
| **[Git](git.md)** | Mandatory. Every job, every team. |
| **Deployment** ([Vercel](https://vercel.com/), [Netlify](https://www.netlify.com/), [Cloudflare Pages](https://pages.cloudflare.com/)) | Free hosting for static sites. Push to GitHub → auto-deploy. |
| **[Docker](docker.md)** | "Works on my machine" → "works everywhere". |
| **Email HTML** ([MJML](https://mjml.io/), [Maizzle](https://maizzle.com/)) | Niche, in-demand skill. Tables-based markup, inline CSS. |
| **Web Components** | Framework-agnostic custom elements. Future of UI libraries. |

### 11.5 — Suggested Order After This Syllabus

```
CSS → JavaScript → Git → React (or Vue) → Deploy → Build a real project
```

Build, ship, repeat. There is no substitute for *finishing* projects.

---

## Common Mistakes

Avoid these pitfalls that trip up most beginners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Skipping `alt` on images | Breaks accessibility; screen readers can't describe the image; hurts SEO | Always add descriptive `alt` text (or empty `alt=""` for decorative) |
| 2 | Using `<br>` for spacing | That's what CSS margin/padding is for | Use CSS for spacing between elements |
| 3 | Using headings for appearance | Breaks document hierarchy; confuses screen readers and search engines | Use headings to reflect content structure, then style with CSS |
| 4 | Using `<div>` for everything | Loses semantic meaning; hurts SEO and accessibility | Use `<nav>`, `<main>`, `<section>`, `<article>`, `<button>`, etc. |
| 5 | Forgetting `<!DOCTYPE html>` | Browser enters "quirks mode" and renders things differently | Always start with `<!DOCTYPE html>` |
| 6 | Inline styles everywhere | Makes code unmaintainable, hurts caching | Use external CSS files |
| 7 | Leaving non-void elements unclosed | Causes broken nesting and confusing markup; void elements like `<img>` do not need closing tags | Close non-void elements properly; learn which elements are void |
| 8 | Using `<table>` for layout | Tables are for data; layout should use CSS | Use CSS Flexbox or Grid (exception: HTML email) |
| 9 | Skipping `<label>` on form inputs | Inputs become unusable for screen readers and harder to click | Wrap or link every input with a `<label>` |
| 10 | Ignoring mobile viewport | Page won't scale properly on phones | Add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` |
| 11 | Missing `width`/`height` on images | Causes CLS (Cumulative Layout Shift) — Google penalizes this | Always set both — even if you use CSS `width: 100%` |
| 12 | Generic link text ("Click here") | Bad for SEO and screen readers (which often list all links out of context) | Use descriptive text: "Read the full report" |
| 13 | `<div role="button">` instead of `<button>` | Native `<button>` already has keyboard, focus, accessibility, default styles | Always use `<button>` for interactive things |
| 14 | Missing `lang` on `<html>` | Screen readers can't pronounce content correctly | Set `<html lang="en">` (or your page's language) |
| 15 | Putting secrets in HTML comments | Comments ship to every visitor — they can View Source | Never write API keys, TODOs about security, or internal URLs in comments |

---

## Interview Questions

For the dedicated interview-prep version, see [HTML Interview Questions](../interviews/html.md).

---

## Practice Projects

Build these projects as you progress through the syllabus. They are designed to be **resume-worthy, practical, and closer to real product work**. Each project gives you a real artifact you can deploy and link from your resume.

> [!IMPORTANT]
> The goal is not "just building pages." The goal is proving you can write semantic, accessible, SEO-aware HTML that teams can ship. Push every project to GitHub and deploy live (Vercel/Netlify/Cloudflare Pages — all free).

### Project 1: Developer Profile + Resume Microsite
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A multi-section profile site with home, about, skills, project cards, contact. Multiple linked HTML files, semantic sectioning, downloadable resume PDF, social meta tags so your link unfurls nicely on LinkedIn.

**Skills practiced:** Page structure, links, lists, media, semantic layout, heading hierarchy.

**Stretch goal:** Add a printable resume style sheet (`@media print`). Self-host fonts. Score 100 on Lighthouse SEO.

---

### Project 2: Documentation-Style Product Page
![Phase 3-5](https://img.shields.io/badge/After-Phase%203--5-green)

**What you'll build:** A documentation page with sticky left nav, table of contents, callouts (info / warning / danger), code snippets with `<pre><code>`, a comparison table, and an FAQ accordion using `<details>`.

**Skills practiced:** Lists, tables, internal anchors, semantic sections, `<pre><code>`, reusable information architecture.

**Stretch goal:** Add a "copy code" button hint, a search bar, dark/light theme via `prefers-color-scheme`.

---

### Project 3: Multi-Step Job Application Form
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** A realistic hiring form: candidate details, work experience (repeating fieldsets), file upload (resume + cover letter), role preferences, availability, and declarations. HTML5 validation only — no JavaScript validation.

**Skills practiced:** Full form system, `<fieldset>`/`<legend>` grouping, validation attributes, `inputmode`/`autocomplete`, accessibility labels, error association with `aria-describedby`.

**Stretch goal:** Add a multi-step progress indicator using `<progress>`. Inline + summary error messages with proper ARIA.

---

### Project 4: SEO + Social Optimized Blog Template
![Phase 6-8](https://img.shields.io/badge/After-Phase%206--8-yellow)

**What you'll build:** A long-form article template with semantic layout, full meta + Open Graph + Twitter card tags, JSON-LD `Article` structured data, related-posts sidebar, and reading-progress indicator (`<progress>`).

**Skills practiced:** Head/meta strategy, semantic content modeling (`<article>`, `<aside>`, `<time>`, `<figure>`), share metadata, JSON-LD, byline conventions.

**Stretch goal:** Pass [Google Rich Results Test](https://search.google.com/test/rich-results). Get a screenshot of your social preview from [OpenGraph.xyz](https://www.opengraph.xyz/).

---

### Project 5: Accessibility-First Government Service Portal
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-red)

**What you'll build:** A public services portal — homepage, service listing, service-detail page, application form, help center. Designed from the ground up for keyboard and screen-reader users. Skip-to-content links, visible focus rings, no-mouse navigation, multilingual `lang` switching, accessible tables.

**Skills practiced:** Landmark semantics, robust forms, focus flow, error handling, accessible tables, skip links, RTL/LTR direction switching.

**Stretch goal:** Pass Lighthouse Accessibility 100. Zero critical issues in [axe DevTools](https://www.deque.com/axe/devtools/) and [WAVE](https://wave.webaim.org/). Test with VoiceOver or NVDA.

---

### Project 6: E-commerce Product Detail + Checkout Skeleton
![Phase 8-10](https://img.shields.io/badge/After-Phase%208--10-red)

**What you'll build:** A production-style product page with image gallery (`<picture>` + `srcset`), variant selectors (radio groups), quantity (`<input type="number">`), reviews summary, delivery info, and a checkout form skeleton with multi-step `<fieldset>`s. Add JSON-LD `Product` + `Review` schema.

**Skills practiced:** Information hierarchy, semantic commerce markup, responsive images, structured data, high-quality forms, FAQ accordion.

**Stretch goal:** Native `<dialog>` for "Added to cart" and size guide. Image zoom on hover. Breadcrumb navigation with `BreadcrumbList` schema.

---

### Project 7: SaaS Marketing + Pricing + FAQ Site
![Phase 6-10](https://img.shields.io/badge/After-Phase%206--10-red)

**What you'll build:** A complete marketing site — hero, features, pricing comparison table, testimonials, FAQ (using `<details>`), contact form, footer. Each page semantically distinct, all sharing a head/meta strategy. Add `Organization` and `FAQPage` JSON-LD.

**Skills practiced:** Conversion-oriented content structure, accessible pricing tables, CTA semantics, metadata strategy for SEO and social discovery.

**Stretch goal:** Build as a reusable template system. Identical document outline structure across all pages.

---

### Project 8: Real-World Audit & Refactor (Capstone)
![Capstone](https://img.shields.io/badge/Capstone-Interview%20Ready-purple)

**What you'll build:** Pick an existing public webpage (a small business site, a school site, a charity site — something flawed). Recreate and refactor its HTML to improve semantics, accessibility, SEO, and performance — without changing the visual design. Write a 1-page audit report explaining each before/after change with measurable improvements (Lighthouse before/after scores, axe issue counts).

**Skills practiced:** Code review mindset, markup quality auditing, practical remediation, professional documentation. **This is portfolio gold for any frontend interview.**

**Stretch goal:** Submit a Pull Request to the original site (if open source) or send the audit to the owner.

---

## Final Outcome Checklist (Job/Project Ready)

By the end of this roadmap, you should be able to:

- Explain HTML clearly to a beginner *and* to an interviewer
- Build complete multi-page structures without copy-pasting templates blindly
- Write semantic, accessible, and SEO-conscious markup as a default habit
- Design robust forms and content structures used in real products
- Add JSON-LD structured data and verify it in Google's tools
- Audit any HTML codebase and identify quality, accessibility, and performance issues quickly
- Pass Lighthouse 95+ on Accessibility, SEO, and Best Practices for any page you ship

If you can do all 7 confidently, you are ready to move into CSS and JavaScript with a strong foundation.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [MDN — Learn HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content) | The gold standard. Structured curriculum from Mozilla with interactive examples. Start here for any topic |
| [MDN — HTML Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) | Complete reference for every HTML element — attributes, examples, browser support |
| [web.dev — Learn HTML](https://web.dev/learn/html) | Google's modern HTML course. Covers structure, meta tags, semantic HTML with real-world focus |
| [HTML Living Standard (WHATWG)](https://html.spec.whatwg.org/) | The official spec. Use when you need the definitive answer |
| [WAI Tutorials](https://www.w3.org/WAI/tutorials/) | Official W3C accessibility tutorials for page structure, forms, tables, images |
| [Schema.org](https://schema.org/) | The vocabulary for structured data. Browse types (`Article`, `Product`, `Recipe`, `FAQPage`) |
| [Open Graph Protocol](https://ogp.me/) | Official reference for `og:*` meta tags |
| [Can I Use](https://caniuse.com/) | Browser support tables for every HTML feature |
| [Can I Email](https://www.caniemail.com/) | Email-client support tables — essential for HTML emails |

### Books & Long-form Reads

| Book | Why Read |
|------|---------|
| [HTML5 for Web Designers (Jeremy Keith)](https://html5forwebdesigners.com/) | Short, opinionated, beautifully written. The "why" behind HTML5 |
| [Inclusive Components (Heydon Pickering)](https://inclusive-components.design/) | Building accessible UI patterns from scratch |
| [Resilient Web Design (Jeremy Keith)](https://resilientwebdesign.com/) | A free online book on the philosophy of progressive enhancement |
| [HTML5 Doctor](http://html5doctor.com/) | Article archive on semantic HTML — "should I use `<section>` or `<article>`?" answered |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 100% free. Build 5 certification projects. No videos — you learn by writing code |
| [The Odin Project — HTML Foundations](https://www.theodinproject.com/paths/foundations/courses/foundations) | Open-source curriculum used by thousands. Teaches you to learn like a developer |
| [Codecademy — Learn HTML](https://www.codecademy.com/learn/learn-html) | In-browser coding with instant feedback. Best for absolute beginners |
| [Scrimba — HTML & CSS](https://scrimba.com/learn-html-and-css) | Pause any video and edit the instructor's code directly |

### YouTube (Specific Courses)

| Video / Playlist | Duration | Why Watch |
|-----------------|----------|-----------|
| [Traversy Media — HTML Crash Course](https://www.youtube.com/@traversymedia) | ~1 hour | Best first video. Covers everything a beginner needs |
| [Programming with Mosh — HTML Tutorial](https://www.youtube.com/c/programmingwithmosh) | ~1 hour | Professional instructor, clean explanations |
| [The Net Ninja — HTML & CSS Crash Course](https://www.youtube.com/@NetNinja) | Series | Step-by-step playlist, focused topics |
| [Web Dev Simplified — HTML & CSS Full Course](https://www.youtube.com/@WebDevSimplified) | ~2 hours | Beginner to intermediate in one video |
| [Kevin Powell](https://www.youtube.com/@KevinPowell) | Various | Best for HTML + CSS integration. Deep semantic and a11y dives |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — HTML](https://roadmap.sh/html) | Interactive learning path — click each topic to see resources |
| [roadmap.sh — Frontend](https://roadmap.sh/frontend) | Bigger picture — where HTML fits in the full frontend stack |

### Practice & Build Real Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional Figma designs to build. Real-world workflow. Community code reviews |
| [freeCodeCamp Projects](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 5 certification projects (Survey Form, Tribute Page, etc.) |
| [DevChallenges](https://devchallenges.io/) | Front-end projects with varying difficulty. Great for portfolio |
| [Frontend Practice](https://www.frontendpractice.com/) | Recreate real, beautifully designed websites |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [VS Code](https://code.visualstudio.com/) | Free, fast, huge ecosystem |
| [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) | Auto-refreshes the browser on save |
| [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) | Renames closing tag when you rename the opener |
| [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) | Autocompletes class names and IDs |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-formats on save |
| [Axe Accessibility Linter](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter) | Catches a11y issues in real-time |

> [!TIP]
> Install in this order: **Live Server** → **Prettier** → **Auto Rename Tag** → **Axe Linter**.

### Online Code Playgrounds

| Playground | Best For |
|-----------|---------|
| [CodePen](https://codepen.io/) | Quick experiments. Huge community |
| [JSFiddle](https://jsfiddle.net/) | Minimal interface. Great for sharing snippets |
| [CodeSandbox](https://codesandbox.io/) | Full project environment with npm |
| [StackBlitz](https://stackblitz.com/) | Runs Node.js in the browser |

### Validation, Testing & Performance Tools

| Tool | What It Checks |
|------|---------------|
| [W3C Markup Validator](https://validator.w3.org/) | Official HTML validator |
| [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/) | Built into Chrome DevTools (F12 → Lighthouse) — Performance, A11y, SEO, Best Practices scores |
| [PageSpeed Insights](https://pagespeed.web.dev/) | Lighthouse + real-world Core Web Vitals from Chrome users |
| [WebPageTest](https://www.webpagetest.org/) | Deep performance analysis. Test load times across devices and network speeds |
| [Chrome DevTools](https://developer.chrome.com/docs/devtools/) | Right-click → Inspect on any site. The #1 daily-use tool |

### Accessibility Tools

| Tool | What It Does |
|------|-------------|
| [axe DevTools](https://www.deque.com/axe/devtools/) | Browser extension; finds accessibility issues with one click |
| [WAVE](https://wave.webaim.org/) | Paste any URL — highlights every accessibility issue on the page |
| [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) | Enter two colors → see if they pass WCAG AA/AAA |
| [Coolors Contrast Checker](https://coolors.co/contrast-checker) | Beautiful UI, pass/fail for normal & large text |
| [Accessibility Insights](https://accessibilityinsights.io/) | Microsoft's a11y test suite for desktop & web |
| [The A11y Project](https://www.a11yproject.com/) | Community-driven a11y patterns and checklists |

### Meta Tags & SEO Tools

| Tool | What It Does |
|------|-------------|
| [OpenGraph.xyz](https://www.opengraph.xyz/) | Preview how your page looks on Facebook, Twitter, LinkedIn, Discord, Slack, iMessage |
| [Google Rich Results Test](https://search.google.com/test/rich-results) | Validate your JSON-LD structured data |
| [Schema.org Validator](https://validator.schema.org/) | Independent JSON-LD / Microdata / RDFa validator |
| [RealFaviconGenerator](https://realfavicongenerator.net/) | Generate favicons for every platform from one image |
| [Favicon.io](https://favicon.io/) | Quick favicons from text, emoji, or image |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [MDN HTML Cheatsheet](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Cheatsheet) | Official Mozilla quick reference with copy-paste snippets |
| [htmlcheatsheet.com](https://htmlcheatsheet.com/) | Interactive — live preview editor |
| [QuickRef.ME — HTML](https://quickref.me/html.html) | Clean, scannable layout. All common tags on one page |

---

[Back to Main Syllabus](../README.md)

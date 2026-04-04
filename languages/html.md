# HTML Syllabus

A complete, structured learning path for HTML — from writing your first tag to building accessible, SEO-friendly web pages.

![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Estimated Duration: 4-6 Weeks](https://img.shields.io/badge/Duration-4--6%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: HTML Basics](#phase-2-html-basics)
- [Phase 3: Links, Images & Media](#phase-3-links-images--media)
- [Phase 4: Lists & Tables](#phase-4-lists--tables)
- [Phase 5: Forms & User Input](#phase-5-forms--user-input)
- [Phase 6: Semantic HTML](#phase-6-semantic-html)
- [Phase 7: HTML Head & Meta Tags](#phase-7-html-head--meta-tags)
- [Phase 8: Advanced HTML](#phase-8-advanced-html)
- [Phase 9: Accessibility](#phase-9-accessibility)
- [Phase 10: Best Practices & SEO](#phase-10-best-practices--seo)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](../interviews/html.md)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> HTML requires **zero programming experience**. It's the perfect starting point for anyone entering web development.

- A computer (Windows, Mac, or Linux)
- A web browser (Chrome recommended)
- A text editor ([VS Code](https://code.visualstudio.com/) — free)
- Curiosity and willingness to practice

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what HTML is and write your first web page.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is HTML | What HTML stands for, why every website needs it, and how it fits with CSS & JavaScript |
| 2 | History of HTML | The evolution from HTML4 → XHTML → HTML5 and why HTML5 is the modern standard |
| 3 | How the Web Works | The browser-server model — what happens when you type a URL and hit Enter |
| 4 | Setting Up Your Editor | Install VS Code, enable Emmet shortcuts, open Chrome DevTools (F12) |
| 5 | HTML Document Structure | `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` — the skeleton of every page |
| 6 | Your First HTML Page | Create, save, and open an `.html` file in the browser — see your code come alive |

> [!TIP]
> In VS Code, type `!` and press Tab to instantly generate the full HTML boilerplate. This shortcut alone will save you hours.

<details>
<summary><strong>HTML Boilerplate Reference</strong></summary>

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

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain what HTML is and its role in web development
- [ ] Set up a code editor and browser dev tools
- [ ] Write and view a complete HTML page from scratch

</details>

---

## Phase 2: HTML Basics

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the fundamental building blocks of every web page.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Elements, Tags & Attributes | Opening tags, closing tags, void elements, and attribute syntax (`name="value"`) |
| 2 | Headings | `<h1>` through `<h6>` — heading hierarchy and when to use each level |
| 3 | Paragraphs & Spacing | `<p>` for paragraphs, `<br>` for line breaks, `<hr>` for horizontal rules |
| 4 | Text Formatting | `<strong>` vs `<b>`, `<em>` vs `<i>`, `<u>`, `<del>`, `<sub>`, `<sup>`, `<code>`, `<pre>` |
| 5 | Comments | `<!-- -->` — hide notes in your code that don't show on the page |
| 6 | Block vs Inline Elements | Block elements (`<div>`) take full width, inline elements (`<span>`) flow with text |
| 7 | Nesting Elements | How to properly nest tags inside each other without breaking the structure |

> [!IMPORTANT]
> `<strong>` means **semantically important** (screen readers emphasize it). `<b>` is just **visual bold**. Always prefer `<strong>` when the text is truly important.

<details>
<summary><strong>Quick Reference: Text Formatting Tags</strong></summary>

| Tag | Purpose | Example |
|-----|---------|---------|
| `<strong>` | Important text (bold) | **important** |
| `<em>` | Emphasized text (italic) | *emphasized* |
| `<mark>` | Highlighted text | highlighted |
| `<del>` | Deleted text | ~~deleted~~ |
| `<ins>` | Inserted text | underlined |
| `<sub>` | Subscript | H₂O |
| `<sup>` | Superscript | x² |
| `<code>` | Inline code | `code` |
| `<pre>` | Preformatted text | preserves spacing |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Identify HTML elements, tags, and attributes
- [ ] Use headings, paragraphs, and text formatting correctly
- [ ] Understand the difference between block and inline elements

</details>

---

## Phase 3: Links, Images & Media

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Connect pages together and add visual content.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Hyperlinks (`<a>`) | Link to other pages with `href`, open in new tabs with `target="_blank"`, anchor to page sections with `#id` |
| 2 | Email & Phone Links | Create clickable email (`mailto:`) and phone number (`tel:`) links |
| 3 | Images (`<img>`) | Add images with `src` and `alt`, set dimensions, choose between JPEG/PNG/WebP/SVG |
| 4 | Audio (`<audio>`) | Embed sound files with player controls, support multiple formats with `<source>` |
| 5 | Video (`<video>`) | Embed videos with controls, poster image, multiple format fallbacks, and captions/subtitles with `<track>` |
| 6 | File Paths | Absolute vs relative paths, navigating directories with `../`, root-relative paths |

> [!WARNING]
> Always add `rel="noopener noreferrer"` when using `target="_blank"`. Without it, the opened page can access your page via `window.opener` — a security risk.

<details>
<summary><strong>Quick Reference: Image Formats</strong></summary>

| Format | Best For | Transparency | Animation |
|--------|----------|:------------:|:---------:|
| JPEG | Photos, complex images | No | No |
| PNG | Graphics, screenshots | Yes | No |
| GIF | Simple animations | Yes | Yes |
| WebP | Modern replacement for JPEG/PNG | Yes | Yes |
| SVG | Icons, logos, illustrations | Yes | Yes |

> Use **WebP** for the best file size. Use **SVG** for icons and logos that need to scale.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create hyperlinks to external sites, internal pages, and page sections
- [ ] Add images with proper alt text
- [ ] Embed audio and video content
- [ ] Understand relative vs absolute file paths

</details>

---

## Phase 4: Lists & Tables

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Organize and display structured data.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Unordered Lists | Bullet-point lists with `<ul>` and `<li>` |
| 2 | Ordered Lists | Numbered lists with `<ol>`, `<li>`, and custom numbering (`type`, `start`) |
| 3 | Nested Lists | Lists inside lists — for menus, outlines, and hierarchical data |
| 4 | Description Lists | Key-value pairs with `<dl>`, `<dt>`, `<dd>` — great for glossaries and FAQs |
| 5 | Table Basics | Build tables with `<table>`, `<tr>`, `<td>`, and `<th>` for headers |
| 6 | Table Structure | Organize with `<thead>`, `<tbody>`, `<tfoot>`, and add titles with `<caption>` |
| 7 | Merging Cells | Span columns with `colspan` and rows with `rowspan` for complex layouts |

> [!CAUTION]
> Never use `<table>` for page layout. Tables are for **tabular data only** (like spreadsheets, schedules, comparisons). Use CSS Flexbox or Grid for layout.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create ordered, unordered, and description lists
- [ ] Build tables with headers, body, and footer sections
- [ ] Merge table cells using colspan and rowspan

</details>

---

## Phase 5: Forms & User Input

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build interactive forms to collect user data.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The `<form>` Element | `action` (where data goes), `method` (`GET` vs `POST`), and how forms submit data |
| 2 | Labels | `<label>` with `for` attribute — connects text to inputs for accessibility and UX |
| 3 | Text Inputs | `text`, `password`, `email`, `number`, `tel`, `url`, `search` — each has built-in validation |
| 4 | Date & Time Inputs | `date`, `time`, `datetime-local` — native browser date/time pickers |
| 5 | Selection Inputs | `checkbox` (multi-select), `radio` (single-select), `<select>` dropdowns, `<datalist>` autocomplete |
| 6 | File, Range & Color | `file` (uploads), `range` (sliders), `color` (color picker), `hidden` (invisible data) |
| 7 | Textarea & Buttons | `<textarea>` for multi-line text, `<button>` vs `<input type="submit">` |
| 8 | Grouping Fields | `<fieldset>` and `<legend>` — visually and semantically group related inputs |
| 9 | HTML5 Validation | `required`, `minlength`, `maxlength`, `min`, `max`, `pattern` (regex), `placeholder` |
| 10 | Input Attributes | `name`, `value`, `id`, `disabled`, `readonly`, `autofocus`, `autocomplete`, `inputmode`, `accept` — control behavior, mobile keyboards, and uploads |

> [!TIP]
> Always use `<label>` with every input. Clicking the label focuses the input — better UX for everyone, especially mobile users.

<details>
<summary><strong>Quick Reference: All Input Types</strong></summary>

| Input Type | Purpose | Example Use |
|------------|---------|-------------|
| `text` | Single-line text | Name, username |
| `password` | Hidden text | Password fields |
| `email` | Email with validation | Email address |
| `number` | Numeric input | Age, quantity |
| `tel` | Phone number | Contact number |
| `url` | URL with validation | Website link |
| `search` | Search field | Search bar |
| `date` | Date picker | Birth date |
| `time` | Time picker | Appointment time |
| `datetime-local` | Date + time | Event scheduling |
| `checkbox` | Multiple selections | Preferences |
| `radio` | Single selection | Gender, plan type |
| `file` | File upload | Profile picture |
| `range` | Slider | Volume, rating |
| `color` | Color picker | Theme color |
| `hidden` | Hidden data | Form tokens |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build a complete form with various input types
- [ ] Apply HTML5 validation (required, pattern, min/max)
- [ ] Group related fields with fieldset and legend
- [ ] Understand GET vs POST methods

</details>

---

## Phase 6: Semantic HTML

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write meaningful HTML that browsers and screen readers understand.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Semantics Matter | How semantic HTML improves accessibility, SEO, and code readability |
| 2 | `<header>` & `<footer>` | Page/section introductions and footer content (contact, copyright) |
| 3 | `<nav>` | Wrap your navigation links — tells browsers and screen readers "this is a menu" |
| 4 | `<main>` | The primary content of the page (only one per page) |
| 5 | `<section>` & `<article>` | `<section>` groups related content, `<article>` is self-contained (blog post, card) |
| 6 | `<aside>` | Sidebar content, related links, or supplementary information |
| 7 | `<figure>` & `<figcaption>` | Images, diagrams, or code with a descriptive caption |
| 8 | `<details>` & `<summary>` | Native collapsible/expandable sections — no JavaScript needed |
| 9 | Other Semantic Tags | `<time>`, `<mark>`, `<progress>`, `<meter>`, `<address>`, `<blockquote>`, `<cite>` |
| 10 | `<div>` vs Semantic Tags | When `<div>` is okay and when you should use a semantic element instead |

> [!IMPORTANT]
> Think of `<div>` as a last resort. If there's a semantic element that describes your content (`<nav>`, `<article>`, `<aside>`, etc.), always use that instead.

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
│   ┌───────────────┐ ┌────────┐  │
│   │  <article>    │ │<aside> │  │
│   │  ┌─────────┐  │ │        │  │
│   │  │<section>│  │ │        │  │
│   │  └─────────┘  │ │        │  │
│   │  ┌─────────┐  │ │        │  │
│   │  │<section>│  │ │        │  │
│   │  └─────────┘  │ │        │  │
│   └───────────────┘ └────────┘  │
├──────────────────────────────────┤
│            <footer>              │
└──────────────────────────────────┘
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Replace generic `<div>` elements with proper semantic tags
- [ ] Structure a page using header, nav, main, section, article, aside, footer
- [ ] Explain why semantic HTML improves SEO and accessibility

</details>

---

## Phase 7: HTML Head & Meta Tags

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Control how your page appears in browsers, search engines, and social media.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The `<head>` Section | What goes inside `<head>` — none of it is visible on the page, but all of it matters |
| 2 | `<title>` Tag | Sets the browser tab text and the title shown in Google search results |
| 3 | Essential Meta Tags | `charset` (encoding), `viewport` (mobile), `description` (SEO), `author`, `robots` |
| 4 | Open Graph Tags | `og:title`, `og:description`, `og:image` — control how your page looks when shared on social media |
| 5 | Twitter Card Tags | Similar to Open Graph but specifically for Twitter/X previews |
| 6 | Favicon | `<link rel="icon">` — the small icon in the browser tab |
| 7 | External Resources | `<link rel="stylesheet">` for CSS, `<link rel="preload">` for performance, `<link rel="canonical">` for SEO |
| 8 | Script Loading | `<script>` placement, `defer` vs `async` — controls when JavaScript runs relative to page loading |

> [!TIP]
> Always include these 3 meta tags in every page — they're non-negotiable:
> ```html
> <meta charset="UTF-8">
> <meta name="viewport" content="width=device-width, initial-scale=1.0">
> <meta name="description" content="Your page description here">
> ```

<details>
<summary><strong>Quick Reference: Script Loading — defer vs async</strong></summary>

| Attribute | HTML Parsing | Script Download | Script Execution |
|-----------|:----------:|:----------:|:----------:|
| `<script>` | Pauses | Downloads | Runs immediately |
| `<script defer>` | Continues | Downloads in parallel | Runs after HTML is parsed |
| `<script async>` | Continues | Downloads in parallel | Runs as soon as downloaded |

**Rule of thumb:** Use `defer` for most scripts. Use `async` only for independent scripts (analytics, ads).

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Configure essential meta tags for every page
- [ ] Set up Open Graph tags for social media previews
- [ ] Understand defer vs async for script loading

</details>

---

## Phase 8: Advanced HTML

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Explore features beyond the basics.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Iframes (`<iframe>`) | Embed external content (maps, videos), use `sandbox` for security, `loading="lazy"` for speed |
| 2 | HTML Entities & Symbols | Special characters like `&amp;`, `&lt;`, `&gt;`, `&nbsp;`, `&copy;` and numeric references |
| 3 | Data Attributes (`data-*`) | Store custom data on any element, access it in JavaScript with `element.dataset` |
| 4 | Responsive Images | `<picture>` with `<source>`, `srcset` and `sizes` — serve the right image for every screen |
| 5 | Canvas (`<canvas>`) | Draw graphics, build games, create visualizations (requires JavaScript) |
| 6 | SVG (`<svg>`) | Inline vs `<img>`, basic shapes (circle, rect, path) — always sharp at any size |
| 7 | Dialogs (`<dialog>`) | Native modal and non-modal dialogs, form submission with `method="dialog"`, and focus behavior |
| 8 | Popovers & `inert` | Declarative popovers, `popovertarget`, and temporarily making background UI non-interactive |
| 9 | HTML Templates | `<template>` and `<slot>` — reusable markup for Web Components |
| 10 | Progressive Enhancement | `hidden`, `noscript`, fallback content, and letting HTML work before JavaScript loads |

> [!WARNING]
> Always use the `sandbox` attribute on iframes to restrict what embedded content can do. Without it, embedded pages can run scripts, submit forms, and more.

<details>
<summary><strong>Quick Reference: Canvas vs SVG</strong></summary>

| Feature | Canvas | SVG |
|---------|--------|-----|
| Type | Raster (pixels) | Vector (math) |
| Scaling | Gets blurry | Always sharp |
| Performance | Better for many objects | Better for few objects |
| Interaction | Manual (JavaScript) | Built-in (DOM events) |
| Best for | Games, data visualizations | Icons, logos, charts |
| Accessibility | Poor (just pixels) | Good (DOM elements) |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Embed external content safely with iframes
- [ ] Use data attributes to store custom data
- [ ] Implement responsive images with picture and srcset
- [ ] Understand when to use Canvas vs SVG

</details>

---

## Phase 9: Accessibility

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make your web pages usable by everyone.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Why Accessibility Matters | Legal requirements, wider audience reach, and better UX for everyone |
| 2 | WCAG Principles | **Perceivable**, **Operable**, **Understandable**, **Robust** — the 4 pillars of web accessibility |
| 3 | Semantic HTML (Recap) | How using the right elements (`<nav>`, `<main>`, `<button>`) makes pages accessible by default |
| 4 | Image Accessibility | Meaningful `alt` text, decorative images (`alt=""`), long descriptions for complex images |
| 5 | ARIA Basics | `role`, `aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`, `aria-live` |
| 6 | When NOT to Use ARIA | Native HTML is always better — `<button>` beats `<div role="button">` every time |
| 7 | Keyboard Navigation | `tabindex`, focus management, skip-to-content links — your site must work without a mouse |
| 8 | Form Accessibility | Labels for every input, clear error messages, fieldset/legend for grouping |
| 9 | Language & Contrast | `lang` attribute for screen readers, color contrast ratios for readability |
| 10 | Screen Reader Testing | How to test with VoiceOver (Mac), NVDA (Windows), or ChromeVox (browser) |

> [!IMPORTANT]
> The #1 rule of ARIA: **Don't use ARIA if you can use a native HTML element instead.** A `<button>` is always better than `<div role="button">`.

<details>
<summary><strong>Quick Reference: Writing Good Alt Text</strong></summary>

| Image Type | Alt Text Approach | Example |
|-----------|-------------------|---------|
| Informative | Describe the content | `alt="Golden retriever playing fetch in a park"` |
| Functional (link/button) | Describe the action | `alt="Search"` or `alt="Go to homepage"` |
| Decorative | Leave empty | `alt=""` |
| Complex (charts/graphs) | Summarize + provide long description | `alt="Sales chart showing 30% growth in Q4"` |
| Text in image | Repeat the text | `alt="Sale: 50% off all items"` |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Apply WCAG principles to any web page
- [ ] Write effective alt text for images
- [ ] Use ARIA attributes correctly (and know when NOT to)
- [ ] Test your pages with a screen reader

</details>

---

## Phase 10: Best Practices & SEO

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write clean, performant, search-engine-friendly HTML.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Code Quality | Consistent indentation, meaningful class/ID names, proper tag nesting |
| 2 | Heading Hierarchy | Use one `<h1>` per page, follow a logical `<h2>` → `<h3>` → `<h4>` structure |
| 3 | SEO Meta Tags | Descriptive `<title>` and `<meta description>` that make Google want to show your page |
| 4 | Structured Data | Schema.org basics — help search engines understand your content (recipes, reviews, events) |
| 5 | Sitemap & robots.txt | Tell search engines what to crawl and what to skip |
| 6 | Lazy Loading | `loading="lazy"` on images and iframes — only load what the user can see |
| 7 | Preloading | `<link rel="preload">` — load critical fonts, images, and scripts early |
| 8 | DOM Performance | Minimize nesting depth, remove unnecessary wrapper `<div>`s |
| 9 | HTML Validation | Use the [W3C Validator](https://validator.w3.org/) to catch errors browsers silently ignore |
| 10 | Cross-Browser Testing | Test in Chrome, Firefox, Safari. Use [Can I Use](https://caniuse.com/) before using new features |

> [!TIP]
> Run your pages through the [W3C Validator](https://validator.w3.org/) regularly. It catches errors you won't see visually but that hurt SEO and accessibility.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Validate your HTML using W3C Validator
- [ ] Structure HTML for optimal SEO
- [ ] Optimize page load with lazy loading and preloading
- [ ] Test cross-browser compatibility

</details>

---

## Common Mistakes

Avoid these pitfalls that trip up most beginners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Skipping `alt` on images | Breaks accessibility; screen readers can't describe the image | Always add descriptive `alt` text |
| 2 | Using `<br>` for spacing | That's what CSS margin/padding is for | Use CSS for spacing between elements |
| 3 | Using headings for appearance instead of structure | Breaks document hierarchy and confuses assistive technology | Use headings to reflect content structure, then style them with CSS |
| 4 | Using `<div>` for everything | Loses semantic meaning; hurts SEO and accessibility | Use `<nav>`, `<main>`, `<section>`, `<article>`, etc. |
| 5 | Forgetting `<!DOCTYPE html>` | Browser enters "quirks mode" and renders things differently | Always start with `<!DOCTYPE html>` |
| 6 | Inline styles everywhere | Makes code unmaintainable and hard to update | Use external CSS files |
| 7 | Leaving non-void elements unclosed | Causes broken nesting and confusing markup; void elements like `<img>` do not need closing tags | Close non-void elements properly and learn which elements are void |
| 8 | Using `<table>` for layout | Tables are for data; layout should use CSS | Use CSS Flexbox or Grid for layout |
| 9 | Skipping `<label>` on forms | Inputs become unusable for screen readers and harder to click | Wrap or link every input with a `<label>` |
| 10 | Ignoring mobile viewport | Page won't scale properly on phones | Add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` |

---

## Interview Questions

For the dedicated interview-prep version, see [HTML Interview Questions](../interviews/html.md).

---

## Practice Projects

Build these projects as you progress through the syllabus:

### Project 1: Personal Bio Page
![Phase 1-2](https://img.shields.io/badge/After-Phase%201--2-green)

**What you'll build:** A simple "About Me" page with your name, photo, bio, and a list of hobbies.

**Skills practiced:** Headings, paragraphs, text formatting, images, lists.

---

### Project 2: Recipe Page
![Phase 3-4](https://img.shields.io/badge/After-Phase%203--4-green)

**What you'll build:** A complete recipe page with a hero image, ingredient list, step-by-step instructions, and a nutrition info table.

**Skills practiced:** Images, ordered/unordered lists, tables, links to sources.

---

### Project 3: Survey Form
![Phase 5](https://img.shields.io/badge/After-Phase%205-yellow)

**What you'll build:** A registration/survey form with text fields, dropdowns, radio buttons, checkboxes, and validation.

**Skills practiced:** All form elements, input types, validation attributes, fieldset grouping.

---

### Project 4: Blog Article Page
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A fully semantic blog post with header, navigation, main content with sections, sidebar, and footer. Includes proper meta tags and Open Graph data.

**Skills practiced:** Semantic elements, meta tags, Open Graph, proper heading hierarchy.

---

### Project 5: Accessible Portfolio
![Phase 8-10](https://img.shields.io/badge/After-Phase%208--10-red)

**What you'll build:** A multi-page portfolio site with responsive images, embedded content, proper ARIA attributes, and SEO optimization. Should pass W3C validation and score 90+ on Lighthouse accessibility.

**Skills practiced:** Everything from all phases — your HTML graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [MDN — Learn HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content) | The gold standard. Structured curriculum from Mozilla with interactive examples. Start here for any topic |
| [MDN — HTML Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) | Complete reference for every HTML element — attributes, examples, and browser support |
| [web.dev — Learn HTML](https://web.dev/learn/html) | Google's modern HTML course. Covers document structure, meta tags, semantic HTML with real-world focus |
| [WAI Tutorials](https://www.w3.org/WAI/tutorials/) | Official W3C accessibility tutorials for page structure, forms, tables, images, and more |
| [HTML Living Standard](https://html.spec.whatwg.org/) | The official spec. Use when you need the definitive answer on how something should work |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 100% free. Build 5 certification projects. No videos — you learn by writing code |
| [The Odin Project — HTML Foundations](https://www.theodinproject.com/paths/foundations/courses/foundations) | Open-source curriculum used by thousands. Teaches you to learn like a developer, not just follow tutorials |
| [Codecademy — Learn HTML](https://www.codecademy.com/learn/learn-html) | In-browser coding with instant feedback. Best for absolute beginners who want hand-holding |
| [Scrimba — HTML & CSS](https://scrimba.com/learn-html-and-css) | Pause any video and edit the instructor's code directly. Backed by Mozilla's MDN curriculum |

### YouTube (Specific Courses, Not Just Channels)

| Video / Playlist | Duration | Why Watch This One |
|-----------------|----------|-------------------|
| [Traversy Media — HTML Crash Course](https://www.youtube.com/@traversymedia) | ~1 hour | Best first video. Covers everything a beginner needs in one sitting |
| [Programming with Mosh — HTML Tutorial](https://www.youtube.com/c/programmingwithmosh) | ~1 hour | Professional instructor, clean explanations. Covers HTTP, formatting, images, hyperlinks |
| [The Net Ninja — HTML & CSS Crash Course](https://www.youtube.com/@NetNinja) | Series | Step-by-step playlist. Each video is one focused topic — easy to follow |
| [Web Dev Simplified — HTML & CSS Full Course](https://www.youtube.com/@WebDevSimplified) | ~2 hours | Beginner to intermediate in one video. Great for a weekend binge |
| [Kevin Powell](https://www.youtube.com/@KevinPowell) | Various | Best for HTML + CSS integration. Deep dives into semantic HTML and accessibility |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — HTML](https://roadmap.sh/html) | Interactive learning path — click each topic to see resources. Track your progress |

### Practice & Build Real Projects

| Platform | What You Get |
|----------|-------------|
| [Frontend Mentor](https://www.frontendmentor.io/) | Professional Figma designs to build. Real-world workflow. Community code reviews |
| [freeCodeCamp Projects](https://www.freecodecamp.org/learn/2022/responsive-web-design/) | 5 certification projects (Survey Form, Tribute Page, etc.) — build them to earn a certificate |
| [DevChallenges](https://devchallenges.io/) | Front-end projects with varying difficulty. Great for building a portfolio |
| [Frontend Practice](https://www.frontendpractice.com/) | Recreate real, beautifully designed websites. Learn by reverse-engineering actual sites |

### Code Editors & Extensions

| Tool | Why You Need It |
|------|----------------|
| [VS Code](https://code.visualstudio.com/) | The most popular code editor. Free, fast, huge extension ecosystem |
| [Live Server Extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) | Auto-refreshes the browser every time you save. No more manual refreshing |
| [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) | Rename an opening tag and the closing tag updates automatically. Prevents mismatched tags |
| [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) | Autocompletes class names, IDs, and CSS properties inside HTML files |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Auto-formats your HTML on save. Consistent, clean code every time |
| [Axe Accessibility Linter](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter) | Catches accessibility issues in real-time as you type. Learn a11y by doing |

> [!TIP]
> After installing VS Code, install these extensions in order: **Live Server** (see changes instantly) → **Prettier** (clean code) → **Auto Rename Tag** (fewer bugs). Add the others as you progress.

### Online Code Playgrounds

| Playground | Best For |
|-----------|---------|
| [CodePen](https://codepen.io/) | Quick experiments. Huge community — search for any HTML pattern and see live examples |
| [JSFiddle](https://jsfiddle.net/) | Minimal interface. Great for testing snippets and sharing code with others |
| [Playcode](https://playcode.io/) | Fastest live preview. AI-powered suggestions. Modern editor feel |

### Validation & Testing Tools

| Tool | What It Checks |
|------|---------------|
| [W3C Markup Validator](https://validator.w3.org/) | Official HTML validator. Paste your URL or code — it finds every error and explains the fix |
| [Can I Use](https://caniuse.com/) | Check if an HTML feature works in all browsers before using it |
| [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/) | Built into Chrome DevTools (F12 → Lighthouse tab). Scores your page on Performance, Accessibility, SEO, and Best Practices |
| [WebPageTest](https://www.webpagetest.org/) | Deep performance analysis. Test load times across different devices and network speeds |
| [Chrome DevTools](https://developer.chrome.com/docs/devtools/) | Right-click → Inspect on any website. The #1 tool every developer uses daily |

### Accessibility Tools

| Tool | What It Does |
|------|-------------|
| [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) | Enter two colors → instantly see if they pass WCAG AA/AAA contrast requirements |
| [Coolors Contrast Checker](https://coolors.co/contrast-checker) | Beautiful UI. Shows pass/fail for normal text, large text, and UI components |
| [WAVE Web Accessibility Evaluator](https://wave.webaim.org/) | Paste any URL — it highlights every accessibility issue directly on the page |
| [Accessibility Checker](https://www.accessibilitychecker.org/) | Full WCAG 2.2 compliance scan for any website. Detailed reports with fix suggestions |

### Meta Tags & SEO Tools

| Tool | What It Does |
|------|-------------|
| [OpenGraph.xyz](https://www.opengraph.xyz/) | Preview how your page looks when shared on Facebook, Twitter, LinkedIn, Discord, Slack |
| [RealFaviconGenerator](https://realfavicongenerator.net/) | Generate favicons for every platform (desktop, iOS, Android) from one image |
| [Favicon.io](https://favicon.io/) | Create favicons from text, emoji, or image in seconds. Download all sizes at once |
| [Google Rich Results Test](https://search.google.com/test/rich-results) | Check if your HTML structured data (Schema.org) will show rich results in Google |
| [Open Graph Protocol Spec](https://ogp.me/) | Official reference for og: meta tags. Bookmark this when working on Phase 7 |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [MDN HTML Cheatsheet](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Cheatsheet) | Official Mozilla quick reference with copy-paste code snippets |
| [htmlcheatsheet.com](https://htmlcheatsheet.com/) | Interactive — has a live preview editor built into the cheat sheet |
| [QuickRef.ME — HTML](https://quickref.me/html.html) | Clean, scannable layout. All common tags on one page |

---

[Back to Main Syllabus](../README.md)

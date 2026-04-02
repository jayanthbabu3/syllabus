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
- [Interview Questions](#interview-questions)
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

### Learning Outcomes
- [ ] Explain what HTML is and its role in web development
- [ ] Set up a code editor and browser dev tools
- [ ] Write and view a complete HTML page from scratch

### Topics
- What is HTML and why it matters
- Brief history of HTML (HTML4 → XHTML → HTML5)
- How the web works (browser, server, request/response)
- Setting up your environment
  - Code editor (VS Code recommended)
  - Browser developer tools (Chrome DevTools)
- HTML document structure
  - `<!DOCTYPE html>` declaration
  - `<html>`, `<head>`, `<body>` tags
  - The boilerplate template
- Writing and viewing your first HTML page

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

---

## Phase 2: HTML Basics

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the fundamental building blocks of every web page.

### Learning Outcomes
- [ ] Identify HTML elements, tags, and attributes
- [ ] Use headings, paragraphs, and text formatting correctly
- [ ] Understand the difference between block and inline elements

### Topics
- HTML elements, tags, and attributes
  - Opening tags, closing tags, self-closing tags
  - Attribute syntax (`name="value"`)
- Headings (`<h1>` through `<h6>`)
  - Heading hierarchy and when to use each
- Paragraphs (`<p>`)
- Line breaks (`<br>`) and horizontal rules (`<hr>`)
- Text formatting tags
  - Bold: `<strong>` vs `<b>`
  - Italic: `<em>` vs `<i>`
  - Underline: `<u>`
  - Strikethrough: `<s>`, `<del>`
  - Subscript: `<sub>`, Superscript: `<sup>`
  - Code: `<code>`, Preformatted: `<pre>`
- HTML comments (`<!-- -->`)
- Block-level vs inline elements
  - `<div>` (block container)
  - `<span>` (inline container)
- Nesting elements properly

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

---

## Phase 3: Links, Images & Media

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Connect pages together and add visual content.

### Learning Outcomes
- [ ] Create hyperlinks to external sites, internal pages, and page sections
- [ ] Add images with proper alt text
- [ ] Embed audio and video content
- [ ] Understand relative vs absolute file paths

### Topics
- Hyperlinks with `<a>`
  - `href` attribute (URLs, relative paths)
  - `target="_blank"` to open in new tab
  - `rel="noopener noreferrer"` for security
  - Linking to page sections with `id` anchors
  - Email links (`mailto:`) and phone links (`tel:`)
- Images with `<img>`
  - `src` and `alt` attributes
  - Width and height attributes
  - Image formats (JPEG, PNG, GIF, WebP, SVG)
- Audio with `<audio>`
  - `src`, `controls`, `autoplay`, `loop`
  - Multiple sources with `<source>`
- Video with `<video>`
  - `src`, `controls`, `poster`, `width`, `height`
  - Multiple sources with `<source>`
- File paths
  - Absolute vs relative paths
  - Parent directory (`../`)
  - Root-relative paths (`/`)

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

---

## Phase 4: Lists & Tables

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Organize and display structured data.

### Learning Outcomes
- [ ] Create ordered, unordered, and description lists
- [ ] Build tables with headers, body, and footer sections
- [ ] Merge table cells using colspan and rowspan

### Topics
- Unordered lists (`<ul>`, `<li>`)
- Ordered lists (`<ol>`, `<li>`)
  - `type` attribute (1, A, a, I, i)
  - `start` attribute
- Nested lists
- Description lists (`<dl>`, `<dt>`, `<dd>`)
- Tables
  - Basic structure: `<table>`, `<tr>`, `<td>`
  - Table headers: `<th>`
  - Table sections: `<thead>`, `<tbody>`, `<tfoot>`
  - Merging cells: `colspan`, `rowspan`
  - `<caption>` for table titles
  - When to use tables (tabular data) vs when not to (layout)

> [!CAUTION]
> Never use `<table>` for page layout. Tables are for **tabular data only** (like spreadsheets, schedules, comparisons). Use CSS Flexbox or Grid for layout.

---

## Phase 5: Forms & User Input

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Build interactive forms to collect user data.

### Learning Outcomes
- [ ] Build a complete form with various input types
- [ ] Apply HTML5 validation (required, pattern, min/max)
- [ ] Group related fields with fieldset and legend
- [ ] Understand GET vs POST methods

### Topics
- The `<form>` element
  - `action` attribute (where to send data)
  - `method` attribute (`GET` vs `POST`)
- The `<label>` element and `for` attribute
- Text inputs
  - `<input type="text">`
  - `<input type="password">`
  - `<input type="email">`
  - `<input type="number">`
  - `<input type="tel">`
  - `<input type="url">`
  - `<input type="search">`
- Date and time inputs
  - `<input type="date">`
  - `<input type="time">`
  - `<input type="datetime-local">`
- Selection inputs
  - `<input type="checkbox">`
  - `<input type="radio">`
  - `<select>` and `<option>` dropdowns
  - `<datalist>` for autocomplete suggestions
- Other inputs
  - `<input type="file">` for file uploads
  - `<input type="range">` for sliders
  - `<input type="color">` for color picker
  - `<input type="hidden">` for hidden data
- `<textarea>` for multi-line text
- Buttons
  - `<button>` element
  - `<input type="submit">`, `<input type="reset">`
- Grouping with `<fieldset>` and `<legend>`
- HTML5 form validation
  - `required` attribute
  - `minlength`, `maxlength`
  - `min`, `max`, `step`
  - `pattern` (regex validation)
  - `placeholder` text
- Common input attributes: `name`, `value`, `id`, `disabled`, `readonly`, `autofocus`

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

---

## Phase 6: Semantic HTML

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write meaningful HTML that browsers and screen readers understand.

### Learning Outcomes
- [ ] Replace generic `<div>` elements with proper semantic tags
- [ ] Structure a page using header, nav, main, section, article, aside, footer
- [ ] Explain why semantic HTML improves SEO and accessibility

### Topics
- What is semantic HTML and why it matters
  - Improved accessibility
  - Better SEO
  - Easier to read and maintain
- Page structure elements
  - `<header>` — introductory content or navigation
  - `<nav>` — navigation links
  - `<main>` — main content (one per page)
  - `<section>` — thematic grouping of content
  - `<article>` — self-contained content
  - `<aside>` — sidebar or tangentially related content
  - `<footer>` — footer content
- Content elements
  - `<figure>` and `<figcaption>` — images with captions
  - `<details>` and `<summary>` — expandable content
  - `<time>` — dates and times
  - `<mark>` — highlighted text
  - `<progress>` — progress bars
  - `<meter>` — scalar measurements
  - `<address>` — contact information
  - `<blockquote>` and `<cite>` — quotations
- When to use `<div>` vs semantic elements

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

---

## Phase 7: HTML Head & Meta Tags

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Control how your page appears in browsers, search engines, and social media.

### Learning Outcomes
- [ ] Configure essential meta tags for every page
- [ ] Set up Open Graph tags for social media previews
- [ ] Understand defer vs async for script loading

### Topics
- The `<head>` section
- `<title>` — page title (shown in browser tab)
- `<meta>` tags
  - `charset="UTF-8"` — character encoding
  - `viewport` — responsive design on mobile
  - `description` — page description for search engines
  - `keywords` — (less important for SEO today)
  - `author`
  - `robots` — search engine crawling instructions
- Open Graph meta tags (for social media sharing)
  - `og:title`, `og:description`, `og:image`, `og:url`
  - Twitter Card meta tags
- Favicon
  - `<link rel="icon">` — browser tab icon
- Linking external resources
  - `<link rel="stylesheet">` — CSS files
  - `<link rel="preload">` — preload critical resources
  - `<link rel="canonical">` — canonical URL
- `<script>` tag
  - Inline vs external scripts
  - `defer` vs `async` attributes
  - Where to place script tags

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

---

## Phase 8: Advanced HTML

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Explore features beyond the basics.

### Learning Outcomes
- [ ] Embed external content safely with iframes
- [ ] Use data attributes to store custom data
- [ ] Implement responsive images with picture and srcset
- [ ] Understand when to use Canvas vs SVG

### Topics
- Iframes (`<iframe>`)
  - Embedding external content
  - `sandbox` attribute for security
  - `loading="lazy"` for performance
- HTML entities and symbols
  - `&amp;`, `&lt;`, `&gt;`, `&nbsp;`, `&copy;`
  - Numeric character references
- Data attributes (`data-*`)
  - Custom data storage in HTML elements
  - Accessing with JavaScript (`dataset`)
- Responsive images
  - `<picture>` element with `<source>`
  - `srcset` and `sizes` attributes
  - Art direction vs resolution switching
- Canvas (`<canvas>`)
  - What it's used for (graphics, games, visualizations)
  - Basic setup (JavaScript required for drawing)
- SVG (`<svg>`)
  - Inline SVG vs `<img>` tag
  - Basic shapes (circle, rect, path)
  - When to use SVG vs raster images
- Drag and Drop API (overview)
  - `draggable` attribute
  - Drag events
- Web Storage overview
  - `localStorage` vs `sessionStorage`
  - How HTML relates to client-side storage
- HTML Templates
  - `<template>` element
  - `<slot>` element (Web Components)

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

---

## Phase 9: Accessibility

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Make your web pages usable by everyone.

### Learning Outcomes
- [ ] Apply WCAG principles to any web page
- [ ] Write effective alt text for images
- [ ] Use ARIA attributes correctly (and know when NOT to)
- [ ] Test your pages with a screen reader

### Topics
- Why accessibility matters
  - Legal requirements
  - Wider audience reach
  - Better user experience for all
- WCAG principles
  - **Perceivable** — content can be perceived by all senses
  - **Operable** — interface can be operated by all users
  - **Understandable** — content is understandable
  - **Robust** — works across assistive technologies
- Semantic HTML for accessibility (recap)
- Image accessibility
  - Meaningful `alt` text
  - Decorative images (`alt=""`)
  - Complex images (long descriptions)
- ARIA (Accessible Rich Internet Applications)
  - `role` attribute
  - `aria-label` and `aria-labelledby`
  - `aria-describedby`
  - `aria-hidden`
  - `aria-live` for dynamic content
  - When NOT to use ARIA (prefer native HTML)
- Keyboard navigation
  - `tabindex` attribute
  - Focus management
  - Skip navigation links
- Form accessibility
  - Labels for every input
  - Error messages and instructions
  - Fieldset and legend for grouping
- Language attribute (`lang`)
- Color contrast considerations
- Screen reader testing basics

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

---

## Phase 10: Best Practices & SEO

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Write clean, performant, search-engine-friendly HTML.

### Learning Outcomes
- [ ] Validate your HTML using W3C Validator
- [ ] Structure HTML for optimal SEO
- [ ] Optimize page load with lazy loading and preloading
- [ ] Test cross-browser compatibility

### Topics
- Code quality
  - Consistent indentation and formatting
  - Meaningful class and ID names
  - Proper nesting and closing of tags
- SEO fundamentals
  - Heading hierarchy (`<h1>` once per page)
  - Descriptive `<title>` and `<meta description>`
  - Structured data basics (Schema.org)
  - Sitemap and robots.txt (overview)
- Performance
  - Lazy loading images (`loading="lazy"`)
  - Preloading critical resources
  - Minimizing DOM depth
  - Reducing unnecessary wrappers
- HTML validation
  - W3C Markup Validator
  - Browser developer tools
- Cross-browser compatibility
  - Testing across browsers
  - Can I Use (caniuse.com)
  - Progressive enhancement approach

> [!TIP]
> Run your pages through the [W3C Validator](https://validator.w3.org/) regularly. It catches errors you won't see visually but that hurt SEO and accessibility.

---

## Common Mistakes

Avoid these pitfalls that trip up most beginners:

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Skipping `alt` on images | Breaks accessibility; screen readers can't describe the image | Always add descriptive `alt` text |
| 2 | Using `<br>` for spacing | That's what CSS margin/padding is for | Use CSS for spacing between elements |
| 3 | Multiple `<h1>` tags | Confuses search engines about the page topic | One `<h1>` per page, use `<h2>`-`<h6>` for subsections |
| 4 | Using `<div>` for everything | Loses semantic meaning; hurts SEO and accessibility | Use `<nav>`, `<main>`, `<section>`, `<article>`, etc. |
| 5 | Forgetting `<!DOCTYPE html>` | Browser enters "quirks mode" and renders things differently | Always start with `<!DOCTYPE html>` |
| 6 | Inline styles everywhere | Makes code unmaintainable and hard to update | Use external CSS files |
| 7 | Not closing tags | Causes unpredictable rendering and nesting issues | Close every tag (or use self-closing syntax) |
| 8 | Using `<table>` for layout | Tables are for data; layout should use CSS | Use CSS Flexbox or Grid for layout |
| 9 | Skipping `<label>` on forms | Inputs become unusable for screen readers and harder to click | Wrap or link every input with a `<label>` |
| 10 | Ignoring mobile viewport | Page won't scale properly on phones | Add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` |

---

## Interview Questions

Test your HTML knowledge with these commonly asked questions:

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What does HTML stand for?**
   - HyperText Markup Language

2. **What is the difference between an element and a tag?**
   - A tag is the markup syntax (`<p>`, `</p>`). An element is the tag plus its content (`<p>Hello</p>`).

3. **What is the purpose of the `alt` attribute in images?**
   - Provides alternative text for screen readers and displays when the image fails to load.

4. **What's the difference between `<div>` and `<span>`?**
   - `<div>` is block-level (takes full width). `<span>` is inline (takes only needed width).

5. **What are empty/void elements? Name a few.**
   - Elements that don't have closing tags: `<br>`, `<hr>`, `<img>`, `<input>`, `<meta>`, `<link>`.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What is semantic HTML? Why does it matter?**
   - Using HTML elements that clearly describe their meaning (like `<nav>`, `<article>`, `<footer>`) instead of generic `<div>`. It improves accessibility, SEO, and code readability.

2. **What is the difference between `<strong>` and `<b>`?**
   - `<strong>` indicates importance (semantic). `<b>` is just visual boldness (presentational). Screen readers emphasize `<strong>`.

3. **Explain the difference between `GET` and `POST` form methods.**
   - `GET` appends data to the URL (visible, bookmarkable, limited size). `POST` sends data in the request body (hidden, no size limit, for sensitive data).

4. **What is the `data-*` attribute used for?**
   - Storing custom data on HTML elements that can be accessed via JavaScript using `element.dataset`.

5. **What's the difference between `defer` and `async` on script tags?**
   - Both download in parallel with HTML parsing. `defer` executes after parsing is complete (in order). `async` executes immediately when downloaded (no guaranteed order).

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What are ARIA roles and when should you use them?**
   - ARIA roles define what an element is or does for assistive technologies. Use them only when native HTML elements can't provide the needed semantics (e.g., custom widgets).

2. **How do `srcset` and `sizes` work for responsive images?**
   - `srcset` provides multiple image sources with their widths. `sizes` tells the browser how wide the image will display at different viewport sizes. The browser picks the best image automatically.

3. **What is the Shadow DOM and how does it relate to `<template>`?**
   - Shadow DOM encapsulates HTML, CSS, and JS inside a component. `<template>` holds markup that isn't rendered until cloned via JavaScript, often used with Shadow DOM for Web Components.

4. **How would you optimize an HTML page for Core Web Vitals?**
   - Specify `width`/`height` on images (reduces CLS), use `loading="lazy"` on below-fold images, preload critical resources, minimize render-blocking scripts with `defer`, use semantic HTML for faster parsing.

5. **Explain the difference between `localStorage`, `sessionStorage`, and cookies.**
   - `localStorage`: persists until cleared, ~5MB, client-side only. `sessionStorage`: cleared when tab closes, ~5MB, client-side only. Cookies: sent with every HTTP request, ~4KB, can be server-side, have expiry.

</details>

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
| [W3Schools HTML Tutorial](https://www.w3schools.com/html/) | "Try It Yourself" editor on every page — great for quick experimentation |
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

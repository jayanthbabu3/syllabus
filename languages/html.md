# HTML Syllabus

A complete, structured learning path for HTML — from writing your first tag to building accessible, SEO-friendly web pages.

**Estimated Duration:** 4-6 weeks (learning part-time)

---

## Table of Contents

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
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Phase 1: Getting Started

> Understand what HTML is and write your first web page.

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

---

## Phase 2: HTML Basics

> Learn the fundamental building blocks of every web page.

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

---

## Phase 3: Links, Images & Media

> Connect pages together and add visual content.

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

---

## Phase 4: Lists & Tables

> Organize and display structured data.

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

---

## Phase 5: Forms & User Input

> Build interactive forms to collect user data.

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

---

## Phase 6: Semantic HTML

> Write meaningful HTML that browsers and screen readers understand.

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

---

## Phase 7: HTML Head & Meta Tags

> Control how your page appears in browsers, search engines, and social media.

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

---

## Phase 8: Advanced HTML

> Explore features beyond the basics.

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

---

## Phase 9: Accessibility

> Make your web pages usable by everyone.

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

---

## Phase 10: Best Practices & SEO

> Write clean, performant, search-engine-friendly HTML.

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

---

## Practice Projects

Build these projects as you progress through the syllabus:

| # | Project | Phase | Description |
|---|---------|-------|-------------|
| 1 | Personal Bio Page | Phase 1-2 | A simple page about yourself with headings, paragraphs, and text formatting |
| 2 | Recipe Page | Phase 3-4 | A recipe page with images, lists of ingredients, and step-by-step instructions |
| 3 | Survey Form | Phase 5 | A form collecting user information with various input types and validation |
| 4 | Tribute Page | Phase 6 | A tribute to someone you admire using semantic HTML elements |
| 5 | Technical Documentation | Phase 7-10 | A multi-section documentation page with navigation, code examples, and proper accessibility |

---

## Resources

### Documentation
- [MDN Web Docs — HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) — The most comprehensive and accurate HTML reference
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/) — Beginner-friendly tutorials with a "Try It Yourself" editor
- [HTML Living Standard](https://html.spec.whatwg.org/) — The official HTML specification

### Interactive Courses (Free)
- [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) — Project-based curriculum with certification
- [Codecademy — Learn HTML](https://www.codecademy.com/learn/learn-html) — Interactive lessons with in-browser coding
- [The Odin Project — HTML Foundations](https://www.theodinproject.com/paths/foundations/courses/foundations) — Open-source, community-driven curriculum
- [Scrimba — HTML & CSS](https://scrimba.com/learn-html-and-css) — Interactive video-based learning (backed by Mozilla)

### YouTube Channels
- [Traversy Media](https://www.youtube.com/@traversymedia) — Clear, practical tutorials for beginners
- [The Net Ninja](https://www.youtube.com/@NetNinja) — Well-structured HTML & CSS tutorial series
- [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified) — Concise, beginner-friendly explanations
- [Kevin Powell](https://www.youtube.com/@KevinPowell) — Deep dives into HTML and CSS

### Roadmaps
- [roadmap.sh — HTML](https://roadmap.sh/html) — Interactive learning path with progress tracking

### Practice & Challenges
- [Frontend Mentor](https://www.frontendmentor.io/) — Real-world projects with design files
- [freeCodeCamp Projects](https://www.freecodecamp.org/learn/2022/responsive-web-design/) — Certification projects to build

### Tools
- [VS Code](https://code.visualstudio.com/) — Recommended code editor
- [W3C Markup Validator](https://validator.w3.org/) — Validate your HTML
- [Can I Use](https://caniuse.com/) — Check browser support for HTML features
- [Chrome DevTools](https://developer.chrome.com/docs/devtools/) — Inspect and debug your HTML

---

[Back to Main Syllabus](../README.md)

# HTML Interview Questions

A dedicated HTML interview preparation guide with `30` commonly asked questions, including conceptual, accessibility, semantic, and practical scenario-style prompts.

**Use this with the main syllabus:** [HTML Syllabus](../languages/html.md)

---

## Table of Contents

- [How to Use This Guide](#how-to-use-this-guide)
- [Beginner Level](#beginner-level)
- [Intermediate Level](#intermediate-level)
- [Advanced + Practical Level](#advanced--practical-level)
- [How to Practice Answers](#how-to-practice-answers)
- [Back to HTML Syllabus](#back-to-html-syllabus)

---

## How to Use This Guide

- Read each question and answer it out loud before checking the sample answer.
- Rewrite at least a few answers in your own words.
- For scenario-based questions, write actual markup instead of only reading theory.
- If you can explain *why* a semantic or accessibility choice is correct, you're interview-ready.

---

## Beginner Level

1. **What is HTML and how is it different from CSS and JavaScript?**
   - HTML provides structure and meaning, CSS handles presentation, and JavaScript adds behavior and interactivity.

2. **What does `<!DOCTYPE html>` do?**
   - It tells the browser to use standards mode instead of quirks mode, which prevents old legacy rendering behavior.

3. **What is the difference between a tag, an element, and an attribute?**
   - A tag is the syntax like `<p>`. An element is the full node such as `<p>Hello</p>`. An attribute adds configuration, like `href`, `alt`, or `lang`.

4. **What are void elements? Name a few.**
   - Void elements do not have closing tags or child content. Examples: `<img>`, `<br>`, `<hr>`, `<input>`, `<meta>`, `<link>`.

5. **What is the difference between `id` and `class`?**
   - `id` should uniquely identify one element in a document. `class` can be reused across many elements for styling or grouping.

6. **What is the difference between block-level and inline elements?**
   - Block-level elements generally start on a new line and take available width. Inline elements flow within text and only take the width they need.

7. **Why is the `alt` attribute important, and when should it be empty?**
   - `alt` provides alternative text for assistive tech and broken images. Use `alt=""` only for decorative images that add no meaning.

8. **What is the difference between absolute and relative URLs?**
   - Absolute URLs include the full path and domain. Relative URLs are resolved from the current document or site root.

9. **What is the difference between `<div>` and `<span>`?**
   - `<div>` is a generic block container. `<span>` is a generic inline container. Neither carries semantic meaning by itself.

10. **What is the difference between `<strong>` and `<b>`, and `<em>` and `<i>`?**
   - `<strong>` and `<em>` carry semantic meaning. `<b>` and `<i>` are mostly presentational or alternate-voice styling elements.

---

## Intermediate Level

1. **What is semantic HTML? Why does it matter?**
   - Using HTML elements that clearly describe their meaning instead of generic containers. It improves accessibility, SEO, maintainability, and shows strong frontend fundamentals.

2. **When would you use `<section>` versus `<article>`?**
   - Use `<section>` for grouped content inside a page. Use `<article>` for self-contained content that could stand on its own, like a blog post, news item, or card.

3. **What is the purpose of `<header>`, `<nav>`, `<main>`, `<aside>`, and `<footer>`?**
   - They define common structural regions in a document so browsers, search engines, and assistive tech can understand the page layout.

4. **Why should every form input have a label?**
   - Labels improve click targets, mobile UX, and accessibility. Screen readers use them to announce what each field is for.

5. **What is the difference between `GET` and `POST` in forms?**
   - `GET` puts form data in the URL and is suited for searches or shareable/filterable state. `POST` sends data in the request body and is better for submissions that change data or include sensitive input.

6. **What is the role of the `name` attribute in form fields?**
   - `name` is the key used when form data is submitted. Without it, the control's value is generally not included in form submission payloads.

7. **What built-in HTML form validation features do you know?**
   - `required`, `minlength`, `maxlength`, `min`, `max`, `step`, `pattern`, input types like `email` and `url`, and attributes like `autocomplete`.

8. **What is the difference between `defer` and `async` on script tags?**
   - Both download scripts without blocking HTML parsing. `defer` waits until parsing finishes and preserves script order. `async` runs as soon as the file is ready and does not preserve order.

9. **What is the difference between `srcset` / `sizes` and the `<picture>` element?**
   - `srcset` and `sizes` let the browser choose the most efficient source for one image. `<picture>` gives you more explicit source control, including art direction and format switching.

10. **What is the difference between `data-*` attributes and ARIA attributes?**
   - `data-*` stores custom developer data for scripts. ARIA attributes communicate semantics and state to assistive technologies.

---

## Advanced + Practical Level

1. **When should you use native HTML instead of ARIA?**
   - As a rule, use native HTML whenever it already provides the semantics and behavior you need. A native `<button>` is better than `<div role="button">` in almost every normal case.

2. **What is the `<dialog>` element, and why is it better than many custom modal implementations?**
   - `<dialog>` is a native dialog element for modal and non-modal UI. It gives you better focus handling and built-in semantics instead of recreating modal behavior from scratch.

3. **What does the `popover` attribute solve?**
   - It gives you a declarative way to build popovers, menus, and small overlays with less custom JavaScript and better built-in behavior.

4. **What does the `inert` attribute do, and when is it useful?**
   - It makes an element subtree non-interactive and removes it from the focus order and accessibility tree. It is useful when background UI should not be reachable while a modal or overlay is active.

5. **How would you make a form field accessible when it has validation errors?**
   - Keep the field associated with a visible label, place a clear error message near it, connect help or error text using `aria-describedby` when needed, and indicate invalid state in a way both visual users and assistive tech can detect.

6. **What attributes improve mobile form usability without JavaScript?**
   - `autocomplete`, `inputmode`, appropriate input `type`, `enterkeyhint`, and `autocapitalize` can dramatically improve keyboards, autofill, and input speed on mobile devices.

7. **What head/meta/link tags are most important for SEO and sharing?**
   - A good `<title>`, useful meta description, `viewport`, canonical URL where relevant, Open Graph tags, favicon links, and structured data where appropriate.

8. **How do you embed an iframe safely?**
   - Use `sandbox` when possible, set a clear `title`, restrict features with `allow`, lazy-load when appropriate, and only embed trusted origins.

9. **Coding / Scenario: How would you mark up a blog card semantically?**
   - A strong answer usually uses `<article>` as the container, a heading like `<h2>`, an image inside `<figure>` when needed, supporting text in `<p>`, metadata with `<time>`, and a real link or button for the main action.

10. **Coding / Scenario: How would you write high-quality responsive image markup?**
   - A strong answer uses `<img>` with meaningful `alt`, explicit `width` and `height`, `loading="lazy"` when appropriate, and `srcset`/`sizes` or `<picture>` when multiple sources or art direction are needed.

---

## How to Practice Answers

- Answer each question in 30-60 seconds first.
- Then expand the tougher ones into 2-3 minute explanations.
- For semantic and accessibility questions, pair the answer with a short code sample.
- For scenario questions, write actual HTML and explain each tag choice.

---

## Back to HTML Syllabus

- [Return to HTML Syllabus](../languages/html.md)
- [Return to Main README](../README.md)

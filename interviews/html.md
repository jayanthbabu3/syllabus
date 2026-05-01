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
   - HTML defines the structure and meaning of content: headings, paragraphs, forms, links, buttons, tables, landmarks, and so on. CSS is responsible for presentation such as layout, spacing, typography, colors, and responsive behavior. JavaScript adds behavior like event handling, state updates, form logic, network calls, and dynamic UI changes.
   - In interviews, a stronger answer is that HTML is not just "content"; it is semantic structure. A `<button>` is not the same as a styled `<div>` because HTML also affects accessibility, keyboard behavior, and how browsers and search engines understand the page.

2. **What does `<!DOCTYPE html>` do?**
   - `<!DOCTYPE html>` tells the browser to render the page in standards mode instead of quirks mode. That matters because quirks mode exists for very old legacy compatibility and can change layout, sizing, and general rendering behavior in surprising ways.
   - In modern HTML, it is short and simple because it is not a version string anymore. A practical interview point is: if you forget it, the page may still render, but browser behavior can become inconsistent.

3. **What is the difference between a tag, an element, and an attribute?**
   - A tag is the markup syntax itself, such as an opening tag like `<p>` or a closing tag like `</p>`. An element is the full HTML node, including its content and attributes, for example `<p class="lead">Hello</p>`. An attribute is additional configuration on an element, such as `href`, `src`, `alt`, `lang`, `disabled`, or `required`.
   - If an interviewer pushes further, you can mention that some attributes are boolean, like `disabled`, and some values affect browser behavior, not just metadata.

4. **What are void elements? Name a few.**
   - Void elements are elements that cannot have child content and do not use closing tags. Common examples are `<img>`, `<input>`, `<br>`, `<hr>`, `<meta>`, `<link>`, and `<source>`.
   - A good interview nuance is that in HTML, these are not "self-closing" in the XML sense. Browsers will often tolerate a trailing slash like `<img />`, but the important rule is that the element is void by definition.

5. **What is the difference between `id` and `class`?**
   - An `id` should uniquely identify a single element within a document, while a `class` can be reused across many elements. `id` is commonly used for fragment links, form label associations, accessibility relationships, or targeted scripting; `class` is typically used for styling, grouping, and reusable behavior hooks.
   - Another useful point is that an element can have only one `id`, but it can have multiple classes separated by spaces.

6. **What is the difference between block-level and inline elements?**
   - Historically, block-level elements start on a new line and typically expand to fill available inline width, while inline elements flow within surrounding text and only take up the space they need. Examples are `<div>` and `<p>` for block-like behavior, and `<span>` and `<a>` for inline behavior.
   - The stronger answer is that this is the default display behavior, not the element's entire meaning. CSS can change display, so you should still choose HTML based on semantics, not just on whether it looks block or inline by default.

7. **Why is the `alt` attribute important, and when should it be empty?**
   - `alt` provides the text alternative for an image, which is used by screen readers and also appears when the image cannot load. Good `alt` text describes the image's purpose in context, not every visual detail. For example, if an image acts as a product link, the `alt` should reflect the product or action, not just "image."
   - Use `alt=""` only when the image is purely decorative and contributes no meaning. If the image is complex, like a chart, the right answer is usually short `alt` text plus a longer explanation in nearby content.

8. **What is the difference between absolute and relative URLs?**
   - An absolute URL includes the full scheme and domain, such as `https://example.com/about`, so it can be resolved from anywhere. A relative URL is resolved based on the current document or the site root, such as `about.html`, `../images/logo.png`, or `/contact`.
   - In practice, relative URLs are useful inside the same site because they are easier to move between environments, while absolute URLs are necessary for external resources and sometimes for canonical references.

9. **What is the difference between `<div>` and `<span>`?**
   - `<div>` is a generic container with block-like default behavior, and `<span>` is a generic container with inline default behavior. Neither element carries semantic meaning on its own.
   - A strong interview answer also says you should prefer semantic elements like `<section>`, `<article>`, `<nav>`, `<button>`, or `<label>` when they fit the content. Use `<div>` and `<span>` only when no more meaningful element matches the job.

10. **What is the difference between `<strong>` and `<b>`, and `<em>` and `<i>`?**
   - `<strong>` and `<em>` carry meaning: `<strong>` indicates importance, and `<em>` indicates stress emphasis that can change how text is interpreted. `<b>` and `<i>` do not usually add that semantic meaning; they are more about drawing attention or representing alternate voice, technical terms, taxonomy, idiomatic text, and similar cases.
   - The interview-ready takeaway is: use semantic elements when you mean something, and use purely visual styling through CSS when you only want a look.

---

## Intermediate Level

1. **What is semantic HTML? Why does it matter?**
   - Semantic HTML means choosing elements based on what the content is, not just how it should look. For example, use `<nav>` for navigation, `<main>` for primary page content, `<article>` for self-contained content, and `<button>` for actions.
   - It matters because semantic elements improve accessibility, help browsers build a better accessibility tree, make code easier to maintain, and give search engines clearer structural signals. In real projects, it also reduces the amount of ARIA and JavaScript you need.

2. **When would you use `<section>` versus `<article>`?**
   - Use `<section>` for a thematic grouping of related content within a page, usually with its own heading. Use `<article>` for content that is self-contained and still makes sense if it is reused elsewhere, such as a blog post, news story, forum post, or product card.
   - A helpful rule of thumb is: if the content could be syndicated, bookmarked, shared, or listed independently, `<article>` is a strong choice. If it is mainly a named subsection of a larger page, `<section>` is usually better.

3. **What is the purpose of `<header>`, `<nav>`, `<main>`, `<aside>`, and `<footer>`?**
   - These elements define major structural regions of a page. `<header>` introduces a page or section, `<nav>` contains major navigation links, `<main>` wraps the primary content of the page, `<aside>` contains complementary content like side notes or related links, and `<footer>` contains closing metadata, ownership, navigation, or related information.
   - Interviewers often want you to mention landmarks: these elements help assistive technologies navigate the page more efficiently. One nuance is that `<header>` and `<footer>` can also be used inside articles or sections, not only for the whole page.

4. **Why should every form input have a label?**
   - A label gives the form control an accessible name, which is critical for screen readers and voice technology. It also improves usability because clicking the label can focus or toggle the associated control, which is especially helpful for checkboxes, radios, and mobile users.
   - A good follow-up point is that placeholder text is not a replacement for a label. Placeholders disappear when the user types, often have poor contrast, and usually do not provide a stable accessible name.

5. **What is the difference between `GET` and `POST` in forms?**
   - `GET` appends form data to the URL, so it is visible in the address bar, browser history, bookmarks, and server logs. That makes it appropriate for searches, filters, and other read-oriented operations where shareable URLs are useful.
   - `POST` sends data in the request body, so it is better for submissions that create or change data. The important interview nuance is that `POST` is not automatically "secure"; security still depends on HTTPS, server-side validation, authentication, and proper backend handling.

6. **What is the role of the `name` attribute in form fields?**
   - The `name` attribute is the key used when form data is serialized and submitted. If an input has a value but no `name`, that value is generally not included in the form submission.
   - This is a common interview trap because people confuse `id` and `name`. `id` is useful for labels, DOM lookup, and fragment targeting; `name` is what the backend actually receives as part of the submitted form data.

7. **What built-in HTML form validation features do you know?**
   - HTML gives you built-in validation through semantic input types like `email`, `url`, `number`, and date-related fields, plus attributes such as `required`, `minlength`, `maxlength`, `min`, `max`, `step`, and `pattern`. Browsers can also expose validation state through APIs like `checkValidity()` and `reportValidity()`.
   - A complete answer should mention that client-side validation improves UX but is never enough on its own. You still need server-side validation because requests can be modified or sent outside the browser UI.

8. **What is the difference between `defer` and `async` on script tags?**
   - Both `async` and `defer` allow the browser to fetch external scripts without blocking HTML parsing during the download. `defer` waits until the document has been parsed, preserves the order of deferred scripts, and runs before `DOMContentLoaded`.
   - `async` executes as soon as the script is available, so execution order is not guaranteed. That makes `async` good for independent scripts like analytics, while `defer` is better for application code that depends on DOM structure or script order. For module scripts, defer-like behavior is the default.

9. **What is the difference between `srcset` / `sizes` and the `<picture>` element?**
   - `srcset` and `sizes` on an `<img>` help the browser choose the most appropriate file for the same image based on viewport width or device pixel density. That is mainly about responsive delivery and performance.
   - `<picture>` is more powerful because it lets you define multiple `<source>` candidates for art direction or format switching, such as serving AVIF or WebP when supported, or using a different crop on small screens. A strong answer is: use `srcset` and `sizes` when the content is the same image, and use `<picture>` when the source itself may need to change.

10. **What is the difference between `data-*` attributes and ARIA attributes?**
   - `data-*` attributes are for custom application data that your scripts may read, such as `data-user-id` or `data-state`. They do not provide accessibility semantics by themselves.
   - ARIA attributes describe roles, states, names, and relationships for assistive technologies, such as `aria-expanded`, `aria-controls`, or `aria-describedby`. A strong interview answer includes the warning that ARIA should complement native HTML, not replace it when a native element already provides the semantics and behavior you need.

---

## Advanced + Practical Level

1. **When should you use native HTML instead of ARIA?**
   - Use native HTML whenever it already provides the meaning and interaction you need. This is effectively the first rule of ARIA: if a native element or attribute already solves the problem, use that instead of recreating it with roles and states.
   - For example, a real `<button>` gives you keyboard interaction, focus behavior, semantics, and accessibility support for free. A `<div role="button">` usually requires extra JavaScript, keyboard handling, focus management, and still tends to be easier to get wrong.

2. **What is the `<dialog>` element, and why is it better than many custom modal implementations?**
   - `<dialog>` is a native element for modal and non-modal dialogs. With JavaScript methods like `.show()` and `.showModal()`, it gives you built-in semantics and a better foundation for focus management than a generic `<div>` overlay.
   - The biggest advantage is that modal dialogs opened with `.showModal()` get platform-aware behavior such as focus containment and an inert background layer. It still needs good labeling and testing, but it removes a lot of fragile custom modal code.

3. **What does the `popover` attribute solve?**
   - The `popover` attribute gives HTML a built-in way to create small overlays such as menus, teaching UI, and lightweight floating panels without writing all the open/close plumbing from scratch. It works with declarative controls like `popovertarget`, and built-in modes such as `auto` and `manual`.
   - A good answer mentions that popovers live in the top layer and support light-dismiss behavior in the appropriate mode. That means less custom JavaScript and fewer bugs around layering and dismissal behavior.

4. **What does the `inert` attribute do, and when is it useful?**
   - `inert` makes an element and its descendants non-interactive. Users cannot focus, click, or reach that subtree through normal keyboard navigation, and it is removed from the accessibility tree.
   - It is especially useful when background UI should not be reachable while an overlay or modal is active. A good nuance is that if you only need to disable one control, `disabled` is usually the better choice; `inert` is meant for larger regions.

5. **How would you make a form field accessible when it has validation errors?**
   - Start with proper basics: a visible `<label>`, the right input type, and clear instructions before the user makes a mistake. When there is an error, place the message close to the field, explain what is wrong in plain language, and make the error programmatically associated with the field using `aria-describedby` when appropriate.
   - Mark the field as invalid with `aria-invalid="true"` when the state is actually invalid, and avoid relying on color alone. For longer forms, it is also useful to provide an error summary at the top so keyboard and screen reader users can understand what needs attention.

   ```html
   <label for="email">Email address</label>
   <input
     id="email"
     name="email"
     type="email"
     aria-describedby="email-error"
     aria-invalid="true" />
   <p id="email-error">Enter a valid work email address, such as name@company.com.</p>
   ```

6. **What attributes improve mobile form usability without JavaScript?**
   - Good mobile form UX often comes from choosing the right HTML attributes, not from extra JavaScript. Important ones are the correct input `type`, `autocomplete`, `inputmode`, `enterkeyhint`, `autocapitalize`, and sometimes `spellcheck`.
   - A stronger answer includes practical examples: use `type="email"` for email addresses, `autocomplete="street-address"` or other meaningful tokens for autofill, and `inputmode="numeric"` when you want a numeric keyboard without the semantics of `type="number"`.

7. **What head/meta/link tags are most important for SEO and sharing?**
   - The most important basics are a unique, descriptive `<title>` and a useful meta description because they directly affect how pages are understood and presented in search results. For modern websites, you also usually want `meta viewport` for mobile rendering, a canonical URL when duplicate or near-duplicate pages exist, and appropriate robots directives when indexing rules matter.
   - For sharing, Open Graph tags and often Twitter/X card tags improve previews on social platforms. A stronger answer can also mention structured data, implemented through JSON-LD, when the content type benefits from rich search features.

8. **How do you embed an iframe safely?**
   - Start by only embedding trusted origins and asking whether an iframe is actually necessary. Then apply least privilege: use `sandbox` to restrict capabilities, use the `allow` attribute only for the features the embedded content genuinely needs, and add a meaningful `title` so assistive technologies can identify the frame.
   - For performance and privacy, consider `loading="lazy"` for below-the-fold frames and an appropriate `referrerpolicy` when needed. If you relax the sandbox too much, you lose most of the safety benefit, so that tradeoff is worth mentioning in interviews.

9. **Coding / Scenario: How would you mark up a blog card semantically?**
   - I would usually treat a blog card as an `<article>` because it represents a self-contained piece of content. Inside it, I would use a heading, a real link to the post, optional media with meaningful `alt` text, a summary paragraph, and publish metadata with `<time datetime="...">`.
   - If multiple cards appear in a collection, the parent wrapper might be a `<ul>` or `<section>` depending on context. The goal is to preserve structure that still makes sense when the card is read out of context.

   ```html
   <article class="blog-card">
     <a href="/posts/semantic-html">
       <img
         src="/images/semantic-html-cover.jpg"
         alt="Illustration representing semantic HTML landmarks"
         width="640"
         height="360" />
     </a>
     <header>
       <h2><a href="/posts/semantic-html">Why Semantic HTML Still Matters</a></h2>
       <p><time datetime="2026-04-01">April 1, 2026</time></p>
     </header>
     <p>Learn how better markup improves accessibility, SEO, and maintainability.</p>
   </article>
   ```

10. **Coding / Scenario: How would you write high-quality responsive image markup?**
   - High-quality responsive image markup balances accessibility, performance, and layout stability. I would always include meaningful `alt` text when the image is informative, explicit `width` and `height` to reduce layout shift, and `loading="lazy"` only when the image is not critical above the fold.
   - If the image content is the same but the file size should vary by screen, I would use `srcset` and `sizes`. If I need format switching or art direction, I would use `<picture>` with multiple `<source>` elements and a fallback `<img>`.

   ```html
   <picture>
     <source
       type="image/avif"
       srcset="/images/team-480.avif 480w, /images/team-960.avif 960w"
       sizes="(max-width: 600px) 100vw, 600px" />
     <source
       type="image/webp"
       srcset="/images/team-480.webp 480w, /images/team-960.webp 960w"
       sizes="(max-width: 600px) 100vw, 600px" />
     <img
       src="/images/team-960.jpg"
       srcset="/images/team-480.jpg 480w, /images/team-960.jpg 960w"
       sizes="(max-width: 600px) 100vw, 600px"
       alt="The product team collaborating around a whiteboard"
       width="960"
       height="640"
       loading="lazy" />
   </picture>
   ```

---

## How to Practice Answers

- Answer each question in 30-60 seconds first.
- Then expand the tougher ones into 2-3 minute explanations with tradeoffs, not just definitions.
- For semantic and accessibility questions, pair the answer with a short code sample and explain why the chosen element is better than a generic `<div>`.
- For scenario questions, write actual HTML and explain each tag choice, what screen readers get from it, and what would break if you used weaker markup.

---

## Back to HTML Syllabus

- [Return to HTML Syllabus](../languages/html.md)
- [Return to Main README](../README.md)

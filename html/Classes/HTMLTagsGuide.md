## What Are HTML Tags?

HTML **tags** are special keywords enclosed in angle brackets (`< >`) that provide **structure**, **meaning (semantics)**, or **formatting** to content on a web page.    They allow you to define where content like text, images, videos, or audio appears, what it represents (e.g., a heading or paragraph), and how it should look, enabling features like text-to-speech or search engine optimization.   

> Think of tags as instructions for the browser: "<h3> marks a main title, telling the browser 'this is a top-level heading' rather than just bold text."
> This semantic meaning matters because it helps screen readers and SEO understand content hierarchy, unlike plain formatting.  

## Tags vs Elements: Key Distinction

A **tag** is just the markup like `<h1>` (opening tag) or `</h1>` (closing tag), while an **element** is the complete unit: opening tag + content + closing tag (e.g., `<h1>Maharana Pratap</h1>`).   

- **Opening tag**: Starts the element, e.g., `<p>`.
- **Closing tag**: Ends it, e.g., `</p>`.
- **Element**: The full combo, conveying structure and meaning.  

> **⚠️ Warning/Common Misconception:** Don't confuse tags with elements—tags are the brackets; elements include the content between them. Inspecting Wikipedia shows `<h1>Maharana Pratap</h1>` as an h1 **element** with "Maharana Pratap" as content.      

This distinction builds understanding for nesting elements and debugging.

## Attributes: Adding Properties to Tags

**Attributes** are extra properties added inside opening tags (e.g., `<img src="image.jpg" alt="description">`) to provide additional instructions like location or behavior.    They appear as `key="value"` pairs and customize tags without changing their core purpose.  

- **src** (source): Specifies the file path or URL for images/links, e.g., copying a link from an image and pasting into `src="https://example.com/image.jpg"`.   
- **alt** (alternative text): Provides fallback text if the image fails to load, crucial for accessibility (screen readers read it aloud). Example: `alt="Parmesh Verma"` displays if image doesn't load.   
- **href** (hypertext reference): Defines the link destination in anchor tags, e.g., `href="https://example.com"` for external links or `#section` for bookmarks.  

Attributes make tags flexible—building on basic tags, they add functionality like linking or sourcing media.  

## Headings and Paragraphs: Basic Semantic Structure

**Heading tags** (`<h1>` to `<h6>`) create hierarchical titles, with `<h1>` for main topics and smaller numbers for subsections, conveying document outline.    Inspect Wikipedia: "Maharana Pratap" uses `<h1>`, "Early Life" uses `<h2>`.  

**Paragraph tag** (`<p>`) wraps blocks of text for readable chunks.   Example from Wikipedia: Main content sits in `<p>` elements.  

These provide **semantics**—browsers know it's a heading, aiding navigation and SEO—unlike generic bold/italic.  

```html
<h1>Maharana Pratap</h1>  <!-- Main title -->
<h2>Early Life</h2>       <!-- Subsection -->
<p>This is body text...</p>   
```
  

## Lists: Organizing Items

**Ordered lists** (`<ol>`) create numbered sequences with `<li>` (list item) children.    Wikipedia sidebar uses `<ol><li>View history</li>...</ol>` for navigation items.  

- Mechanism: `<ol>` starts the list, each `<li>` adds an item, browser auto-numbers.
- Why it matters: Conveys sequence (e.g., steps), semantics for screen readers.  

Homework: Explore **description lists** (`<dl>`, `<dt>`, `<dd>`) on MDN for key-value pairs.  

## Hyperlinks and Bookmarks with Anchor Tags

The **anchor tag** (`<a>`) creates hyperlinks via `href`.  

- External: `<a href="https://wikipedia.org">Wikipedia</a>`.
- Email: `<a href="mailto:email@example.com">Email</a>`.
- Bookmarks (internal jumps): `<a href="#section">Jump to Section</a>` links to `<h2 id="section">Section</h2>`. Wikipedia uses this for "References" jumping to bottom.   

Homework: Create bookmarks for multi-section pages to jump between areas.  

This builds navigation, essential for user experience on long pages.  

## Tables: Structuring Tabular Data

**Tables** organize data in rows and columns using `<table>`, `<tr>` (table row), `<td>` (table data/cell).   

Step-by-step creation:
1. `<table>` opens the table.
2. `<tr>` for each row.
3. `<td>` for each cell in the row.

Example (student timetable-like):
```html
<table>
  <tr>
    <td>Serial No</td>
    <td>Roll No</td>
    <td>Name</td>
  </tr>
  <tr>
    <td>1</td>
    <td>123</td>
    <td>Login</td>
  </tr>
  <!-- Repeat <tr> for more rows -->
</table>
```
    Renders as grid; styling (borders/colors) covered later.  

Copy-paste `<tr>` blocks speeds up multi-row tables—logic: consistent columns per row.   Tables matter for data like schedules, providing grid semantics.  

## Images: Embedding Visuals with img Tag

The self-closing **img tag** (`<img>`) adds images, requiring attributes.   Unlike prior tags, it uses attributes inside (no closing tag needed).  

```html
<img src="https://example.com/parmesh-verma-picture.jpg" alt="Parmesh Verma">
```
  

- **src**: Image URL/path (copy link address).  
- **alt**: Accessibility text, shows if image fails (tested by blocking load).  

Why crucial: Images enhance pages, alt ensures inclusivity for non-visual users.  

## Inline Styling with style Attribute

The **style attribute** applies CSS directly: `style="property: value"`.  

Examples:
- Background: `<h1 style="background-color: aqua;">Title</h1>` colors background aqua.  
- Text color: `<h2 style="color: brown;">Subtitle</h2>` sets text brown.  

This previews styling changes appearance instantly, bridging to full CSS. Deeper styling (classes/IDs) later.  

## Structural and Semantic Tags: Page Layout

**Structural tags** define page sections semantically, improving accessibility/SEO over `<div>`.    They overlap categories but primarily provide layout meaning (e.g., header content).  

| Tag       | Purpose/Example                          | Real-World Connection                  |
|-----------|------------------------------------------|----------------------------------------|
| `<header>`| Page/banner top (nav links, logo).   | RazorPay nav links.               |
| `<nav>`   | Navigation menus (even if possible without).   | Semantic for menus.               |
| `<main>`  | Core content area.                   | Wraps primary page body.          |
| `<aside>` | Sidebars (e.g., ads, related info).  | Dual sidebars in layouts.         |
| `<article>`| Independent content (blog post).    | Self-contained sections.          |
| `<section>`| Themed groupings (inter-dependent).  | Multi-part areas; homework: vs `<article>`.   |
| `<footer>`| Bottom info (copyright).            | Page end.                         |
| `<figure>`| Media wrappers (images).            | Photo sections.                   |

Example layout:
```html
<header><nav>Links</nav></header>
<aside>Sidebar</aside>
<main>
  <article>Post</article>
  <section>Related</section>
</main>
<footer>Copyright</footer>
```
   

Semantics convey role (e.g., screen readers announce "banner" for header), even if visually similar without.  

## Formatting Tags: Text Appearance

**Formatting tags** alter text visuals semantically:
- `<strong>`/`<b>`: Bold (emphasis vs visual).
- `<em>`/`<i>`: Italic (stress vs style).
- `<u>`: Underline.
- `<s>`: Strikethrough.
- `<sup>`/`<sub>`: Superscript/subscript.
- `<code>`: Code font.
- `<br>`: Line break.  

Use MDN for details/homework; practice renders monospace/code-like text.   

## Practice and Next Steps

Inspect sites like Wikipedia: Right-click → Inspect to see tags in action (h1/h2/p/ol/li/a/img).     Use Lorem Ipsum generators for filler text (e.g., 50 words).  

- **Homework**: Description lists (`<dl>`), bookmarks, `<article>` vs `<section>`, MDN reading.    
- **Tip**: Practice builds comfort—replicate UIs, share progress. Structural tags apply to most layouts (header/main/footer standard).   

Mastery comes from projects using only HTML tags; upcoming: forms, advanced styling.  

---

## What Are HTML Tags?

**HTML tags** are special words (markup elements) that provide **structure** (skeleton or layout description of the web page), **semantics** (meaning or significance to content like headings or paragraphs), and **formatting** (visual emphasis like bold or italic) to content on a web page, such as text or images.   

This matters because tags tell browsers, search engines, and screen readers how to interpret and display content—semantics improve accessibility and SEO, while structure organizes the page logically.   

Most visual styling (e.g., exact font sizes) is handled by CSS later, not HTML tags—HTML focuses on meaning first.   

## Categories of HTML Tags

HTML tags fall into three main types, building a complete web page:

- **Semantic tags**: Add meaning (e.g., "this is a heading" or "this implies order").
- **Structural tags**: Define page skeleton (e.g., `<header>`, `<footer>`, `<main>`, `<section>`, `<aside>`, `<article>`).  
- **Formatting tags**: Apply emphasis (e.g., bold, italic)—used sparingly for semantics, not pure visuals.  

> **💡 Key Insight:** Use semantic tags for meaning (e.g., screen readers emphasize `<strong>`), not just looks—visual differences like size come from browser defaults but convey importance levels.   

## Semantic Tags: Headings (h1 to h6)

**Heading tags** (`<h1>` to `<h6>`) create headings with decreasing importance levels—`<h1>` is most significant (largest, boldest by default), `<h6>` least.   

**Mechanism:**
1. Write opening `<h1>` and closing `</h1>`.
2. Browser auto-closes on Tab in VS Code for speed.  
3. Content inside shows as heading; e.g., `<h1>This is my first heading</h1>` renders large and bold.  

**Example in code:**
```html
<h1>This is my first heading</h1>
<h2>This is my second heading</h2>
<h3>This is my third heading</h3>
<h4>This is my fourth heading</h4>
<h5>This is my fifth heading</h5>
<h6>This is my sixth heading</h6>
```
   

**Why levels matter semantically:** `<h1>` signals top importance (use only one per page ideally for document outline); lower levels nest subtopics—search engines prioritize accordingly, not just size.   

> **⚠️ Warning:** `<h7>` or higher works without error but renders like normal text (same as `<p>`), losing semantic heading benefits—stick to h1-h6.   

**Homework:** Can you use multiple `<h1>` tags on one page? Why or why not? (Answer: Technically yes, but avoid—dilutes main topic semantics.)  

## Semantic Tags: Paragraphs and Line Breaks

**Paragraph tag** (`<p>`) wraps text into semantic blocks, adding spacing by default.  

Use **lorem generator** in VS Code: Type `lorem` + number (e.g., `lorem50`) for dummy text.   

**Line break** (`<br>`) or (`<br />`) forces new line without paragraph spacing—**self-closing tag** (no content, no closing needed).   

**Example:**
```html
<p>I read in 10th class<br>I live in Delhi</p>
<p>lorem50</p>
```
   

**Connection:** Builds on headings—paragraphs fill content under them for readable structure.  

## Semantic Tags: Anchor Links (<a>)

**Anchor tag** (`<a>`) creates hyperlinks for navigation (web, email, phone).  

**Mechanism (href attribute):**
- Website: `href="https://www.google.com"`
- Email: `href="mailto:example@email.com"`
- Phone: `href="tel:+1234567890"`

**Example:**
```html
<a href="https://www.google.com">Click here</a><br>
<a href="mailto:test@email.com">Send email</a><br>
<a href="tel:+1234567890">Call</a>
```
   

Clickable text ("Click here") links to target—must prefix "https://" or it fails.   

**Tip:** Read MDN docs for full attributes (e.g., target="_blank").  

## Semantic Tags: Lists

Lists organize items semantically—three types: unordered (`<ul>`), ordered (`<ol>`), description (homework).   

**Unordered list** (`<ul>`, `<li>`): Bulleted, random order (e.g., shopping: Maggi, Kurkure).   

**Ordered list** (`<ol>`, `<li>`): Numbered, implies sequence (e.g., tea steps: 1. Boil water, 2. Add tea, 3. Drink).   

| Feature | Unordered List (`<ul>`) | Ordered List (`<ol>`) |
|---------|------------------------|-----------------------|
| **Display** | Bullets/dots | Numbers/sequence |
| **Semantics** | Random order OK | Strict sequence matters |
| **Example Use** | Grocery items | Recipe steps |
| **Change Style** | Possible via CSS | Possible via CSS |
   

**Example code (unordered):**
```html
<ul>
  <li>Maggi</li>
  <li>Kurkure</li>
  <li>Item 3</li>
</ul>
```
  

**Key difference:** Visuals (bullets vs numbers) are CSS-changeable; semantics matter—ordered for steps, unordered for non-sequential.   

## Structural Tags Overview

Define page layout skeleton: `<header>`, `<nav>`, `<main>`, `<section>`, `<aside>`, `<footer>`, `<article>`—provide meaning like "this is the top section".   

Used with images (`<img>`), forms (`<form>`, `<input>`), tables (`<table>`, `<tr>`, `<td>`) for full structure.   

**Why?** Creates logical document outline for accessibility/SEO, beyond basic `<html>`, `<head>`, `<body>`.  

## Formatting Tags: Emphasis and Visuals

Apply inline formatting—prefer semantic versions (e.g., `<strong>` over `<b>`) for meaning (screen readers emphasize).   

| Tag | Purpose/Effect | Semantic Meaning | Example |
|-----|----------------|------------------|---------|
| `<b>` / `<strong>` | Bold | Visual / Important/strong emphasis   | `<strong>Important</strong>` |
| `<i>` / `<em>` | Italic | Visual / Stress/emphasis   | `<em>Stress</em>` |
| `<u>` | Underline | Underlined text   | `<u>Underlined</u>` |
| `<s>` | Strikethrough | Deleted/irrelevant   | `<s>Old price</s>` |
| `<sup>` | Superscript | Power/math (e.g., $$2^5$$)   | `<sup>5</sup>` → $$2^5$$ |
| `<sub>` | Subscript | Chemistry formulas (e.g., H$$_2$$O)   | `<sub>2</sub>` → H$$_2$$O |

**Code example:**
```html
<p>2<sup>5</sup> = 32</p>
<p>H<sub>2</sub>O</p>
<strong>Bold with meaning</strong> <em>Italic stress</em>
```
   

**VS Code tip:** Multi-cursor (Windows: Alt+click; Mac: Option+click) to edit multiple lines fast.   

## Preformatted Text and Best Practices

**Pre tag** (`<pre>`) preserves exact spacing/formatting (e.g., code snippets, poems)—shows as typed.   

**Example:**
```html
<pre>My name is Love Babbar
I live in Delhi</pre>
```
  

> **ℹ️ Note:** Avoid overusing formatting tags—CSS handles visuals; HTML for structure/semantics. Do homework: Experiment with description lists, tables.   

**Setup for Practice:** Create "lecture5" folder on Desktop, open in VS Code, make `index.html`, use Live Server extension.

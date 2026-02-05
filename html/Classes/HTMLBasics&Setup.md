## Introduction to HTML

### What is HTML?

HTML stands for ‘HyperText Markup Language’—but knowing the full form isn't enough. HTML is a language used to define the STRUCTURE of your web page.

* **HTML is not a programming language; it's a markup language.**  
* Its job is to identify and label different parts of a webpage—like headings, paragraphs, images, articles, lists, forms, etc.  
* Whenever you want to tell the browser “What is this?”—be it a heading, paragraph, image, or video—you define it with HTML.

### Importance of HTML

HTML is like the skeleton of a website. Just as a body cannot function without bones, a website cannot be defined without HTML. CSS and JavaScript add beauty and interactivity, but the backbone remains HTML.

---

## What Roles Do HTML, CSS, and JavaScript Play?

| Technology      | Function                                              |
|-----------------|--------------------------------------------------------|
| HTML            | Structure and labeling                                |
| CSS             | Appearance and styling                                |
| JavaScript      | Logic, interaction, and functionality                  |

Your webpage’s WHAT—meaning, what parts it contains and their roles—is decided by HTML.  
Making the website look attractive—adding colors, backgrounds, animations—is CSS.  
Adding smart functions, like buttons changing when clicked, is JavaScript.

---

## Understanding Website Structure

Look at any website:  
- It has a banner at the top  
- A navigation bar  
- Multiple headings, paragraphs, images, buttons  
- Some parts are shown as articles

Label each part separately—that’s HTML’s main job.  
Now, the question is: Where is the text? Where are images? Buttons? Articles?  
All these are identified and labeled using HTML tags.

---

## Basic Setup of HTML Coding

### Install Visual Studio Code

- Download VS Code on your Windows or Mac machine.  
- The installation process is very simple (Next, Next, Finish)—it’s a popular IDE for coding.

### Add Essential Extensions

To make coding smooth and professional, install these two extensions:  
1. **Prettier:** Automatically formats your code  
2. **Live Server:** Lets you run your code in real-time on the browser

Once installed, your environment is fully ready for coding!

---

## Create Your First Project: ‘Hello World’

### Project Steps

1. **Create a new folder—call it `Project One`**  
2. **Inside it, create a file—`index.html`**  
   - The filename can be anything, but the extension must be `.html`.  
3. **Generate a basic HTML template**  
   - In VS Code, type `!` and press Enter—this will generate a complete basic HTML structure.

### Project Folder Structure

```plaintext
Project One/
    |-- index.html
```

### Basic HTML Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="description" content="Learn Full Stack Development" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Hello World</title>
</head>
<body>
    Hello World! I am here in the world of Web!
</body>
</html>
```

---

## Introduction to HTML Elements and Tags

### Tags, Elements, and Attributes

**Tags:**  
- `<h1>`—for headings  
- `<p>`—for paragraphs  
- `<img>`—for images  
- `<article>`—to define articles  
Each tag identifies a specific part of the user interface.

**What is an Element?**  
When you combine an opening tag, content, and a closing tag, you create an element.  
For example:

```html
<h1>Hello World!</h1>
```

Here, `<h1>` is the opening tag, `Hello World!` is the content, and `</h1>` is the closing tag. All three together form the h1 element.

**Attributes:**  
Attributes provide additional information inside tags.  
For example, to specify the image source:

```html
<img src="image.jpg" alt="Description" />
```

---

## Basic Structure of an HTML Document

When creating an HTML file, it typically contains three main parts:

### 1. `<!DOCTYPE html>`

Declares the HTML version (HTML5).

### 2. `<html>` Tag

The root element—inside which all content goes.

### 3. `<head>` Tag

Contains meta-information like SEO description, page title, linked stylesheets, etc.

### 4. `<body>` Tag

Contains the main content—headings, paragraphs, images, videos—that the browser displays.

---

## Running Code with Live Server

After installing the Live Server extension in VS Code, click on 'Go Live'.  
Your webpage will open in the browser in real time.  
Every time you save your file, the browser updates automatically—making coding and previewing easy!

---

## Best Practices for HTML Coding

1. Write clean, indented code  
2. Use meaningful tags—proper headings, paragraphs, lists, articles  
3. Add comments to explain sections—improves readability

**Comments in HTML:**

```html
<!-- This is a comment which will not show on the webpage -->
```

Comments help others (and yourself) understand the code better.

---

## Trusted Resources and Documentation

### Importance of Documentation

Reading documentation is essential in web development. It helps you learn about tags, attributes, new features, and updates.

**Top Resources:**  
- [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML) (most trusted)  
- [W3Schools](https://www.w3schools.com/)  
- [Tutorials Point](https://www.tutorialspoint.com/html/index.htm)

---

## What Next in HTML?

After understanding basic tags and syntax, you will learn:  
- Formatting tags  
- Creating lists and tables  
- Inline and block elements  
- Faster coding with tools like Emmet  
- Forms and media tags (video, audio, images)  
- Advanced concepts like SEO, navigation, and design patterns

Each topic will be explained step-by-step with practical projects.

---

## Summary: What You Learned Today

- What is HTML— a markup language that defines webpage structure and labels  
- Setting up your coding environment—VS Code, Prettier, Live Server  
- Creating your first webpage—‘Hello World’  
- Basics of tags, elements, and attributes  
- Structure of an HTML document—doctype, html, head, body  
- The importance of comments and documentation

---

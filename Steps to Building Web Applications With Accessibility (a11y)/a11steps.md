Accessibility (a11y) is the practice of making web applications that are usable for people whose abilities are limited in some way, such as vision (using a screen reader) and mobility (using the keyboard only). In addition, the limitation could come from the device’s capability, such as mobile devices.

The followings are the rationales of accessibility:

- It provides equal access to everyone, including people with disabilities.
- It improves usability for a more intuitive user experience.
- It meets federal, state, and international laws to make electronic and web content accessible to people with disabilities. Violating these laws can result in loss of funds or contracts.

It takes time and effort to build up usability, and it would be important that usability is baked into the framework of web applications. In this article, we will provide ten steps on how to build web applications with accessibility.

**Step 1: Choose Semantic HTML**

Semantic HTML introduces meaning to web pages rather than just presentation. Sometimes, it is called Plain Old Semantic HTML (POSH).

The following is the semantic definition of a heading:

```
<h1>This is heading text</div>
```

Visually, it would look the same with the specified style:

```
<div style="font-size:32px;font-weight:600;">This is heading text</div>
```

However, `div `is not a correct way to implement a heading. Although it looks the same on the desktop, it will be translated incorrectly by a screen reader.

Historically, there are two common pitfalls in web development:

- Emphasize a text using `<b>` instead of `<strong`>.
- Lay out elements using `<table>` instead of CSS.

HTML5 provides us with all the semantic elements to write the markup in a meaningful way, such as `<article>`, `<details>`, `<figure>`, `<nav>`, `<section>`, and `<summary>`. Search Engine Optimization (SEO) gives more importance to the content inside these tags and makes the underlining web page more searchable.

It is recommended to use Semantic HTML, and it is also important that a web page’s HTML is semantically correct.

W3C has a website to validate the markup validity of web documents in HTML, XHTML, SMIL, MathML, etc. We can use it to make sure HTML syntaxes are used correctly.


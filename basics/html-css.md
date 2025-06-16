# HTML & CSS Guide
<< [back](../README.md)

## Introduction

This guide will help you get you started with writing semantic HTML and styling your application using CSS.
Although a full description of all HTML and CSS is outside the scope of this repository, check out online tutorials and sites such
as [W3Schools](https://www.w3schools.com/) for more in depth information.

---

## HTML

HTML stands for **HyperText Markup Language**. It is the basic structure of a webpage. It tells the browser what to show — like text, images, buttons, and more.

An HTML file is made up of **elements** — each element is like a building block of your page.

### HTML Basics

- Use tags like `<header>`, `<main>`, `<section>`, and `<footer>` to organize your page.
- These are called semantic tags — they help describe the meaning of the content.

### HTML Example

```html
<header class="site-header">
    <h1>My Web App</h1>
</header>
```

- `<header>` and `<h1>` are elements.
- The text inside `Hello World` is what you see on the page.
- Elements often come in pairs: an opening tag `<h1>` and a closing tag `</h1>`.
- The `class="site-header"` part lets us add styles using CSS.

---

## CSS

CSS stands for **Cascading Style Sheets**. It controls how your webpage looks — like colors, spacing, fonts, and layout.

CSS is often written in a separate file with a .css extension.

You can style your components using plain CSS, CSS Modules, or utility-first frameworks like [Tailwind](https://tailwindcss.com/).

### CSS Basics

You can add styles to your webpage in different ways:

- Global CSS: in files like `src/index.css` or `App.css`
- Component CSS: specific to a component (like `Button.module.css`)
- Utility Libraries: like Tailwind CSS, which gives you pre-made classes

### CSS Example

```css
h1 {
    color: blue;
}
```

### Adding New CSS

1. Create a new file like `style.css`
2. Add some CSS code:
```css
.site-header {
  background-color: #f0f0f0;
  padding: 1rem;
}
```
3. Import the CSS at the top of your component file (like `App.tsx`):
```tsx
import './style.css';
```
Now any element with `class="site-header"` will have this style.

---

## Learn More
This guide gives you the basics, but you can learn more by exploring:
- 🔗 [w3schools HTML Tutorial](https://www.w3schools.com/html)
- 🔗 [w3schools CSS Tutorial](https://www.w3schools.com/css)
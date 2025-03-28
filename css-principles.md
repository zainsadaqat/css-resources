# CSS Principles

CSS is the foundation of styling websites, and understanding CSS principles, document flow, and units is essential for creating responsive and scalable designs. Let's break down everything in a structured and digestible way.

## 🔹 Part 1: Core CSS Principles

We need to understand how CSS works behind the scenes.

### 1️⃣ CSS is a Declarative Language

You define styles for elements, and the browser applies them.

You don’t directly “draw” the UI like in Photoshop or Figma.

CSS follows a cascading structure.

### 2️⃣ The Cascade in CSS

Styles are applied based on specificity, inheritance, and source order.

The browser decides which CSS rule wins based on:

Inline Styles (Highest Priority) → style="color: red;"

IDs → #myElement { color: blue; }

Classes & Attributes → .class-name { color: green; }

Element Selectors → p { color: black; }

Universal Selector & Inherited Styles → * { margin: 0; }

👉 Best Practice: Avoid using inline styles and use classes or CSS files instead.

## 🔹 Part 2: Understanding CSS Flow

### 1️⃣ Normal Document Flow

Elements are naturally arranged from top to bottom and left to right (for LTR languages).

- Block-level elements (e.g., `<div>`, `<p>`, `<h1>`):

- Take up full width and start on a new line.

- Inline elements (e.g., `<span>`, `<a>`, `<strong>`):

- Only take up as much width as needed.

### 👉 Example of Normal Flow

```css
<p>This is a paragraph.</p>
<span>This is an inline element.</span>
```

✅ The paragraph will take the full width, while the <span> stays inline.

### 2️⃣ How to Override Normal Flow?

Use positioning (relative, absolute, fixed, sticky).

Use Flexbox or Grid to align elements.

Use float (though it's outdated for layouts).

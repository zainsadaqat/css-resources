# CSS Units

CSS has two main types of units:
- ✅ Absolute Units → Fixed values (e.g., px, cm, in)
- ✅ Relative Units → Adjust based on screen size or parent elements (e.g., em, rem, %, vh, vw)

## 1️⃣ px (Pixels) – Absolute Unit
px is a fixed-size unit based on screen resolution.

It does not scale with screen size.

Commonly used for: ✅ Borders → `border: 1px solid black;`
- ✅ Icons & Images → width: 50px;
- ✅ Fixed-width layouts (not recommended for responsive design)

👉 Restriction: Not ideal for responsive designs because it doesn't scale.

## 2️⃣ em (Relative to Parent)

1em = Size of the parent element’s font.

If a parent element has `font-size: 20px`, then `1em = 20px`.

Used for: ✅ Padding & Margin
✅ Typography (scaling text with parent elements)

### Example
```css
.container {
    font-size: 20px;
}

.child {
    font-size: 1.5em; /* 1.5 × 20px = 30px */
}
```

✅ Best Practice: Use em for spacing and typography when it should depend on the parent’s font size.

## 3️⃣ rem (Relative to Root <html> Size)
1rem = Root font size (default 16px in browsers).

Unlike em, it does not depend on the parent.

Used for: ✅ Consistent typography
✅ Layout spacing that remains predictable

```css
html {
    font-size: 16px; /* Default */
}

h1 {
    font-size: 2rem; /* 2 × 16px = 32px */
}
```

✅ Best Practice: Use rem for typography so it scales consistently across the page.

## 4️⃣ % (Relative to Parent)
100% = Same size as the parent.

Used for: ✅ Flexible containers
✅ Fluid layouts

### Example

```css
.parent {
    width: 400px;
}

.child {
    width: 50%; /* 50% of 400px = 200px */
}
```
✅ Best Practice: Use % for layouts that need to shrink and expand dynamically.

## 5️⃣ vw (Viewport Width)

1vw = 1% of the viewport width.

### Used for: 
- ✅ Full-width elements (width: 100vw;) 
- ✅ Scaling text based on screen width

### Example

```css
h1 {
    font-size: 5vw; /* 5% of viewport width */
}
```
❌ Restriction: Not ideal for fixed content because text can become too small or too large.

## 6️⃣ vh (Viewport Height)

1vh = 1% of the viewport height.

### Used for: 
- ✅ Making full-height sections
- ✅ Sticky/fixed elements

✅ Best Practice: Use vh for full-screen sections but avoid using it inside scrollable elements.

## Best Practices for CSS Units

✅ Use rem for Typography
Ensures text scales properly for accessibility.

✅ Use % for Flexible Layouts
Adapts to parent containers without hardcoding widths.

✅ Use vw & vh for Full-Screen Sections
Perfect for hero sections & backgrounds.

✅ Avoid Fixed px for Layouts
Can cause responsive issues on different screen sizes.

## 🚀 Final Challenge for You!

Try creating a fully responsive card component using:

- ✅ rem for typography
- ✅ % for layout widths
- ✅ vh for full-height sections
- ✅ vw for hero text



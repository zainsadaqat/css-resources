# Media Query in CSS 

CSS media queries allow you to make your website responsive, meaning it adjusts based on different screen sizes, devices, or specific conditions (like screen resolution, color scheme, or orientation).

A media query in CSS applies styles only when a specified condition is met. For example, you can change the font size when the screen width is less than 600px:

```css
@media (max-width: 600px) {
  body {
    font-size: 14px;
  }
}
```

## 🔹 Basic Syntax of Media Queries

```css
@media media-type and (media-feature) {
  /* CSS styles here */
}
```

- media-type (optional): Defines the type of device (like screen, print, all).
- media-feature: Specifies the condition (like max-width, orientation, resolution).
- and, not, only: Logical operators for combining conditions.

## 🔹 Types of Media Queries

### 1️⃣ Based on Screen Width (Common Use)

#### 👉 Mobile First (Recommended Approach)

Start with mobile styles by default, then apply styles for larger screens:

```css
/* Default styles (for mobile) */
body {
  font-size: 14px;
}

/* Tablet */
@media (min-width: 768px) {
  body {
    font-size: 16px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  body {
    font-size: 18px;
  }
}
```

✅ Better performance (loads faster on mobile).
✅ Easier maintenance.

#### 👉 Desktop First (Alternative Approach)

Start with desktop styles, then override them for smaller screens:

```css
/* Default styles (for desktop) */
body {
  font-size: 18px;
}

/* Tablet */
@media (max-width: 1024px) {
  body {
    font-size: 16px;
  }
}

/* Mobile */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

### 2️⃣ Based on Device Type

You can target different device types:

```css
@media screen {
  /* Styles for screens (default) */
}

@media print {
  /* Styles for printing */
}

@media speech {
  /* Styles for screen readers */
}
```

#### 🔹 Example: Hide navigation bar in print mode

```css
@media print {
  .navbar {
    display: none;
  }
}
```

### 3️⃣ Based on Orientation

Portrait (vertical screen) or landscape (horizontal screen):

```css
@media (orientation: portrait) {
  body {
    background-color: lightblue;
  }
}

@media (orientation: landscape) {
  body {
    background-color: lightgreen;
  }
}
```

### 4️⃣ Based on Resolution (Retina & HD Screens)

```css
@media (min-resolution: 2dppx) {
  body {
    background-image: url("high-res-image.png");
  }
}
```

- 1dppx = Normal display
- 2dppx = Retina display (Apple)
- 3dppx = Ultra HD display

### 5️⃣ Based on Dark Mode (Color Scheme)

```css
@media (prefers-color-scheme: dark) {
  body {
    background-color: black;
    color: white;
  }
}
```

## 🔹 Combining Multiple Conditions

You can combine multiple conditions with logical operators:

### 👉 Using and (Both conditions must be true)

```css
@media screen and (min-width: 600px) and (max-width: 900px) {
  body {
    background-color: yellow;
  }
}
```

### 👉 Using or (Comma ,)

```css
@media (max-width: 600px), (orientation: portrait) {
  body {
    background-color: red;
  }
}
```

### 👉 Using not (Excluding a condition)

```css
@media not (max-width: 600px) {
  body {
    background-color: blue;
  }
}
```

## 🔹 Best Practices for Media Queries

✅ Use Mobile-First Approach (Start with smaller screens).
✅ Use Relative Units (em, %, rem instead of px).
✅ Limit the Number of Breakpoints (3-5 is ideal).
✅ Use CSS Grid & Flexbox instead of too many media queries.

## 🔹 Common Breakpoints (Industry Standard)

Here are the most commonly used screen sizes:

Device Type Breakpoint (Width)
Small Mobile max-width: 480px
Mobile (default) max-width: 768px
Tablet min-width: 768px and max-width: 1024px
Laptop min-width: 1024px and max-width: 1440px
Desktop min-width: 1440px

## 🔹 Real-World Example (Responsive Layout)

```css
/* Default (Mobile) */
.container {
  display: flex;
  flex-direction: column;
}

/* Tablet */
@media (min-width: 768px) {
  .container {
    flex-direction: row;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .container {
    justify-content: space-between;
  }
}
```

### 📌 This ensures:

✅ Mobile: Stacks items vertically.
✅ Tablet: Arranges items horizontally.
✅ Desktop: Aligns items with space between.

✔ Media Queries make websites responsive by applying styles based on screen width, device type, resolution, and more.
✔ Mobile-First Approach is recommended for better performance.
✔ Use min-width for scaling up (mobile first) and max-width for scaling down (desktop first).
✔ Combine conditions using and, or, not for advanced styling.

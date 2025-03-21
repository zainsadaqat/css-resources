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

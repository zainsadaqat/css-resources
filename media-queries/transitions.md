# Transitions and Animations

## 📌 What You’ll Learn in This Guide
- ✅ What transition and transform are
- ✅ How to use them effectively
- ✅ Where to apply them for best results
- ✅ Common mistakes and restrictions
- ✅ Modern trends and best practices

By the end, you’ll be able to create smooth, professional-looking animations that make your UI feel modern and interactive! 🎨✨

## 1️⃣ Understanding transition – Smoothly Changing Properties

### What is transition

The transition property smooths changes between one CSS state and another. Without transition, style changes happen instantly.

#### Syntax
```css
element {
    transition: property duration timing-function delay;
}
```

- 🔹 property → The CSS property you want to animate (e.g., opacity, width, background-color).
- 🔹 duration → How long the animation takes (0.5s, 1s, etc.).
- 🔹 timing-function → Controls speed variation (ease, linear, ease-in, etc.).
- 🔹 delay (optional) → Adds a wait time before animation starts (1s, 0.2s, etc.).

### 🛠 Example: Smooth Background Color Change

```css
button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    border: none;
    transition: background-color 0.3s ease-in-out;
}

button:hover {
    background-color: red;
}
```
✅ When the user hovers over the button, it smoothly changes from blue to red over 0.3s.

### 🔹 What Properties Can You Transition?
- ✅ opacity, background-color, width, height, transform, border-radius, box-shadow
- ❌ Cannot transition: display, visibility, position, z-index, grid-template-columns

### 🔹 transition-timing-function - Control the Speed Curve
- 🔹 ease → Starts slow, speeds up, then slows down (default).
- 🔹 linear → Moves at a constant speed.
- 🔹 ease-in → Starts slow, then speeds up.
- 🔹 ease-out → Starts fast, then slows down.
- 🔹 ease-in-out → Starts slow, speeds up, then slows down.
- 🔹 cubic-bezier(x, y, x2, y2) → Custom speed curve.

```css
.box {
    width: 100px;
    height: 100px;
    background: blue;
    transition: width 1s ease-in-out;
}

.box:hover {
    width: 300px;
}
```

## 2️⃣ Understanding transform – Moving & Scaling Elements

The transform property modifies an element’s shape, position, or rotation without affecting its normal flow.

### Syntax

```css
element {
    transform: transform-function(value);
}
```

### Transform Functions

#### Transform Functions

1. Function: `translate(x, y)`	-> What It Does: Moves an element	-> Example: `transform: translate(50px, 20px);`
2. Function: `scale(x, y)`	-> Resizes an element	-> Example: `transform: scale(1.5);`
3. Function: `rotate(deg)`	-> Rotates an element	-> Example: `transform: rotate(45deg);`
4. Function: `skew(x, y)`	-> Tilts an element	-> Example:	`transform: skew(10deg, 5deg);`
5. Function: `matrix(a, b, c, d, e, f)`	-> Example: Combines transformations	Rarely used

## 3️⃣ Combining transition & transform – Next Level Animations

### 🚀 Example: Smooth Card Hover Effect

```css
.card {
    width: 200px;
    height: 300px;
    background: white;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-10px);
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
}
```
✅ Real-world use case: Makes cards feel lightweight and interactive.

## 4️⃣ Advanced: animation – Full Control

If you need looping or more complex effects, use @keyframes animations.

### Example: Bouncing Button

```css
@keyframes bounce {
    0% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0); }
}

button {
    animation: bounce 0.5s infinite alternate;
}
```

✅ The button bounces up and down infinitely.

## 5️⃣ Modern Trends in CSS Animations (2025)

- ✅ Microinteractions → Small animations that enhance UX (e.g., buttons, loaders).
- ✅ Glassmorphism & Neumorphism → Smooth shadow transitions for realistic UI effects.
- ✅ Scroll-based animations → Animations triggered by scrolling (@scroll-timeline).
- ✅ AI-powered animations → Tools like GSAP & CSS Houdini give more control.
- ✅ Reduced motion for accessibility → Use @media (prefers-reduced-motion: reduce) to respect users' preferences.

### Example: Scroll Animation
```css
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

.reveal {
    opacity: 0;
    animation: fadeIn 1s ease-out forwards;
}
```
✅ Use JavaScript to trigger .reveal class on scroll.

## 🚀 Best Practices for Smooth Animations

- ✅ Use will-change for performance (will-change: transform;)
- ✅ Limit animations to opacity & transform (GPU-accelerated)
- ✅ Avoid animating width, height, and position (causes reflow)
- ✅ Use requestAnimationFrame() in JavaScript for smooth animations
- ✅ Test animations on mobile (Check prefers-reduced-motion)

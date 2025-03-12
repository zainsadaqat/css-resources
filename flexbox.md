# Flexbox

Flexbox (Flexible Box Layout) is a CSS layout model that makes it easier to design responsive and dynamic layouts. It allows elements to be arranged efficiently, even when their sizes are unknown or dynamic.

## Flexbox works on a parent-child relationship

- The container (parent) has display: flex;, which enables flex behavior.
- The items (children) inside the container adjust according to flex properties.

## 1. Flex Container Properties 🏗️

These properties are applied to the parent (flex container).

### 1.1 display: flex

This property enables the flexbox layout and makes all direct children flex items.

#### Example
```css
.container {
  display: flex;
}
```

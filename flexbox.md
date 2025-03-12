# Flexbox

Flexbox (Flexible Box Layout) is a CSS layout model that makes it easier to design responsive and dynamic layouts. It allows elements to be arranged efficiently, even when their sizes are unknown or dynamic.

## Flexbox works on a parent-child relationship

- The container (parent) has `display: flex;` which enables flex behavior.
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

### 1.2 flex-direction

Defines the main axis along which the items are placed.

#### Value	Description
- row (default)	Items align horizontally (left to right)
- row-reverse	Items align horizontally (right to left)
- column	Items align vertically (top to bottom)
- column-reverse	Items align vertically (bottom to top)

#### Example
```css
.container {
  display: flex;
  flex-direction: column;
}
```

#### Use Case
Used when designing vertical navigation menus or sidebars.

### 1.3 justify-content
Aligns items along the main axis.

#### Value	Description
- flex-start (default)	Items align to the start of the main axis
- flex-end	Items align to the end of the main axis
- center	Items align in the center of the main axis
- space-between	Items are spread out with space in between
- space-around	Items have equal space around them
- space-evenly	Items have equal space between and around them

#### Example

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

#### Use Case
Used in navigation bars where items need to be evenly distributed.

### 1.4 align-items
Aligns items along the cross axis (perpendicular to the main axis).

#### Value	Description
- stretch (default)	Items stretch to fill the container height
- flex-start	Items align at the start of the cross axis
- flex-end	Items align at the end of the cross axis
- center	Items align at the center of the cross axis
- baseline	Items align based on their text baseline

#### Example

```css
.container {
  display: flex;
  align-items: center;
}
```

#### Use Case
Used in the vertical centering of items inside a section.

### 1.5 align-content
Aligns multiple rows (only works when `flex-wrap: wrap;` is used).

#### Value	Description
- stretch (default)	Rows stretch to fill the container height
- flex-start	Rows align at the start of the container
- flex-end	Rows align at the end of the container
- center	Rows align at the center of the container
- space-between	Rows are spread out with no extra space at edges
- space-around	Rows have equal space around them

#### Example

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: space-between;
}
```
#### Use Case
Used in grids and multi-line layouts.

### 1.6 flex-wrap
Controls whether flex items wrap to the next line.

#### Value	Description
- nowrap (default)	Items stay in one line, shrinking if needed
- wrap	Items wrap onto the next line if necessary. The second row appears below the first row.
- wrap-reverse	Items wrap in reverse order. The second row appears above the first row.

#### Example

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

#### Use Case
Used in responsive layouts where items need to wrap on smaller screens.


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

## 2. Flex Item Properties 📦

These properties are applied to child items inside the flex container.

### 2.1 flex-grow
Defines how much a flex item can grow relative to others.

#### Value	Description
- 0 (default)	Item does not grow
- 1+	Item grows based on available space

#### Example

```css
.item {
  flex-grow: 1;
}
```
#### Use Case

Used in responsive layouts where some elements need to expand dynamically.

### 2.2 flex-shrink
Defines how much a flex item can shrink relative to others.

#### Value	Description
- 1 (default)	Item shrinks if needed
- 0	Item does not shrink
#### Example
```css
.item {
  flex-shrink: 0;
}
```

#### Use Case
Used when an item should not shrink, like a logo in a navbar.

### 2.3 flex-basis

Sets the initial size of a flex item before it grows/shrinks.

#### Value	Description
- auto (default)	Size depends on content
- px, %, rem, etc.	Fixed size

#### Example:

```css
.item {
  flex-basis: 200px;
}
```
#### Use Case
Used in grid-based layouts where elements have predefined sizes.

### 2.4 flex (Shorthand)

Shorthand for flex-grow, flex-shrink, and flex-basis.

#### Value	Equivalent
- flex: 1;	flex-grow: 1; flex-shrink: 1; flex-basis: 0;
- flex: 0 1 auto;	Default value

#### Example

```css
.item {
  flex: 1;
}
```
#### Use Case
Used for equal-width layouts.

2.5 order
Defines the order of flex items.

#### Value	Description
- 0 (default)	Normal order
- 1+	Higher numbers appear later
- -1	Negative numbers appear earlier

#### Example

```css
.item {
  order: -1;
}
```
#### Use Case
Used to rearrange content for mobile-first designs.

### 2.6 align-self

Overrides align-items for a specific item.

#### Value	Description
- auto (default)	Inherits from align-items
- flex-start	Aligns to the start of the cross axis
- flex-end	Aligns to the end of the cross axis
- center	Aligns to the center
- baseline	Aligns to text baseline
- stretch	Stretches to fill

#### Example

```css
.item {
  align-self: center;
}
```

#### Use Case
Used when only one item needs different alignment.



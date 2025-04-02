# CSS Grid                
 
- we can use gap property once display is set to grid
- Use `gap` property instead of margin e.g., `gap: 1.5rem`

One of the hardest thing to do while using the Grid might be to decide how many columns we are gonna need. we can decide that by checking the number of boxes we might have if the design is already there.

`grid-template-columns` property is used to decide the number of columns in grid container. it is applied on the parent property.

```css
display: grid;
grid-template-columns: 1fr 1fr 1fr; /* divide equal amount of space between each column OR */
grid-template-columns: repeat(3, 1fr) /* means 3 columns with equal amount of space */
```
we don't need to create row explicitly because by setting columns to 3 will automatically create a second row for us. we don't need to create the complexity.


## Let's talk about grid-template-columns

```css
grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
```

- repeat(auto-fill, minmax(250px, 1fr)) creates as many columns as can fit in the container.
- Each column has a minimum width of 250px (so they don’t get too narrow).
- If there’s extra space, columns stretch up to 1fr (filling remaining space evenly).
- This keeps your grid responsive, automatically wrapping into new rows when columns no longer fit.

### 1. repeat(...)

Tells the grid to create repeated columns (or rows) based on the pattern you specify.

### 2. auto-fill

Automatically creates as many columns as will fit in the container, wrapping onto new rows when necessary.

### 3. minmax(...)

Sets a minimum and maximum size for each grid track (column or row).

#### For example

minmax(250px, 1fr) means:
- Don’t go smaller than 250px,
- But grow up to fill remaining space (1fr).

#### Another Quick Example

```css
.grid-container {
  display: grid;
  /* Create columns that are at least 200px and stretch to fill space */
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}
```
This creates a responsive grid where each column is at least 200px wide but can expand to fill extra space, and new columns wrap as needed.

### What is 1fr?

fr stands for “fraction” unit in CSS Grid.
1fr means “take up one fraction of the available space.”

### Can we use 2fr or 0.5fr?

Yes, you can use any fraction value like 2fr, 3fr, or 0.5fr.
For example, 2fr means “twice as much space” as 1fr in the same grid.

One fraction of available space” means that after any fixed-width columns (like 100px) are accounted for, the remaining free space in the container is split into fractions. If a track is defined as 1fr, it gets exactly one share of that leftover space.

For example, if you have 2 columns defined as 1fr and 2fr and there are 300px of free space:
- The 1fr column gets 100px (1 share).
- The 2fr column gets 200px (2 shares).

Think of the container’s width as a pie you’re slicing up.

- If you say `grid-template-columns: 1fr 1fr 1fr;`, you’re cutting the pie into 3 equal slices. Each slice is “1 fraction” of what’s left after any fixed-sized columns.

- If you say `grid-template-columns: 2fr 1fr;`, you’re cutting the pie into 3 total slices (2 for the first column, 1 for the second), so the first column gets twice as much space as the second.

In other words, 1fr is “one share” of whatever space remains, 2fr is “two shares,” etc. The browser adds up all the fr values and divides leftover space among them proportionally.

## Grid Column Span

```css
.grid-col-span-2 {
  grid-column: span 2; /* it's shorthand property for grid-column-start and grid-column-end */
}
```

```css
grid-row-start: 1;
grid-row-end: 3;
/* or we can use shorthand property for that it does the same job and it is applied on the child property */
grid-row: 1 / 3; 
```

```css
/* when we have complex layout then we use grid-template-areas approach */
'one two three four'
'five six seven eight';
/* in the above, we have two rows with 4 columns something like 8 boxes in 2 rows

```
## Recommended Approach
```css
.parent {
display: grid;
gap: 1.5rem;
grid-auto-columns: 1fr; /* gives equal size columns */
grid-template-areas: 
'one one two five' 
'three four four five';
}
.child:nth-child(1) { grid-area: one; }
.child:nth-child(2) { grid-area: two; }
.child:nth-child(3) { grid-area: three; }
.child:nth-child(4) { grid-area: four; }
.child:nth-child(5) { grid-area: five; }
.child:nth-child(6) { grid-area: six; }
```

 
> with min-width defined, the css without media queries will be used for the mobile size and code written inside the min-width block will be used for the desktop or tablet size screens etc.


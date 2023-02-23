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

```css
.parent {
display: grid;
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


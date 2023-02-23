# CSS Grid

- we can use gap property once display is set to grid
- Use `gap` property instead of margin e.g., `gap: 1.5rem`

One of the hardest thing to do while using the Grid might be to decide how many columns we are gonna need. we can decide that by checking the number of boxes we might have if the design is already there.

`grid-template-columns` property is used to decide the number of columns in grid container.

```css
display: grid;
grid-template-columns: 1fr 1fr 1fr; <!-- divide equal amount of space between each column OR -->
grid-template-columns: repeat(3, 1fr) <!-- means 3 columns with equal amount of space -->
```
we don't need to create row explicitly because by setting columns to 3 will automatically create a second row for us. we don't need to create the complexity.

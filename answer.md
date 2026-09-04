## Practical III – Quick Check Answers

### Q1
All 5 pages update because they all link to the same external stylesheet. If only an inline style was used on index.html, only that page would change because inline styles have higher specificity.

### Q2
`#welcome` (id selector) is more specific than `h1` (element selector). If both set colour, `#welcome` wins because id selectors have higher specificity.

### Q3
`#0369a1` = `rgb(3, 105, 161)`. Designers prefer hex because it's more compact (6 characters vs 11 for rgb) and easier to copy from design tools.

### Q4
`display: none` removes the element completely from layout (other elements shift to fill the space). `visibility: hidden` makes it invisible but it still occupies space (other elements don't shift).

### Q5
**Phone:** 1 card stacked vertically. **Desktop:** 3 cards side-by-side using `col-md-4` grid.

### Q6
`styles.css` must be linked AFTER Bootstrap so your custom styles can override Bootstrap's defaults. If reversed, Bootstrap would load last and override your styles, so if both set an `h1` colour, Bootstrap's colour would win.
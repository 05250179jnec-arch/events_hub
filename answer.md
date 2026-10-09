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

## Practical IV

**Q1. If validate.js runs before main.js and calls a function only defined in main.js, what error appears?**
A `ReferenceError` appears in the Console, for example
`Uncaught ReferenceError: seatsMessage is not defined`.
Scripts run from top to bottom, so when validate.js runs first, main.js has not
loaded yet and its functions do not exist. That is why main.js must be loaded first.

**Q2. What happens if you use document.write after the page has loaded? Why is innerHTML safer?**
The whole page was erased and only the text I wrote ("oops") was left.
document.write after load replaces the entire document. innerHTML is safer
because it only changes the content inside one chosen element and leaves
the rest of the page alone.

**Q3. Click Clear, then Cancel. Does the form clear? Which line stops it?**
No, the form did not clear; my text stayed in the boxes.
`confirm("Clear the whole form?")` returned false when I clicked Cancel, so the
line `e.preventDefault();` inside bindRegisterExtras() ran and stopped the
browser's normal reset action.

**Q4. What error do you get for console.log(b)? What does it say about let? What is typeof null?**
The error was `Uncaught ReferenceError: b is not defined`.
This shows that `let` is block-scoped: a variable made with let only exists
inside the { } block where it was created, while `var a` leaked outside the block.
`typeof null` returns "object", which is a well-known historical bug in JavaScript.

**Q5. Change Inter-College Football seats from 0 to 5 and reload. What happens to the card and the Register button?**
The card was no longer faded and the title was no longer crossed out.
The grey "Sold out" badge changed to a green "5 seats" badge, the message
changed to "Filling fast!", and a Register button appeared.
This happens because eventCardHtml() checks `ev.seats === 0` to decide
if an event is sold out, so the card is built from the data in the events array.

**Q6. What do seatsMessage(0) and seatsMessage(12) return?**
`seatsMessage(0)` returned "Sold out" and `seatsMessage(12)` returned "Filling fast!".
For 0, neither `seats > 20` nor `seats > 0` is true, so it returns "Sold out".
For 12, `seats > 20` is false but `seats > 0` is true, so it returns "Filling fast!".

**Q7. Submit with an empty email. Which line stops the browser leaving the page? What would happen without e.preventDefault()?**
The line `e.preventDefault();` inside validateForm() in validate.js stops the
browser leaving the page, so I stayed and saw "Invalid email".
Without it, the browser would submit the form as normal and reload/navigate
away, so the error messages would disappear before the user could read them.

**Q8. Is document.querySelectorAll("nav a") a NodeList or an HTMLCollection? Does forEach work on it?**
It is a NodeList; the Console shows `NodeList(5)`.
Yes, forEach works on it in modern browsers. Running
`document.querySelectorAll("nav a").forEach(a => console.log(a.textContent))`
printed all 5 link names (Home, Events, Register, Gallery, Contact).
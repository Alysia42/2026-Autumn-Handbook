# Lab — Polka Dottys 🎨

## What You'll Make

Create some simple point-and-click art by spawning a polka dot wherever you click! You'll build up an interactive canvas where every click leaves a colourful dot — and by the end, you'll have the foundations of a digital pointillism painting tool.

---

## Learning Goals

By the end of this lab you will be able to:

- Switch p5.js into event-driven mode using `noLoop()`
- Spawn shapes in response to mouse clicks with `mousePressed()`
- Use `random()` to vary size and colour
- Respond to keyboard input with `keyPressed()`
- Work with p5.js colour values using `color()`, `red()`, `green()`, and `blue()`

---

## Background

### Two Modes: Video vs. Event-Driven

So far we've used p5.js in **video mode** — `draw()` runs 60 times per second like frames in a film, and we animate by changing things each frame.

In this lab we're switching to a different approach: **event-driven mode**. Instead of continuously redrawing, the sketch only changes when something happens — a mouse click, a key press, an event.

To stop the draw loop, call `noLoop()` inside `setup()`:

```js
function setup() {
  createCanvas(500, 500);
  background(255);
  noLoop();  // draw() will not loop — we're in event-driven mode
}
```

> 💡 We're not going to use the `draw()` function in this lab at all. Changes happen only when the user does something!

### Key Functions

| Function | When it runs |
|---|---|
| `mousePressed()` | Once, every time the mouse button is clicked |
| `keyPressed()` | Once, every time a key on the keyboard is pressed |

### Working with Colour

| Function | What it does | Example |
|---|---|---|
| `color(r, g, b)` | Creates a colour value you can store in a variable | `let c = color(255, 0, 0)` |
| `fill(c)` | Applies a stored colour as the fill | `fill(c)` |
| `red(c)` | Extracts the red channel from a colour | `red(c)` → `255` |
| `green(c)` | Extracts the green channel | `green(c)` |
| `blue(c)` | Extracts the blue channel | `blue(c)` |
| `random(min, max)` | Returns a random number between min and max | `random(0, 255)` |

---

## Part 1 — Polka Dots

### Step 1 — Set Up Event-Driven Mode

Start with this skeleton. Notice there is no `draw()` function — we won't need it:

```js
function setup() {
  createCanvas(500, 500);
  background(255);
  noLoop();
}

function mousePressed() {
  // PUT YOUR CODE HERE
}
```

---

### Step 2 — Spawn a Dot on Click

Inside `mousePressed()`, draw a circle where the mouse is:

```js
circle(mouseX, mouseY, 40);
```

Click around the canvas. A dot should appear wherever you click!

> 💡 Because we used `noLoop()`, the background is only drawn once in `setup()`. Old dots aren't erased — they stay on the canvas permanently. That's exactly what we want!

---

### Step 3 — Vary the Size

Make each dot a random size by replacing the fixed diameter with `random()`:

```js
let minSize = 20;
let maxSize = 80;
circle(mouseX, mouseY, random(minSize, maxSize));
```

Click around — each dot should now be a different size!

---

### Step 4 — Vary the Colour

Write a helper function that picks and applies a random colour, then call it before drawing each dot:

```js
function mousePressed() {
  randomColour();
  noStroke();  // remove the outline if you don't like it
  circle(mouseX, mouseY, random(20, 80));
}

function randomColour() {
  fill(random(0, 255), random(0, 255), random(0, 255));
}
```

- [ ] Click lots of dots — do you like fully random colours, or is it a bit chaotic?
- [ ] Try limiting the random range (e.g. `random(100, 255)`) to get pastel tones.

---

## Part 2 — Pointillism Extension

You realise these colourful polka dots remind you of **pointillism** — an art style where dots of different colours are placed close together to form a painting. Let's expand your tool to make something more intentional!

### Step 1 — Change Base Colour with Number Keys

Add a global `baseColour` variable and a `keyPressed()` function that changes it when the user presses a number key:

```js
let baseColour;

function setup() {
  createCanvas(500, 500);
  background(255);
  baseColour = color(0, 0, 0);  // start with black
  noLoop();
}
```

```js
function keyPressed() {
  if (key === '1') {
    baseColour = color(255, 0, 0);      // red
  } else if (key === '2') {
    baseColour = color(0, 68, 170);     // blue
  } else if (key === '3') {
    baseColour = color(255, 214, 0);    // yellow
  } else if (key === '4') {
    baseColour = color(34, 139, 34);    // green
  } else {
    print('Controls: 1 = red, 2 = blue, 3 = yellow, 4 = green');
  }
}
```

> 💡 If the user presses a key that isn't listed, `print()` sends a helpful message to the console — a handy way to guide the user!

---

### Step 2 — Show the Currently Selected Colour

Draw a small reference dot in a corner of the canvas so the user can always see which colour is active. Update it every time the colour changes:

```js
function showSelectedColour() {
  // Draw with a black outline so the reference dot is always visible
  stroke('black');
  strokeWeight(2);
  fill(baseColour);
  circle(470, 470, 40);

  // Switch back to no outline for polka dots
  noStroke();
}
```

Call `showSelectedColour()` at the end of both `setup()` and `keyPressed()` so it always stays up to date.

---

### Step 3 — Add Colour Variance to Each Dot

Instead of fully random colours, add a small random offset to the channels of `baseColour`. This keeps dots recognisably in the right colour family while adding natural variation:

```js
function mousePressed() {
  let variance = 40;  // how much each channel can vary

  let r = red(baseColour)   + random(-variance, variance);
  let g = green(baseColour) + random(-variance, variance);
  let b = blue(baseColour)  + random(-variance, variance);

  noStroke();
  fill(r, g, b);
  circle(mouseX, mouseY, random(20, 80));

  showSelectedColour();  // redraw reference dot on top
}
```

Try painting a scene using different colours in different areas — a blue sky, a green field, a yellow sun!

---

## Challenge Activity

Go further with your pointillism tool:

- [ ] Add more colour keys (5, 6, 7...) for a richer palette
- [ ] Add a key (e.g. `c`) that clears the canvas back to white — use `background(255)` and redraw the reference dot
- [ ] Make dots near the edges of the canvas smaller, and dots near the centre larger
- [ ] Add a key that toggles between round dots and square dots (`rect()` vs `circle()`)

---

## Key Takeaways

- `noLoop()` stops the `draw()` loop — useful when you only want changes on user input.
- `mousePressed()` and `keyPressed()` are event functions that run exactly once per interaction.
- Storing colours in a variable with `color()` lets you reuse and modify them later.
- `red()`, `green()`, and `blue()` extract individual channels from a colour — perfect for adding variance while staying on-theme.
- `print()` is a handy debugging and feedback tool — messages appear in the console.

---

## Reference

- [p5.js reference — `noLoop()`](https://p5js.org/reference/p5/noLoop/)
- [p5.js reference — `mousePressed()`](https://p5js.org/reference/p5/mousePressed/)
- [p5.js reference — `keyPressed()`](https://p5js.org/reference/p5/keyPressed/)
- [p5.js reference — `color()`](https://p5js.org/reference/p5/color/)
- [Pointillism on Wikipedia](https://en.wikipedia.org/wiki/Pointillism)
- [p5.js web editor](https://editor.p5js.org)

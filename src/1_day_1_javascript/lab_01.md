# Shapes & the Canvas

## What You'll Learn

By the end of this lab you will be able to:

- Understand how the p5.js canvas coordinate system works
- Use `setup()` and `draw()` to structure a sketch
- Draw basic shapes: rectangles, ellipses, lines, and triangles
  
## Background

Every p5.js sketch has two core functions:

```js
function setup() {
  // Runs once when the sketch starts
  createCanvas(400, 400);
}

function draw() {
  // Runs continuously 60 times per second
  background(220);
}
```

The canvas is a grid of pixels. The **top left corner is (0, 0)**. X increases to the right, Y increases downward.

```
(0,0) ──────────────▶ x
  │
  │
  │
  ▼
  y
```

---

## Common Shape Functions

| Function | What it draws |
|---|---|
| `rect(x, y, width, height)` | Rectangle — x/y is the top left corner |
| `ellipse(x, y, width, height)` | Ellipse — x/y is the centre |
| `line(x1, y1, x2, y2)` | A straight line between two points |
| `triangle(x1,y1, x2,y2, x3,y3)` | Triangle with three corner points |
| `circle(x, y, diameter)` | Circle — x/y is the centre |
| `point(x, y)` | A single dot |

---

## Exercises

### Exercise 1 — Hello Canvas

Create a new sketch and paste this starter code:

```js
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```

Run it. You should see a grey square. This is your canvas!

> 💡 `background(220)` fills the canvas with a grey colour. Try changing `220` to `0` (black) or `255` (white).

---

### Exercise 2 — Draw Some Shapes

Add the following shapes inside `draw()`, below `background(220)`:

```js
// A rectangle
rect(50, 50, 100, 80);

// An ellipse
ellipse(250, 100, 120, 80);

// A line
line(0, 200, 400, 200);

// A circle
circle(200, 300, 90);
```

**Questions to think about:**
- What happens if you change the numbers?
- Why does the line go all the way across?
- Where is the centre of the canvas? (Hint: the canvas we made is 400×400.)

---

### Exercise 3 — Build a Simple Face

Using only basic shapes, draw a simple face on the canvas. Your face should include:

- [ ] A head (ellipse or circle)
- [ ] Two eyes (circles or ellipses)
- [ ] A nose (line or triangle)
- [ ] A mouth (ellipse, arc, or line)

There is no single correct answer — make it your own!

**Starter hint:**

```js
// Head
ellipse(200, 200, 180, 200);

// Left eye
circle(160, 170, 30);

// Right eye (add this yourself!)

// Nose (add this yourself!)

// Mouth (add this yourself!)
```

---

### Exercise 4 — Challenge: A Simple Scene

Draw a simple outdoor scene using only shapes. It could include:

- A sky and ground (`rect` for both)
- A sun or moon (`circle`)
- A house (rectangle + triangle for the roof)
- A tree (rectangle trunk + circle top)

Try to use **at least 8 shapes** in total.

---

## Reference

- [p5.js reference — 2D Primitives](https://p5js.org/reference/#group-2D%20Primitives)
- [p5.js web editor](https://editor.p5js.org)

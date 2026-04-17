# Lab — Recreating Mondrian-Style Paintings 🟥🟦🟨

## What You'll Make

In this exercise, you'll recreate the style of Piet Mondrian, an abstract artist known for paintings made strictly using straight black lines, rectangles, and primary colours. By the end, you will have your very own abstract digital painting in p5.js!

---

## Learning Goals

By the end of this lab you will be able to:

- Practise drawing rectangles with `rect()`
- Set fill colours with `fill(r, g, b)`
- Set outline colours with `stroke()`
- Change line thickness with `strokeWeight()`
- Place shapes using x and y coordinates

---

## Background

Piet Mondrian was a Dutch artist who developed a style called **Neoplasticism** — paintings built entirely from horizontal and vertical black lines, filled with blocks of red, blue, yellow, and white. This style translates almost perfectly into p5.js code!

### Functions You'll Need

| Function | What it does | Example |
|---|---|---|
| `rect(x, y, w, h)` | Draws a rectangle. x/y is the top-left corner | `rect(50, 50, 200, 150)` |
| `fill(r, g, b)` | Sets the fill colour using RGB values | `fill(255, 0, 0)` |
| `stroke(r, g, b)` | Sets the outline colour | `stroke(0, 0, 0)` |
| `strokeWeight(n)` | Sets the outline thickness in pixels | `strokeWeight(6)` |
| `noStroke()` | Removes the outline entirely | `noStroke()` |

### Mondrian's Colour Palette

| Colour | RGB values |
|---|---|
| Red | `fill(214, 0, 0)` |
| Blue | `fill(0, 68, 170)` |
| Yellow | `fill(255, 214, 0)` |
| White | `fill(240, 240, 240)` |
| Black (for lines) | `stroke(0, 0, 0)` |

---

## Exercise

### Step 1 — Set Up the Canvas

Start with this sketch:

```js
function setup() {
  createCanvas(500, 500);
  // This painting doesn't need to animate
  noLoop();
}

function draw() {
  background(240);

  // black outlines
  stroke(0);
  // thick lines
  strokeWeight(8);

}
```

Run it. You should see a plain grey canvas which is ready to paint!

---

### Step 2 — Add Your First Rectangle

Inside `draw()`, add a coloured rectangle:

```js
fill(214, 0, 0);
rect(0, 0, 200, 200);
```

> 💡 The order matters — set `fill()` and `stroke()` **before** calling `rect()`.

---

### Step 3 — Build the Composition

Add more rectangles to fill the canvas. Think of the canvas as a grid divided by thick black lines. Below is an example:
```js
// Red block
fill(214, 0, 0);
rect(0, 0, 200, 180);

// Blue block
fill(0, 68, 170);
rect(280, 300, 220, 200);

// Yellow block
fill(255, 214, 0);
rect(200, 0, 300, 120);

// White fill blocks
fill(240, 240, 240);
rect(0, 180, 200, 320);
rect(200, 120, 300, 180);
rect(200, 300, 80, 200);
```

> 💡 Don't worry about getting it perfect straight away. Play around with the numbers until it looks balanced!

---

### Step 4 — Refine Your Composition

Look at your painting so far. Consider:

- [ ] Are the coloured blocks spread out, or all clustered together?
- [ ] Do the thick black lines divide the canvas clearly?
- [ ] Is there a good balance of colour vs. white space?

Move your rectangles around, resize them, and keep tweaking until you're happy with the result.

---

## Extension Tasks

Once your basic composition is working, push it further:

- [ ] Add at least **6 rectangles** total, and **3 coloured sections**
- [ ] Make your composition balanced and interesting. Think about how you can manipulate the size and position of your rectangles to create visual tension!

---

## Challenge Activity

Make a **random Mondrian generator**, where the colours are randomised each time the program is run. Keep in mind you're still constrained to red, blue, yellow, and white!

**Hint:** Store the colour options in an array and pick from it randomly:

```js
// Define the Mondrian palette
let palette = [
  [214, 0, 0],
  [0, 68, 170],
  [255, 214, 0],
   // more white to make it more common
  [240, 240, 240],
  [240, 240, 240],
  [240, 240, 240],
];

// Pick a random colour from the palette
let c = random(palette);
fill(c[0], c[1], c[2]);
```

Click **Run** a few times. Does it produce interesting compositions every time?

---

## Reference

- [p5.js reference — `rect()`](https://p5js.org/reference/p5/rect/)
- [p5.js reference — Color](https://p5js.org/reference/#group-Color)
- [Mondrian-style Painting Examples](https://galeriemontblanc.com/en/blogs/articles/what-are-the-8-most-beautiful-abstract-paintings-by-piet-mondrian)

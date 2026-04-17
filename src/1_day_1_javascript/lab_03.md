# Lab — Bouncing Ball Activity

**Difficulty:** Beginner  
**Time:** ~30 minutes  
**Topics:** `draw()`, `mousePressed()`, `mouseDragged()`, `mouseReleased()`, velocity, gravity

---

## What You'll Make

In this exercise, you'll create a sketch of a ball that is affected by gravity, which the user can drag with the mouse. By the end, you will have an interactive physics simulation built entirely in p5.js!

---

## Learning Goals

By the end of this lab you will be able to:

- Use variables to simulate velocity and gravity
- Update position each frame to create movement
- Detect mouse interaction with a shape
- Control behaviour using a boolean flag

---

## Background

### Simulating Gravity with Velocity

Real gravity accelerates objects downward — it doesn't just move them, it speeds them up over time. We can simulate this with two variables:

| Variable | What it represents |
|---|---|
| `y` | The ball's vertical position on the canvas |
| `vy` | The ball's vertical **velocity** — how fast it's moving up or down |

Each frame, we:
1. Increase `vy` by a small `gravity` value (speeding up the fall)
2. Add `vy` to `y` (moving the ball by its current speed)

```js
vy += gravity;  // accelerate downward
y += vy;        // move the ball
```

### Bouncing

When the ball hits the bottom of the canvas, we reverse its velocity and reduce it slightly so the bounce loses energy over time:

```js
if (y > height - size / 2) {
  y = height - size / 2;  // stop it going through the floor
  vy *= bounce;            // bounce is -0.8, so this flips and weakens vy
}
```

### Mouse Interaction Functions

| Function | When it runs |
|---|---|
| `mousePressed()` | Once, the moment the mouse button is clicked |
| `mouseDragged()` | Every frame the mouse moves while the button is held |
| `mouseReleased()` | Once, the moment the mouse button is released |

### Checking if the Mouse is on the Ball

`dist(mouseX, mouseY, x, y)` returns the distance between the mouse and the ball's centre. If that distance is less than the ball's radius, the mouse is on the ball:

```js
if (dist(mouseX, mouseY, x, y) < size / 2) {
  // mouse is inside the ball!
}
```

---

## Provided Code

Start with this skeleton — **do not change anything outside the marked sections**:

```js
let x = 200;
let y = 200;

let vy = 0;

let gravity = 0.5;
let bounce = -0.8;

let size = 50;

let dragging = false;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);

  // PUT YOUR CODE HERE

  circle(x, y, size);
}

function mousePressed() {
  // PUT YOUR CODE HERE
}

function mouseDragged() {
  // PUT YOUR CODE HERE
}

function mouseReleased() {
  // PUT YOUR CODE HERE
}
```

---

## Requirements

### Gravity and Movement

Add code inside `draw()` to make the ball fall:

- [ ] Each frame, increase `vy` by `gravity`
- [ ] Each frame, update `y` using `vy`

### Bouncing

Still inside `draw()`, add code to make the ball bounce:

- [ ] When the ball hits the bottom of the canvas, flip the direction of `vy` and reduce how strong it is using the `bounce` variable

### Dragging

Add code to the mouse functions to handle dragging:

- [ ] In `mousePressed()` — if the mouse is on the ball, set `dragging` to `true`
- [ ] In `mouseDragged()` — if `dragging` is `true`, update `x` and `y` to follow the mouse
- [ ] In `mouseReleased()` — set `dragging` to `false`
- [ ] In `draw()` — only apply gravity when `dragging` is `false`

---

## Hints

> 💡 Use `dist(mouseX, mouseY, x, y)` to check if the mouse is on the ball.

> 💡 The `dragging` boolean tracks whether the ball is being dragged — check it before applying gravity.

> 💡 When the ball hits the floor, make sure you also reset `y` to the edge of the canvas, otherwise the ball can get stuck below it.

---

## Extension Tasks

Once the ball is working, try these additions:

- [ ] Style the ball — add a colour, gradient effect, or face using shapes
- [ ] Add a horizontal velocity `vx` so the ball also drifts sideways when released after dragging
- [ ] Add left and right wall bouncing using the same logic as the floor bounce
- [ ] Add friction — reduce `vx` slightly each frame so the ball slows down over time

---

## Challenge Activity

Add a **trail effect** behind the ball as it moves. The trail should fade out behind the ball and disappear when the ball is being dragged.

**Hint:** Try removing `background(220)` from `draw()` and instead using a semi-transparent background to create a fading trail:

```js
background(220, 40);  // low alpha = old frames fade slowly
```

---

## Key Takeaways

- Velocity (`vy`) changes position each frame; gravity changes velocity each frame — this creates realistic acceleration.
- Multiplying velocity by a negative number less than 1 (like `-0.8`) reverses and weakens it — simulating an energy-losing bounce.
- Boolean variables like `dragging` are great for toggling between two modes of behaviour.
- `mousePressed()`, `mouseDragged()`, and `mouseReleased()` let you respond to different stages of a mouse interaction.

---

## Reference

- [p5.js reference — `mousePressed()`](https://p5js.org/reference/p5/mousePressed/)
- [p5.js reference — `dist()`](https://p5js.org/reference/p5/dist/)
- [p5.js web editor](https://editor.p5js.org)

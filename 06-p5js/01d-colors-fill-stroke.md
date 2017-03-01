# Colors, `fill`, `stroke`, `background`

Now that you know how to draw shapes, let's add some color!


![jake paints](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/jake.gif)

Start with this code in your `sketch.js` file to make a black and white line drawing of an apple.

```javascript
function setup() {
  createCanvas(640, 480);
}

function draw() {
  ellipse(150, 150, 160, 160);
  rect(145, 40, 10, 30);
  quad(145, 70, 120, 60, 110, 45, 125, 50);
}
```

![apple](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/blankApple.png)

To fill in the shapes with color we will use a function called `fill`.

## `fill`

`fill` can take **3 arguments**. These arguments are the **Red**, **Green**, and **Blue** color values in a **range from 0 to 255**.  This works exactly the same way the RGB color system works in CSS, all 3 of the colors combined at the maximum value of `255` would produce white. All 3 values at `0` is the absence of any color, so that produces black. We combine varying amounts of Red, Blue, and Green to result in any color in between.

![rgb](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/rgb.gif)

To paint the apple a nice, rich red we can call the `fill` function at the beginning of `draw` with `200` for the red value, and `0` for blue and green.

```javascript
fill(200, 0, 0);
```
![all red apple](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/all-red-apple.gif)

Hmm... All of the shapes became red. Close, but not quite what we want to see.

 p5 sees that the `fill` is set once to a red color and then uses that color to fill *all shapes that are drawn below it*. We'll definitely need to call `fill` more than once in our code.

By calling `fill` again *further down in the code* we can change the value for any shapes that come *after* that call to the `fill` function.

#### 🔔🔑💡 Tip 💡🔑🔔
> Your code is always read by your computer from **top to bottom**. Keeping this in mind will be helpful when you are making more complex programs.

Try this in your `draw` function:

```javascript
function draw() {
  fill(200, 0, 0);
  ellipse(150, 150, 160, 160);

  fill(150, 120, 0)
  rect(145, 40, 10, 30);

  fill(0, 225, 0);
  quad(145, 70, 120, 60, 110, 45, 125, 50);
}
```
![filled apple](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/filled-apple.png)

Nice! 🍎

Say we wanted to take a bite out of this apple.  This can be done by drawing a small white circle on top of and overlapping the red circle. For a shape to be 'on top', the function that draws it simply needs to come further down in the code. This is because, again, all your code is read one line at a time from the top to the bottom.

Here's where we want to place the ellipse:

```javascript
 ellipse(220, 120, 60, 60);
```

Watch the gif below closely.

![take a bite](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/apple-bite.gif)

You probably noticed a few important things:

First, the new ellipse originally was green. This is because the last time `fill` was called was for the green leaf.

Next, you may have thought that to make the circle white the code would look like `fill(255, 255, 255);`, and that code would totally work! Though instead, what was written was `fill(255);`

This is because `fill` can also be called with *1 argument*. The p5 library provides more than one way to use the `fill` function. The 1-argument-way is a shortcut, it means make all 3 arguments, the R, G, and B values, the same. `fill(255, 255, 255);` and `fill(255);` result in the same thing. *Any time you call `fill` with 1 argument the color you will see will be black, white, or some shade of gray*. Since red, blue, and green are all present in exactly equal amounts they cancel each other out.

The only problem remaining is how to remove the black outline around our shape. The function that controls this outline is called `stroke`.

## `stroke`

`stroke` can take either 3 arguments, or 1 argument to determine the color of the outline. It works exactly like `fill`.  

There are some additional functions we can use to modify the stroke.

`strokeWeight` takes one argument, the width of the outline in pixels. We've so far seen shapes with the default weight of 1 pixel.

`noStroke` takes no arguments. It can be called to get rid of the stroke entirely. Remember that even though it takes no arguments, parentheses are still required for us to instruct the computer to *call* a function.  You must therefore write `noStroke()` for it to take effect.

Let's put it all together.

```javascript
function draw() {
  stroke(0);
  strokeWeight(1);
  fill(200, 0, 0);
  ellipse(150, 150, 160, 160);

  fill(150, 120, 0);
  rect(145, 40, 10, 30);

  stroke(50, 150, 0);
  strokeWeight(2);
  fill(0, 225, 0);
  quad(145, 70, 120, 60, 110, 45, 125, 50);

  noStroke();
  fill(255);
  ellipse(220, 120, 60, 60);
}
```
![finished bite](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/apple-bite-stroke.png)

## Mini-Challenge

 1. On a new canvas, draw at least three different shapes with three different colors.  Experiment with changing the Red, Green, and Blue values to produce different colors.  How do you make a yellow color?

 2. You've seen a method like `fill` or `stroke` called with 1 argument and with 3 arguments. One more way these functions can be used is to supply an additional *4th argument*.  This should be a number between 0 and 100 that signifies how opaque or transparent the color should be. This is sometimes referred to as the **alpha** of the color. `0` signifies total transparency (it would be invisible) and `100` represents a totally opaque color (not see-through at all).  Add some transparency to your shapes above. Make two transparent shapes overlap.

 3. Now that you're an expert on color and opacity, use the code above that created the apple to add a gleam of light on the apple and make it rest on a colored countertop. The result should look something like this:

 ![final apple](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/finished-apple.png)

 The `background` function may be helpful here. It takes the same arguments `fill` and `stroke` do, but remember there is always the documentation!

## Resources

- [`background` Documentation](https://p5js.org/reference/#/p5/background)
- [`fill` Documentation](https://p5js.org/reference/#/p5/fill)
- [`stroke` Documentation](https://p5js.org/reference/#/p5/color)

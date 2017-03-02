# The `map` function

Imagine that you were making a thermometer program that showed temperatures between 0 and 100 degrees fahrenheit. As the temperature slides up toward 100 degrees you want the background to be solid red and a temperature of 0 degrees should be solid blue. In between should be shades of purple.

![temp slider](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/temp.gif)

## Using `map`

Let's start out with something a bit simpler. As we move the mouse from left to right let's make the background change from white to black.

![b/w fade](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/fade.gif)

So if we started to build this, as `mouseX` goes from `0` on the left to the full `width` of the canvas on the right (let's say the canvas width is `600`), the background color should go from `0`, black, to `255`, white.

There are 2 ranges of values here:

- `0` to `600`
- `0` to `255`

We could think about doing some complicated math to *map* every value in one range to a value in the range of the other. But this is exactly what `map` is for. It saves us from doing this complicated math!

Map takes 5 arguments.

```javascript
map(__, __, __, __, __);
```

The 2nd and 3rd arguments are the *starting point* and *ending point* of the first range. In our case, `0` and `600`.

```javascript
map(__, 0, 600, __, __);
```

The 4th and 5th arguments are the *start* and *end* values of the second range. So, `0` and `255`.

```javascript
map(__, 0, 600, 0, 255);
```

The first argument is the value we want to map. Here that's `mouseX` because it's `mouseX` that is changing in the range of `0` to `600`.

```javascript
map(mouseX, 0, 600, 0, 255);
```

Awesome, store the result of this in a variable and that's it!

```javascript
function setup() {
  createCanvas(600,400);
}

function draw() {
  var c = map(mouseX, 0, 600, 0, 255);
  background(c);
}
```

## Two `maps`

Now let's try to use `map` for the red and blue values of the background color.

Our first attempt might be something like this:

```javascript
function setup() {
  createCanvas(600,400);
}

function draw() {
  var red = map(mouseX, 0, width, 0, 255);
  var blue = map(mouseX, 0, width, 0, 255);
  background(red, 0, blue);
}
```

But that doesn't quite work.

![purple fade](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/purple-fade.gif)

Think about our blue color range for a second.  The closer the mouse is to `0` in the x-axis the closer our blue value should be to `255`.  So we actually need to flip the *starting* and *ending* values for our range.

Paste in this code for the variable `blue`

```javascript
var blue = map(mouseX, 0, width, 255, 0);
```

Nice, that should work!

## Mini-Challenge

```javascript
var sunSize = 400;

function setup() {
  createCanvas(400,400);
  frameRate(15);
}

function draw() {
 background(0);

 noStroke();
 fill(245, 180, 80);
 ellipse(width/2, height/2, sunSize, sunSize);


 if (sunSize > 0) {
  sunSize -= 1;
 }
}
```

The code above will make a large orange circle slowly shrink to nothing.

*Notice that the frameRate was made smaller with the `frameRate` function. p5's normal frame rate is `60` frames per second. This means `draw` is called 60 times each second. Here we slowed it down to `15` fps.*

Your job is to make it blend into the background and become black as it gets smaller:

![sunset](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/sunset.gif)

Experiment and have fun! Below is the result with the exact same code, only the line `background(0);` is moved from `draw` into the `setup` function so the background is only drawn once.  Why is the result so different?

![peach](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/peach.gif)

And here is *that* code with the values of the color ranges reversed

![better sun](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/better-sun.gif)

#### Expert Challenge

Alter the above code to make a realistic looking sunrise or sunset. Things I would think about: maybe the size of the "sun" shouldn't shrink all the way to `0` and it's `x` and `y` coordinates can slowly move below or above a horizon line, maybe none of the ranges should map all the way to or from `0`, maybe the color of the sky could be mapped to change along with the color of the sun.

## Resources

- [`map` Documentation](https://p5js.org/reference/#/p5/map)

# The `map` function

Imagine that you were making a thermometer program that showed temperatures between 0 and 100 degrees fahrenheit. As the temperature slides up toward 100 degrees you want the background to be solid red and a temperature of 0 degrees should be solid blue. In between should be shades of purple.

![temp slider](/resources/temp.gif)

## Using `map`

Let's start out with something a bit simpler. As we move the mouse from left to right let's make the background change from white to black.

![b/w fade](/resources/fade.gif)

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

The first argument is the value we want to map. Here that's `mouseX`.

```javascript
map(mouseX, 0, 600, 0, 255);
```

Awesome, store this in a variable and that's it!

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

![purple fade](/resources/purple-fade.gif)

Think about our blue color range for a second.  The closer the mouse is to `0` in the x-axis the closer our blue value should be to `255`.  So we actually need to flip the *starting* and *ending* values for our range.

Paste in this code for the variable `blue`

```javascript
var blue = map(mouseX, 0, width, 255, 0);
```

Nice, that should work!

## Resources

- [`map` Documentation](https://p5js.org/reference/#/p5/map)

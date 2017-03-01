# Built-in Variables

Imagine you are the top p5.js programmer for the  UpperLine Rocket Corporation.  Your captain asks you to build a model of the different flight paths the rockets can take from the launch pad.

She asks that in a 200 x 200 canvas you draw a 50 x 50 pixel square in the exact center representing the launch pad.  From the center of the launch pad there should be 3 lines representing the various flight paths. One that goes directly up to the top of the canvas, one that ends in the bottom left corner, and one that heads toward the bottom right corner. Something that looks like this:

![landing pad](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/landing-pad.png)

"No problem at all", you reply as your mind starts tackling the problem.

- The exact middle point of the canvas is at half the width and half the height.
- For the launch pad you'll use the `rect` function. To call `rect` you need to know where the *top left corner* of the square should be.  The top left corner will be half the width of the square over to the right and half the length of the square up from the exact middle point.
- All the lines should start with one point at the center of the canvas.
- The top line should end at the midpoint for `x` and `y` will be `0`.
- The bottom left line will end at `0` for `x` with the `y` value being the maximum height of the whole canvas.
- The bottom right line will end with both `x` and `y` values being the maximum width and height of the canvas.

You quickly translate that to code:

```javascript
function setup() {
  createCanvas(200, 200);
}

function draw() {
  background(225);

  rect(75, 75, 50, 50);
  line(100, 100, 100, 0);
  line(100, 100, 0, 200);
  line(100, 100, 200, 200);
}
```

Your captain is impressed. So impressed, they want to see it drawn on a bigger canvas, and actually, they add, a canvas that is not a square but 800 x 600 to fit the corporation's new displays.

You go ahead and change the canvas size, but suddenly your code does not draw the correct model as described.

![woops](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/launch-pad-resize.gif)

While you could redo all your calculations and get the program to work as intended with this new canvas size, that might not totally solve the problem.  What if you were asked to change the canvas size yet again? Would you have multiple different versions of the program for each canvas size?

What is annoying about this problem is that nothing about *the logic of your program has changed at all*. You still need to find the center, draw a line to the bottom corner, etc.  The only thing that might change is the *actual values* you pass to some of your functions.  

As programmers we don't like to redo work.  Let's see if there's a way around this.

## `width` and `height`
By now you are familiar with a few of the functions provided by the p5 library.  You also have access to several built-in **variables**.  A variable is a word you write in your code that represents some other value.  "Value" means some actual data. So far the data we've seen has been different numbers. The numbers `0`, `100`, `255`, etc. are all different values.

In our case we will be able to write the word `height` and it will be *as if* we were writing the number `600` or `200` or **whatever the height of the canvas is** from p5.js. Variables are dynamic, they can hold any different value.

Another way to think of a variable is like a bucket or container with a label on it. Inside of the bucket can be any value.  You use a variable by writing the name of the label on the outside of the bucket, but when you write the name you get the value that's inside.

To prove that these variables exist, we'll use the `print` function. If you open up the developer tools in Chrome and click in the console tab (by either right clicking the screen then clicking "Inspect" or use a keyboard, usually command+option+j) you will be able to see whatever is logged to the console with `print`.

![print width](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/print-width.gif)

As shown here, we see the *value* of the variable `width`, `800` logged to the console. In fact, it's logged many, many times in a row because `draw` is called repeatedly over and over. Each time it prints the value of the variable `width`. That's what the gray and white increasing number in the console indicates, the same output is being printed multiple times.

When we try to print a variable name that doesn't exist like `zebra`, we see a red JavaScript error that tells us `zebra` does not exist, it's not defined the way `width` and `height` are.

Here's how we could use these variables in our code:

```javascript
rect(width/2 - 25, height/2 - 25, 50, 50);
line(width/2, height/2, width/2, 0);
line(width/2, height/2, 0, height);
line(width/2, height/2, width, height);
```

You'll see that that is a pretty direct translation into code of the steps we thought through when we originally imagined the problem.

And, check it out, the *same exact code* will work with any sized canvas. How dynamic!

![dynamic sizing with variables](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/dynamic-variables.gif)

## `mouseX` and `mouseY`
Two additional built-in variables `mouseX` and `mouseY` are also available to us. The value that they hold onto is the `x` or `y` coordinate of the mouse on the canvas. Try using `print` and see how the values change as you move your mouse.

If now your captain wanted a moveable green line that could indicate what path the rocket should take, you could write code like this:

```javascript
function draw() {
  background(225);

  rect(width/2 - 25, height/2 - 25, 50, 50);

  stroke(0,200,0);
  strokeWeight(10);
  line(width/2, height/2, mouseX, mouseY);

  stroke(0);
  strokeWeight(1);
  line(width/2, height/2, width/2, 0);
  line(width/2, height/2, 0, height);
  line(width/2, height/2, width, height);
}
```

![radar](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/radar.gif)

Pretty cool!  `mouseX` and `mouseY` open up a lot of interesting possibilities.

## Mini-Challenges

1. Use `width` and `height` to divide the a canvas into 4 different color squares. The arguments you provide to draw each rectangle should only use a combination of `width`, `height`, and `0`.  Half the width would be `width/2` or `width * 0.5`

  ![4 squares](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/4squares.png)

2. Make a web using several `line`s.  The center of the web should move as you move your mouse.  There should be lines going from the center to all 4 corners as well as the midpoints of each side of the canvas.
 ![web](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/web.gif)

3. Use `mouseX`, `mouseY` and the `ellipse` function to make a program that can draw a line as you move your mouse. Write your name in cursive. If you have to dot an 'i' or cross a 't' (or an 'x')... good luck!

  ![your name](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/alex.gif)

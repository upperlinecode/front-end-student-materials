# Events

![rube goldberg](https://media.giphy.com/media/ywNJFJR54KfQY/giphy.gif)

When you interact with any program on your computer you are used to it being responsive to your input. Your input might be clicking certain things, moving your mouse to different areas, or pressing certain keys on the keyboard These ways that you interact with the program are called **events**.

p5.js is actually *always waiting or listening* for certain events to happen. When the event does happen, it provides us, the programmer, a way to fire off code in response to the event.

We get to give the computer instructions like, "When the mouse is clicked do this", or "When the spacebar is pressed do this other thing". When the user does one of those things the code we provided will get run.

In a way, you have already seen the way events are handled in p5.  What if we considered the web-page being loaded as an event. What happens with our p5 program when the page loads? What functions get called automatically?

If you said `setup` (called once) and `draw` (called repeatedly), you are totally correct! There's an event that occurs that says "Ok, the page is ready", when that happens p5 looks for those two functions with very specific names to be defined. Then it will run whatever code is inside those functions.

Other events will work the same way. When an event happens that says "Ok, the mouse was clicked", p5 will look for a specific function to be defined. If it is , whatever code inside the function will get run. If it's not, no big deal, nothing special will happen.

## `mousePressed()` and `mouseReleased()`
First things first, let's just make sure these functions work. We'll use `print` to confirm that a function named `mousePressed` is called when the mouse is pressed. To *define* a function we'll need to make it looks like the other functions we've defined such as `draw`.  That means writing the word `function` making sure we have the `{}` in place and all that. For now just think of this as part of the magical incantation needed to get the code to work.

Start a new p5 project with only an empty canvas. Now add this:

```javascript
function mousePressed() {
  print('The mouse was pressed')
}
```

*Note: The quotation marks around `'The mouse was pressed'` are super important. Without them, the computer will think each one of these words is a variable name and your code will error because those variables don't exist.  Surrounding text with quotes, either single or double quotes are fine, makes the text what is called a String. Strings are another type of data, like numbers, that we will discuss much more later*

You should see something like this in the console every time you click.

![pressed](/resources/pressed.gif)

If you don't, check your spelling and syntax before moving forward.

Now that we've seen that function work, let's have it do something like change the color of a shape when the mouse is pressed.

With this code, you should be able to see something like in the gif below

```javascript
var col = 0;

function setup() {
  createCanvas(400,400);
}

function draw() {
  fill(col)
  ellipse(mouseX, mouseY, 20, 20)
}

function mousePressed() {
  col = 255;
}
```

![press event](/resources/press-event.gif)

You might have notice that after you press the mouse once you're line stays white.  Your first **Mini-Challenge** is to define a function `mouseReleased()` that resets the line back to black.

#### 🔔🔑💡 Tip 💡🔑🔔
> In the above code I would have loved to call my variable `color` instead of the harder-to-understand `col`, Unfortunately `color` is a function in p5.  If I defined my own variable called `color` I would have **over-written** p5's function and could experience some weird behavior. Before declaring a new variable or a function it's always good to check that the name isn't already taken by p5.

## Mini-Challenge
### `mouseClicked()`
A mouse 'press' event means the mouse is being held down. A 'click', on the other hand, happens once exactly when the mouse is clicked.

- Your Mission, should you choose to accept it, is to use the `mouseClicked` function to launch a rocket.
Your goal is something like this:

![rocket launch](/resources/rocket-launch.gif)

Use this starter code:

```javascript
var groundLevel = 550;
var rocketBodyHeight = 80;
var rocketBodyWidth = 20;
var rocketBodyY = groundLevel - rocketBodyHeight;
var rocketBodyX = 200 - rocketBodyWidth/2;

var rocketConeX1 = rocketBodyX;
var rocketConeY1 = rocketBodyY;
var rocketConeX2 = rocketBodyX + rocketBodyWidth;
var rocketConeY2 = rocketBodyY;
var rocketConeX3 = rocketBodyX + rocketBodyWidth/2;
var rocketConeY3 = rocketBodyY - 20;

var rocketSpeed = 0;

function setup() {
  createCanvas(400,600);
}

function draw() {
  background(252);
  line(0, groundLevel, width, groundLevel);

  rect(rocketBodyX, rocketBodyY, rocketBodyWidth, rocketBodyHeight)
  triangle(rocketConeX1, rocketConeY1, rocketConeX2, rocketConeY2, rocketConeX3, rocketConeY3);

  rocketBodyY += rocketSpeed;
  rocketConeY1 += rocketSpeed;
  rocketConeY2 += rocketSpeed;
  rocketConeY3 += rocketSpeed;
}
```

**Hint: when the click event happens, what variable needs to change?**

### `keyPressed()`

- Alright, now try to do the same thing, but instead of when the mouse is clicked, have the event that triggers the rocket launch be that *any key is pressed*. [Here is the documentation](https://p5js.org/reference/#/p5/keyPressed) for `keyPressed()`

- Next, try to get the rocket to launch only when *the space bar* is pressed. You'll have to use the `keyCode` variable as well as [this table of ASCII character values](https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes).  To your computer, different characters are stored as different number values. For example `'a'` is `65` and `'b'` is `66`. Find the value of the `' '`space character.

- As an extra challenge, can you use the left and right arrows to control the direction of the rocket as it launches? Be sure to read the documentation.

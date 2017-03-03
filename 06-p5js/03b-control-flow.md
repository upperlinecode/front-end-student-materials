# Control Flow, Animation

Here's the code we left off with last time

```javascript
var x = 1;
var y = 1;

function setup() {
  createCanvas(600, 200);
}

function draw() {
  noStroke();

  fill(255);
  rect(0, 0, width, height/2);

  fill(0);
  rect(0, height/2, width, height/2);

  if (y > height/2 ) {
    fill(255);
  } else {
    fill(0);
  }

  ellipse(x, y, 20, 20);

  x += 1;
  y += 2;

}
```

This results in a ball that changes color, but doesn't bounce back when it hits the edge of the canvas. Instead, it just continues off of it.

![black to white](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/black-to-white.gif)

Try to put the logic into words for bouncing off the bottom edge and reversing direction.

```
if the coordinates of the ball are
greater than the height of the canvas,

it's y coordinate should start to decrease each time draw is called
```

A decreasing `y` value means it would be heading back up toward the top.  Our first attempt might be something like this,

```javascript
function draw() {
  //... all our code

  x += 1;
  y += 2;

  if (y > height) {
    y -= 2;
  }
}
```

Look at what that does:

![stuck ball](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/stuck-ball.gif)

Can you figure out why the ball gets stuck?  Try to think like your computer, start at the top and read down.

When the ball makes it the bottom of the canvas:

- The conditional is `true` and `y` decreases by `2`.
- That's the end of the function, so the next thing that happens is `draw` gets called again.
- All the code gets read, it comes to the line `y += 2` and `y` gets incremented.
- This makes `y > height` be `true` again when it reaches the conditional.
- So `y` is then decremented by `2`.
- Then `draw` is called again.

The value continues to have `2` added and then subtracted, meaning no change in it's `y` coordinate, until it is off the canvas.

Clearly not what we want.

We're thinking through the process of how our computer reads the code, in what order, and what decisions it makes.  That process is  called **control flow**.  It's often helpful to thoughtfully consider your program's control flow when working on projects.

The problem here stems from the fact that we need to do more than `y -= 2` one time. After the ball reaches the edge, every call to `draw` should further decrement `y` until the ball hits the top. Then we should start incrementing with `+=` again.

What if instead we incremented with `+=` every single call to `draw`.  Only sometimes we incremented with a *negative number*. The value we increment with can flip from negative to positive and since adding a negative number is the same as subtracting we should be all good! To do this, we'll make an additional variable called `ySpeed`.

```javascript
//... previous code
var ySpeed = 2;

function draw() {
  //... previous code

  if (y > height) {
    ySpeed = -2;
  }

  y += ySpeed;

}
```

![first bounce](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/first-bounce.gif)

Amazing! The first bounce. It makes sense that it only bounces on the bottom since we never wrote the logic for bouncing off the top.  

One important thing to point out, notice that our new conditional comes *before* the line where we increment `y`.  The incrementing is done *outside* of any conditional, it happens every single time `draw` is called.  Therefore when we increment we must *already* have flipped the number to negative. That's why it has to come first.

## `else if`

This logic is covered:

```
if the coordinates of the ball are
greater than the height of the canvas,

it's y coordinate should start to decrease each time draw is called
```

Next we may want to add:

```
if the coordinates of the ball are
less than the 0 (the top of the canvas),

it's y coordinate should start to increase again each time draw is called
```

Since we would never want both of these things to happen at once, only one or the other, we can use an `else if`.  

Change the conditional to:

```javascript
if (y > height) {
  ySpeed = -2;
} else if (y < 0) {
  ySpeed = 2;
}
```

That should basically work-- Congrats!

![conditional bounce](/resources/conditional-bounce.gif)

## More on `else if` statements

An `if` statement can be followed by any number of `else if`s. The order of them is very important. The computer will go through them from top to bottom and find the first one that matches (evaluates to `true`).

Consider this code:

```javascript
if (x > 10) {
  print(10);
} else if ( x > 5) {
  print(5);
} else if ( x > 0) {
  print(0);
}
```

Imagine you are the computer running this code and I told you the value of `x` was 12.  You would start at the top and find the first `if` that is `true`. What value would you print if `x = 12`?

`10`. Perfect.

Now what if `x = 6`?

`5`, pretty easy!

Ok, let's change the code you are running to this:
```javascript
if (x > 0) {
  print(0);
} else if ( x > 5) {
  print(5);
} else if ( x > 10) {
  print(10);
}
```

A small change, you may think, but now `x` could be any positive number, `12`, `6`, `1`, `100` and you would print `0` every time.

There is no way for the lines `print(5);` or `print(10);` to get read. The first `if` catches all positive numbers.

See why the order of your `else if`s is important?

If you want a *default case*, some code that should be run only if *none of the if's are true*. You can put an `else` at the bottom to catch any input that doesn't match.

## A Quick Refactor, Logical Operators

Though our code above works, I am not totally satisfied with this

```javascript
if (y > height) {
  ySpeed = -2;
} else if (y < 0) {
  ySpeed = 2;
}
```

Notice that the value of `ySpeed` remains the same (it's always the number `2`) only the sign (`+` or `-`) flips or toggles back and forth.  Can't we toggle the sign of a number by multiplying by `-1` ?

I want code that looks like this:

```
if (the ball is past the bottom OR past the top) {
  ySpeed = ySpeed * -1;
}

y += ySpeed;
```

See that capitalized 'OR', we can write that in code with two pipe symbols `||`. This key is generally above the enter button on your keyboard.  

'OR' is called a **Logical Operator**,
another Logical Operator is 'AND', we write that in code with two ampersands like so `&&`. ('ampersand' if the name of the '&' symbol, if you didn't know).  

The finished refactored code looks like:

```javascript
if (y > height || y < 0) {
  ySpeed = ySpeed * -1;
}
```

I think this is more clear. It's how I would explain the problem to someone in words. "If the ball goes below the bottom or above the top, toggle the direction".

Nice job!

## Mini-Challenge
1. Draw a rectangle in the middle of the canvas, if the mouse is in the top half of the canvas it should be one color, if the mouse is in the bottom half it should be a second color.

 ![flip](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/flip.gif)

 Use `if` and `else`.

2. Next, draw 4 different colored smaller squares in each corner. When the mouse is hovering over any of them, the center square should be the same color as the square. If you are not hovering over any squares the middle square should be gray.

 Get one square working at a time and test that it works. That way you won't get overwhelmed.

 ![color-hover](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/color-hover.gif)

 Use `if`, `else if`, `else` and the `&&` logical operator.

3. Change your code so that the two opposite smaller squares are the same color

 ![2-hover](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/2-hover.gif)

 Try to use only 1 `else if`. To do this you will have to use the `||` logical operator.  You can use parentheses just like you would in math to group statements together `(one conditional statement) || (another conditional statement)`

## Resources

- [JavaScript if/else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
- [JavaScript Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
- [JavaScript Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

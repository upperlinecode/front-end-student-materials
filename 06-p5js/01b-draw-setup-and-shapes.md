# `draw`, `setup`, and Shapes
![dolphin](https://media.giphy.com/media/Q6Jk8FeKkSLLi/giphy.gif)

Every artist needs a canvas. Obviously.

Paste this into your `sketch.js`:

```javascript
function setup() {
  createCanvas(640, 480);
}

function draw() {

  fill(225, 0, 150);
  noStroke();
  ellipse(mouseX, mouseY, 40, 40);
}
```

Preview your `index.html` and check out what happens when you move your mouse!

![we're drawing!](http://g.recordit.co/D2aJ134ms1.gif)

## Special Words

All the words you see above such as `createCanvas`, `fill`, or `ellipse` are
special words coming from, you guessed it, the p5.js library.  They need to be written
exactly as shown above with exactly the same capitalization.

Don't take my word for it, replace the word `createCanvas` with `createcanvas` or
`fill` with `zebra`, what happens now when you preview your code.... nothing. If it ever happens
that you are writing some code and then you don't see what you expect or everything is broken
( \*\*SPOILER ALERT\*\* this will definitely happen, it's totally normal) check that you don't have any small typos
or spelling mistakes.

The technical term for these special words is **functions**.  Interestingly enough you also
see the word `function` above before `setup()` and `draw()`.  So if `createCanvas` and `fill`
are also functions why isn't the word `function` in front of them too?

You will learn much more about JavaScript functions later, but for know it's very important
to understand the difference between *using* a function and *defining* a function.

When you see:
```Javascript
// Function Definition
function setup() {
  //.. some code
}
```
That is the **definition of a function**

On the other hand, something like:
```Javascript
// Calling the ellipse Function
ellipse(mouseX, mouseY, 40, 40);
```
is using the function `ellipse` that happens to be defined already somewhere else.
The technical way to say "using" a function is to say **calling on a function**.  You
might also hear the term **invoking** a function. They all mean the same thing.

Code needs to be used or called on to actually get run by a computer.

## Defining Functions: `setup` and `draw`
p5.js is expecting that some functions are defined with very specific names.
Functions in JavaScript must be  defined with the pattern you've see above,

- first the word `function`
- then the name of the function
- next, an opening and closing parentheses `()`
- an opening curly brace `{`
- any code that should go inside the function
- a closing curly brace `}`

All together it looks like:

```Javascript
function nameOfYourFunction() {
  any code you may need;
}
```

For now there's no need to dive super deep into this. Just consider this
pattern as part of the magic-spell needed to get JavaScript to run. Forgetting a `}`
may seem like a minor mistake, but JavaScript needs everything to be in order to correctly
understand the code you wrote.

When a webpage that is linked to the p5 library loads, it will *automatically call* on a
function called `setup` once.

After that it will repeatedly call on a function called `draw`. Each time the `draw`
function gets called it will follow the instructions given inside that function.
It's here, inside the body of the function, that you can call on other functions.

## Calling on Functions

Calling a function is giving your computer a command to do something.  Computer's follow
the instructions you give them in the order you give them. Let's look more in depth at some of
the instructions we've seen:

### `createCanvas`
A well named function has a name that describes to other programmers like you exactly what it does.
A function named `createCanvas` creates the canvas that the rest of our shapes will be drawn on.

It seems like creating a canvas is something that we would want to happen once at
the beginning of our project.  Given that information do you think we should call
the `createCanvas` function inside `setup` or inside `draw`?

If you guessed `setup` you are correct! Whatever code is inside `setup` will get run
one time when the page loads-- just what we need.

In the code above there are some numbers after the name of the function:

```Javascript
createCanvas(640, 480);
```

What's going on there? Those numbers separated by commas are called **arguments** to
a function.

It's kind of like when we say `createCanvas` the computer is like,

```
"Alright, I will go ahead and make a new canvas for you, but I need a little more
info so I have a few questions."

"What should the width of the canvas be?"

"What should the height of the canvas be?"
```

The way we supply that information to our friendly computer is with arguments.

In between the parentheses we tell it the width and the height in pixels. So,
`createCanvas(250, 1000);` would create a narrow but tall canvas 250 pixels
across and 1000 pixels tall.

### `ellipse`

The `ellipse` function draws an ellipse shape on the canvas.  
We've seen the `ellipse` function called with 4 arguments:

```Javascript
ellipse(50, 50, 80, 80);
```

The *third* and *fourth* arguments determine the *width* and *height* of the ellipse.
If those values are the same you'll see a perfect circle, otherwise you'll have a squashed
or elongated circle in some way. Playing around with it in cloud9 is encouraged :).

So we know what some of the arguments to ellipse are:

`ellipse(?, ?, widthOfShape, heightOfShape)`.

I bet you could guess what information the *first* and *second* arguments supply.  Think
about what other questions your computer might have about how to draw a shape on the screen.

We've answered `"How big should the shape be?"`

But we still have not answered the question `"Where should I draw the shape?"`.  That's exactly
what the *first* and *second* arguments tell your computer! Where to draw the shape
using `x` and `y` coordinates on the canvas.

### A Note on the p5.js Coordinate System
There's one key thing to keep in mind when describing `x` and `y` coordinates to a
p5 function.  From math class you are probably familiar with using an `(x,y)` coordinate system. `(0,0)` would be in the bottom left,
the x axis increases to the right and the y axis increases upwardly.

The p5.js coordinate system is sort of reversed. `(0,0)` is actually the *top left* corner.
The x axis still increases rightward, but the y axis gets bigger in a
downward direction.

![coordinate plane](https://static1.squarespace.com/static/567458eda128e6372f9c1656/t/573cd44e4d088ee581102125/1463604324172/?format=2500w)

## How Do You Remember All This?
### Reading Documentation

This seems like a ton of information.

Who can remember if the order of the arguments to `createCanvas`
is supposed to be `(width, height)` or was it `(height, width)`?

There's a function `rect` that draws a rectangle that takes arguments very similar
to `ellipse` but draws a rectangle instead of an ellipse.  Wait-- was the function
called  `rect` or `rectangle`?

Luckily p5 has amazing **documentation** that can be found [here](https://p5js.org/reference/).
Code documentation shows how functions are intended to be used.

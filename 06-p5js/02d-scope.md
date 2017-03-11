# Scope

To build your own programs it is extremely important you understand the concept of **scope**.

A variable *has* a certain scope.  A variable's scope is the **section of the code that the variable can be used in**.

To understand what that means lets look at some examples of some different types of scope.

## Global Scope

![globe](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/earth.gif)

Take a look at the code below

```javascript
var globalSize = 100;

function setup() {
    createCanvas(globalSize, globalSize);
}

function draw() {
  background(0);

  fill(0, 100, 200)
  ellipse(width/2, height/2, globalSize, globalSize)
}
```

The variable `globalSize` is used in both the `setup()` and `draw()` functions to make a circle fit exactly in the square canvas.

![global scope](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/global-scope.png)

`globalSize` has a global scope because it is **declared** outside of any functions at the top of the code.  **All sections** of the code have access to a *global variable* like `globalSize`, which is why the term "global" is used in the first place.

You are free to change, or *re-assign*, the value of a global variable anywhere that it is in scope, which is everywhere!

Here we will leave `globalSize` alone in the `setup` function which is called first. Then in `draw` we'll reassign a new value to it which will change the size of the circle.

```javascript
var globalSize = 100;

function setup() {
  createCanvas(globalSize, globalSize);
}

function draw() {
  background(0);
  globalSize = 125;

  fill(0, 100, 200)
  ellipse(width/2, height/2, globalSize, globalSize)
}
```

That will result in something like this

![global scope](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/global-scope-2.png)

When the canvas was created, `globalSize` is `100` and when circle is made the variable has a value `125`.

## Local Scope

![global to local scope](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/global-to-local.gif)

Watching the gif above you'll notice that the variable `globalSize` is changed so that rather than being declared at the top *outside* of any function it is declared *inside the `setup()` function*.

The result is that we see a black canvas with the correct size but no blue circle.  What's going on?

If you open up the chrome console you'll see something like this:

![not in scope](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/uncaught-reference-error.png)

This *error message* is our computer telling us that it doesn't know about the variable `globalSize`; it tells us "`globalSize is not defined`".

Here's that code:

```javascript
function setup() {
  var globalSize = 100;
  createCanvas(globalSize, globalSize);
}

function draw() {
  background(0);

  fill(0, 100, 200)
  ellipse(width/2, height/2, globalSize, globalSize)
}
```

The fact that we see the variable `globalSize` being defined (on the first line in `setup`), but our computer tells us it's not defined is because of **scope**.

The variable `globalSize` is **defined inside the `setup` function** and therefore it's scope is **local** to that function.  When the lines of code inside the `draw` function are read, `globalSize` is no longer defined at that point. It's *out of scope*.

In fact, we should probably not call it `globalSize` anymore, `localSize` might be more fitting.

## Key Takeaways

A variable's scope is determined by where it is **declared**.

As long as a variable is in scope you can do anything to it, use it, reassign it's value.

Pretty soon you'll learn about *conditionals* and *loops*. We can think of these as *blocks* of code. You'll soon learn way more about this, but a block will be all the code in between a set of curly braces

```
{
  ...the block
}
```

The scope of variables can also be *local* to the block (this is called, you guessed it, *block scope*). We don't need to dive deep into this at the moment, but the exact same rules will apply!

If the variable is *declared in the block* it's scope will be the block.  If the variable is in scope wherever you're writing the block, you can use it inside the block-- the same way you use a global variable inside of a function.

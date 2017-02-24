# Loops

![looping](https://media.giphy.com/media/gYaG5BzJbzAly/giphy.gif)

For the moment, let's set aside getting our bubbles to move and just focus on drawing ellipses on the screen.

```javascript
function setup() {
  createCanvas(500,400);
}

function draw() {
  var x = 50;

  background(0);
  fill(250);

  ellipse(x, height/2, 40, 40);
}
```

![one ellipse](/resources/one-ellipse.png)

Great, now let's add a few more bubbles to the right.

![copying and pasting](/resources/copy-paste.gif)

That works, but it's so repetitive. Notice the same code is copied and pasted over and over again. There must be a better way, doing things over and over again is actually exactly what computers are great at. Think about `draw`, it's called over and over.

## `while` loops

Think back to conditionals

```
if (something is true) {
  run the code here...
}
```

Ok, but if the conditional is `true` the code only gets run once. There's another way to control the flow of our code that looks very similar. The difference is that as long as the conditional is true, the code inside will keep running. "while" the conditional is true, you might say. That's exactly what we'll write:

```
while (something is true) {
  run the code we want to be repeated here...
}
```

That's called a **while loop**.

🚫 **CAUTION:** read ahead before following exactly the code below 🚫

Delete all the repeated code

![deleting repetition](/resources/delete.gif)

Add in the while loop

![inifnite loop](/resources/crash.gif)

and..

![crash](https://media.giphy.com/media/nv99yd56AMNDa/giphy.gif)

That froze up my whole computer. What's going on??

The computer was stuck in an **infinite loop**. While `true` was `true` (a.k.a *forever*) we instructed our computer to run the code in the loop. The computer always does exactly what we tell it, we just happened to tell it to do a crazy thing!

Let's fix this by adding a condition that will not be `true` forever. Like 'as long as `x` is less than the width of the canvas':

![while loop](/resources/while-loop.gif)

Cool!

## `for` loops

How could you use a `while` loop to draw exactly 3 ellipses?

The condition on when to stop the loop would have to be as long as *the number of ellipses is less than 3*.

How are we going to keep track of the count of ellipses? With a variable of course!

Make variable `count` that will start at `0` and grow bigger by one every time the loop runs

![3 bubbles](/resources/3-bubbles.gif)

```javascript
function draw() {
  background(0);
  fill(250);

  var x = 50;
  var count = 0;

  while (count < 3) {
    ellipse(x, height/2, 40, 40);
    count += 1;
    x += 50;
  }
}
```

The pattern here is:
- Make a variable outside of the loop
- Increment it inside the loop
- Stop the loop after the variable has reached a certain size.

This pattern is so common that there is another type of loop that condenses all of this into one!  In fact, it's much more common than a `while` loop.

It's called a `for` loop.

```
for ( ____; ____; ____ ) {
  run the code we want to be repeated here...
}
```

There are 3 parts to what we put inside the parentheses, and yes, those are semi-colons in between each.

**The first is:**

```
for ( where to start counting; ____; ____ ) {
  ...
}
```

In practice that will look like making a new variable telling us where to start:

```javascript
for ( var count = 0; ____; ____ ) {
  //...
}
```

**Second:**
```
for ( ____; when to stop the loop; ____ ) {
  ...
}
```

This is just like the conditional to a `while` loop. Our loop would now look like;

```javascript
for ( var count = 0; count < 3; ____ ) {
  //...
}
```

**And Third:**
```
for ( ____; ____; how to count ) {
  ...
}
```

What does `how to count` mean?  Well, are we counting up by one? Up by 10, like `10`, `20`, `30`..., bacwards from 100, `99`, `98`

All together it looks like:

```javascript
for ( var count = 0; count < 3; count += 1 ) {
  //...
}
```

This may seem like a lot, but you will definitely get the hang of it!



#### 🔔🔑💡 Tip(s) 💡🔑🔔
**Common Practices**
> Remember how `count += 1` is a shortcut for `count = count + 1` because incrementing is such a common thing to do.  Well, incrementing **by 1** is a very, very common way to increment, so there's even a shortcut for that!

>Writing: `count++`

>is exactly the same as `count += 1` or `count = count + 1`. In `for` loops in particular, you will often see the `++` way. Remember, `++` only works for *incrementing by 1*

> In `for` loops it is extremely common that the variable you use will be named `i`. This is just a convention, but a very strong one.

>Using these common practices, the typical `for` loop would look like this:

>```javascript
for ( var i = 0; i < 3; i++ ) {
  //...
}
```

Here's the final code with a `for` loop:

```javascript
function setup() {
  createCanvas(500,400);
}

function draw() {
  background(0);
  fill(250);

  var x = 50;

  for (var i = 0; i < 3; i++) {
    ellipse(x, height/2, 40, 40);
    x += 50;
  }

}
```

## Mini-Challenge

(TODO add loop mini challenges)

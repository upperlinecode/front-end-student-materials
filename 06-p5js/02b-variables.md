# Creating Your Own Variables

The concept of variables is fundamental to programming and extends beyond just a few p5.js built-in variables.  You can also create your own variables to store data and make your code easier to read, more descriptive, and easier to change.

## Off to the Races

![fail](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/races.gif)

Our goal is to make a series of circles race across the screen to the finish line:

![race](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/race.gif)

Often when you write code you'll start with a first draft the way you would when writing an essay. The process of refining and working toward the final draft that is the most clear and efficient is what is known as **refactoring**.  We'll do some refactoring together here.


Let's start by getting the background and finish line up on the canvas.

```javascript
function setup() {
  createCanvas(600, 500);
}

function draw() {
  background(200, 225, 255);

  strokeWeight(4);
  stroke(0)
  line(580, 0, 580, height);
}
```

Not worrying about any movement yet, let's draw 4 ellipses on the left hand side of the canvas. Add this to the code:

```javascript
function draw() {
  //...previous code
  strokeWeight(1)

  ellipse(0, 100, 100, 100);
  ellipse(0, 200, 100, 100);
  ellipse(0, 300, 100, 100);
  ellipse(0, 400, 100, 100);
}
```
![too big](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/too-big-to-start.png)

The circles seem way too big. No worries...

![painful](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/painful.gif)

Wow... that was painful to watch... so slow. What if I want to change the size again??

There must be a better way.

Notice how all those values are the same. Wouldn't it be great if I could change that value in **one place** and it would change everywhere in the code?

Well, there is a way to do this-- We can create our own variables.

## Declaring and Assigning Variables

Making a variable start's with a name. Naming variables can sometimes be surprisingly difficult. The trick is to make it descriptive and sensical to any other developer reading your code.  "Other developer" can even mean you in a few days from now! You will be shocked by how quickly you can forget what is going on in your own code when you revisit it.

Since that number that was the same for every ellipse is the size of each racing circle, I'll call it `racerSize`. You can choose another name, but it should be a reasonable choice that describes the value it represents.

Making a variable is pretty simple, at the top of the file outside any function write

```javascript
var racerSize = 60;
```

That's it. Now instead of **hard-coding** in the number `60` or whatever it is, place the variable name `racerSize` as the third and fourth arguments to each `ellipse` function. Check this out:

![first variable](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/first-variable.gif)

SO MUCH NICER! Not only is our job easier if we have to change something, the code is easier to understand.

Though that seemed pretty straightforward, there are actually two distinct parts to creating a variable. We wrote it out on one line, but you can also write it out across two. Let's do that here to be super clear.

```javascript
var racerSize;
racerSize = 60;
```
#### Variable Declaration

The first step is to say "hey, I want a new variable called `racerSize` to exist". We can't just go ahead and say that this variable now contains the value `60` when the container doesn't even exist yet! That's what the first line `var racerSize;` does. `var` stands for variable.

#### Variable Assignment

At this point the variable `racerSize` exists, but it has no value, it's an empty bucket.  We have to **assign** a value to the variable. We do that with an `=`.  That's what's happening on the second line `racerSize = 60;`

You'll often see this done on one line, but it's important to understand that it's conceptually two distinct parts. There are also times when a variable will have to be declared but assigned a value later.

#### 🔔🔑💡 Tip 💡🔑🔔
> You are probably familiar with variables from math class. While there are some similarities, there are also some key differences. In math `x = 3` and `3 = x` signify the same thing.  This is NOT the case in computer programming. It's very important that on the LEFT HAND side of the `=` is the variable you are *assigning* a value to. On the RIGHT HAND side must be the value to be assigned. `60 = racerSize;` is not valid code :(

## A Quick Refactor

I see an additional place that we may want to use variables, that is the starting location of each ellipse. Though not exactly the same value, there is definitely a relationship between each starting location.

Let's add two variables `startX` and `startY`. The first argument to every `ellipse` function will be `startX`, and the second argument will have some relationship to our initial value of `startY`.

```javascript
var racerSize = 40;
var startX = 0;
var startY = 100;

function setup() {
  createCanvas(600, 500);
}

function draw() {
  background(200, 225, 255);

  strokeWeight(4);
  stroke(0)
  line(580, 0, 580, height);


  strokeWeight(1)

  ellipse(startX, startY, racerSize, racerSize);
  ellipse(startX, startY * 2, racerSize, racerSize);
  ellipse(startX, startY * 3, racerSize, racerSize);
  ellipse(startX, startY * 4, racerSize, racerSize);
}
```

So we didn't change what the program does at all, but we made it *easier to change* if we ever need to in the future. That's the sign of a good refactoring!

## Movement

p5.js's ability to animate things is possible because of the fact that `draw` is called repeatedly over and over.

The way to think about moving our circles across the screen is that each time the `draw` function is called the `x` coordinate of the ellipse needs to be a different value. The number needs to have increased for the shape to move rightward. If it was `10` it needs to be something like `12` (or really any number bigger than `10`).

This is a perfect place to use a variable because we need a value for the `x` coordinate, but we don't know exactly what number it needs to be. In fact, it needs to continually change and grow.

### Incrementing Variables

Imagine you have a variable called `age` that stores the value of your current age.  Then you have a birthday! You'd have to tell your variable that it's new value should be *whatever it's current value is* plus one additional year.

![b-day](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/bday.gif)

Here's how that is done in code:

![increment](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/increment.gif)

Notice that line:

```javascript
age = age + 1;
```

That's another thing about variables that doesn't make sense from math class.  Of course `age` would never be equal to `age + 1`. The difference is that here the equals sign doesn't mean the one side *equals* the other, it's about *assigning* the value on the right to the variable on the left. We are actually saying that the new value of `age` should be assigned to whatever the current value is + 1, which is just what we wanted to say. Note that *we never used the word `var`*, the variable was already declared and only had to be re-assigned a new value.

This is a really common thing in programming, increasing, or *incrementing*, a variable. It's so common there's even a shortcut for it.
Writing `age += 1` is *exactly the same* as `age = age + 1`.

You can also decrease, or *decrement* a value. `y = y - 10` or `y -= 10`. Both assign a new value to `y` that is `10` less than it's current value.

### Getting the Racers to Move, Finally

*At the bottom of `draw`* after all the other code has ran, but before `draw` is called the next time, we need to tell our variable to increment it's value so it will be bigger for the next call to `draw`.

Hopefully that was clear, let that take a moment to sink in before seeing how it's all put together.

![tie](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/tie-race.gif)

A 4 way tie! Every time `draw` is called the `x` coordinate of each circle has increased by `2`.  Here's the final code with an additional variable `speed`:

```javascript
var racerSize = 40;
var startX = 0;
var startY = 100;
var speed = 2;

function setup() {
  createCanvas(600, 500);
}

function draw() {
  background(200, 225, 255);

  strokeWeight(4);
  stroke(0)
  line(580, 0, 580, height);


  strokeWeight(1)

  ellipse(startX, startY, racerSize, racerSize);
  ellipse(startX, startY * 2, racerSize, racerSize);
  ellipse(startX, startY * 3, racerSize, racerSize);
  ellipse(startX, startY * 4, racerSize, racerSize);

  startX = startX + speed;
}
```

## Mini-Challenge

1. You probably noticed all 4 racers move at the same speed. Take the code above and modify it so the different circles move at different speeds. Replace the variable `speed` with at least 3 different speed variables such as `winningSpeed`, `averageSpeed`, `losingSpeed`.  To make the different racers move differently you'll need multiple variables for their `x` locations instead of one variable `startX`. As a suggestion you could use `racer1X`, `racer2X`, etc.  All of those variables will need to be incremented at the bottom of `draw`.
2. STRETCH GOAL -- Only if you have time. Use a variable to make each racer a different shade of the same color. Look at the way the `startY` variable is used for inspiration.

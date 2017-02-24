# JavaScript Objects

![bubbles](https://media.giphy.com/media/mUMA3nPwgx0jK/giphy.gif)

Over the next few readings we'll be making some bubbles that wobble over the screen! If that doesn't excite you on it's own you should definitely get excited about all the learning you will be doing because by then end you will have some really powerful tools in your programmer's tool belt.

![learning](https://media.giphy.com/media/qKltgF7Aw515K/giphy.gif)


## A First Attempt

Alright, here's *a lot* of code to make a few little bubbles:

![bubbles](/resources/bubbles.gif)

```javascript
var bubbleSize = 40;

var bubble1X, bubble1Y, bubble2X, bubble2Y,
    bubble3X, bubble3Y, bubble4X, bubble4Y;

function setup() {
  createCanvas(500,400);
  bubble1X = random(width/2 - 100, width/2 + 100);
  bubble1Y = random(height/2 - 100, height/2 + 100);

  bubble2X = random(width/2 - 100, width/2 + 100);
  bubble2Y = random(height/2 - 100, height/2 + 100);

  bubble3X = random(width/2 - 100, width/2 + 100);
  bubble3Y = random(height/2 - 100, height/2 + 100);

  bubble4X = random(width/2 - 100, width/2 + 100);
  bubble4Y = random(height/2 - 100, height/2 + 100);
}

function draw() {
  background(0);
  fill(250);

  ellipse(bubble1X, bubble1Y, bubbleSize, bubbleSize);
  ellipse(bubble2X, bubble2Y, bubbleSize, bubbleSize);
  ellipse(bubble3X, bubble3Y, bubbleSize, bubbleSize);
  ellipse(bubble4X, bubble4Y, bubbleSize, bubbleSize);

  bubble1X += random(-2, 2);
  bubble1Y += random(-2, 2);

  bubble2X += random(-2, 2);
  bubble2Y += random(-2, 2);

  bubble3X += random(-2, 2);
  bubble3Y += random(-2, 2);

  bubble4X += random(-2, 2);
  bubble4Y += random(-2, 2);
}
```

Now go ahead and add a 100 bubbles...

Just kidding, that would take ages, your hands would be cramped, and you probably wouldn't learn all that much.

One not-great thing about the code above is that there are so many different variables, which means so many places to make a small typo. Also, there's so many variables that are clearly associated with each other. `bubble3X` and `bubble3Y` for example. Every new brick means (at least) 2 new variables cluttering up the code.  

What if we could group those variables together into one. A bubble is *one thing*, so shouldn't we have it in our code as *one variable*. It could be called `bubble3` and *store both pieces of data* the `x` and `y`. That would cut our number of variables in half, or even less!

## JavaScript Objects

The way we can do this is with **JavaScript Objects**. An object is *one thing* that can be stored in one variable. An object can have many **properties**, think of these as additional variables stored inside the larger object.

That sounds pretty abstract, but it's not so bad, let's take make a an object called `brick`:

![first object](/resources/object-intro.gif)

Nice, the object we created with this code has two properties, `x` and `y`.

```javascript
var brick = {x: 10, y: 100};
```
#### Creating Objects

We create objects using curly braces

```javascript
var emptyObject = {};
```

#### Properties, key: value

Properties are added inside of an object. A property has two main parts, a *name* and a *value*.  This is very much like a variable, `x = 3`, the name is `x` the value is `3`.

With objects the name is called a **key**.  You will often hear people talk about objects by talking about *key-value pairs*. The object below has one key-value pair, the key is `firstName` and the value is `"Jenny"`:

```javascript
var student = {firstName: "Jenny"};
```

#### Multiple Properties

When there are multiple properties in an object, they are separated by commas. Often objects will be written across multiple lines. Either way is fine as long as your commas and braces are in the right place.

```javascript
var student = {firstName: "Jenny", grade: 11};
// or
var student = {
  firstName: "Jenny",
  grade: 11
};
```
#### Accessing Properties

That's how objects are created, but we will also need to *access* the values inside of objects. We do this with a dot after the object name.

`student.firstName` gives us back `"Jenny"`.

`student.grade` gives us back `11`.

#### Adding Properties

You can also use the same *dot notation* plus an `=` to add additional properties to an object after it's created

![adding properties](/resources/add-to-object.gif)

## Now with Objects

Here's the same program built with objects. This may not seem like a huge change from before, it's still pretty long. But we're started in the right direction.

```javascript
var bubbleSize = 40;

var bubble1, bubble2, bubble3, bubble4;

function setup() {
  createCanvas(500,400);
  bubble1 = {
    x: random(width/2 - 100, width/2 + 100),
    y: random(height/2 - 100, height/2 + 100)
  };

  bubble2 = {
    x: random(width/2 - 100, width/2 + 100),
    y: random(height/2 - 100, height/2 + 100)
  };

  bubble3 = {
    x: random(width/2 - 100, width/2 + 100),
    y: random(height/2 - 100, height/2 + 100)
  };

  bubble4 = {
    x: random(width/2 - 100, width/2 + 100),
    y: random(height/2 - 100, height/2 + 100)
  };
}

function draw() {
  background(0);
  fill(250);

  ellipse(bubble1.x, bubble1.y, bubbleSize, bubbleSize);
  ellipse(bubble2.x, bubble2.y, bubbleSize, bubbleSize);
  ellipse(bubble3.x, bubble3.y, bubbleSize, bubbleSize);
  ellipse(bubble4.x, bubble4.y, bubbleSize, bubbleSize);

  bubble1.x += random(-2, 2);
  bubble1.y += random(-2, 2);

  bubble2.x += random(-2, 2);
  bubble2.y += random(-2, 2);

  bubble3.x += random(-2, 2);
  bubble3.y += random(-2, 2);

  bubble4.x += random(-2, 2);
  bubble4.y += random(-2, 2);
}
```

Objects are a super important concept in programming. JavaScript objects are fundamental to how data from the internet is structured. With an understanding of objects, you're on your way to becoming an awesome developer.

## Mini-Challenge

1. Add a `size` property to each bubble object. The size can be random or hard-coded in.

2. Add a `color` property to every bubble object that is a random number between `0` and `255`. Use that number to make the bubbles `fill` a random grayscale color.

  You don't have to worry that the word `color` will conflict with p5's built-in `color`.  This is because you will be accessing it by something like `bubble1.color`.

3. Wouldn't it be cool if the bubbles were a random color that wasn't gray. One way to do this would be to make 3 new properties inside each object. The keys could be `r`, `g`, and `b` perhaps, and the values a random value.

  If you're up for a challenge, one interesting thing is that a key can have a value that is *another object*.  What if you're bubble looked like:
  ```javascript
  bubble = {
    x: ...,
    y: ...,
    colors: {
      r: ...,
      g: ...,
      b: ...
    }
  }
  ```

  The way you would access the `g` key would be `bubble.colors.g`.  Give it a shot!

## Resources
- [Coding Train](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA) The bubble example is copied from here. These videos are awesome!!

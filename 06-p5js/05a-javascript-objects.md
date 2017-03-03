# JavaScript Objects

![bubbles](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/monkey-bubbles.gif)

Over the next few readings we'll be making some bubbles that wobble over the screen! If that doesn't excite you on it's own you should definitely get excited about all the learning you will be doing because by then end you will have some really powerful tools in your programmer's tool belt.

![learning](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/info.gif)


## A First Attempt

![bubbles](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/bubbles.gif)

That image shows several bubbles, but let's start with one:

```javascript
var bubbleSize = 40;

var bubble1X, bubble1Y;

function setup() {
  createCanvas(500,400);
  bubble1X = random(0, width);
  bubble1Y = random(0, height);
}

function draw() {
  background(0);
  fill(250);

  ellipse(bubble1X, bubble1Y, bubbleSize, bubbleSize);

  bubble1X += random(-2, 2);
  bubble1Y += random(-2, 2);
}
```

Now go ahead and add a 100 bubbles...

Just kidding, that would take ages, your hands would be cramped, and you probably wouldn't learn all that much.

One thing that I'm thinking ahead about is that it seems like every time I'd want to add one new bubble, it would require two new variables. But, those two variables are clearly associated with each other. `bubble2X` and `bubble2Y` for example. Every new bubble adds (at least) 2 new variables.

What if we could group those related variables together into one. A bubble is *one thing*, so shouldn't we have it represented in our code as *one variable*. Ideally, a single variable `bubble1` could *store both pieces of data* the `x` and `y`. That would cut our number of variables in half, or even less!

## JavaScript Objects

The way we can do this is with **JavaScript Objects**. An object is *one thing* that can be stored in one variable. An object can have many **properties**, think of these as additional variables stored inside the larger object.

That sounds pretty abstract, but it's not so bad, let's make a an object called `brick`:

![first object](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/object-intro.gif)

Nice, the object we created with this code has two properties, `x` and `y`.

```javascript
var brick = {x: 10, y: 100};
```
#### Creating Objects

We create objects using curly braces

```javascript
var emptyObject = {};
```

#### Properties, {key: value}

Properties are added inside of an object. A property has two main parts, a *name* and a *value*.  This is very much like a variable, `x = 3`, the name is `x` the value is `3`.

With objects the name to a property is called a **key**.  You will often hear people refer to properties and their values as *key-value pairs*. The object below has one key-value pair, the key is `firstName` and the value is `"Jenny"`:

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

#### \* Your Turn \*
Make an object that represents you!  You can write it in the text editor, but better would be to open up the chrome console so you can interact with your object.

It should have *at least 5* key-value pairs. Some ideas for the keys might be: name, age, date of birth, grade, favorite food, favorite color, mood, or number of siblings. Some of the vales can also be Boolean values, `true` or `false`, something like`{hasGlasses: true}` or `{tiredToday: false}`.

Read the section below on how to access and change the properties. Change one of the properties on your "me" object.

#### Accessing Properties

We've seen how new objects are created, but we will also need to *access* the values inside of objects. We do this with a dot (a period `.`) after the object name.

`student.firstName` gives us back the value `"Jenny"`.

`student.grade` gives us back the value `11`.

#### Adding Properties

You can also use the same *dot* after the object name plus an `=` to add additional properties to an object after it's created or to change existing properties

![adding properties](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/add-to-object.gif)

## Now with Objects

Here's the same program built with objects. This may not seem like a huge change from before, but we're headed in the right direction.

```javascript
var bubbleSize = 40;

var bubble1;

function setup() {
  createCanvas(500,400);
  bubble1 = {
    x: random(0, width),
    y: random(0, height)
  };
}

function draw() {
  background(0);
  fill(250);

  ellipse(bubble1.x, bubble1.y, bubbleSize, bubbleSize);

  bubble1.x += random(-2, 2);
  bubble1.y += random(-2, 2);
}
```
## Why are Objects Important

Objects are a super important concept in programming and we've just scratched the surface here.

Objects allow us to group together into one container all the useful data that makes sense to be together.  This makes sense because it's like the real world, an object called `dog` might have `age`, `name`, `color`, and `weight` properties.

JavaScript objects are fundamental to how data from the internet is structured and retrieved.  If you wanted to make an app that used information about the current weather, movies playing near your zip-code, or just about any data you can imagine that comes from the internet, it is very, very likely that that data will be in the form of a big JavaScript object. With an understanding of objects, you're on your way to becoming an awesome developer.

## Mini-Challenge
1. Add at least one more bubble, make it an object.

2. Add a `size` property to each bubble object. The size can be random or hard-coded in.

3. Add a `color` property to every bubble object that is a random number between `0` and `255`. Use that number to make the bubbles `fill` a random grayscale color.

  You don't have to worry that the property `color` will conflict with p5's built-in `color` function.  This is because you will be accessing it by something like `bubble1.color`. The property `color` is sort of protected inside the object.

4. Wouldn't it be cool if the bubbles were a random color that wasn't gray. One way to do this would be to make 3 new properties inside each object. The keys could be `r`, `g`, and `b` perhaps, and the values a random value.

  If you're up for a challenge, one interesting thing is that a key of an object can have a value that is *another object*.  What if you're bubble looked like:
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
- Watch Dan Shiffman explain the bubbles in a video over at the [Coding Train](https://www.youtube.com/watch?v=pGkSHeEZLMU&index=23&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)

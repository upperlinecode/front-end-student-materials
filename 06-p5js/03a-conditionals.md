# Conditional Logic

![conditional bounce](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/conditional-bounce.gif)

Think about how you would write code that would produce the image above. Currently, we're missing one key tool that will enable us to write this code. Here's what we're able to do so far.  

```javascript
var x = 1;
var y = 1;

function draw() {
  noStroke();

  fill(255);
  rect(0, 0, width, height/2);

  fill(0);
  rect(0, height/2, width, height/2);

  ellipse(x, y, 20, 20);

  x += 1;
  y += 2;
}
```

What happens with that code:

![lost ball](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/lost-ball.gif)

As soon as the ball goes into the black area we lose sight of it.  To fix this we would need code that instructed the computer:

```
"when the ball is in the black area,
it's fill should be white,
otherwise,
it's fill should be black".  
```
We have not really seen anything like that before. So far our code has only been read from top to bottom.  The first line gets read, then the second, then the third, and so on.  Here, on the other hand, we need to say "sometimes read line 4 and other times read line 6", depending on if some condition is met. A *condition* is something that is clearly either *true* or *false*, such as, the center of the ball is in the bottom half of the canvas or it's in the top.

## `if` Statements and Booleans

The additional tool we'll be adding to our toolbox is an `if` statement. For the ball example the code would look like:

```javascript
if ( the ball is in the black area ) {
  fill(255);
}
```

Only if the code inside the parentheses *evaluates* to `true`, will the line `fill(255);` ever be read by the computer. If the expression inside the `()` and after the `if` is false, it will never be run.  To demonstrate that really quick, let's use the special words `true` and `false` in JavaScript. These are what are called **Boolean values**.

That's a weird word, it comes from someone's name, George Boole. He studied logic concerning two values, true or false, on or off, 0 or 1.  That kind of thinking is fundamental to how computer's work.  After we study some basic Boolean logic using the Boolean values `true` and `false`, we'll discuss what it means for code to *evaluate* to `true` or `false`.

![your first if](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/first-if.gif)

This some brand new functionality for us, pretty cool! The line that set the ball's fill to green *only was run by the computer when the condition was `true`*. Otherwise, the line was literally ignored. The code didn't do anything different.

### Comparison Operators

We can do more than just write in `true` or `false`.  We can ask questions and have them result in a value that's `true` or `false`. Examples of the type of questions we ask are
- is this variable greater than some value?
- is this variable less than some value?
- is this variable equal to some other value?
- is this variable NOT equal to some other value?

The tool's we use to do this are called *comparison operators*, and they're not as complicated as that may sound. You've seen very similar things before from math class. They look like:
- `>` greater than
- `<` less than
- `>=` greater than OR equal to
- `<=` less than OR equal to
- `==` exactly equal to
- `!=` NOT equal to
- `!` NOT (this means 'the opposite'. It will make anything `true` be `false`, and anything that is `false` be `true`)

![operators](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/operators.gif)

And that's them in action!

🔔🔑💡 Tip 💡🔑🔔
> One operator that may be a little tricky to get the hang of is the `==`. Remember that a single `=` isn't asking the question "Are these things the same?", it's actually used for *variable assignment*.  Since `=` is already used to mean one thing, we have to use the double equals `==` when we want to get back a `true` or `false` answer to our question.  It's easy to forget the double `==`. If you ever see a single `=` inside of a conditional, it'a probably a mistake.

### Back to the Bouncing Ball.

Now we know how to complete this code:

```javascript
if ( the-ball-is-in-the-black-area ) {
  fill(255);
}
```
A slightly more technical conditional to determine if the ball is in the bottom half of the canvas would be:

 `if the ball's y coordinate is *greater than* the half the canvas height`

 In code that's:

 ```javascript
 if (y > height/2) {
   fill(255);
 }
 ```

![black to white](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/black-to-white.gif)

Yay! Sort of.. before we get to the next conditional needed to make the ball bounce off the edge and reverse direction let's look back at the way we said:

```
"when the ball is in the black area,
it's fill should be white,
otherwise,
it's fill should be black".  
```

To take care of that "otherwise" part we can use an `else` statement.  An `else` can optionally come after an `if` if you need it.  This won't change the behavior of the code now but it will help us soon.

```javascript
if (y > height/2) {
  fill(255);
} else {
  fill(0);
}
```
It's cool to see how putting the problem into words translates really well into code.

We can cover getting the ball to bounce in the next reading.

## A Quick Quiz

Let's put our knowledge of comparison operators to the the test. Do your best to answer the following questions. The answers are at the bottom of the reading.

Given the code:

```javascript
// code for questions 1 - 3
var highNumber = 99;
var lowNumber = 30;
```

Will the following statements evaluate to `true` or `false`?

**1** - `highNumber > lowNumber`

**2** - `highNumber <= lowNumber`

**3** - `lowNumber != highNumber`

```javascript
// code for questions 4 - 6
if (x < y) {
  print('hi')
} else  {
  print('bye')
}
```

**4** - What will the code above print if the variables were initialized as follows?
```javascript
var x = 3;
var y = 4;
```

**5** - What will the code above print if the variables were initialized as follows?
```javascript
var x = 3;
var y = 2;
```

**6** - What will the code above print if the variables were initialized as follows?
```javascript
var x = 3;
var y = 4;
x = x + 1;
```

```javascript
// code for questions 7 - 8
 var started = true;
```

Does the following code evaluate to `true` or `false`?

**7** - `!started`

**8** - `!!started`

## Resources
- [Coding Train Introduction to Conditional Statements](https://www.youtube.com/watch?v=1Osb_iGDdjk&index=11&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)
- [George Boole](http://www.telegraph.co.uk/technology/google/google-doodle/11968997/george-boole-google-doodle.html)
- [JavaScript if/else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
- [JavaScript Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

## Answers
```
1- true
2- false
3- true
4- 'hi'
5- 'bye'
6- 'bye'
7- false
8- true
```

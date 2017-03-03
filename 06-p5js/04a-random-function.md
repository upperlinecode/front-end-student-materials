# The `random` function

![d'oh](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/doh.gif)

Earlier we built a small racing program. It probably wasn't as fun as it could be because either all the balls moved at the same speed, or the winner would be the same circle every time. The one with the highest speed hard coded in would always win.  Wouldn't it be great if we could add some *unpredictability*, so that every time we ran the code different values produced a different winner.

## `random`
This is part of the description of `random` from the p5.js documentation.

>Takes either 0, 1 or 2 arguments.

>If no argument is given, returns a random number from 0 up to (but not including) 1.

>If one argument is given and it is a number, returns a random number from 0 up to (but not including) the number.

>If two arguments are given, returns a random number from the first argument up to (but not including) the second argument.

One thing you may notice in the text above is the word 'returns'.  We've seen functions like `ellipse` or `fill` which do something action on the canvas. Functions can also have a *return value*, which simply means the function gives us something back after we call it. That's really cool because it we can do things like store the return value in a variable to re-use in our code.

So, given the code:
```javascript
var winningNumber = random(100);
```
`winningNumber` could have the value of any number from `0` up to `99`. We'd have to run the code to find out, how exciting!

## Back to the Races

![random race](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/random-race.gif)

Here's the code that generates the random races.

```javascript
var racerSize = 40;

var start1 = 0;
var start2 = 0;
var start3 = 0;
var start4 = 0;

var startY = 100;

var speed1, speed2, speed3, speed4;

function setup() {
  createCanvas(600, 500);
  speed1 = random(1,7);
  speed2 = random(1,7);
  speed3 = random(1,7);
  speed4 = random(1,7);
}

function draw() {
  background(200, 225, 255);

  strokeWeight(4);
  stroke(0)
  line(580, 0, 580, height);


  strokeWeight(1)

  ellipse(start1, startY, racerSize, racerSize);
  ellipse(start2, startY * 2, racerSize, racerSize);
  ellipse(start3, startY * 3, racerSize, racerSize);
  ellipse(start4, startY * 4, racerSize, racerSize);

  start1 += speed1;
  start2 += speed2;
  start3 += speed3;
  start4 += speed4;
}
```

*Notice that to use p5's `random` function it must be called inside of a p5.js function like `setup` or `draw`.*  

I declared the variables up top and then assigned them a random value once in `setup()`. This chooses *one* random value and then uses that throughout the program.  

What do you think would happen if we set the speed using the `random` function inside of `draw()` instead of in the `setup()` function?

### Upping the Stakes

Even this race is a little bit boring. Whichever circle begins with the top speed will surely always win.  What if at a random point in the middle of the race the racers changed their speed. Either making a strong push to the finish line or growing tired toward the end.

![finish line](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/finish.gif)

I'll pick a random `switchPoint` value for each racer at which to change their speed, once they pass it, they will be assigned a new random speed value.

Now this is much more interesting

![tight finish](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/tight-finish.gif)

The final code

```javascript
var racerSize = 40;

var start1 = 0;
var start2 = 0;
var start3 = 0;
var start4 = 0;

var startY = 100;

var speed1, speed2, speed3, speed4, speed5, speed6, speed7, speed8;
var switchPoint1, switchPoint2, switchPoint3, switchPoint4;

function setup() {
  createCanvas(600, 500);
  speed1 = random(2,7);
  speed2 = random(2,7);
  speed3 = random(2,7);
  speed4 = random(2,7);
  speed5 = random(2,7);
  speed6 = random(2,7);
  speed7 = random(2,7);
  speed8 = random(2,7);
  switchPoint1 = random(100,450);
  switchPoint2 = random(100,450);
  switchPoint3 = random(100,450);
  switchPoint4 = random(100,450);
}

function draw() {
  background(200, 225, 255);

  strokeWeight(4);
  stroke(0)
  line(580, 0, 580, height);


  strokeWeight(1)


  ellipse(start1, startY, racerSize, racerSize);
  ellipse(start2, startY * 2, racerSize, racerSize);
  ellipse(start3, startY * 3, racerSize, racerSize);
  ellipse(start4, startY * 4, racerSize, racerSize);


  if (start1 > switchPoint1) {
    start1 += speed5
  } else {
    start1 += speed1;
  }

  if (start2 > switchPoint2) {
    start2 += speed6
  } else {
    start2 += speed2;
  }

  if (start3 > switchPoint3) {
    start3 += speed7
  } else {
    start3 += speed3;
  }

  if (start4 > switchPoint4) {
    start4 += speed8
  } else {
    start4 += speed4;
  }
}
```

## Mini-Challenges

1. Use the `random` function to make each racer a random color.  You can randomize one of RGB values, or all three!

2. Use the `random` function to make at least one bubble (an ellipse) that randomly shakes across the screen.

 ![bubbles](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/bubbles.gif)

 **Hint:** You want `random` to be called every frame with a new random value, make sure you call it *inside of the `draw` function*. This will ensure that a new random value is picked each time.

 **Hint:** The idea is that the bubble may sometimes move a small number of pixels to the left, sometimes to the right, sometimes up, sometimes down. The range given to `random` to randomly choose a number between can't start at 0.

 ### T.M.R.T.Y.C.B
3. *The Most Random Thing You Can Build*

 Try to make the most random possible thing. Coordinates can be random values, widths and heights can be random, colors can be randomized.  What if your range of random values was between `0` and a randomly chosen value?

## Resources

- [`random` Documentation](https://p5js.org/reference/#/p5/random)

# Arrays

Knowing about loops will really open up the possibilities of what we can do with code.  What are some examples of "loops" from everyday life?

![bubbles](https://media.giphy.com/media/W8OfQ8S1PXWKY/giphy.gif)

Reading, might be one. It's happening so fast, but really you are looking at the first word, then the second, then the third, and so on. You keep doing this until the paragraph, book, tweet or whatever group of words you are looking at is finished.

Another might be your school day. You go to your first period class, and then second period, then third period, etc.  Your schedule, a list of what classes you have when, determines that first period is english, second is math and so on.

Or maybe you make to-do lists either in your head or on paper.  You "loop" over the list and check off a task if it's completed.

What these all have in common is that in each case we are *looping through* a **list** of things.

As programmers, the way we represent lists of things, that is to say *groups* or *collections* of *elements* that have an **order** (first, second, third...), is with `Arrays`.

## Array Basics

You've seen one way that collections of things are grouped together with code-- that's JavaScript Objects, something like :

```javascript
var book = {
  title: "Calvin and Hobbes: Weirdos from Another Planet",
  author: "Bill Watterson",
  pages: 147,
  published: 1990
}
```

While that is a collection of associated data, it doesn't really make sense to think of that as a list.  

It's more like an online dictionary. You type in a word (*the key*) and get back the definition (*the value*). An online dictionary doesn't just load the entire dictionary into your browser and let you scroll through, looking at the first word, the second,.... the hundred-thousandth..., until you find the definition you're looking for.

The distinction here is that Arrays *have an order*. Think: something we could loop through.

## Order (What's an Index)

Watch how an array is created, and then we'll break it down.

![create an array](/resources/create-array.gif)

As you can see to make an array you use square brackets and inside you put the items that make up the list separated by commas. Here's an example:

```javascript
var testScores = [89, 91, 95, 86, 79];
```

### Accessing Values

With objects we got a value out of a collection with the help of the key.

Something like, `student.firstName`.

With arrays we don't really have keys, but we do have the order in the list. We can ask what *position* we want to get the value of.

The number of the position within the array is called the **index** of the array.

We get the value at a certain index using square brackets written after the name of the array, like so:

```javascript
myArray[index]
```

Here's the list of countries again:

```javascript
var countries = ["Algeria", "Brazil", "Canada", "Denmark"]
```

You might guess that writing `countries[1];` would give us back "Algeria" because it's the first item, or element, in the array.

Let's take a look

![index 1](/resources/index-1.gif)

Huh??? Last I checked `"Brazil"` was the *second* country in the list...

![wat](/resources/wat.png)

Before you put on your Darth Vader costume and grab the nearest Brita filter, watch this:

![indices](/resources/indices.gif)

Ooooo, we just learned something really important about arrays. The indexes **start at `0`**.  

Index `0` is the first element of the array, index `1` is the second, index `2` is the third and so on.

This also means the *last index* of any array is always *one less* than the total number of items in the array. The highest index in an array with 100 items would be `99`. Which brings us to the next array property, `length`.

## `length`

We can find out the length of any array by adding `.length` to the end of the array.

![length](/resources/length.gif)

Think about `for` loops for a moment, where might the `length` property be useful??

We'll get to that soon enough :)

## Manipulating Arrays with Functions
What are some of things, conceptually, you could do to a list?

Maybe add things to it, at the end or at the beginning, or remove things from it. Arrays have functions to do just that!

### `push()`

`push` adds a new element to the end of an array. Think of it as 'pushing' onto the end.

![push](/resources/push.gif)

It's a function so it takes an argument of the new element to add.

### `unshift()`

`unshift` adds an element to the *beginning* of an array. It's like the opposite of `push`.

Let's say we forgot to add the country starting with `'A'`. Unshift to the rescue!

![unshift](/resources/unshift.gif)

## `splice()`

`splice` is used to remove elements from arrays, it's a little bit trickier because it needs two arguments.

The first argument is the *index* where to start removing and the second argument is *how many elements to remove*.

![splice](/resources/splice.gif)

Bye Canada 🇨🇦 😢

## Mini-Challenge

That was a whirlwind introduction to Arrays, complete the exercises below then we'll move on to using arrays and loops in our bubble example.

(TODO add array mini-challenges)

## Resources

- [JS Arrays](https://www.w3schools.com/jsref/jsref_obj_array.asp)
- [`push()`](https://www.w3schools.com/jsref/jsref_push.asp)
- [`splice()`](https://www.w3schools.com/jsref/jsref_splice.asp)
- [`unshift()`](https://www.w3schools.com/jsref/jsref_unshift.asp)

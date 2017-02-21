# Using Classes and IDs to select items

So far, we've only been able to select elements (like `<h1>` and `<p>`) in css. While this is useful, sometimes we need to be more specific. What if I want to select only one `<p>` element, or style a few (but not all) of the images on my page in a specific way. We use classes and ids to make this happen.

## What are Classes and IDs?
Classes and ids are types of attributes that we can add onto an element in order to be more specific with our CSS selectors. This is what they look like:

```html
<p class="animal-description">
```
```html
<h1 id="main-title">
```
## Why are they useful?
Classes and Ids allow us to more finely select elements to style using CSS. If we have 10 `<p>` elements on our page, but only want to change the background color of a few of them, we'd reference their class instead of the tag type. If you wanted to only style the `<h1>` on your page that is the main title, while leaving all other `<h1>` elements alone, we'd reference the id we've given it.

## CSS Syntax for Ids and Classes
We reference a class by using a `.` and the class name:

```css
.animal-description {
  background-color: #FF0000;
}
```

We reference an id by using a `#` and the id name:

```css
#main-title {
  background-color: #FF0000;
}
```
## The Magical `<div>` element
Open up the source file for any website and you'll see the `<div>` element scattered around all over the place. It's one of the most widely used tags on the web. But what is a div?

**Divs are boxes or containers that hold HTML elements**

Let's say we have the following HTML elements, and we want to give them all a single blue background color, and want all of the elements to be centered in the page.

```html
<img src="http://www.nobelprize.org/nobel_prizes/medicine/laureates/1962/watson.jpg">
<h2>James Watson</h2>
<p>Nobel Prize winner and co-discoverer of the double-helix structure of DNA</p>
```

We could work on individually styling each of these elements, but this gets old very fast. Instead, we can put all of these elements inside of a `<div>` and then apply styling to the div itself (Remember that the 'C' in CSS stands for **Cascading** - meaning that styling to a parent element will cascade down to its children)

```html
<div class="scientist">
  <img src="http://www.nobelprize.org/nobel_prizes/medicine/laureates/1962/watson.jpg">
  <h2>James Watson</h2>
  <p>Nobel Prize winner and co-discoverer of the double-helix structure of DNA</p>
</div>
```

We can now style this div by referencing the id or class that we've given it (in this case it's a class):

```css
.scientist {
  text-align: center;
  background-color: lightblue;
}
```

You should use `<div>` elements whenever you want to create a "group" of elements that receive the same styling and layout (more on layout later).

## Resources
+ [Divs Explained on Stack Overflow](http://stackoverflow.com/questions/14027243/explain-what-a-div-tag-is-to-a-non-programmer)

# Using Classes and IDs to select items

So far, we've only been able to select elements (like `<h1>` and `<p>`) in css. While this is useful, sometimes we need to be more specific. What if I want to select only one `<p>` element, or style a few (but not all) of the images on my page in a specific way. We use classes and ids to make this happen.

## What are Classes and IDs?
Classes and Ids are a type of attribute that we can add onto an element in order to be more specific with our CSS selectors. This is what they look like:

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

**Divs are boxes or containers that hold



+ Labs
  + [Sushi Selectors](https://flukeout.github.io/)
  + Sushi Menu Lab

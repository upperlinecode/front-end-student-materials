# Using the Bootstrap Framework

As we recently learned, page layout with css can be a long and tedious process. It makes my head hurt. As developers, whenever we encounter situations like this we need to ask ourselves **"Is there an easier way to do this?"**. Developers are lazy.

Well, it turns out that Bootstrap (and other front-end frameworks like Foundation) are the answer to our laziness! Bootstrap is a CSS library that makes website layout a breeze. It's used by many of the world's top websites.

## What is Bootstrap? Why is it Useful?

Bootstrap is a CSS **library**. A library is just a collection of code that has been written by other developers to save us time and give us functionality that we otherwise might not have in our code. If you want to take a look at the Boostrap CSS library, [click here](https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.css) (it's a little overwhelming).

## Integrating the Bootstrap Framework into a Project

At the end of the day, this is all CSS that someone else has written for us. To use it, we have to link to the Bootstrap stylesheet in the same way we would link to our own stylesheets in the `<head>` tag:

```html
<head>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.css">
    <link rel="stylesheet" href="style.css">
</head>
```
Notice that I also linked my own stylesheet **after** linking to Bootstrap. This allows us to write custom CSS that can overwrite bootstrap, if necessary.

## Using Bootstrap

**Now here is the trick:** Instead of writing any CSS, we are going to use the Bootstrap CSS by applying the pre-written classes into our HTML page. To put this another way, we're going to apply styling by adding in classes that reference the Bootstrap CSS (where the classes have already been defined).

This is tricky to understand at first. Let's style a basic button element as an example. Here's what a basic button looks like:

```html
<button>This is a regular button</button>
```
![IMAGE OF A REGULAR BUTTON](https://s3.amazonaws.com/upperline/curriculum-assets/css/regular-button.png)

Now lets head to the Bootstrap documentation and look at the samples that they have for buttons there:

![BOOTSTRAP DOCUMENTATION](https://s3.amazonaws.com/upperline/curriculum-assets/css/bootstrap-buttons.png)

It looks like all we have to do to update our button is to add classes to the HTML. To make the button blue, we'd add `class="btn btn-primary"`:

```html
<button class="btn btn-primary">This is a cool blue button</button>
```

![Bootstrap Button](https://s3.amazonaws.com/upperline/curriculum-assets/css/blue-button.png)

See what we did there? We never touched our CSS, instead we used a pre-defined class from Bootstrap and applied it to our HTML.

**YOU DO:** Look at the [documentation for images in Bootstrap](http://getbootstrap.com/css/#images). Can you create a webpage with *circular images* of your five favorite places to eat in NYC?

## Layout With The Grid System

Imagine that you can divide your website into up to twelve different parts. What combinations can you come up with?

![DIFFERENT COMBINATIONS](https://s3.amazonaws.com/upperline/curriculum-assets/css/bootstrap-combinations.png)

Other combinations include 2-2-4-4, 6-3-3, 8-4, etc. As long as they add up to 12, you're filling the page.

This is how bootstrap layout works. We create horizontal **rows** of content (divs with the `class="row"`) and within those divs, we create divs that are columns with a specific size `class="col-sm-6"` or `class="col-sm-2"`. Using the `row` and `col` classes, we're able to build out our pages with amazing flexibility

Here's a 4-4-4 row setup:

```html
<div class="container">

  <div class="row">
    <div class="col-md-4">
      ...
    </div>

    <div class="col-md-4">
      ...
    </div>

    <div class="col-md-4">
      ...
    </div>

  </div>
</div>
```
[SHOW AN ACTUAL PAGE BROKEN UP SO WE CAN SEE ROWS AND COLUMNS]

+ Using the Documentation

+ Other Elements

+ Using (and modifying) Bootstrap Templates

+ Labs
  + Build a Business Page (Convert a web 1.0 to a web 2.0 page)
  + Use a bootstrap template

+ Resources

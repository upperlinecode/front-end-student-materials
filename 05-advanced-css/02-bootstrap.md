# Using the Bootstrap Framework

As we recently learned, page layout with css can be a long and tedious process. It makes my head hurt. As developers, whenever we encounter situations like this we need to ask ourselves **"Is there an easier way to do this?"**. Developers are lazy.

![LAZY DOG GIF](http://upperline.s3.amazonaws.com/curriculum-assets/css/lazydog.gif)

Well, it turns out that Bootstrap (and other front-end frameworks like Foundation) are the answer to our laziness! Bootstrap is a CSS library that makes website layout a breeze. It's used by many of the world's top websites.

## What is Bootstrap? Why is it Useful?

Bootstrap is a CSS **library**. A library is just a collection of code that has been written by other developers to save us time and give us functionality that we otherwise might not have in our code. If you want to take a look at the Boostrap CSS library, [click here](https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.css) (it's a little overwhelming).

## Integrating the Bootstrap Framework into a Project

At the end of the day, Bootstrap is just *CSS that someone else has written for us.* To use it, we have to link to the Bootstrap stylesheet in the same way we would link to our own stylesheets in the `<head>` tag:

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

Without bootstrap, we'd open up our custom CSS stylesheet, select the button, and change the values of certain properties like background-color and font-size. However, with bootstrap, this has already been done. All we need to do is apply the right class name.

Let's head to the [Bootstrap documentation](http://getbootstrap.com/css/#buttons) and look at the samples that they have for buttons there:

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

Notice that all rows and columns must be in a `<div>` element with the class "container". The container class provides proper width for the layout - it serves as a "wrapper" for the rest of the content.

Let's take a look at how rows and columns are used on an actual page:

![Upperline Rows and Columns](http://upperline.s3.amazonaws.com/curriculum-assets/css/rows-and-columns.png)

In the picture above, we see:

+ 4 rows
+ Rows 1 and 2 both have one column that is the width of the page (12).
+ Row 3 has four columns (1,5,5,1).
+ Row 4 has four columns (3,3,3,3)

Notice how the widths of the columns in a row **always add up to 12!**

### xs, sm, md, lg

If you look at the way we create column divs, the classes look like these:

```
<!-- Extra Small -->
<div class="col-xs-6">

<!-- Small -->
<div class="col-sm-6">

<!-- Medium -->
<div class="col-md-6">

<!-- Large -->
<div class="col-lg-6">
```

These sizes tell the browser how to behave when users are using different types of devices. For professionals, the look of a site on an iPhone should be very different from looking at that site on a laptop or desktop monitor. In general, if we want the website to look the same across devices we use the `col-xs` prefix. Look in the resources section to learn more about responsive break-points.

## Using the Documentation

The Bootstrap library is enormous, and the only way to really get into is by tinkering and reading through the documentation. Take some time to click around (especially the "CSS" and "Components" sections) and add different Bootstrap elements to your page!

## Resources

+ [SitePoint's Understanding Bootstrap](https://www.sitepoint.com/understanding-bootstrap-grid-system/)
+ [Bootply](http://www.bootply.com/) - A great place to tinker with Bootstrap in a 'drag and drop' environment.
+ Quora: [What's the best way to learn Bootstrap?](https://www.quora.com/What-is-the-best-way-to-learn-Bootstrap)

Here are a few documentation challenges for you:

+ Use bootstrap to create a striped table that lists your classes, the name of the teacher, and the amount of work you have for each one every week.

+ Create a "Block Level Button" that

+ Add a navbar to the top of the page

+ Create a sign-up form

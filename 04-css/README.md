# CSS Fundamentals - Let's Style our Pages!

## What is CSS?

CSS (which stands for *cascading style sheets*) is ***the*** fundamental way of adding style to your websites. Without it, your sites are just a bunch of text in ugly chunks. All the color, style, and generally cool things you see on the web require tons of CSS. Today will be a nice starting point for you to get your feet wet and see some cool results.

## CSS Syntax

## Follow Along
If you want to follow along, navigate to your passion or hobby project in the terminal.

## Applying CSS styling to an HTML Page
### Create a CSS file
The first thing we need to do is create a css file that our html page can get its styling from. In your terminal or navigator, create a new file called `style.css`.

### Link to your CSS file from your HTML page
We need to connect our `style.css` page to the HTML page. Inside the `<head>` tag of your html page, we're going to add a `<link>` tag to connect to our new stylesheet. Add the following element to your `<head>` section:

```HTML
<link rel="stylesheet" href="style.css">
```
(make sure that your html page and your css stylesheet are at the same folder level)

### Select and Style elements, by element
Try selecting an element and styling it! In your stylesheet type:
```css
h1 {
  color: blue;
  font-size: 25px;
}
```
This will look for all h1 elements and style them with a font size of 25 pixels, and blue color. Open up your webpage to check it out!


## Good Starter Properties To Play With
  + color
  + font-size
  + background-color
  + width and height (for images)
  + text-align
  + border-color

  This is just a little tiny list to start playing with. Look for more in the resources or by Googling "CSS Properties list"

## A Note About Color
Color in CSS can be tackled a few different way:
+ Using key words: There are 140 differnt color names which your web brower can make sense of--basically every crayon color you could want from "cornslik" to "rebeccapurple." You can find a [complete list of colors here](http://www.w3schools.com/colors/colors_names.asp).
+ Using Hex Codes: `#4286f4`, `#336034`, etc. You can find hex codes by using this cool [color picker tool](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool)
+ Using RGB: `rgb(255,0,0)`, `rgb(120,200,0)`, etc. RGB Stands for red, green blue. You can also use the [color picker tool](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool) to get rgb values (each value has to be between 0 and 255).

## Resources
+ [Shay Howe's Awesome HTML and CSS Tutorial](http://learn.shayhowe.com/html-css/)

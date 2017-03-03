# Initital setup

### Let's dive right in
![dive](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/dive.gif)

Create a new project in cloud9.  In cloud 9's terminal use the `mkdir` (short for "make directory") command to create a new folder. Inside that folder use the `touch` command to create two new files *inside that directory*. One called `index.html` and another called `sketch.js`.

![mkdir](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/mkdir.gif)

When you need to make another project you can use `mkdir` again to make another folder. You can copy the two files we'll make here and place into any new project.

Paste this code for an empty html document into `index.html`

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta charset="utf-8">
	  <title>p5 Project</title>
  </head>
  <body>

  </body>
</html>

```

The first thing we need to do is
hook up our project with the p5.js library.

Try visiting `https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.7/p5.js` in your browser.

![so much](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/cdnjs.gif)

Wow so much code! That's the p5.js library. What you have to do is tell your html file to
go that address and get all that code. You do this with a `script` tag.

JavaScript code can actually be written directly inside of a `script` tag, but since here
the code we want to use lives elsewhere, at that web address, you can use the `src` property of a `script` tag.

Paste this into the `head` tag in your `index.html` file:

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.7/p5.js"></script>
```

![paste the script tag](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/setup1.gif)

Great! Now when you write JavaScript you will have access to the full p5.js library. What's missing
is a place for you to write all your code.

Make a new file in the root directory of your project called `sketch.js`.

Now you need to let your html know about that file the same we we let it know about
the p5 library-- with a `script` tag. The `src`, or source, that a script tag
retrieves code from can be either a web address or another file you have locally in your project.

Paste this inside the `head` as well:

```html
  <script type="text/javascript" src="sketch.js"></script>
```
![paste the next script tag](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/setup2.gif)

To test that everything works paste this code into your empty `sketch.js` file.

```javascript
function setup() {

}

function draw() {
  ellipse(50, 50, 80, 80);
}
```

If you see an circle on the screen when you preview your `index.html` you're good to go.

![our first program](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/setup3.gif)

In the next lesson we can explore more what that code you just wrote is doing. Good work 👍

## Resources

- [Getting Started with p5.js](https://p5js.org/get-started/)
- [Coding Train](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)


### Let's dive right in
![dive](https://media.giphy.com/media/m1HVrsf3wn25q/giphy.gif)

Starting with an empty HTML document in cloud9, the first thing to do is
hook up our project with the p5.js library.

Try visiting `https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.7/p5.js` in your browser.

![so much](http://g.recordit.co/oWEqwenO8b.gif)

Wow so much code! That's the p5.js library. What you have to do is tell your html file to
go that address and get all that code. You do this with a `script` tag.

JavaScript code can actually be written directly inside of a `script` tag, but since here
the code we want to use lives elsewhere, at that web address, you can use the `src` property of a `script` tag.

Paste this into the `head` tag in your `index.html` file:

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.7/p5.js"></script>
```

![paste the script tag](http://recordit.co/98KmEldioi.gif)

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
![paste the next script tag](http://g.recordit.co/MQVV1QiSE5.gif)

To test that everything works paste this code into your empty `sketch.js` file.

```javascript
function setup() {

}

function draw() {
  ellipse(50, 50, 80, 80);
}
```

If you see an circle on the screen when you preview your `index.html` you're good to go.

![our first program](http://g.recordit.co/v8dvz1uMD8.gif)

In the next lesson we can explore more what that code you just wrote is doing. Good work 👍

## Resources

- [Getting Started with p5.js](https://p5js.org/get-started/)
- [p5.js Interactive Introductory Video](http://hello.p5js.org/)
- [Coding Train](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)

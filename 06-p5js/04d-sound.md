# Sound

The way sounds are loaded into p5 works exactly the way same images do. In the `preload()` function we will use a function called `loadSound()` and we will store the result in a variable to use later.

There's one thing we have to do first though.  Remember the concept of a *library* of code, in our case the p5.js library is where all of the functions we use, `draw`, `setup`, `createCanvas`, `ellipse`, `mouseClicked`, etc. come from.

In one of the first lessons we added a link to to this library inside of a `<script>` tag in our `index.html` file.  

Well, the functions we need for sounds such as `loadSound` and `play` or `stop` come from a *separate library*-- the p5.sound.js library.

We'll have to also link that library up to our project by following the steps here

1. Visit [this link](https://p5js.org/download/) and download the .zip file of the **Complete Library**

2. After downloading, locate the `p5.sound.js` file and drag it into your cloud9 project. Your project should look like this:

 ![p5.sound.js in the top level](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/sound-lib.png)

3. Now, in the `index.html` file you need to add this line:
```html
<script type="text/javascript" src="p5.sound.js"></script>
```
 It is extremely important that you paste this in **after** the `<script>` tag linking to the main library and **before** the `<script>` tag linking to your `sketch.js` file

 ![paste after main lib](https://s3.amazonaws.com/upperline/curriculum-assets/p5js/add-sound-library.gif)

And that's it-- you are good to go with sound!

To test this out download the file [found here](http://soundbible.com/85-Cartoon-Hop.html) in either .wav or .mp3 format.  I renamed it to `boing.wav` for a shorter filename.

If you add that file to your project in a directory called `sounds`, using this code you should hear a sound when your preview first loads

```javascript
var boing;

function preload() {
  boing = loadSound("sounds/boing.wav");
}

function setup() {
  createCanvas(200, 200);
  boing.play()
}

function draw() {

}
```

🔔🔑💡 Tip 💡🔑🔔
> Currently you link to the main p5.js library in your `index.html` file with a URL. That means all that code lives somewhere else on the internet and each time your project loads you go find it at that web address.  Since now you know how to add the p5.js file locally to your project and link to a local file the way you did with the p5.sound.js file, it might be a good time to repeat the process we went through above with the main p5.js library.  You may notice that things load a little quicker!

## Mini-Challenge

Add sound to an existing project!  A bouncing ball can make a boing when it hits a wall, a rocket can make a loud sound when it launches and a sonic boom as it leaves the screen, when the first circle wins the race it can trigger a congratulatory "TA-DA", or maybe your favorite mp3 plays the whole time while a project is running. Try to make sounds tied to events happening from the user or on the screen.

## Resources

- [Sound Tutorial at the Coding Train](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6aFcVjlDAkkGIixw70s7jpW)
- [`p5.sound.js` Library Documentation](https://p5js.org/reference/#/libraries/p5.sound)

There are tons and tons of resources to find free sound effects online, here are a few, try googling if you can't find what you need here

- [Sound Bible](http://soundbible.com/)
- [Free Sound](https://www.freesound.org/browse/tags/sound-effects/)
- [Free SFX](http://www.freesfx.co.uk/)

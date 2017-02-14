# Attributes for Links and Images

In this section, we're going to learn how to use attributes inside of our HTML elements. Attributes provide extra information to the element, like where a photo is, or where a link should direct users to.

![html attributes syntax](https://s3.amazonaws.com/upperline/curriculum-assets/html/attribute-syntax.png)

##  Linking with <a> Tags
To create a link to another website or page in your project, use the anchor `<a>` tag. Surround whatever content you want to link with an opening and closing `<a>` tag. The `<a>` tag includes the attribute `href`, which points to the address that the link will send users to. For example:

```html
<a href="www.google.com">
  <h2> Click here for my favorite search engine </h2>
</a>
```

### Linking to Pages in your Project
To link to another HTML page in your project, use the file's *relative path* as the `href` attribute. For example, if you have an 'about us' page at the same level as your index page, you can link to it like so:

```html
<a href="./about.html">
  <h2> About Us </h2>
</a>
```

## Adding Images
Without any images, your website will be pretty boring... Let's add in an image or two.

Use the `<img>` tag (which doesn't need a closing tag) to add an image to your site. The `src` attribute links to the location of the image (either online or in your project directory).

```html
<img src="http://thecatapi.com/api/images/get?format=src&type=gif">
```
(To get the source of an image, find any image online, and right/alt click it and select "copy source" or "copy image URL".)

## Extra: Audio and Video
Here are a few tags to look up and experiment with. We won't tell you much more since there is amazing documentation online, and part of learning to program is being able to sift through all of the resources available to you!

+ <audio>
+ <video>
+ <iframe>
+ <canvas>

+ Labs
  + Fix the broken links
  + Harder linking within directories
  + Images that are links to your favorite sites
  + Unscramble Basic
  + Unscramble Challenge
  + Work on your personal page

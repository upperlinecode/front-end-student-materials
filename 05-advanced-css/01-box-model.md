# The Box Model

Every single element on every HTML page is inside of a rectangular box. Every image, header, paragraph, div, video - everything. But don't take my word for it. Go to your favorite website and open up the developer tools. Add the following CSS rule:

```css
*, *:before, *:after {
    border: 1px solid red;
}
```
![Wikipedia with rectangles](https://s3.amazonaws.com/upperline/curriculum-assets/css/Wikipedia-box.png)

We've just added a solid red border to every element on the page (using the * wildcard selector) and you can see - a whole lot of rectangles!

## What is the Box Model?
The box model is the framework we use in HTML and CSS to style and position elements. Each element on the page is its own 'box' - I actually like to think of boxes as picture frames.  

![framed pictures](https://s3.amazonaws.com/upperline/curriculum-assets/css/framed-pics.jpg)

Look at the picture above and you'll notice that each picture have some characteristics in common.

+ First, there's the content itself (in this case, the image). It has a **width** and **height**.
+ Moving outward, we next have that white space, which we call **padding**.
+ After the padding, we hit the picture frame itself. In CSS we call this the **border**.
+ Last, we have the space beyond the frame that distances it from the other frames on the wall - this is the **margin**.

![box model gif](https://s3.amazonaws.com/upperline/curriculum-assets/css/BoxModel.gif)

Each of these properties (width, height, padding, border, and margin) can be modified in css. Take a minute to play around with them by opening up developer tools and changing their values.

## Page Layout
Our websites are still probably not as well styled as we want them to be, and that's most likely because our content isn't laid out in an interesting way. Without an understanding of the box model, our layouts end up being pretty boring. Elements follow each other one at a time - there aren't any sidebars, and the spacing between elements just doesn't look right.

The box model allows us to get really creative with the way we put content on the screen. By placing our content (text, images, etc) inside of divs, and giving those divs classes, we can modify their position and size to improve the layout of our page.

**CSS Layout is HARD. We're going to learn a bit here, but we'll be using layout frameworks later on to make our lives easier!**

## Learn Layout
To learn about different ways of laying out content, head to [Learn Layout](http://learnlayout.com/) and walk through their lesson (They explain layout way better than we can!). Then come back to try your hand at some basic layout labs!

# Resources
+ [CodeAcademy - CSS Positioning](https://www.codecademy.com/courses/web-beginner-en-6merh/0/1#)
+ [Learn Layout](http://learnlayout.com/)
+ [CSS Tricks - The Box Model](https://css-tricks.com/the-css-box-model/)
+ [Shay Howe on the Box Model](http://learn.shayhowe.com/html-css/opening-the-box-model/)

+ Labs
  + Celebrity Photo Wall
  + CSS Zen Garden

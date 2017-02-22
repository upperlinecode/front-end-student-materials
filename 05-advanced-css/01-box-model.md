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

+ Types of Layout (display: float, block, inline etc)

# Resources
+ [CodeAcademy - CSS Positioning](https://www.codecademy.com/courses/web-beginner-en-6merh/0/1#)
+ [Learn Layout](http://learnlayout.com/)
+ [CSS Tricks - The Box Model](https://css-tricks.com/the-css-box-model/)
+ [Shay Howe on the Box Model](http://learn.shayhowe.com/html-css/opening-the-box-model/)

+ Labs
  + Celebrity Photo Wall
  + CSS Zen Garden

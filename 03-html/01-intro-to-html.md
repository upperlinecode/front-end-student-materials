# HTML Fundamentals

## What is HTML?

HTML, or *Hypertext Markup Language* is the language of the web--every time you load a web page you are loading a long page of HTML code, and being able to write and understand HTML is the very first step in becoming a real developer.
Not only that, but HTML is here to stay. You've probably head about a lot of computer languages, but HTML has been **the** language of the web for the last ~25 years, and it's not going anywhere.
Think of HTML as the skeleton of a webpage - it provides the **content** while javascript and css provide the *styling*.

## Getting Started  
HTML is written in .html files. To create a new webpage, use your terminal or finder to create a new file called `my_page.html` (you can name it anything you want). Open the file up in your text editor if you want to follow along.

## General Syntax
+ HTML elements are written using tags. Tags have an opening tag surrounded by angle brackets (e.g. `<tag>`) and a closing tag that has a slash after the first bracket (e.g. `</tag>`).

```HTML
<tag>
  Content
</tag>
```
For example, if we wanted to create a paragraph, we'd use the `<p>` opening and closing tags:

```HTML
<p>
  This is a paragraph about how great polar bears are. Aren't they just the best?
</p>
```
+ Elements can be placed inside of other elements:
```HTML
  <parent>
    <child>
      This content is inside of the child tag, which is inside of the parent tag. Keep an eye on indentation to see which is the parent and which is the child!
    </child>
  </parent>
```

## Structure of an HTML Page
**Every** webpage has a basic layout that is the same. It looks like this:

```HTML
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
  </body>
</html>
```
**Let's Break it down:**
+ `<!DOCTYPE html>` - This tag tells your browser that the rest of text that is about to follow is apart of an HTML document. If you leave it out, some browsers won't 'know' what type of document they are looking at (computers are dumb), and the page will break. It's a little boring, but you should have it.
+ `<html>` - The most basic HTML tags are simply `<html>` and `</html>`, and **all the content of your pages will be written inside these tags.**
+ `<head>` - The `<head>` contains information *about* your website, but not actual content that will show up on the page (think of it as the 'brains' of your webpage.) It will contain things like links to stylesheets and code that will make your page beautiful and interactive.
+ The `<body>` contains all the content of your page that will actually show up on the screen. 90% of the HTML you write will go inside the `<head>`


## Proper Indentation - HTML as a Tree Structure
Indentation is **super important** to writing good HTML. I know it's a pain, but trust me, it's going to make you a way better developer. Remember how HTML is made up of tags inside of tags inside of tags? The indentation shows us which tags belong to each other, sort of like a family tree.

```HTML
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h1>This is a header </h1>
    <p> This is a paragraph about penguins. Way better than polar bears!</p>
  </body>
</html>
```

**[INSERT FAMILY TREE OF HTML CODE ABOVE]**

Look at the examples below for terrible, ok and great indentation:

### Gross

```html
<!DOCTYPE html> <html><head></head><body><h1>Hello World</h1></body></html>
```

### OK: Still Needs Work Indenting

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
<h1>Hello World</h1>
</body>
</html>
```

### Go Work at Google!

```html
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```
## Viewing your Page

+ On Cloud9:
Click on the "Preview" Button, and then select "Live Preview File"

![preview live preview](https://s3.amazonaws.com/upperline/curriculum-assets/html/preview+live+preview+)

+ On your Mac/PC:
In the command line, navigate the folder with your html page and type `open filename`, replacing "filename" with the name of your HTML page.


## Adding Content

At this point, you're ready to add content to your first web page!

Experiment with the following tags by adding them inside the body of your html document! What do each of them do? What do you think they stand for?
+ `<h1> This text is big and bold! Like my paintings of koalas. </h1>`
+ `<h2> What about this text? </h2>`
+ `<h3> And what about this text?? </h3>`
+ `<p> What do you think p stands for? Here I will write a paragraph about the various things I find interesting about Koalas.  </p>`
+ `<div> The DIV tag exists to make a "divider" to keep your page organized, but you'll be surprised at how often you'll end up using it </div>`
+ This next tag closes itself (note the slash right at the end of the tag) and it doesn't have anything that goes inside it: `<hr />`
+ Same here: `<br />`
+ **EXPLORE!** Go online and look at other tags you can use. Check out the resources section below for more!

## Resources
+ [HTML Cheat Sheet](http://www.simplehtmlguide.com/cheatsheet.php)
+ [Shay Howe's Awesome HTML and CSS Tutorial](http://learn.shayhowe.com/html-css/)
+ [Mozilla Thimble](https://thimble.mozilla.org/en-US/?ref=webmaker.org) - Great for playing with other peoples' projects.
+ [Mozilla X-Ray Goggles](https://goggles.mozilla.org/) - Super cool tool for changing existing websites.
+ [HTML Dog](http://www.htmldog.com/guides/html/beginner/) - Solid tutorial
+ [HTML Examples](http://www.htmlandcssbook.com/code-samples/) - Use 'Inspect Element' to look at the code behind these examples.

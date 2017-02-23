# Using Google Fonts in CSS

Your browser comes with a very limited number of fonts, which means that your pages can only look so cool. If you really want to spice it up, use Google Fonts to pick from an enormous collection of font styles!

## Step 1: Find your font

Navigate to [Google Fonts](https://fonts.google.com/) and browse around until you find a font that you like.

When you've found the font you like, click on the + button to add it to your 'font cart'.

![google-fonts](https://s3.amazonaws.com/upperline/curriculum-assets/css/google-fonts.gif)

## Step 2: Import your Font

Open up your selected fonts, and click on the "@import" tab, and then copy the line of code that starts with `@import`. It should look something like this:

```css
@import url('https://fonts.googleapis.com/css?family=Pangolin');
```
Paste this line in in at the top of your stylesheet.

## Step 3: Use your Font

You can now use the font in your styling, using the `font-family` property:

```css
  h1 {
    font-family: 'Pangolin';
  }
```

That's all there is to it!

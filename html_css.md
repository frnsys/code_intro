All web pages must have the same basic HTML tag structure (the content inside the tags can change):

```html
<html>
<head>
    <title>Your title goes here!</title>
    <style>
    </style>
</head>
<body>
Main content goes here!
</body>
</html>
```

You'll spend your time primarily in two places:

- between the `<body></body>` tags, which is where your page's content will be (what's _in_ the page). HTML is what we use to structure the page content.
- between the `<style></style>` tags, which is where your page's style will be (how the page _looks_, i.e. affects colors, positioning, etc). CSS is what we use to style the page content.

From now on, if you see any HTML, assume it goes inside the `<body></body>` tags.

### Basic Tags

Some HTML tags have default styles. For instance:

```html
<h1>Hello world</h1>
```

If you write this and view your page, you'll see that the font is big and bold.

There are variations of this tag: `h1`, `h2`, `h3`, `h4`, `h5`, and `h6` (remember these must be surrounded by `<` and `>`, and must be accompanied by its closing tag -- I'm going to omit these from here on for brevity but you need to include them in your code).

Another note on terminology: _tags_ define _elements_. So the `h1` tags define an `h1` element (for our purposes, the terms are somewhat interchangeable).

Other tags you will use frequently include:

- `p`: "paragraph" tags, for grouping text
- `b`: "bold" tags, for making text bold
- `em`: "emphasis" tags, for making text italic
- `div`: for grouping other elements together
- `a`: "anchor" tags, for defining links
- `img`: "image" tags, for displaying images
- `ul`/`ol` and `li` tags: "unordered list"/"ordered list" and "list item" tags, for displaying lists of things

The `a` and `img` tags introduce a new concept: _attributes_.

Here's an example of using an `a` tag:

```html
<a href="https://youtube.com">Click me</a>
```

You'll see the opening tag here has more than just `a` in it. It also has `href="https://youtube.com"`. The `a` tag has an attribute called `href` which you set equal to the URL you want the link to go to.

For the `img` tag it's very similar:

```html
<img src="http://weknowmemes.com/wp-content/uploads/2012/04/interesting.jpg">
```

Here we use an attribute called `src` and set it to the URL of the image we want to display. (Also note that the `img` tag is one of the very few tags that doesn't have a closing tag).

### Nesting

You will often _nest_ tags together.

For example, to display a list of things, I could use the `ul` and `li` tags:

```html
<ul>
    <li>Eggs</li>
    <li>Milk</li>
    <li>Bread</li>
</ul>
```

Here the `li` tags are _nested_ within the `ul` tags.

We could go further and put links in our list items:

```html
<ul>
    <li><a href="https://www.google.com/search?q=eggs">Eggs</a></li>
    <li><a href="https://www.google.com/search?q=milk">Milk</li>
    <li><a href="https://www.google.com/search?q=bread">Bread</li>
</ul>
```

### Example

Here's a more complete example that brings together these ideas:

```html
<html>
<head>
    <title>My Grocery List</title>
    <style>
    </style>
</head>
<body>
<div>
    <h1>Hello!</h1>
    <p>This is my <b>grocery list</b>. I hope you like it.</p>
    <img src="http://weknowmemes.com/wp-content/uploads/2012/04/interesting.jpg">
</div>
<ul>
    <li><a href="https://www.google.com/search?q=eggs">Eggs</a></li>
    <li><a href="https://www.google.com/search?q=milk">Milk</li>
    <li><a href="https://www.google.com/search?q=bread">Bread</li>
</ul>
</body>
</html>
```

## Styling

So what if we want to change how the page looks? Fonts, colors, and so on? We use a language called CSS.

The basic way CSS works is:

1. Choose a _selector_: this can be a tag name, e.g. `h1`, or a _class_, which is described below.
2. Write some _rules_ about how elements matching that selector should look.

For example (remember, all CSS goes inside the `style` tags):

```css
h1 {
    color: red;
    font-style: italic;
}
```

This makes it so that everything in `h1` tags are red and italicized.

You might run into an issue here. What if you have a few `h1` tags on your page, but you want some of them to be red, and some of them to be blue? Can you be more selective in how you target them?

Yes! One very important attribute that is available to all tags is the `class` attribute. This lets us target elements much more carefully. For example:

```html
<h1 class="important">This text is really important</h1>
<h1 class="chill">This text is not as important</h1>
```

Then we can write CSS rules to target these separately. When using a tag name as a CSS selector, we just use the tag name, e.g. `h1`. When using a class as a CSS selector, we use the class name prefixed with a `.`:

```css
.important {
    color: red;
}
.chill {
    color: blue;
}
```

So far you've seen the `color` and `font-style` rules, but there are many more:

- `font-size`: sets font size (use `px` or `em`, e.g. `20px` or `2em`)
- `font-family`: sets font, some options include `"Helvetica"`, `"Georgia"` (note the quotes are required!), `sans-serif`, `serif`, `monospace` (note no quotes for these last three!)
- `padding`: sets padding around elements (also in `px` or `em`)
- `margin`: sets margin around elements (also in `px` or `em`)
- `text-align`: sets text alignment (can be one of `left`, `right`, `center`, or `justify`)
- `width`: sets element width (also in `px` or `em`)
- `height`: sets element height (also in `px` or `em`)
- `background`: sets background (can be a color, e.g. `red`)
- `text-shadow`: sets shadow for text (for example: `2px 2px 2px rgba(0,0,0,0.2)`)
- `box-shadow`: sets shadow for an element (for example: `2px 2px 2px rgba(0,0,0,0.2)`)

__A note on colors__: so far we've used color names as colors, e.g. `red`, `blue`. But more typically you'll use the _hexadecimal_ color, since you can be much more precise than a color name. You can use [this tool](https://www.google.com/search?q=color+picker&ie=utf-8&oe=utf-8) to pick a color and see its hexadecimal value. Then you'd use it like so:

```css
h1 {
    color: #4286f4;
}
```

Another way of specifying a color is with its RGBA (red-green-blue-alpha) values. This lets you get transparent colors:

```css
h1 {
    color: rgba(255,0,0,0.2);
}
```

Here's a more complete example:

```html
<html>
<head>
    <title>My Grocery List</title>
    <style>
        .important {
            color: red;
            text-align: center;
        }
        .welcome {
            font-style: italic;
            padding: 2em;
        }
        a {
            color: green;
        }
    </style>
</head>
<body>
<div>
    <h1 class="important">Hello!</h1>
    <p class="welcome">This is my <b>grocery list</b>. I hope you like it.</p>
    <img src="http://weknowmemes.com/wp-content/uploads/2012/04/interesting.jpg">
</div>
<ul>
    <li><a href="https://www.google.com/search?q=eggs">Eggs</a></li>
    <li><a href="https://www.google.com/search?q=milk">Milk</li>
    <li><a href="https://www.google.com/search?q=bread">Bread</li>
</ul>
</body>
</html>
```

There are many more CSS rules than the ones I've shown here. If you want to explore further:

- <https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>
- <http://cssreference.io/>

__Remember__ you can also go to any webpage, right-click and click "Inspect" to poke around at what HTML/CSS is being used there!
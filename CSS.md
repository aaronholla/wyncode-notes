# Intro to CSS

CSS = Cascading Style Sheets

Tells the browser how elements should look on the screen. Lets you modify specific elements to look a certian way. Applying styles.

## User agent stylesheet

Each browser has default styles that it sets for elements.

## Flexbox

> Use Spans to group inline elements. This will help to group for spacing using flexbox.

## CSS Grid

new. css grid. Later we will go over css grid.

```css
#box {
    display: grid;
    place-items: center;
}
```

```css
#language-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 10px;
    padding: 0;
}

#language-list li {
    width: 250px;
    margin: 0 auto;
}

#language-list li img {
    width: 100%;
}
```

Grid template Columns - set the columns names and widths for the grid.
1fr - fraction of the remaining space

## Seperation of Concerns
A software design pricinple.
Best practive to keep html and css seperate. All css in one place, inline styling is usually not best practice. However there are times where inline may make more sense.

Creating seperate files for different parts of the page can help to seperate your css. A file for the nav styles, a file for the footer, etc.

## CSS Selectors

```
selector { property: value; }
```

```css
h1 {
    color: red;
}
```

use id and classes to target specific elements

> WARNING: id's and classes are case sensitive

tag uses the tag so `a` would use uses `a{}`  
id uses `#`  
class uses `.`  
universal uses `*` - select everything. All the tags!
- commonly used for fonts

## Pseudo Selectors
Access lifecycles of elements instead of just selecting the actual element.

> pseudo class use `:` pseudo elements use `::` 

```css
/* when mouse moves over input 8 */
input:focus {
    font-size: 18px;
}

/* before and after element */
blockquote::before{
    content: open-quote;
}
blockquote::after{
    content: close-quote;
}
```

Link Pseudo Selectors
```css
a:link {
    color: yellow;
}
a:visited {
    color:red;
}
a:active {
    color: green;
}
a:hover {
    color: fuchsia;
}
```

## Attribute Selector

Find elements based on the attributes it has. or a value of an attribute

```css
/* any element with type attribute that has value of text */
[type="text"] {
    background-color: yellow;
}

/* any input element with type attribute that has value of text */
input[type="text"] {
    background-color: yellow;
}

/* the first of the given selector */
input:first-of-type {
    background-color: yellow;
}

/* anything with a type */
[type] {
    background-color: yellow;
}
```

## Comments

> Over comment your css as much as possible.

```css
/* This is a CSS comment */
```

## Linking CSS in HTML
When linking cascading still matters. The last css file imported will win.
```html
<link rel="stylesheet" type="text/css" href="css/global.css">
```
## Cascading and inheritance

Cascade - certian styles overwrite others based on the order.

Whatever is last in the file will win.

tag selector  1  
class selector  10  
id selector  100  
inline styles  1000  

Exception to this is if you use `!important` it will win no matter what.

> Try to avoid `!important`, usually a sign that something is overwriting in the css.

```css
color: red !important;
```

## Combining Selectors

this kind of tag with this class or id

```css
h3.maybe_blue {

}

a#maybe_blue {

}
```

> can put multiple classes on same element

Can select many elements in one go using commas to seperate selectors.
```css
h1, h3 {
    color: red;
}
```

## Decendents or Children
seperate with a space to get any child regardless of nesting
```css
#main-section h1 {

}
```

use `>` to target only one level of nesting. A direct decendent.
```css
#main-section > h1 {

}
```

## Styling Text

### Font Family

use font-family to set the fonts.  

google fonts (fonts.google.com) - Roboto as an example

<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">

use the star `*` to apply it to the whole page.

```
* {
    font-family: 'Roboto', sans-serif;
}

```

font-size - sets the font size.

## Styling Boxes

Include padding and border in the width. Will not make it bigger than the width you provide even if there is border and padding on it.

```css
* {
    box-sizing: border-box;
}
```
### Padding  
adds space inside to move content in away from the edges  

### Margin
push content away from the edges on the outside

### Border

Width, Style, Color of the border.

border-width  
border-style (required)  
border-color  

```css
border: width style color;
```

example:

```css
border: 5px solid red;
```

You can also define borders for specific sides individually.

```css
border-left: 5px solid red;
border-right: 5px solid red;
border-top: 5px solid red;
border-bottom: 5px solid red;
```

### Display

Inline elements render left to right. Can no loger apply margin or padding left and right.

Block elements render vertically on top of each other display on a new line and take up all available space on the line.

> use `display: inline-block;` if you want inline elements that can have margin and padding on all sides.

To prevent a space between inline-block elements 
```css
ul {
    font-size: 0;
}
li {
    font-size: 1rem;
}
```

### Position

#### Static
default for divs

#### Fixed
stays in posistion no matter scrolling. fixed to window.
#### Relative

#### Absolute
only use sparingly. 
## Media Queries

A way to make web pages responsive. Can set styles based on (screen size?) mobile vs desktop.

```css
@media only screen and (max-width: 800px) {
    .box {
        background-color: yellow;
    }
}
```

## Units - Measuring Length

px - it attempts to represent one pixel on the screen  
em - multiplier of fonts around them  
rem - length relative to the base font-size of the html element  
percent - a percentage of the space needed to render the content inside the element  
1fr - fill the screen?
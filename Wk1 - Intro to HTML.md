# Intro to HTML

d. HTML - Hyper Text Markup Language  

d. semantic - more descriptive names that describe the structure not the way it looks. 

d. DOM (Document Object Model) - Browsers understanding of what will be on the page and how it will look. Browser will display the contents of the dom. Browsers convert html and css into the dom

W3C (http://www.w3.org/) - The org responsible for Web standards.

HTML5 Specification (http://www.w3.org/TR/html5/)

CanIUse Feature Standards (https://caniuse.com)

Validating HTML (https://validator.w3.org/)

> markup language is not a programming language

> Browsers ignore whitespace, would need to use css  

> URLs should be all lowercase and cannot have spaces... spaces get replaced with %20

## Tags

The tag has attributes. In the below code the href is an attribute of the a tag that has a value.

```html
<a href="https://www.wyncode.co">Wyncode</a>
```


There are block level elements that force loading a new line create a new block and inline elements that by default will be rendered inside.

## Boilerplate
This is the most basic html to get a valid html5 document
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>My Document</title>
  </head>
  <body>
    
  </body>
</html>
```

## Comment

They don't show in the browser. Only visible in the code.

```html
<!-- This is a comment -->
```

## Classes and Ids

Classes and Ids are used to tag an element so that you can style it using css or target with javascript. An element can have both class and id on the same element.

```html
<div id="users">
    <div class="actor" id="bill_murry">
        <h1 class="name">Bill Murray</h1>
        <img src="http://fillmurray.com/200/200" alt="bill murray" class="image"/>
        <a href="/users/1" class="button">View Bill's profile</a>
    </div>

    <div class="actor" id="nick_cage">
        <h1 class="name">Nick Cage</h1>
        <img src="http://www.placecage.com/200/200" alt="nick cage" class="image" />
        <a href="/users/1" class="button">View Nick's profile</a>
    </div>

    <div class="actor" id="stevey_segal">
        <h1 class="name">Stevey Segal</h1>
        <img src="https://www.stevensegallery.com/200/200" alt="steven segal" class="image"/>
        <a href="/users/3" class="button">View Stevey's profile</a>
    </div>
</div>
```

## HyperLinks

Use the anchor tag `<a></a>` to create links  
Use target attribute to open in new tab

```html
<a href="https://www.wyncode.co">
  Wyncode
</a>

<a 
  href="https://www.wyncode.co"
  target="_blank"
>
  Wyncode
</a>
```

## Images

Image tags have no content inside so they are self closing.

src - 
alt - text to describe the picture for screen readers

```html
<img src="https://picsum.photos/200/300" />
```

## Paragraphs

`p` tags stack vertically

## Divs

Divs are wrappers for content to store them. Mostly used for styling.  

Divs stack vertically by default.

```html
<div><!-- content here --></div>
```

## Spans

Inline elements. mostly used for styling later.

```html
<span>Text</span>
```

## Common Attributes

`id` is used to tag an element for styling with CSS later, usually, an element with an id only appears once on a page.

`class` is used to tag an element for styling with CSS or selecting an element with javascript. Unlike id usually, many elements will share the same class name.

`src` is used for loading external content mostly used with img or script elements.

`href` is used in link and anchor elements to specify a URL to link to or file to load.

`title` is used to display extra information about an element in a tooltip

`alt` is used as fallback text to load if an image fails to load, or if a user is using a screen reader to navigate it will be used to describe the image.

`style` is used to input styling for an element such as color or size.

`disabled` is used on interactive elements to disable the use of them. You will not be able to do anything with a disabled element it will be greyed out.

`hidden` is used to hide an element from the screen when the content is no longer relevant to the user. Commonly used to hide element until it is needed and then can be turned visible by using javascript.

## Nesting

Use the different elements as building blocks to build up the page. Elements can have children to future structure the page.

```html
<div><p><a href="#"></a></p></div>
```

## Forms

https://www.w3schools.com/html/html_form_elements.asp
https://www.w3schools.com/html/html_form_attributes.asp

method - get, post, delete, (patch, put) change something existing  
action -  where are you submitting to

```html
<form method="" action="">
  <label>First Name</label>
  <input 
    id="first_name"
    type="text"
    name="first_name" 
  />
</form>
```

> The default behavior of a form is add query perameters after question mark in the page url

Example URL:
```
http://example.com/html_demo.html?inputname=textinput
```

## Inputs

https://www.w3schools.com/html/html_form_input_types.asp

Inputs are self closing tags so you don't need a second closing tag. the forward slash `/` is optional.


```html
<input id="first_name" type="text" name="first_name" />
```

*type - text, numbers, range, date, color, password, checkbox, email, tel, radio, hidden, reset  
*name - the name of the query perameter  
autocomplete - false, true - use to turn off autocomplete on inputs

## Datalist
A filterable predefined list of dropdown options.
```html
<input list="browsers">

<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```

## Radio Select

A select that shows circle inputs and can only select one at a time

```html
<label>White Space</label>
<input type="radio" name="tabs_or_spaces" value="tabs">
<label for="tabs"></label>
<input type="radio" name="tabs_or_spaces" value="spaces" checked>
<label for="spaces"></label>
```

## Select

A form input to be able to have a dropdown.

```html
<select name="" id="">
    <option value="html">HTML</option>
    <option value="css">CSS</option>
    <option value="js">JavaScript</option>
</select>
```

## Button

There are different ways to make buttons.

```html
<input type="button" value="Submit" />

<button type="button">Do Stuff</button>

<input type="submit" value="Go" />
```

## Unordered List

```html
<ul>
  <li></li>
</ul>
```

## Article

The article element should only be used for content that can be plucked from the website and displayed anywhere and have it make sense.

They have their own headers, footers, and document outline.

```html
<article>
  <h1>Semantic HTML</h1>
  <p>By Troy McClure. Published January 3rd</p>
  <p>This is an example web page explaining HTML5 semantic markup.</p>
  <!-- ... -->
  <p>This fake article was written by somebody at InternetingIsHard.com, which
     is a pretty decent place to learn how to become a web developer.</p>
</article>
```

## Section

the section element is the same as article but it doesn;t have to be used for displaying on another site.

## Time

Helps display time on the page and make it easily readable by search engines.

![time format](https://internetingishard.com/html-and-css/semantic-html/datetime-format-d0c825.png)

```html
<time datetime='2017-1-3 15:00-0800'>January 3rd</time>
```

## Address

use to include contact information on a page... not for physical addresses

## Image Formats

.jpg - used to handle large color pallettes, good for lots of gradients  
.gif - animation, has transperancy but not high quality use .png instead if no animation. never use for photos.  
.png - great for anything not a photo or animation, has transperancy  
.svg - great at scaling in size without loosing quality
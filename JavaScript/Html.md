What is HTML ?
=============

HTML stands for Hyper Text Markup Language and is one of the original languages of the web. HTML contains a set of elements that create the structure of a web page. We need HTML because it provides the support and structure for your web page.

Elements and Tags
==================

HTML consists of a series of elements, which you use to enclose, wrap, or mark up different parts of the content to make it appear or act a certain way. HTML tags are used to markup the page so the web browser knows how to format and structure the text layout.

With this minor adjustment, the web browser knows how the page should be formatted. The HTML Elements can use :

* `<h1>` - represents a header or title
* `<p>` - represents a paragraph of text
* `<div>` - represents a division
    the <div> has an attribute (align) that moves its positioning to the right of the page.

Each HTML element has its own set of characteristics that are applied to the formatting of the web page. For example, the `<h1>` element increased the text size and adjusted the font weight to bold and the `<p>` element added a line breaks and grouped text together.

To apply an element, you need to use "tags". The general syntax of an HTML tag is:

`<TAG> TEXT </TAG>`

Tags are the building blocks or lego pieces you add to your web page to build the structure and layout.

ANATOMY OF AN HTML ELEMENT:
--------------------------

An element is an individual component of HTML such as paragraphs, headings, tables, lists, links, images, etc.

A tag marks the beginning and end of an element in your document (web page) and contains characters that indicate the purpose of the tag.

![](https://learndotresources.s3.amazonaws.com/workshop/5b61f79872a1ef0004c070da/element-anatomy.png)

ESSENTIAL TAGS OVERVIEW:
--------------------------

Here are some of the most commonly used HTML tags:

* Section Headings - `<h1>` - `<h6>`
The HTML `<h1>–<h6>` elements represent six levels of section headings. `<h1>` is the highest section level and `<h6>` is the lowest.

* Paragraph
    * Tag: `<p> Hello World </p>`
    * Creates and separates a block of text from its surrounding elements with a blank space
    * Paragraphs are block-level elements (we'll take a look at block vs inline elements soon)

* Anchor
    * Tag: `<a href='https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a'> This is a Hyperlink </a>`
    * The Anchor element or `<a></a>`tag creates a hyperlink
    * `href` is an attribute. An attribute provides extra configuration details or adds behavior to an element. `href` holds the reference to the link the user will be redirected to when clicked.

* Content Division
    * Tag: `
    content
    * The `div` element is a flexibile container commonly used to group related elements with one another.

Block vs Inline Elements
========================

BLOCK-LEVEL ELEMENTS
--------------------

Block-level elements take up the full width of the document (web page) and "block out" elements to its left and right. Take a look at the example below, notice how each element spans the full width of the page.

INLINE ELEMENTS
--------------

Inline elements stay on the same line and do not consume the available width, in other words, inline elements sit next to other inline elements. 

Attributes
===========

HTML Elements can have additional information associated with them, called attributes. We've seen a few attributes, such as the src attribute in an image element and the align attribute in a division (`<div>`) element.

Attributes appear inside the opening tag of an element and their values sit inside quotation marks (or apostrophe), just like a string. Here is the generalized syntax of a tag with an attribute:

```js 
<tag attributeName="the value"> CONTENT </tag>
```

There are a few common attributes common to all HTML elements, these are called Global Attributes. The most common global attributes are:

* class
* id
* hidden
* title
* style

Elements also have specific attributes they recognize and interact with. Let's take a look at a few of the specific attributes that the input element uses.

APPLYING ATTRIBUTES
---------------------

The input element has a self-closing tag (meaning we don't need to add a closing tag) and a few of the compatible attributes can change the entire display and functionality of the input element.

The `<input>` element adds a field where you can insert text. If we wanted to inform our user what type of input to add, we can add a "placeholder" attribute that provides a hint to users what text to enter. 

Let's say our web page requires a different type of input, such as a checkbox, color value, or a file from your computer? The input element has you covered with the `type` attribute. Here are a few examples using the type attribute, notice how it changes the appearance and function of the input element.

```js
<input type='file'>
<hr> <!-- hr (horizontal rule) adds a line break -->
<input type='color'>
<hr>
<input type='checkbox'>
<hr>
<input type='radio'>
<hr>
<input type='date'>
```
Attributes can change the appearance and functionality of an element. The type attribute adds a lot of functionality and versatility to the input element but, what happens if you add the "type" attribute to a `h1`, `p` or other tags we looked at? Not much...they will just ignore the attribute. Different tags have different attributes they "care about", elements may have specific attributes they recognize such as the `href` attribute in an anchor (link) element or the `src` attribute in an image element.

Parent and Child Elements
==========================

HTML Elements can contain other HTML Elements, this is often called "nesting". Here is an example:

```js
<div>

  <h1> Child 1 </h1>
  <h2> Child 2 </h2>


</div>
```

In the example, we have 3 different elements and HTML uses a tree-like structure to name the positioning of each element (just like a family tree). Here are a few of the rules:

The outside element is called the parent element
The elements nested inside the parent are child elements or "children"
Every child element is a "sibling" to each other
Applying the naming convention to the code snippet above:

* the `<div>` element is the parent
* `<h1>` and `<h2>` are children of the `<div>` element
* `<h1>` and `<h2>` are siblings to one another
By convention, child elements are indented 2 spaces inside their parent, it's important to do this for the sake of readability. HTML handles whitespaces on its own, so it is okay to add extra spacing to make your code readable.















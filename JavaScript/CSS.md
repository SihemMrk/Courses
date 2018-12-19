What is CSS?
=============

CSS provides more control over the positioning of elements, colors, styles, shadows, animations and more. CSS stands for "Cascading Style Sheets," we'll discuss the "Cascade" in an upcoming section, for now just think of it as style sheets.

CSS is content oriented and is a bunch of rules we provide the browser. The browser applies the rules to elements (HTML elements) that we specify. CSS rules have two core components:

* Identify elements in the document (web page) we want to style
* Describe what styles (or positioning rules) to apply to the selected elements

For example, here is an `<h1>` element:

```js
<h1> Change the text color </h1>
```

How can we change the text color to green? We can't change the text color to green using HTML, let's see how to conquer this using CSS.

ELEMENT SELECTOR
-----------------

Looking at the two steps in creating a CSS rule, the first rule is to identify aka "select" the element we want to style. This is called a *CSS Selector*. There are a lot of different ways to select an element on a webpage, the first type of selector we'll explore is an element selector.

To select an element, call the element name (the tag name) and follow it with opening and closing brackets:

```js
h1 {

}
```

The selector is `h1`. The selector will select ALL elements that meet the selector's criteria. Our selector selects all h1 elements on the page (not just the first one, all of them).

PROPERTIES
-------------

```js
h1 {
      color: green;

}
```

Everything placed inside the brackets (the declaration block) are *declarations*. A declaration is a CSS property assigned to a value. Every declaration separates the property/value pair with a colon and it ends with a semicolon (check the example above).

A CSS property describes the specific CSS feature to apply to the element selected, such as the color, size, or type of font. There are roughly 360 CSS properties (most of the time, you will only use 50 - 100 of them).

Properties are assigned values, in this case, the color property is assigned the color "green". CSS knows a lot of colors by their name, but you can also assign the color property a hex, RGB value, and more!

```js
<style>
  h1 {
    color: green;
  }
</style>

<h1> The color is GREEN </h1>
```

WHERE TO ADD CSS?
-----------------

In the example above, the CSS rule was added in a `<style>` tag. This isn't considered a "best-practice", but for the purpose of this example, it is a demonstration of adding CSS that interacts with your HTML. In an upcoming section, we'll introduce how to add CSS to HTML using a `<link>` tag and a separate CSS file. For now, we'll stick with the `<style>` tag.

ADDING MORE PROPERTIES
----------------------

Let's take the `<h1>` example one step further and add additional properties. CSS can be a lot of fun since there is so much you can do with it!

ID & Class Selectors
----------------------

We already used element selectors. Element selectors need two main components:

* The element name we want to select
* A declaration block that holds each declaration or rules

Let's take a look at selecting elements on a web page using HTML class and id attributes.

HTML .CLASS ATTRIBUTE
------------------------

The *"class" attribute* is assigned a name that describes what the class represents. The name of the class can be re-used, and it allows multiple elements on a webpage to have the same styles and CSS rules. You might be saying, can't we just use inheritance for that? The answer is, maybe but it isn't the best option. As your HTML documents and CSS rules grow in size, it is harder to manage and trace what each element inherits. Instead, you can add a class to an element, and the CSS rules of the class will be applied to the element.

For example, how can we make the "good" habits green text, and the "bad" habits red text with a line through text-decoration in the example below?

Selecting the `<li>` elements with an element selector, the rules are applied to every `<li>` element, but instead, we can create two classes, one for "good" habits and one for "bad" habits to apply different rules to the `<li>` elements we want.

```js
<h1> Good vs Bad Habits </h1>
<ul>
  <li class='bad-habit'>Eating Junk Food</li>
  <li class='good-habit'>Studying during Foundations :) </li>
  <li class='bad-habit'>Watching Netflix all night</li>
  <li class='good-habit'>Going to bed at a decent hour</li>  
</ul>
```
To select a class using CSS, write the name of the class preceded by a `.`. Review the example below (selecting the `.good-habit` and `.bad-habit` classes. 

![Class-syntax diagram](https://learndotresources.s3.amazonaws.com/workshop/5b61f79872a1ef0004c070da/class-selector.png)

```js
.good-habit {
  color: limegreen;
}

.bad-habit {

  color: red;
  text-decoration: line-through;

}
```

HTML #ID ATTRIBUTE
--------------------

The *HTML ID attribute* behaves a lot like the class attribute except for one big difference, it can only be *applied to one element on the page*. It is used often with headers on a webpage. ID's have a name, just like classes. You can have multiple ID's, but you can only assign the ID once, you can't re-use it on additional elements on the page, it is unique. ID's are used often when the styling is only used in one section of the page, such as a header section, navigation bar, or the footer. The ID attribute is also heavily used when javascript is used to manipulate HTML Elements.
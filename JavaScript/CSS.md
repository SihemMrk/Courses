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

The CSS selector for an ID starts with a "hash" # followed by the name of the ID. Check the syntax in the CSS file. In the CSS file, we add styling for main, and header, but notice there isn't additional styling for the ID's first-fifth, so why did we add them?

Unlike classes, IDs have a unique browser ability that works with links (anchor elements). Scroll to the top of the page in the example, and click on "second post" or the "fifth post" link, did you notice any special behavior? You should have jumped to the section of the page that has that post. Looking at the anchor elements (`<a>`) in the HTML file, notice the href attributes, they link to an ID. If you've ever seen a "#" aka hash value, this is what the hash value is; it is an ID. We've used hash value links often throughout this workshop and others when providing links to documentation, e.g. [click here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#Linking_to_another_section_on_the_same_page). The link has a hash, which is an ID on the page linked, when you click on the link, it jumps to the section with the ID instead of loading the page from the top.

Group Selectors
=================

As we've seen, these selectors can provide a lot of control over HTML elements on a web page. Let's take a look at group selectors, which allow us to define multiple rules on a group of elements all at once.

For example, let's say we want all of our `header` elements (`<h1>` - `<h6>`) to use the `font-family` "fantasy" and `color` "teal". Two options come to mind

* Add the rules using an element selector
* create a class and assign it to every header element when used

These are both options...but there is an easier way to solve this common scenario. We can use the group selector. Here is what it looks like:

```js
<style>
  h1, h2, h3, h4, h5, h6 {
    font-family: fantasy;
    color: teal;
  }
  
  
</style>

<h1>Group</h1>
<h2>Selectors</h2>
<h3>Are</h3>
<h4>Super</h4>
<h5>Great</h5>
<h6>What do you think?</h6>
```
Here is the selector group syntax again:

```js
h1, h2, h3, h4, h5, h6 {
  font-family: fantasy;
  color: teal;
}
```

Combinators - Descendant and Child Selectors
==============================================

Let's take a look at the *descendant* and *child* selectors (combinators). Both of the combinators are based on where an element is positioned in a document. Each selectors name (descendant and child) are based on the "family-tree" terminology we've used when describing the positioning of elements relative to their surrounding elements. Combinators combine two (and possibly more) selectors to provide more control of the layout of the document.

DESCENDANT SELECTOR
------------------

The descendant selector combines two or more selectors. The first selector is the "parent" and the second selector is an element selector that is a descendant of the first selector. The first and second child are separated by a single space (the single space is the syntax used to create a descendant selector). Let's take a look at an example.

How can we apply CSS rules to the `<p>` elements nested inside the element with the `#main-content`?

* We can use a descendant selector and select all `<p>`elements that are descendants of the ID 'main-content'

Based on the HTML in the example above, here is the descendant selector we can add to select all `<p>`elements that are descendants of the ID named 'main-content'

```js
#main-content p {
  color: limegreen;
}
```
Here, we used an ID selector followed by a space, the space represents that the next selector must be a descendant of the #main-content id. 

CHILD SELECTORS
----------------

What if we only wanted to select the `<p>` elements that are direct children of `#main-content`? This is a use case for the *child selector*.

The child selector takes two selectors, the "parent" and a child, instead of a space like the descendant selector, a `>` (greater than symbol) is placed between the selectors, eg:

```js
selector > selector-two {

}
````

Here is our example refactored using a child selector, now it ONLY selects `<p>` elements that are direct descendants of id `#main-content`.

```js
<style>
  #main-content > p {
    color: limegreen;
  }
</style>
```

The Cascade
===============

CSS has inheritance and a "priority" system called [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity). Before defining these terms, let's take a look at a few code snippets and provide a context for what they represent.

Before adding our own CSS the browser has its own styling and CSS rules, it's not always the most appealing, but it is there. [Here is a link](https://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css) to the current CSS rules chrome applies to HTML elements. The stylesheets that are built-into a browser are referred to as a ["user-agent stylesheet"](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade#User-agent_stylesheets). There is no need to know all the rules of the a user-agent stylesheet a browser applies to all elements, the main concept to take away is that when you create your own CSS rules, your rules are either using the default styles set by the browser, or apply the rules you created in either your `<style>` element or a CSS file. Stylesheets an author (yourself, or the creator of the site) are called [author stylesheets](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade#Author_stylesheets).

This is the idea of the term "Cascade" in Cascading Style Sheets (CSS). There can be multiple rules that apply to an element defined in various CSS files, every stylesheet shares the same "scope". Let's take a look at an example in our own stylesheet (or `<style>` element).

```js
<style>
  h1 {
    color: blue;
    text-decoration: underline;
  }

  h1 {
    color: red;
    background-color: green;
    font-style: italic;
  }

  h1 {
    color: hotpink;
    font-family: sans-serif;    
    background-color: teal;
  }
</style>

<h1>Hello World</h1>
```
First, let's take a look at the behavior of the `<h1>` selectors. The selectors in the user-agent stylesheet and author stylesheets share the same "scope". Just like in JavaScript, if you create a variable in the global scope, it's possible to have that value re-assigned someplace else in your codebase. In the example, notice there are 3 `<h1>` selectors, with different and the same rules...so which rule "wins"?

When you have multiple *element* selectors selecting the *same element*, like `<h1>` in our example, the last element selector is prioritized. The behavior is different than re-assigning a global variable in JavaScript a brand new value, in that scenario, the original value is replaced. In CSS, some rules are replaced, while others persist from other rules on various stylesheets connected to the page.

In the example, *the last `<h1>` ruleset has the highest priority*, but notice rules from the other `<h1>` selectors are also applied.

Let's list a few observations related to why the last ruleset has the highest priority:

the color property is listed in every `<h1>` ruleset, hotpink is the color that "wins" since it is the last `<h1>` element ruleset defined on the page
the first `<h1>` ruleset sets the text-decoration property to underline, it "wins" and persists, look at the output in the example at the top of this section.
the font-style property is set in the second `<h1>` ruleset, it persists aka "wins" and the `<h1>` in the example is italicized
the background-color is defined in two rulesets, but the last `<h1>` ruleset "wins" and the background-color is teal
the text size of the `<h1>` element is not defined by the author, it is defined by the user-agents stylesheet
As you can see, the `<h1>` element is collecting CSS properties from various sources (the author and user-agent stylesheet). In addition, rules are "competing" (you can think of the C in CSS as "Competing Style Sheets") to have top priority, in the scenario we just reviewed, the last `<h1>` ruleset had the highest priority. As long as the last `<h1>`ruleset didn't override a previously defined rule, the previously defined rule is applied to the `<h1>` element in the example.Here's another example to analyze:

Here's another example to analyze:

```js
<style>
  .main {
    font-family: monospace;
    color: blue;
    font-size: 22px;
    background-color: lightgrey;
  }

  p {
    font-family: cursive;
    color: indigo;
    font-size: 100px;
    background-color: limegreen;
    font-style: italic;
    text-decoration: underline;
    
  }
</style>

<p class='main'>
  Lorem ipsum dolor sit amet a.
</p>
```

Let's take a look at the behavior of the `<p>` element ruleset (created with an *element selector*) and the ruleset for the .main class which is created with a *class selector*.

Let's discuss a few observations:

the `.main` class ruleset is defined before the `<p>` ruleset
even though the `<p>` element ruleset comes before the .main class ruleset, the rules from the `.main` ruleset have higher priority
we can know this since the font-family, color, size, and background-color are all the values from the `.main` ruleset
the only rules applied from the `<p>` element ruleset is the font-style and text-decoration properties (these properties aren't defined in the .main ruleset)
In this example, even though the `.main` class ruleset is defined BEFORE the `<p>` element ruleset, the class has higher priority. This is a different result than the first example when we worked only with element selectors. Based on these observations, let's take a look at specificity, which is a set of rules that determines which CSS rule "wins".

Specificity
=============

CSS uses a priority system to determine what rules are applied to HTML Elements. As we observed in the previous section, the "cascade" demonstrates that multiple rules can apply to the same element, specificity resolves conflicts arising from having multiple rules assigned to an element, it decides which rule "wins".

Every type of selector has a "specificity" value. There are four main specificity values.

* [type selectors (aka element selectors)](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)
* .class selectors, [attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors), [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* #id selectors
* [inline styles](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style)

We didn't discuss all the selectors in this list (which is okay!), let's focus on the selectors we know and determine their specificity.

HOW TO DETERMINE SPECIFICITY
------------------------------

Before getting wrapped into how to calculate specificity, remember the main reasons for specificity is to determine which rule applies when two different selectors select the same element, e.g.

```js
#green p {
  background-color: red;
}

p {
  background-color: blue;
}
```

In the example, both selectors target `<p>` elements (the easiest way to tell what a selector is targeting is reading selectors from right to left).

Which set of rules would be applied to the snippet? (Come back and answer this question after we discuss specificity, keep in mind, the purpose of specificity is to have a system to solve this problem!)

```js
<p id='green'>
  Hello World!
</p>
```

Once again, the primary use case for specificity is to determine what CSS rules are applied when multiple CSS rules are declared for the same element.

Specificity is based on a priority system where "type" selectors have the lowest priority, and [inline-styles](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style) have the highest priority. What is the best way to determine specificity? An easy way to determine specificity is to divide each specificity rule into categories.

![](https://learndotresources.s3.amazonaws.com/workshop/5b61f79872a1ef0004c070da/specificity.png)

not finish 

Intro to the Box Model
======================

OVERVIEW
------------------------

The CSS box model is a term used in describing the design and layout of elements in the DOM (Document Object Model). The CSS box model explains that each element is a box, and each of those boxes consists of the `content`, `padding`, `border`, and `margin`.

![](https://www.dropbox.com/s/nxhkeftnljhm7v8/boxmodel-%283%29.png?raw=1)

Let's briefly discuss each component of the box model:

* *content* is the area of the element itself.
* *padding* is the area between the content and its border.
* the *border* itself can be set using the CSS border property and takes up its own space.
* The element's *margin* is the space between the border and other elements. F

[Here is the documentation for the box model.](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_boxes/Box_model_recap)

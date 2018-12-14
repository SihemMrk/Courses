this
======


The `this` keyword is commonly confused by many professional JavaScript developers. It's a special keyword that doesn't have a static value; rather, it's defined within the scope of a function. The actual value or "thing" the this keyword refers to baffles many programmers!

`this` can refer:

*The Global Object
*An instance of a Constructor Function
*An object a method is attached to
*A specific Object (you can instruct this to be the exact object you want it to be)

Take a look at the examples below and run each code snippet. If you don't understand WHY the value of this changes, that's okay! The key concept is to see how this is used in different situations and that the this value is not static, it changes. Throughout the next few lessons, we'll go over a set of rules that outlines how to determine the value of this. Each code snippet is labeled with the rule that applies to the pattern demonstrated in the code snippet.

**DEFAULT VALUE RULE**
```js
console.log(this);
````

**DEFAULT BINDING RULE**
```js
// Function Invocation
function whatIsThis(){
  console.log(this);
}

whatIsThis()
```

**IMPLICIT/METHOD INVOCATION RULE**
```js
// Method Invocation
const tvRemote = {
    on: function() {
        this.power = "on";
        return this.power;
    },
    off: function() {
        this.power = "off";
        return this.power;
    },
    power: "off"
};

console.log(tvRemote.on());
````

**NEW BINDING RULE**

```js
// `new` Keyword (Constructor)

function Person(name){
    this.name = name;
}

const patrick = new Person("Patrick");

console.log(patrick);
```

**IMPORTANT:**
1. `this` doesn't refer to itself !
2. `this` is not a function's scope !

Call-Site & Execution
-----------------

It's been mentioned that the value of `this` is not static, it can change, and it can refer to many different values...we did not mention WHY this happens. The most important concept to determine `this` is to check the call site​ of the function that uses `this`.

When you invoke or call a function, the function creates its own. The execution context is a record of information of code executing such as where it's called (where the code is on the call stack), how the function was invoked, its Scope Chain, the value of this, and more!

JavaScript has 4 different ways you can invoke a function:

Function Invocation: `alert("TGIF!")`;
Method Invocation: `[].push("Fullstack", "Academy")`;
Constructor Function Invocation: `new Date()`;
Indirect Invocation: `Object.prototype.toString.call([])`
;
The way the function is called determines what value "this" is assigned.

Rule 1 - Default Binding Rule
----------------------------

By default, the “this” keyword references the global object for the current runtime environment (Node.js, Web Browser, etc).

Here is a code snippet demonstrating the default value / global reference rule:

```js
this;
```

Rule 2 - Implicit Binding Rule
----------------------------

The "Implicit Binding Rule" describes the case where a method references the `this` keyword. When a method uses the `this` keyword, this references the object the method is called on. This can be identified by locating the dot operator, the object the method is called on is left of the dot operator, the method is to the right of the dot.

```js
const pizza = {
  toppings: ['Cheese', 'Ham'],
  getToppings: function(){
    return "Toppings: - " + this.toppings;
  }
}
console.log(pizza.getToppings())
```

Rule 3 - Explicit Binding Rule
-----------------------------

In the context of a function, it is possible to vary the value of `this` to apply the instructions / treatments of the function in a particular context.
[Function.prototype.apply](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Function/apply) : first argument is the context applied to the function and then its second argument is an array 
[Function.prototype.call](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Function/call)) : first argument is the context applied to the function and then it calls arguments individually

Rule 4 - `new` Binding Rule
---------------------------

Have a look to constructor functions and classes.


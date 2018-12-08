FOUNDATION PART 2 
===========

ForEach method : it executes a provided function for each  array element.
forEach() executes the provided callback once for each element present in the array in ascending order. It is not invoked for index properties that have been deleted or are uninitialized (i.e. on sparse arrays).

Imperative vs Declarative Programming :
 *	Imperative : It describes « How your program should do something » ; all step are written, we write all the steps.
 *	Declarative : « What your program should do » ; Using the map method for example.

Map method : The map() method creates a new array with the results of calling a provided function on every element in the calling array.

Map is a function on the Array.prototype that takes a callback as its argument. map will create a new array by transforming each element in the array it was called upon. This transformation is determined by the callback that is passed into map. A more concise definition of mapwould be a pairing of elements from one set to another. The concept of mapping is integral to programming in a functional style. 

Example :

```js
const arrayOfNumbers = [2,3,4]
const doubled = arrayOfNumbers.map((elem) => {
  return elem*2;
});
console.log(`original array: ${arrayOfNumbers}`);
console.log(`the mapped aray: ${doubled}`);
```

Here :
 *	map - is called as a method on an array
 *	map - accepts a callback function
 *	map - returns a NEW array (the log statements show the original and mapped array)
 *	the new array is the same length as the original
 *	the callback function is called on each element from the original array and placed in the new array map returns.


Pure and Impure function :
A pure function is a function that given the same input (an argument) produces the same output and does not have any observable side effects.
Pure functions are predictable and produce the same output given the same input. Pure functions are dependent on their input (arguments) and local scope and should not manipulate make use of other state or scope in a program.
Here are a few benefits of pure functions:
 *	they are predictable
 *	since they are independent (they don't use values in their surrounding environment), they are easy to reuse in your program
 *	pure functions simplify state management (calling a pure function will not affect the state of other components of a program because pure functions have no side effects).
 *	it is easy to test pure functions since they are predictable (consider the .toBe and .toEqual, it's easier to pair these matches with a predictable return value)

An impure function is considered to have "side effects" if it manipulates the state of the program or has an observable effect on the program. Here is a short list of side effects (there are plenty more!):
 *	re-assigning a new value to a variable
 *	mutating an object


High order function and « first-class » functions :
Function in JS are considered to be « first –class ». The characteristic of first-class function is that they are treated like an object, boolean, string, number, etc.. They are treated as a value. This means they can be :
 *	Returned from a variable
 *	Passed as an argument to a function
 *	Assigned as a variable, as a method, or stored in an array

Functions that return a function are called « High order function » (and it’s a characteristic of first class function). We already used Higher order functions when we created closure.
```js
// stranger is a function
const stranger = () => {
// things is the value the stranger function returns
 return function things() {
   return "stranger things";
 }
};

const funcReturned = stranger()

console.log(funcReturned); // this is the things function
console.log(funcReturned()); // the `things` function return value

// stranger is a function
const stranger = () => {
// things is the value the stranger function returns
 return function things() {
   return "stranger things";
 }
};

stranger()(); // double parentheses
```

CallBack Function : is a function passed as an argument to another function. If the function it is passed to invokes the function, it is a callback !
Callback functions have a lot of different use such as :
 *	Event handlers (when a user clicks a button, run a callback function)
 *	After a program reads a file on the file system, run a call back function on the text
 *	When a web request is made, run a callback function on the data when it returns
 *	The map method accepts a callback function and transfors the elements in a rray


Reduce Method : Reduce is a higher order function, since it takes a function, or callback, as an argument. reduce loops over the array, and runs this function for each element in the array. That function itself has two arguments. The first is the accumulated value. In this example, it will hold our sum. The second argument represents the current element.

```js
const sum = [1,2,3].reduce(function(sum, elem) {
  return sum + elem;
}
```

Recursion : Recursion occurs when a function calls itself. It is used as an alternative to a for loop and is a declarative style of programming. Recursion is used when you can divide a problem into a smaller set of problems

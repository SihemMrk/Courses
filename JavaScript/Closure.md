Closure
==========

If we take again the function ounce:

```js
function once (callback) {
    let hasBeenCalled = false;
    return function () {
         if (hasBeenCalled === false) {
               hasBeenCalled = true;
               return callback ();
          } Else {
               return "The function has already been called";
         }
    };
}
```

To express how the closure knows that we already call "callback", I will draw a parallel with the Classes (but it's a big parallel eh, it should not be related to the principle of closures is like classes)

If we imagine the same encode but with a Class:

```js
class Once {
     constructor (callback) {
          this.hasBeenCalled = false;
          this.callback = callback;
     }
      
     callBack () {
        if (this.hasBeenCalled === false) {
            this.hasBeenCalled = true;
             return this.callback ();
        } Else {
             return "The function has already been called";
        }
     }
 }
 ```

Now to call him:

```js
var instance_once = new Once (myCallBack);
console.log (instance_once.callBack ()); // This is a message from mycallback
console.log (instance_once.callBack ()); // The function has alreay been called
```

In the class hasBeenCalled it is a booleene property of the current instance, we use its value to identify the behavior to have in the callBack method.

In the closure it is a similar concept, we define a variable boleene hasBeenCalled in the capsule of "ounce", and we use its value to identify the behavior to have in the function returned by the closure.
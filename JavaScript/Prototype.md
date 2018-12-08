Prototype
=========

Prototype is an object property that allow to define properties and methods associated to the class (or to the object).

Prior to ES5 `class` keyword, we defined classes with functions for defining the constructors. Functions are some kind of objects, that why we can define prototype on it. 

The `prototype` property is typed as an object. 


```js
function Animal(){  
}
Animal.prototype = {
    name : 'Poppy',
    bark: function(){
        return 'Ruff Ruff';
    }
}
```

**__proto__** : is an allias that exposes the prototype property.



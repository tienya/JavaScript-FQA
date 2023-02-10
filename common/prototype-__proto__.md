
# `prototype` vs `__proto__`

In JavaScript, `prototype` and `__proto__` are two related but different concepts.

`prototype` is a property that is present on every function in JavaScript. It is an object that is used as a blueprint for creating objects. When you create an object using a constructor function, the object's `__proto__` property is set to the constructor function's `prototype` property.

Here's an example:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log('Hello, my name is ' + this.name);
};

const person = new Person('John', 30);

console.log(person.__proto__ === Person.prototype); // true
```

In this example, the `Person` constructor function has a `prototype` property that is an object with a greet method. When you create a new Person object using the new operator, the object's `__proto__` property is set to the Person.prototype object. This means that you can access the greet method on the person object through its `__proto__` property.

`__proto__`, on the other hand, is a non-standard property that is used to access the prototype of an object. It is supported in most browsers, but it is not a part of the official JavaScript specification and is considered legacy. The official way to access an object's prototype is through the Object.getPrototypeOf method.

Here's an example:

```javascript
const obj = {};
console.log(Object.getPrototypeOf(obj) === obj.__proto__); // true
```

In this example, `Object.getPrototypeOf(obj)` returns the `prototype` of the obj object, which is the same as the value of the object's `__proto__` property.

In summary, `prototype` is a property of functions that is used as a blueprint for creating objects, while `__proto__` is a non-standard property that is used to access the prototype of an object. The recommended way to access an object's prototype is through the `Object.getPrototypeOf` method.

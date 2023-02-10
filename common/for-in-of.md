
# `for...in` vs `for...of`

In JavaScript, `for...in` and `for...of` are two different looping constructs that are used to iterate over objects and arrays, respectively.

`for...in` is used to iterate over the enumerable properties of an object. It loops through the properties of an object, including those that are inherited through the prototype chain. Here's an example:

```javascript
const obj = {a: 1, b: 2, c: 3};
for (let prop in obj) {
  console.log(prop + ': ' + obj[prop]);
}

// Output:
// a: 1
// b: 2
// c: 3
```

`for...of`, on the other hand, is used to iterate over iterable objects, such as arrays, strings, and maps. It loops through the values of an iterable object and does not give you access to the properties or keys of the object. Here's an example:

```javascript
const arr = [1, 2, 3];
for (let value of arr) {
  console.log(value);
}

// Output:
// 1
// 2
// 3
```

In summary, `for...in` is best used for iterating over object properties, while `for...of` is best used for iterating over the values of iterable objects.


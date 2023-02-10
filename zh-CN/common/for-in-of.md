
# `for...in` 对比 `for...of`

在 JavaScript 中，`for...in` 和 `for...of` 是两种不同的循环结构，用于分别迭代对象和数组。

`for...in` 用于迭代对象的可枚举属性。它循环遍历对象的属性，包括通过原型链继承的属性。以下是一个示例：

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

`for...of`，另一方面，用于迭代可迭代对象，如数组、字符串和映射。它循环遍历可迭代对象的值，不提供对对象的属性或键的访问。以下是一个示例：

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

总之，`for...in` 最适用于迭代对象属性，而 `for...of` 最适用于迭代可迭代对象的值。
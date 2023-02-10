
# `prototype` vs `__proto__`

在 JavaScript 中，`prototype` 和 `__proto__` 是两个相关但不同的概念。

`prototype` 是每个函数在 JavaScript 中都具有的属性。它是一个对象，用作创建对象的蓝图。当使用构造函数创建对象时，对象的 `__proto__` 属性将设置为构造函数的 `prototype` 属性。

下面是一个示例：

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

在此示例中，`Person` 构造函数具有一个 `prototype` 属性，该属性是具有 `greet` 方法的对象。当使用 `new` 运算符创建新的 `Person` 对象时，对象的 `__proto__` 属性将设置为 `Person.prototype` 对象。这意味着可以通过其 `__proto__` 属性访问 `person` 对象上的 `greet` 方法。

另一方面，`__proto__` 是一个用于访问对象原型的非标准属性。它在大多数浏览器中是支持的，但不是 JavaScript 规范的一部分，并被视为遗留。访问对象原型的官方方法是通过 `Object.getPrototypeOf` 方法。

下面是一个示例：

```javascript
const obj = {};
console.log(Object.getPrototypeOf(obj) === obj.__proto__); // true
```

在这个例子中，`Object.getPrototypeOf(obj)` 返回 `obj.__proto__`，这说明了两者是等价的。然而，因为 `__proto__` 不是规范的一部分，因此不建议在生产代码中使用它。代替地，应该使用标准的 `Object.getPrototypeOf` 方法。

总的来说，`prototype` 和 `__proto__` 是用于管理 JavaScript 对象之间的原型关系的两种不同的工具。在使用 JavaScript 创建对象时，可以使用 `prototype` 定义对象的蓝图，并通过 `__proto__` 或 `Object.getPrototypeOf` 访问对象的原型。
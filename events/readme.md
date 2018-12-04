# events 

**版本 3.0.0**

## Reflect

源码里面使用了 ES6 的 Reflect

查看 [MDN Reflect](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect)

> Reflect is a built-in object that provides methods for interceptable JavaScript operations.

Reflect 是一个内置对象，它提供拦截 JavaScript 的方法。

与大多数全局对象不同，Reflect 没有构造函数。你不能将其与一个 new 运算符一起使用，或者将 Reflect 对象作为一个函数来调用。Reflect 的所有属性和方法都是静态的（就像Math对象）。

源码里面的使用了的 `Reflect.apply` ，功能与 `Function.prototype.applay` 类似

## Symbol

ES6 新增了 symbol 类型，原生数据类型变成了6个，undefined, null, string, numbel, boolean, symbol

为什么要新增这个类型呢？

**每个从 Symbol() 返回的 symbol 值都是唯一的。一个 symbol 值能作为对象属性的标识符，这是该数据类型仅有的目的**

### Symbols 与 for...in 迭代

Symbols 在 for...in 迭代中不可枚举。另外，`Object.getOwnPropertyNames()` 不会返回 symbol 对象的属性，但是你能使用 `Object.getOwnPropertySymbols()` 得到它们。

```js
var obj = {};

obj[Symbol("a")] = "a";
obj[Symbol.for("b")] = "b";
obj["c"] = "c";
obj.d = "d";

for (var i in obj) {
   console.log(i); // logs "c" and "d"
}
```

## 参考
1. [MDN Reflect](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect)
2. [MDN Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
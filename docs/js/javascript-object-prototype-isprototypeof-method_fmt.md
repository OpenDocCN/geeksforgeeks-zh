# `isPrototypeOf()`方法

> 原文：[https://www.geeksforgeeks.org/javascript-object-prototype-isprototypeof-method/](https://www.geeksforgeeks.org/javascript-object-prototype-isprototypeof-method/)

方法`isPrototypeOf()`用于检查一个对象是否存在于另一个对象的原型链中。

`语法：`
```
prototypeObj.isPrototypeOf(object)
```

*   `object`：这是一个对象，将搜索其原型链。

`返回值：`布尔值。

`抛出的错误：`
如果`prototypeObj`未定义或为空，则会引发`TypeError`。

`示例：`

## 示例 1

```
function obj1() {}
function obj2() {}

obj1.prototype = Object.create(obj2.prototype);
const obj3 = new obj1();
console.log(obj1.prototype.isPrototypeOf(obj3));
console.log(obj2.prototype.isPrototypeOf(obj3));
```

`输出：`
```
true
true
```

`示例 2：` 此例说明了`C.prototype`、`B.prototype`、`A.prototype`和`Object.prototype`存在于对象`c`的原型链中。

## 示例 2

```
function A() {}
function B() {}
function C() {}

B.prototype = Object.create(A.prototype);
C.prototype = Object.create(B.prototype);

var c = new C();

console.log(C.prototype.isPrototypeOf(c));
console.log(B.prototype.isPrototypeOf(c));
console.log(A.prototype.isPrototypeOf(c));
console.log(Object.prototype.isPrototypeOf(c));
```

`输出：`
```
true
true
true
true
```

`支持的浏览器：`
*   Chrome 1 及以上
*   Edge 12 及以上
*   Firefox 1 及以上
*   Internet Explorer 9 及以上
*   Opera 4 及以上
*   Safari 3 及以上
# JavaScript Reflect.getOwnPropertyDescriptor()方法

> 原文：[https://www.geeksforgeeks.org/javascript-reflect-getownpropertydescriptor-method/](https://www.geeksforgeeks.org/javascript-reflect-getownpropertydescriptor-method/)

JavaScript 中的 `Reflect.getOwnPropertyDescriptor()` 方法用于获取对象的描述符。它与 `Object.getOwnPropertyDescriptor` 方法相同，但非对象目标的处理方式不同。

**语法：**
```javascript
Reflect.getOwnPropertyDescriptor(obj, key)
```

**参数：** 该方法接受两个参数，如下所述：
* `obj`：这个参数保存目标对象，它寻找属性。
* `key`：此参数用于获取属性名称的自身属性描述符。

**返回值：** 此方法返回属性描述符对象，如果目标对象不存在，则返回 `undefined`。

**异常：** 当目标不是对象时，`TypeError` 是作为结果给出的异常。

以下示例说明了 JavaScript 中的 `Reflect.getOwnPropertyDescriptor()` 方法：

**示例 1：**
```javascript
let object = {
    property1: "geeks"
};

console.log(Reflect.getOwnPropertyDescriptor(
                    object, 'property1').value);

console.log(Reflect.getOwnPropertyDescriptor(
                    object, 'property2'));

console.log(Reflect.getOwnPropertyDescriptor(
                    object, 'property1').writable);

let object1 = {
    property2: "Javascript"
};

const object3 = {
    property3: 232
};

console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property2').value);

console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property3'));

console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property2').writable);

console.log(Reflect.getOwnPropertyDescriptor
                (object3, "null" ) === undefined
);
```

**输出：**
```
"geeks"
undefined
true
"Javascript"
undefined
true
true
```

**示例 2：**
```javascript
const object1 = {
    property1: "NULL"
};

console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property2'));
console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property1').writable);
console.log(Reflect.getOwnPropertyDescriptor(
                    object1, 'property1'));

console.log(Reflect.getOwnPropertyDescriptor(
                    {val: 'hello'}, 'val'));
console.log(Reflect.getOwnPropertyDescriptor(
                    {val1: 'hello'}, 'y'));
console.log(Reflect.getOwnPropertyDescriptor(
                    [], 'length'));
```

**输出：**
```
undefined
true
[object Object] {
  configurable: true,
  enumerable: true,
  value: "NULL",
  writable: true
}
[object Object] {
  configurable: true,
  enumerable: true,
  value: "hello",
  writable: true
}
undefined
[object Object] {
  configurable: false,
  enumerable: false,
  value: 0,
  writable: true
}
```

**示例 3：** 调用非对象，出现错误。
```javascript
console.log(Reflect.getOwnPropertyDescriptor('foo', 0));
```

**输出：**
```
Error: Reflect.getOwnPropertyDescriptor called on non-object
```

**支持的浏览器：** JavaScript `Reflect.getOwnPropertyDescriptor()` 方法支持的浏览器如下：
* Google Chrome 49 及以上
* Edge 12 及以上
* Firefox 42 及以上版本
* Opera 36 及以上
* Safari 10 及以上

**参考：** [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor)
# JavaScript `handler.defineProperty()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-handler-defineproperty-method/](https://www.geeksforgeeks.org/javascript-handler-defineproperty-method/)

JavaScript 中的 `handler.defineProperty()` 方法用于定义新属性，并直接在对象上修改现有属性。它是 Proxy 对象的陷阱。

## 语法

```javascript
const p = new Proxy(target, {
  defineProperty: function(target, property, descriptor) {
  }
});
```

## 参数

该方法接受三个参数，如下所述：

*   `target`：此参数保存目标对象。
*   `property`：该参数是将要检索其描述的属性的名称或符号。
*   `descriptor`：此参数是正在定义或修改的属性的描述符。

## 返回值

该方法返回一个布尔值，用于指示属性是否定义成功。

下面的示例说明了 JavaScript 中的 `handler.defineProperty()` 方法。

## 示例 1

```javascript
const p = new Proxy({}, {
  defineProperty: function(target, prop, descriptor) {
    console.log('Type : ' + prop);
    return true;
  }
});

const desc = { configurable: true, enumerable: true, value: 10 };
Object.defineProperty(p, 'String', desc);

var xyz = {};
var proxy = new Proxy(xyz, {
  defineProperty: function(target, name, propertyDescriptor) {
    console.log('in defineProperty');
    return Object.defineProperty(target, name, propertyDescriptor);
  }
});
Object.defineProperty(proxy, 'bar', {} );
```
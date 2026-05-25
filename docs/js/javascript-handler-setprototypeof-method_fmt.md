# JavaScript `handler.setPrototypeOf()` 方法

> 原文: [https://www.geeksforgeeks.org/javascript-handler-setprototypeof-method/](https://www.geeksforgeeks.org/javascript-handler-setprototypeof-method/)

JavaScript 中的 `handler.setPrototypeOf()` 方法是 `Object.setPrototypeOf()` 方法的陷阱，它返回一个布尔值。

## 语法:

```
const p = new Proxy(target, {
  setPrototypeOf: function(target, prototype) {
  }
});
```

## 参数:
该方法接受两个参数，如上所述，如下所述:
* `target`: 此参数为目标对象。
* `prototype`: 此参数是对象的新原型或 `null`。

## 返回值:
这个方法返回一个布尔值。如果 `[[Prototype]]` 已成功更改，则返回 `true`。

以下示例说明了 JavaScript 中的 `handler.setPrototypeOf()` 方法:

## 示例 1:

```html
<script>
const handler1 = {
  setPrototypeOf(gfg, gfgProto) {
    gfg.geneticallyModified = true;
    return false;
  }
};

const gfgProto = {};
const gfg = {
  geneticallyModified : false
};

const proxy1 = new Proxy(gfg, handler1);
console.log(Reflect.setPrototypeOf(proxy1, gfgProto));
console.log(gfg.geneticallyModified);

var soo={ 
  foo:1 
} 
var proxy = new Proxy(soo, { 
  setPrototypeOf(target, newProto) { 
  } 
}); 
console.log('a' in proxy);
</script>
```

## 输出:

```
false
true
false
```

## 示例 2:

```html
<script>
const handlerThrows = {
    setPrototypeOf(target, newProto) {
        throw new Error('custom error');
    }
};

const newProto = {}, target = {};

const p2 = new Proxy(target, handlerThrows);
document.writeln(Object.setPrototypeOf(p2, newProto)); 
document.writeln(Reflect.setPrototypeOf(p2, newProto));
</script>
```

## 输出:

```
Error: custom error
```

## 支持的浏览器:
`handler.setPrototypeOf()` 方法支持的浏览器如下:
* Google Chrome 49 及以上
* Edge 12 及以上
* Firefox 49 及以上版本
* Opera 36 及以上
* Safari 10 及以上
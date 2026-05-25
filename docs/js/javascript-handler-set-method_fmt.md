# JavaScript | `handler.set()`方法

> 原文: [https://www.geeksforgeeks.org/javascript-handler-set-method/](https://www.geeksforgeeks.org/javascript-handler-set-method/)

JavaScript 中的 `handler.set()` 方法是设置属性值的陷阱。此方法返回一个布尔值。

## 语法:

```
const p = new Proxy(target, {
  set: function(target, property, value, receiver) {
  }
});
```

## 参数:

该方法接受上述四个参数，描述如下:

*   `target`: 此参数保存目标对象。
*   `property`: 此参数保存属性的名称或符号。
*   `value`: 此参数保存属性的新值。
*   `receiver`: 此参数保存分配最初指向的对象。

## 返回值:

这个方法总是返回一个布尔值。

以下示例说明了 JavaScript 中的 `handler.set()`方法。

## 示例 1:

```
function gfg() {
  this.users = "Millions";
}

const handler1 = {
  set(obj, prop, value) {
    if ((prop === 'users') && ((value % 2) !== 0)) {
      console.log('GEEKSFORGEEKS : Computer Science Portal');
    } else {
      return Reflect.set(...arguments);
    }
  }
};

const gfg1 = new gfg();
const proxy1 = new Proxy(gfg1, handler1);
proxy1.users = 1;

console.log(proxy1.users);
```
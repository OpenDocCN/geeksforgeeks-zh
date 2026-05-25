# JavaScript | handler . getOwnPropertyDescriptor()方法

> 原文: [https://www . geeksforgeeks . org/JavaScript-handler-getownpertysdescriptor-method/](https://www.geeksforgeeks.org/javascript-handler-getownpropertydescriptor-method/)

JavaScript 中的 `handler . getOwnPropertyDescriptor()` 方法是 `Object . getOwnPropertyDescriptor()` 方法的陷阱。如果属性作为目标对象的不可配置的自有属性存在，则不能将其报告为不存在。

## 语法:

```
const p = new Proxy(target, {
  getOwnPropertyDescriptor: function(target, prop) {
  }
});
```

## 参数:

该方法接受两个参数，如上所述，如下所述:

*   `target`: 此参数为目标对象。
*   `prop`: 此参数是应该检索其描述的属性的名称。

## 返回值:

此方法返回一个对象或 `undefined`。

以下示例说明了 JavaScript 中的 `handler . getOwnPropertyDescriptor()` 方法:

## 示例 1:

```javascript
<script>
const monster1 = {
  num: 4
};

const handler1 = {
  getOwnPropertyDescriptor(target, prop) {
    console.log(`Type : ${prop}`);

    return { configurable: true, enumerable: true, value: 5 };
  }
};

const proxy1 = new Proxy(monster1, handler1);

console.log(Object.getOwnPropertyDescriptor(proxy1, 'num').value);
console.log(Object.getOwnPropertyDescriptor(proxy1, 'bool').enumerable);
</script>
```

## 输出:

```
> "Type : num"
> 5
> "Type : bool"
> true
```

## 示例 2:

```javascript
<script>
const p = new Proxy({ VAL: 20}, {
  getOwnPropertyDescriptor: function(target, prop) {
    console.log('Property : ' + prop);
    return { configurable: true, enumerable: true, value: 10 };
  }
});

console.log(Object.getOwnPropertyDescriptor(p, 'VAL').value);

const obj = { a: 10 };
Object.preventExtensions(obj);
const pval = new Proxy(obj, {
  getOwnPropertyDescriptor: function(target, prop) {
    return undefined;
  }
});

console.log(Object.getOwnPropertyDescriptor(pval));
</script>
```

## 输出:

```
> "Property : VAL"
> 10
> undefined
```

## 支持的浏览器:

`handler . getOwnPropertyDescriptor()` 方法支持的浏览器如下:

*   Google Chrome 49 及以上
*   Edge 12 及以上
*   Firefox 18 及以上版本
*   Opera 36 及以上
*   Safari 10 及以上
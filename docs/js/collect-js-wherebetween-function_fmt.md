# Collect.js | `whereBetween()`函数

> 原文：[https://www.geeksforgeeks.org/collect-js-wherebetween-function/](https://www.geeksforgeeks.org/collect-js-wherebetween-function/)

`whereBetween()`函数用于过滤给定范围内的输入。在 JavaScript 中，首先将数组转换为集合，然后将函数应用于集合。

## 语法

```
data.whereBetween(key, [range]);
```

## 参数

该函数接受两个参数，如下所述：

*   `key`：该参数保存定义该键的值的键名。
*   `range`：指定范围。

## 返回值

返回范围内的过滤集合。

下面的示例说明了`collect.js`中的`whereBetween()`函数。

### 示例 1

在本例中，我们取一个集合，然后使用`whereBetween()`方法指定一个键和值范围，以检查该值并返回位于该范围内的值。

```javascript
// It is used to import collect.js library
const collect = require('collect.js');

const input= collect([
  { fruits: 'Apple', price: 200 },
  { fruits: 'Banana', price: 80 },
  { fruits: 'Papaya', price: 150 },
  { fruits: 'Grapes', price: 30 },
  { fruits: 'Cherry', price: 100 },
]);

const output = input.whereBetween('price', [100, 200]);
console.log(output.all());
```

**输出：**

```
[ { fruits: 'Apple', price: 200 },
  { fruits: 'Papaya', price: 150 },
  { fruits: 'Cherry', price: 100 }]
```

### 示例 2

```javascript
// It is used to import collect.js library
const collect = require('collect.js');

const input= collect([
  { quantity: 'Flour', price: 150 },
  { quantity: 'Rice', price: 100 },
  { quantity: 'Vegetables', price: 80 },
  { quantity: 'Fruits', price: 90 },
  { quantity: 'Pulses', price: 200 },
]);

const output = input.whereBetween('price', [90, 150]);
console.log(output.all());
```

**输出：**

```
[ { quantity: 'Flour', price: 150 },
  { quantity: 'Rice', price: 100 },
  { quantity: 'Fruits', price: 90 } ]
```

## 参考

[`https://collect.js.org/api/whereBetween.html`](https://collect.js.org/api/whereBetween.html)
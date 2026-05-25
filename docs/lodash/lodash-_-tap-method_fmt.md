# Lodash _.tap() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-tap-method/](https://www.geeksforgeeks.org/lodash-_-tap-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.tap()` 方法在 `lodash` 中用于调用拦截器。此外，该方法的主要任务是“进入”一个方法链序列，以便修改中间结果。

## 语法

```javascript
_.tap(value, interceptor)
```

## 参数

该方法接受两个参数：

*   `value`: 是给拦截器的值。
*   `interceptor`: 就是要调用的函数。

## 返回值

此方法返回 `value`。

## 示例 1

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling tap() method
let result = _([5, 6, 7]).tap(function(arr) {

// Modifying input array using push operation
   arr.push(8);
 })
.value();

// Displays output
 console.log(result);
```

**输出:**

```
[ 5, 6, 7, 8 ]
```

## 示例 2

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling tap() method
let result = _(['Geeks', 'for']).tap(function(arr) {

// Modifying input array using push operation
   arr.push('Geeks');
   })
   .value();

// Displays output
 console.log(result);
```

**输出:**

```
[ 'Geeks', 'for', 'Geeks' ]
```

## 示例 3

使用 `pop` 操作和 `tail` 方法。

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling tap() method
let result = _(['f', 'g', 'h']).tap(function(arr) {

// Modifying input array using pop operation
   arr.pop();
 })
   .tail()     // Using tail() method
   .value();

// Displays output
 console.log(result);
```

**输出:**

```
[ 'g' ]
```

**参考:** [https://lodash.com/docs/4.17.15#tap](https://lodash.com/docs/4.17.15#tap)
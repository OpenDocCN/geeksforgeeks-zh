# Lodash _.thru()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-thru-method/](https://www.geeksforgeeks.org/lodash-_-thru-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.thru()` 方法与 `_.tap()` 方法相似，唯一的区别是它返回拦截器的结果。此外，该方法主要用于通过替换中间结果来“传递”方法链序列中的值。

**语法:**

```javascript
_.thru(value, interceptor)
```

**参数:** 该方法接受两个参数，如下所述：

*   `value`: 是给拦截器的值。
*   `interceptor`: 就是要调用的函数。

**返回值:** 这个方法返回拦截器的结果。

## 示例

### 示例 1

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling thru() method
let result = _(144).thru(function(value) {
   return [value];
 }).value();

// Displays output
 console.log(result);
```

**输出:**

```javascript
[ 144 ]
```

### 示例 2

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling thru() method
let result = _('GfG').thru(function(value) {
   return [value];
 }).value();

// Displays output
 console.log(result);
```

**输出:**

```javascript
[ 'GfG' ]
```

### 示例 3

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining value
var val = ['g', 'f', 'G']

// Calling thru() method along with
// reverse and chain method
let result = _(val).reverse()
                   .chain()
                   .thru(function(value) {
    return [value];
 })
 .value();

// Displays output
 console.log(result);
```

**输出:**

```javascript
[ [ 'G', 'f', 'g' ] ]
```

这里，输出被反转，因为上面使用了 `reverse()` 方法来反转所述值的顺序。

**参考:** [https://lodash.com/docs/4.17.15#thru](https://lodash.com/docs/4.17.15#thru)
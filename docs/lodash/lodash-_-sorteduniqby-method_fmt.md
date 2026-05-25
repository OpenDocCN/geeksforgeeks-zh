# _.sortedUniqBy 方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-sorteduniqby-method/](https://www.geeksforgeeks.org/lodash-_-sorteduniqby-method/)

`_.sortedUniqBy` 方法用于返回数组中可以插入元素的最低索引，并保持其排序顺序。还有，这个方法就像 `_.uniqBy`，除了它是为排序数组设计和优化的。

**语法：**

```javascript
_.sortedUniqBy(array, [iteratee])
```

**参数：** 该方法接受两个参数，如上所述，如下所述：

*   `array`：此参数存储要检查的数组。
*   `[iteratee=_.identity]` (函数)：此参数持有对每个元素调用的迭代函数。

**返回值：** 此方法用于返回新的无重复数组。

**示例 1：** 这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

```javascript
// Requiring the lodash library 
const _ = require("lodash");

// Original array 
let y = ([1.1, 1.2, 2.1, 2.3, 2.4, 3.5])

// Use of _.sortedUniqBy() 
// method 
let index =  _.sortedUniqBy(y, Math.floor);

// Printing the output 
console.log(index);
```

**输出：**

```javascript
[1.1, 2.1, 3.5]
```

**例二：**

```javascript
// Requiring the lodash library 
const _ = require("lodash");

// Original array 
let y = ([112.1, 112.2, 122.1, 122.3, 122.4, 132.5])

// Use of _.sortedUniqBy() 
// method 
let index =  _.sortedUniqBy(y, Math.floor);

// Printing the output 
console.log(index);
```

**输出：**

```javascript
[112.1, 122.1, 132.5]
```

**注意：** 这在普通的 JavaScript 中不会起作用，因为它需要安装库 `lodash`。
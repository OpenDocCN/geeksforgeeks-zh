# 洛达什 `_.countBy()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-countby-method/](https://www.geeksforgeeks.org/lodash-_-countby-method/)

`_.countBy()` 方法创建一个对象，该对象由通过迭代运行集合的每个元素的结果生成的键组成。每个键的对应值是迭代返回该键的次数。

**语法:**

```
_.countBy(collection, [iteratee=_.identity])
```

**参数:** 该方法接受两个参数，如上所述，如下所述:

*   `Set` (`array` | `object`): 此参数持有要迭代的集合。
*   `[iteratee=_.identity]` (`function`): 此参数持有用于转换键的迭代函数。

**返回值:** 该方法用于返回合成的聚合对象。

**示例 1:** 这里，`const _ = require('lodash')` 用于导入文件中的 lodash 库。

## 示例 1

```
// Requiring the lodash library
const _ = require("lodash");

// Original array
var obj1 = ([6.1, 4.2, 6.3, 5, 7.9, 5.3, 5.1, 7.3]);

// Use of _.countBy() method
let y = _.countBy(obj1, Math.floor);

// Printing the output
console.log(y);
```

**输出:**

```
{ '4': 1, '5': 3, '6': 2, '7':2 }
```

## 示例 2

```
// Requiring the lodash library
const _ = require("lodash");

// Original array
var obj1 = (['one', 'two', 'three', 'five', 'eleven', 'twelve']);

// Use of _.countBy() method
// The `_.property` iteratee shorthand.
let y = _.countBy(obj1, 'length');

// Printing the output
console.log(y);
```

**输出:**

```
{ '3': 2, '4': 1, '5': 1, '6':2 }
```

## 示例 3

```
// Requiring the lodash library
const _ = require("lodash");

// Original array
var obj1 = (['tee', 'cee', 'dee', 'bee', 'eee']);
var obj2 = (['q', 'r', 's', 'p']);

// Use of _.countBy() method
// The `_.property` iteratee shorthand.
let x = _.countBy(obj1, 'length');
let y = _.countBy(obj2, 'length');

// Printing the output
console.log(x);
console.log(y);
```

**输出:**

```
{ '3': 5 }
{ '1': 4 }
```

**注意:** 这段代码在正常的 JavaScript 中无法工作，因为它需要安装库 lodash。
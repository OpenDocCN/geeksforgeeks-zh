# Lodash: `_.sortedLastIndex()`方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-sortedlastindex-method/](https://www.geeksforgeeks.org/lodash-_-sortedlastindex-method/)

`_.sortedLastIndex()`方法用于返回数组中可以插入元素的最高索引，并保持其排序顺序。

**语法:**
```javascript
_.sortedLastIndex(array, value)
```

**参数:** 该方法接受两个参数，如下所述：
*   `Array`: 此参数存储已排序的数组。
*   `Value`: 此参数存储要评估的值。

**返回值:** 该方法返回值应该插入数组的索引。

### 例 1:
```javascript
const _ = require('lodash');

let x = [1, 2, 3, 4, 4, 4, 5, 6, 6]

let index = _.sortedLastIndex(x, 4);

console.log(index);
```
这里，`const _ = require('lodash')`用于将lodash库导入文件。

**输出:**
```
4
```

### 例 2:
```javascript
const _ = require('lodash');

let x = ['a', 'b', 'c', 'd', 'e', 'e', 'e', 'f']

let index = _.sortedLastIndex(x, 'e');

console.log(index);
```

**输出:**
```
7
```

### 例 3:
```javascript
const _ = require('lodash');

let x = ['ajax', 'django', 'mongoDb',
       'react', 'reactnative', 'yarn']

let index = _.sortedLastIndex(x, 'ruby');

console.log(index);
```

**输出:**
```
3
```

**注意:** 这在正常的JavaScript中不会起作用，因为它需要安装库lodash。

**参考资料:** [https://lodash.com/docs/4.17.15#sortedLastIndex](https://lodash.com/docs/4.17.15#sortedLastIndex)
# Lodash: `_.takeRight()`方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-takeright-method/](https://www.geeksforgeeks.org/lodash-_-takeright-method/)

`_.takeRight()`方法用于从给定数组的末尾获取 n 个元素的数组。

**语法:**

```
_.takeRight(array, n)
```

**参数:** 该方法接受两个参数，如下所述:

*   `Array`: 此参数存储查询数组。
*   `n`: 此参数存储元素的数量。

**返回值:** 这个方法从给定的末尾返回一个包含 `n` 个元素的数组。

**例 1:**

```
const _ = require('lodash');

let x = [1, 2, 3, 4, 5, 6, 7]

let newArray = _.takeRight(x);

console.log(newArray);
```

这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

**输出:**

```
[7]
```

**例 2:**

```
const _ = require('lodash');

let x = [1, 2, 3, 4, 5, 6, 7]

let newArray = _.takeRight(x, 5);

console.log(newArray);
```

**输出:**

```
[ 3, 4, 5, 6, 7 ]
```

**例 3:**

```
const _ = require('lodash');

let x = [1, 2, 3, 4, 5, 6, 7]

let newArray = _.takeRight(x, 0);

console.log(newArray);
```

**输出:**

```
[]
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装库 lodash。

**参考:** [https://lodash.com/docs/4.17.15#takeRight](https://lodash.com/docs/4.17.15#takeRight)
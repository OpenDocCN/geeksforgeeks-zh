# Lodash _.sampleSize() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-samplesize-method/](https://www.geeksforgeeks.org/lodash-_-samplesize-method/)

`_.sampleSize()` 方法用于给出给定数组中 `n` 个随机元素的数组。

## 语法

```
_.sampleSize(array, n)
```

## 参数

该方法接受两个参数，如下所述：

*   `array`: 此参数持有样本集合。
*   `n`: 此参数存储要抽取的元素数量。

## 返回值

此方法返回一个包含 `n` 个随机元素的数组。

## 示例

### 例 1

```
const _ = require('lodash');

let x = [1, 2, 7, 10, 13, 15];

let result = _.sampleSize(x, 2);

console.log(result);
```

这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

**输出:**

```
[10, 13]
```

### 例 2

```
const _ = require('lodash');

let x = ['mango', 'apple', 'banana', 'orange', 'grapes'];

let result = _.sampleSize(x, 3);

console.log(result);
```

**输出:**

```
[ 'grapes', 'orange', 'banana' ]
```

### 例 3

```
const _ = require('lodash');

let x = [1, 'a', {'name': 'sampleSize'}, [1, 2, 3]];

let result = _.sampleSize(x, 3);

console.log(result);
```

**输出:**

```
[ { name: 'sampleSize' }, 'a', 1 ]
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装库 lodash。

**参考:** [https://lodash.com/docs/4.17.15#sampleSize](https://lodash.com/docs/4.17.15#sampleSize)
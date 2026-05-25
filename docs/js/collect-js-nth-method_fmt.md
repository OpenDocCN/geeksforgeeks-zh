# Collect.js nth()方法

> 原文: [https://www.geeksforgeeks.org/collect-js-nth-method/](https://www.geeksforgeeks.org/collect-js-nth-method/)

`nth()`方法用于创建由每第 n 个元素组成的新集合。

## 语法

```
collect(array).nth(num)
```

## 参数

`collect()`方法接受一个转换为集合的参数，然后对其应用`nth()`方法。`nth()`方法保存一个数字。

## 返回值

这个方法返回给定集合的第 n 个元素。

下面的例子说明了 collect.js 中的`nth()`方法:

## 例 1

### JavaScript

```
const collect = require('collect.js');

let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

const collection = collect(arr);

const nth_val = collection.nth(3);

console.log(nth_val.all());
```

### 输出

```
[ 1, 4, 7 ]
```

## 例 2

### JavaScript

```
const collect = require('collect.js');

let obj = [
    {
        name: 'Rahul',
        dob: '25-10-96',
        section: 'A',
        score: 98,
    },
    {
        name: 'Aditya',
        dob: '25-10-96',
        section: 'B',
        score: 96,
    },
    {
        name: 'Abhishek',
        dob: '16-08-94',
        section: 'A',
        score: 98
    }
];

const collection = collect(obj);

const nth_val = collection.nth(2);

console.log(nth_val.all());
```

### 输出

```
[
  { name: 'Rahul', dob: '25-10-96', section: 'A', score: 98 },
  { name: 'Abhishek', dob: '16-08-94', section: 'A', score: 98 }
]
```
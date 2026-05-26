# Underscore.js _.weave()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-weave-method/](https://www.geeksforgeeks.org/underscore-js-_-weave-method/)

`_.weave()`方法接受两个数组，返回一个将两个数组编织在一起的数组。

**注：** 返回的数组由`_.weave()`方法编织至最短数组的长度，其余数组的值保持不变。

**语法：**

```
_.weave(array1, array2)
```

**参数：**

*   `array1`：第一个数组。
*   `array2`：第二个数组。

**返回值：** 此方法返回一个由`array1`和`array2`组成的编织数组。

**注意：** 此方法在标准JavaScript中不可用，因为它需要安装`underscore-contrib`库。可以使用`npm install underscore-contrib`命令来安装`underscore-contrib`库。

**示例 1：** 在本例中，我们将生成一个`array1`和`array2`大小相同的编织数组。

## JavaScript示例

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Array1
var array1 = [1, 2, 3, 4];

// Array2
var array2 = [5, 6, 7, 8]

// Generating Array using weave() method
var arr =_.weave(array1, array2);
console.log("Array1 : ", array1);
console.log("Array2 : ", array2);
console.log("Woven Array : ", arr);
```

**输出：**

```
Array1 :  [ 1, 2, 3, 4 ]
Array2 :  [ 5, 6, 7, 8 ]
woven Array :  [
  1, 5, 2, 6,
  3, 7, 4, 8
]
```

**例 2：** 当`array1`的大小小于`array2`的大小时。

## JavaScript示例

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Array1
var array1 = [1, 2];

// Array2
var array2 = [5, 6, 7, 8]

// Generating Array using weave() method
var arr =_.weave(array1, array2);
console.log("Array1 : ", array1);
console.log("Array2 : ", array2);
console.log("Woven Array : ", arr);
```

**输出：**

```
Array1 :  [ 1, 2 ]
Array2 :  [ 5, 6, 7, 8 ]
Woven Array :  [ 1, 5, 2, 6, 7, 8 ]
```

**例 3：** 当`array1`的大小大于`array2`的大小时。

## JavaScript示例

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Array1
var array1 = [1, 2, 3, 4];

// Array2
var array2 = [5, 6]

// Generating Array using weave() method
var arr =_.weave(array1, array2);
console.log("Array1 : ", array1);
console.log("Array2 : ", array2);
console.log("Woven Array : ", arr);
```

**输出：**

```
Array1 :  [ 1, 2, 3, 4 ]
Array2 :  [ 5, 6 ]
Woven Array :  [ 1, 5, 2, 6, 3, 4 ]
```
# 下划线.js _.chunkAll()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-chunkall-method/](https://www.geeksforgeeks.org/underscore-js-_-chunkall-method/)

`_.chunkAll()`方法类似于`_.chunk()`方法，除了下面这点：`_.chunkAll()`方法永远不会从最后丢弃短块。创建分块数组也需要一个数组和一个数字。

**语法:**

```
_.chunkAll(array, number);
```

或者

```
_.chunkAll(array, number, partitions);
```

**参数:**

*   `array`: 待拆分的数组。
*   `number`: 要形成的块的大小。
*   `partitions` (可选): 它表示如何从跳过的区域构建分区。

**返回值:** 这个方法返回一个分块数组。

**注意:** 这在正常的JavaScript中无法工作，因为它需要安装下划线.js contrib库。可以使用`npm install underscore-contrib --save`来安装下划线.js contrib库。

## 示例1

在本例中，我们将对一个简单的数组进行分块。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Array
var arr = [2, 2, 3, 5, 6]

// Number
var num = 3

// Making Chunked array
var carr = _.chunkAll(arr, num); 
console.log("array  : ");
console.log(arr);
console.log("number : "); 
console.log(num); 
console.log("chunked array : ");
console.log(carr);
```

**输出:**

```
array  :
[ 2, 2, 3, 5, 6 ]
number :
3
chunked array :
[ [ 2, 2, 3 ], [ 5, 6 ] ]
```

## 示例2

在本例中，我们将使用可选参数来构建跳过的分区。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Array
var arr = [2, 2, 3, 5, 6]

// Number
var num = 3

// Optional Arg
var opt = 4

// Making Chunked array
carr = _.chunkAll(arr, num, opt);
console.log("array  : ");
console.log(arr);
console.log("number : "); 
console.log(num); 
console.log("chunked array : ");
console.log(carr);
```

**输出:**

```
array  :
[ 2, 2, 3, 5, 6 ]
number :
3
chunked array :
[ [ 2, 2, 3 ], [ 6 ] ]
```
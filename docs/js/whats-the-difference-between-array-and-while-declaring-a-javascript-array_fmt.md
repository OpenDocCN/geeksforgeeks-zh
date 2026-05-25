# `Array()`和`[]`声明JavaScript数组的区别？

> 原文：[https://www.geeksforgeeks.org/whats-the-difference-between-array-and-while-declaring-a-javascript-array/](https://www.geeksforgeeks.org/whats-the-difference-between-array-and-while-declaring-a-javascript-array/)

**考虑以下代码：**

```javascript
var myArray = new Array(5);
```

和

```javascript
var myArray = [5];
```

虽然这两行可能看起来相同，但事实并非如此。

**考虑以下解释：**

**情况 1：`var myArray = new Array(5)`**

*   此方法用于定义一个长度为5的数组。这里传递的参数`5`是一个定义所创建数组初始长度的参数。因此，可以传递任何值来使用此代码获取该长度的数组。

```javascript
// Write Javascript code here
//Creates an array of 5 undefined elements 
var arr = new Array(5);

alert(arr.length);
```

**输出：**

```

```

*   使用此方法的另一个优点是，它会在堆栈中预先创建所需的数组大小。这反过来有助于避免`StackOverflow`错误。

**情况 2：`var myArray = [5]`**

*   此方法用于定义一个包含值的数组，其中数组的长度等于方括号中传递的值的数量。这里传递的参数`5`是`myArray`第0个元素的值，即`myArray[0] = 5`。

```javascript
// Write Javascript code here
//Creates an array of 5 undefined elements 
var arr = [5];

alert(arr[0]);
alert("\n"+arr.length);
```

**输出：**

```

```

*   此方法不会预先在堆栈中创建所需大小的数组。因此，该方法需要在每次数组扩展时定义内存，这又会导致堆栈溢出错误。
# Lodash _.defer()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-defer-method/](https://www.geeksforgeeks.org/lodash-_-defer-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.defer()` 方法用于延迟 `func` 参数的调用，直到清除最近的调用栈。此外，当调用该方法时，任何进一步的参数都被提供给该方法的 `func` 参数。

## 语法

```
_.defer(func, [args])
```

## 参数

该方法接受两个参数，描述如下：

*   `func`: 是要延迟的函数。
*   `args`: 这是调用 `func` 的参数。

## 返回值

该方法返回定时器 id。

## 例 1

```
// Requiring lodash library
const _ = require('lodash');

// Calling defer() method with
// its parameter
_.defer(function(content) {
  console.log(content);
}, 'GeeksforGeeks!');

// Prints content after this
console.log('Content:');
```

**输出:**

```
Content:
GeeksforGeeks!
```

## 例 2

```
// Requiring lodash library
const _ = require('lodash');

// Defining func parameter
let func = number => {
  console.log(number);
};

// Defining for loop
for(let i = 1; i <= 5; i++) {

    // Calling defer() method
    // with its parameter
    _.defer(func, i);
}

// Prints integer after this
console.log('Integers are as follows:');
```

**输出:**

```
Integers are as follows:
```

**参考:** [https://lodash.com/docs/4.17.15#defer](https://lodash.com/docs/4.17.15#defer)
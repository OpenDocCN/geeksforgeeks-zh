# Lodash _.debounce()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-debounce-method/](https://www.geeksforgeeks.org/lodash-_-debounce-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.debounce()` 方法用于创建一个去抖函数，该函数延迟给定的 `func`，直到自上次调用该去抖函数起经过规定的等待时间（单位为毫秒）。去抖功能有一个 `cancel` 方法，可以用来取消被延迟的 `func` 调用，还有一个 `flush` 方法，可以用来立即调用被延迟的 `func`。

它还提供了一些选项，可以用来暗示所述的 `func` 是否应该在等待超时的前沿和/或后沿调用。

**注:**

*   调用 `func` 时，最后一个参数被赋予去抖函数。然而，对去抖函数的后续调用会返回最后一次 `func` 调用的结果。
*   当 `leading` 和 `trailing` 选项为真时，当且仅当在整个等待超时期间多次调用去抖函数时，才会在超时的后沿调用 `func`。
*   当等待时间为 0 且 `leading` 选项为假时，则 `func` 调用被延迟到下一个刻度。

## 语法

```
_.debounce( func, wait, options )
```

## 参数

该方法接受三个参数，如下所述:

*   `func`: 是必须去抖的功能。
*   `wait`: 是呼叫延迟的毫秒数。这是一个可选参数。默认值为 0。
*   `options`: 是可用于改变方法行为的选项对象。这是一个可选参数。

`options` 对象具有以下参数:

*   `leading`: 定义超时前沿的调用。这是一个可选参数。默认值为假。
*   `maxWait`: 是 `func` 被调用前允许延迟的最大时间。这是一个可选参数。
*   `trailing`: 它定义了超时后沿的调用。这是一个可选参数。默认值为真。

## 返回值

该方法返回新的去抖函数。

## 例 1

在本例中，由于等待时间为 1000 毫秒，因此可以在函数调用后 1000 毫秒内再次进入 REPL。

### JavaScript

```
// Requiring lodash library
const _ = require('lodash');

// Using _.debounce() method
// with its parameters
var debounce_fun = _.debounce(function () {
  console.log('Function debounced after 1000ms!');
  }, 1000);

debounce_fun();
```

**输出:**

```
Function debounced after 1000ms!
```

## 例 2

在本例中，循环直到手动停止才停止。

### JavaScript

```
// Requiring lodash library
const _ = require('lodash');

// Using _.debounce() method
// with its parameters
var debounce_fun = _.debounce(function() {
  console.log('Function debounced after 1000ms!');
  }, 4, 1000, {'leading': false});

// Defining loop
var loop = function() {
    setTimeout(loop, 3)
    debounce_fun();
};

// Calling loop to start
loop();
```

**输出:**

```
Function debounced after 1000ms!
Function debounced after 1000ms!
Function debounced after 1000ms!
Function debounced after 1000ms!
Function debounced after 1000ms!
Function debounced after 1000ms!
Function debounced after 1000ms!
.
.
.
.
// Will go on unless stopped manually
```
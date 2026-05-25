# Lodash _.throttle() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-throttle-method/](https://www.geeksforgeeks.org/lodash-_-throttle-method/)

**Lodash** 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

Lodash 中的 `_.throttle()` 方法用于创建一个 throttled 函数，该函数每 `wait` 毫秒最多只能调用 `func` 参数一次。节流函数有一个 `cancel` 方法，用于取消被延迟的 `func` 调用，它还有一个 `flush` 方法，用于立即调用被延迟的 `func`。此外，它还提供了一些选项，用于暗示是否应该在等待超时的前沿和/或后沿调用所述函数。

## 语法

```
_.throttle(func, wait, options)
```

## 参数

该方法接受三个参数：

*   `func`: 是需要节流的功能。
*   `wait`: 是要抑制呼叫的毫秒数。
*   `options`: 是选项对象。
    *   `options.leading`: 它定义了在超时前沿的调用。
    *   `options.trailing`: 它定义了在超时的后沿调用。

## 返回值

该方法返回新的节流函数。

## 注意

*   这里，`func` 是使用节流函数的最后一个参数调用的。然而，随后对节流函数的调用将返回上一次函数调用的结果。
*   这里，如果 `leading` 和 `trailing` 选项都为 `true`，那么当且仅当在整个等待超时期间多次调用节流函数时，`func` 将在超时的后沿被调用。
*   这里，如果等待时间为 `0` 且 `leading` 选项为 `false`，则 `func` 调用将延迟到下一个刻度。

## 示例 1

```
// Requiring lodash library
const _ = require('lodash');

// Calling throttle() method with its parameter
var throt_fun = _.throttle(function () {
        console.log('Function throttled after 1000ms!');
    }, 1000);

throt_fun();
```

**输出:** 这里，1000 毫秒后功能被节流后，因为这里的等待时间是 1000 毫秒。

```
Function throttled after 1000ms!
```

## 示例 2

```
// Requiring lodash library
const _ = require('lodash');

// Calling throttle() method with its parameter
var throt_fun = _.throttle(function() {
        console.log('Function throttled after 1000ms!');
    }, 1000);

// Defining loop
var loop = function() {
    setTimeout(loop, 5)
    throt_fun();
};

// Calling loop to start
loop();
```

**输出:** 所以，在这里，循环直到你手动停止才停止。

```
Function throttled after 1000ms!
Function throttled after 1000ms!
Function throttled after 1000ms!
Function throttled after 1000ms!
Function throttled after 1000ms!
Function throttled after 1000ms!
.
.
.
.
// So on until you stop it manually.
```

## 示例 3

这里，在超时的后沿调用函数。

```
// Requiring lodash library
const _ = require('lodash');

// Calling throttle() method with its parameter
var throt_fun = _.throttle(function () {
    console.log('Function is called on the'
        + ' trailing edge of the timeout '
        + 'and throttled after 2000ms!');
    }, 2000, { 'trailing': true });

throt_fun();
```

**输出:**

```
Function is called on the trailing edge of the 
timeout and throttled after 2000ms!
```

**参考:** [https://lodash.com/docs/4.17.15#throttle](https://lodash.com/docs/4.17.15#throttle)
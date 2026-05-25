# 如何在 JavaScript 中创建一个调用参数后附加部分的函数的函数？

> 原文：[https://www.geeksforgeeks.org/how-to-create-a-function-that-invokes-function-with-partials-appended-to-the-arguments-in-javascript/](https://www.geeksforgeeks.org/how-to-create-a-function-that-invokes-function-with-partials-appended-to-the-arguments-in-javascript/)

在本文中，我们将学习创建一个函数，该函数调用一个函数，该函数在 JavaScript 中接收的参数后附加了部分。

## 方法

我们希望实现一个函数，该函数调用另一个函数并提供它收到的参数。我们可以通过使用（`...`）[展开/静止](https://www.geeksforgeeks.org/javascript-spread-operator/)操作符得到结果。

## 解释

假设我们创建了一个函数`math`，负责传递参数。我们分离出我们对`math`函数的论点。第一个参数保留给`functionName`并给出“`...params`”，它将引用其他参数作为`functionName`的参数。我们调用`functionName`，并使用“`...params`”传递其余的参数。

在下面的代码中，`math`需要很多参数。它保留第一个参数作为函数名，其余参数作为其参数。

我们可以定义不同的函数，这些函数将从`math`函数中得到它们的参数。我们已经定义了函数`sum`，它接受所有的参数，并通过将它们作为`...args`来将其作为一个数组，并遍历它们来执行任务。类似地，实现其他功能，如`sub`、`mul`、`power`。

### 示例 1

```javascript
// Function "math" responsible for
// passing the arguments
const math = (functionName, ...params) => functionName(...params);

//function to add all passed arguments
const sum = (...args) => {
    var result = 0;
    for (const val of args) {
        result += val;
    }
    console.log(result);
}

// Function to substract all
// passed arguments
const sub = (...args) => {
    var result = 0;
    for (const val of args) {
        result -= val;
    }
    console.log(result);
}

// Function to multiply all
// passed arguments
const mul = (...args) => {
    var result = 0;
    for (const val of args) {
        result *= val;
    }
    console.log(result);
}

// Call to the functions via "math"
math(sum, 2, 3, 4, 5, 6);
math(sub, 5, 4, 1);
math(mul, 2, 3, 5, 6);
```

**输出：**`math`函数已经成功调用了其他函数并追加了所需的参数。

### 示例 2

以下示例演示了一个使用前两个参数的函数。它使用了前两个参数，我们的“`...args`”指的是前两个参数的其余参数。

```javascript
const fun = (arg1, arg2, ...args) => {
    console.log(args);
}

fun(1, 2, 3, 4, 5, 6);
```

**输出：**

```
[ 3, 4, 5, 6 ]
```
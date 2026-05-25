# JavaScript 中的纯函数

> Original: [https://www.geeksforgeeks.org/pure-functions-in-javascript/](https://www.geeksforgeeks.org/pure-functions-in-javascript/)

**纯函数**是一个函数（代码块），如果传递相同的参数，则**总是返回相同的结果。它不依赖于程序执行期间的任何状态或数据更改，而只依赖于其输入参数。**

此外，纯函数不会产生任何明显的副作用，如网络请求或数据突变等。

让我们看看下面的 JavaScript 函数：

```javascript
function calculateGST( productPrice ) {
    return productPrice * 0.05;
}
```

如果我们传递相同的 `productPrice`，上述函数将始终返回相同的结果。换句话说，它的输出不受任何其他值/状态更改的影响。因此，我们可以将 `calculateGST` 函数作为纯函数调用。

现在，让我们看看下面的另一个函数：

```javascript
var tax = 20;
function calculateGST( productPrice ) {
    return productPrice * (tax / 100) + productPrice;
}
```

请稍等片刻，您能猜出上面的函数是否为纯函数吗？

耶耶！你是正确的！它不是一个纯粹的函数，因为输出依赖于外部变量 `tax`。因此，如果以某种方式更新了税值，那么我们将获得不同的输出，尽管我们将相同的 `productPrice` 作为参数传递给函数。

但这里我们需要做一个重要的说明：

**注意：** 如果纯函数调用纯函数，这不会产生副作用，调用的函数仍被视为纯函数。（示例：在函数中使用 `Math.max()`）

以下是函数被视为纯函数不应产生的一些副作用（但不限于）：

*   发起 HTTP 请求 (`Issue a HTTP request`)
*   变异数据 (`Mutation data`)
*   打印到屏幕或控制台 (`Print to screen or console`)
*   DOM 查询/操作 (`DOM query / operation`)
*   `Math.random()`
*   获取当前时间 (`Get the current time`)
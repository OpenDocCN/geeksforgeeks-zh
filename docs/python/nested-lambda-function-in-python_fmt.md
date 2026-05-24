# Python 中的嵌套 Lambda 函数

> 原文: [https://www.geeksforgeeks.org/nested-lambda-function-in-python/](https://www.geeksforgeeks.org/nested-lambda-function-in-python/)

**先决条件:** [`lambda`](https://www.geeksforgeeks.org/python-lambda/)

在 Python 中，匿名函数意味着函数没有名称。正如我们已经知道的，`def` 关键字用于定义普通函数，`lambda` 关键字用于创建匿名函数。当我们在另一个 `lambda` 函数中使用 `lambda` 函数时，它被称为 `嵌套 Lambda 函数`。

## 例 1:

```py
# Python program to demonstrate
# nested lambda functions

f = lambda a = 2, b = 3:lambda c: a+b+c

o = f()
print(o(4))
```

**输出:**

```py

```

这里，当调用参数为 `4` 的对象 `o` 时，控制转移到 `f()`，这是整个 `lambda` 函数的调用者对象。然后执行以下操作-

*   嵌套的 `lambda` 函数 `f` 接收第一个 `lambda` 函数中的值 `a=2` 和 `b=3`。
*   它从调用对象 `o` 获取 `c` 的值，这里传递了 `c = 4`。
*   我们得到的最终输出是 `a`、`b` 和 `c` 的和，即 `9`。

## 例 2:

```py
# Python program to demonstrate
# nested lambda functions

square = lambda x: x**2
product = lambda f, n: lambda x: f(x)*n

ans = product(square, 2)(10)
print(ans)
```

**输出:**

```py

```

在上面的例子中，当 `product` 函数被调用时，`square` 函数被绑定到 `f`，`2` 被绑定到 `n`，然后返回一个函数，该函数被绑定到 `product`。当用 `10` 调用时，`x` 被赋值给这个函数，然后调用 `square` 函数，它返回 `100`，这个函数又与 `n` 相乘，`n` 是 `2`。所以它最终会返回 `200`。
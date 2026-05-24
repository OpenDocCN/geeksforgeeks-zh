# “int array[5]”的“array”和“&array”有什么区别？

> 原文：[https://www.geeksforgeeks.org/whats-difference-between-array-and-array-for-int-array5/](https://www.geeksforgeeks.org/whats-difference-between-array-and-array-for-int-array5/)

## 引言

如果有人定义了一个数组，比如 `int array[5]`，那么 `array` 或者 `&array` 是什么意思？它们是相同的还是不同的？您可能会想，它们都指向数组的第一个元素，也就是说，它们都有相同的地址。让我们来看看！

## 初步验证

为了检查这一点，首先想到的是下面的程序。

```cpp
#include "stdio.h"
int main()
{
   int array[5];

/* If %p is new to you, you can use %d as well */
   printf("array=%p : &array=%p\n", array, &array);

return 0;
}
```

所以 `array` 和 `&array` 的地址是一样的。同样，你很容易认为两者是一样的。他们不是！为什么一个变量和它的 `&`（即地址）是一样的？看起来不太符合逻辑，但是我们看到 `array` 和 `&array` 都在打印同一个地址。可能现在下结论还为时过早。这篇文章的关键是，尽管它们都导致相同的地址，但它们是不同类型的地址。而这就是 `array` 和 `&array` 的区别。

## 展示差异

为了展示这种差异，我建议看一下下面的程序。

```cpp
#include "stdio.h"
int main()
{
   int array[5];

/* If %p is new to you, you can use %d as well */
   printf("array=%p : &array=%p\n", array, &array);

printf("array+1 = %p : &array + 1 = %p", array+1, &array+1);

return 0;
}
```

通过指针算术，我们知道当我们向指针添加一个整数时会发生什么。那么不运行就能猜出上面程序的输出吗？`array+1` 和 `&array+1` 不该指向同一个地址。你可能会惊讶🙂

## 核心解释

基本上，`array` 是一个“**指向数组第一个元素的指针**”，但是 `&array` 是一个“**指向整个数组（5个int）的指针**”。

由于 `array` 是指向 `int` 的指针，所以加 1 会得到一个增量为 4 的地址（假设机器中的 `int` 大小为 4 字节）。由于 `&array` 是指向 5 个整数的数组的指针，所以加 1 会得到一个增量为 4 x 5 = 20 = 0x14 的地址。现在你明白为什么这两个看似相似的指针在核心层是不同的了。

这个逻辑也可以扩展到多维数组。假设 `int twoDarray[5][4]` 是 2D 阵。这里，`twoDarray` 是指向 4 个 `int` 数组的指针，但是 `&twoDarray` 是指向 5 行 4 个 `int` 数组的指针。如果这听起来很神秘，你可以在添加 1 后用一个小程序打印出来。

## 结论

我们希望我们能够澄清：**数组名称本身是指向第一个元素的指针，但是数组名称的 `&`（即地址-of）是指向整个数组本身的指针。**

如果你觉得以上有用，请做 Like/Tweet/G+1。此外，请给我们留下进一步澄清或信息的评论。我们很乐意帮助和学习🙂
# 头文件“stdio.h”和“stdlib.h”有什么区别？

> 原文：[https://www.geeksforgeeks.org/whats-difference-between-and/](https://www.geeksforgeeks.org/whats-difference-between-and/)

## 主要区别

这是 C 编程中使用的两个重要头文件。`<stdio.h>` 是 **St**andr**d** **I**nput **O**utput（标准输入输出）的头文件，而 `<stdlib.h>` 是 **St**andr**d** **Lib**rary（标准库）的头文件。

区分这两个头文件的一个简单方法是：`<stdio.h>` 包含 `printf()` 和 `scanf()` 的声明，而 `<stdlib.h>` 包含 `malloc()` 和 `free()` 的声明。从这个意义上说，这两个头文件的主要区别可以认为，`<stdio.h>` 是包含‘文件相关输入/输出’功能的头文件，而 `<stdlib.h>` 包含‘内存分配/释放’功能的头文件信息。

## 一个常见的误解

等一下，你说 `<stdio.h>` 是针对文件相关的 I/O，但是 `printf()` 和 `scanf()` 不处理文件…还是它们处理？

作为一个基本原则，在 C 语言中（由于其与 UNIX 历史的关联），键盘和显示器也被当作‘文件’！实际上，键盘输入是默认的 `stdin` 文件流，而显示输出是默认的 `stdout` 文件流。

## 其他功能

另外，请注意，虽然 `<stdlib.h>` 也包含与内存无关的其他类型函数的声明，如 `atoi()`、`exit()`、`rand()` 等。然而为了我们的目的和简单，我们可以记住 `malloc()` 和 `free()` 属于 `<stdlib.h>`。

需要注意的是，头文件不仅可以包含函数声明，还可以包含常量和变量的定义。甚至宏和新数据类型的定义也可以添加到头文件中。

## 结语

如果觉得以上有用，请做 Like/Tweet/G+1。此外，请给我们留下进一步澄清或信息的评论。我们很乐意帮助和学习 🙂
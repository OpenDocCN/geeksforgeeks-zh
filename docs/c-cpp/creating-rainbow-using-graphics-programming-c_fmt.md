# 使用 C 语言中的图形编程创建彩虹

> 原文：[https://www.geeksforgeeks.org/creating-rainbow-using-graphics-programming-c/](https://www.geeksforgeeks.org/creating-rainbow-using-graphics-programming-c/)

在 Turbo C 图形中，我们使用 `graphics.h` 函数绘制不同的形状（如圆形、矩形等），以不同的格式（不同的字体和颜色）显示文本（任何消息）。通过使用 `graphics.h`，我们可以制作程序、动画和游戏。这些对初学者很有用。

## 使用的函数

*   `Delay(n)`：`dos.h` 头文件中的一个函数，负责根据给定的值 `n` 暂时保存程序。
*   `setcolor(n)`：`graphics.h` 头文件中的一个函数，用于设置指针（光标）的颜色。
*   `Arc(x, y, a1, a2, r)`：`graphics.h` 头文件中的一个函数，绘制以 `(x, y)` 为中心、`(a2-a1)` 为角度、`r` 为半径的弧线。

## 执行

参考：[http://www.xcnotes.com/graphics-in-c-language/draw-rainbow-in-c](http://www.xcnotes.com/graphics-in-c-language/draw-rainbow-in-c)

本文由 [**Shivam Pradhan(anuj _ charm)**](https://www.facebook.com/anuj.charm) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
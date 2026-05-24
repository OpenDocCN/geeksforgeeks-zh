# 如何在 C 中更改 main()中 printf()的输出？

> 原文:[https://www . geesforgeks . org/如何更改 c-in-main-in-printf 的输出/](https://www.geeksforgeeks.org/how-to-change-the-output-of-printf-in-main-in-c/)

要更改 main()中 printf()的输出，我们可以使用**宏参数。**

**#定义宏**可用于此任务。这个宏是在函数内部定义的。虽然， **#define** 不用在函数中声明就可以使用，但在这种情况下，printf()总是会被改变。**需要先调用函数来改变 main()中 printf()的输出。**

考虑以下程序。更改程序，使 printf()的输出始终为 10。

## C

T0T6】

不允许更改 main()。只有乐趣()可以改变。现在，考虑以下使用宏参数的程序，

## 

```cpp
// C Program to demonstrate the use of macro arguments to
// change the output of printf()
#include <stdio.h>

void fun()
{
#define printf(x, y) printf(x, 10);
}

// Driver Code
int main()
{
    int i = 10;
    fun();
    i = 20;
    printf("%d", i);
    return 0;
}
```

**输出**

```cpp
10
```

本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
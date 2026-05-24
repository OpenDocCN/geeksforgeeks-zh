# C 程序寻找栈的增长方向

> 原文:[https://www . geesforgeks . org/c-program-find-direction-growth-stack/](https://www.geeksforgeeks.org/c-program-find-direction-growth-stack/)

先决条件:[C 程序的内存布局](https://www.geeksforgeeks.org/memory-layout-of-c-program/)

在典型的过程中，程序的堆栈段包含局部变量以及每次调用函数时保存的信息。每次调用函数时，要返回的地址和关于调用方环境的某些信息(如一些机器寄存器)都会保存在堆栈中。然后，新调用的函数在堆栈上为其自动变量和临时变量分配空间。

堆栈可能向下或向上增长，这取决于编译代码的环境，即取决于编译器。如何知道栈是向下增长还是向上增长？

思路是这样做的:
1)在 main 中制作一个局部变量。
2)用自己的局部变量编写另一个 fun()函数。
3)从 main 打电话给 fun()。比较两个局部变量的地址。如果 fun()的局部变量的地址大于 main 的局部变量，则堆栈向上增长(即地址增加)

```cpp
// C program to check whether stack grows
// downward or upward.
#include<stdio.h>

void fun(int *main_local_addr)
{
    int fun_local;
    if (main_local_addr < &fun_local)
        printf("Stack grows upward\n");
    else
        printf("Stack grows downward\n");
}

int main()
{
    // fun's local variable
    int main_local;

    fun(&main_local);
    return 0;
}
```

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 用 C 表示重复值的速记数组符号

> 原文:[https://www . geesforgeks . org/a-速记-数组-c 中的符号-重复值/](https://www.geeksforgeeks.org/a-shorthand-array-notation-in-c-for-repeated-values/)

在 C 语言中，当有许多重复的值时，我们可以使用一种速记的数组符号来定义数组。下面的程序演示了同样的内容。

```cpp
// C program to demonstrate working of shorthand
// array rotation.
#include <stdio.h>

int main()
{
    // This line is same as
    // int array[10] = {1, 1, 1, 1, 0, 0, 2, 2, 2, 2};
    int array[10] = {[0 ... 3]1, [6 ... 9]2};

    for (int i = 0; i < 10; i++)
        printf("%d ", array[i]);
    return 0;
}
```

输出:

```cpp
1 1 1 1 0 0 2 2 2 2 

```

请注意，2 的中间间隙自动填充为 0。

本文由 **Kaushik Annangi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
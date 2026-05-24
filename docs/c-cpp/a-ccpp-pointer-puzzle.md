# 一个 C/C++ 指针拼图

> 原文:[https://www.geeksforgeeks.org/a-ccpp-pointer-puzzle/](https://www.geeksforgeeks.org/a-ccpp-pointer-puzzle/)

先决条件:[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)
**假设 int 的大小= 4 字节，一个指针变量的大小= 8 字节，下面的程序会输出什么。**
关于如何解决的提示很少:

*   int 的大小= 4 字节，指针变量的大小= 8 字节(在我的机器上)，给指针加 1 会使指针指向下一个直接类型
*   a 的类型是 int (*)[5][6]
*   a1 是 int *类型，a2 是 int **，a3 是 int **
*   &a1 是 int **，a2 是 int ***，a3 是 int ****。因为所有的都指向一个指针，所以加 1 意味着加 8 个字节(指针的大小)
*   [0][0][0]是 int 类型，&a[0][0][0]是 int *类型，[0][0]是 int *类型，&a[0][0]是 int (*)[6]类型，[0]是 int (*)[6]类型，&a[0]是 int (*)[5][6]类型，a 是 int (*)[5][6]类型，&a 是 int (*)[4][5][6]类型

```cpp
// CPP program to illustrate concept
// of pointers
#include <stdio.h>
int main()
{
    int a[4][5][6];
    int x = 0;
    int* a1 = &x;
    int** a2 = &a1;
    int*** a3 = &a2;
    printf("%d %d %d %d\n", sizeof(a), sizeof(a1), sizeof(a2), sizeof(a3));

    printf("%d ", (char*)(&a1 + 1) - (char*)&a1);
    printf("%d ", (char*)(&a2 + 1) - (char*)&a2);
    printf("%d ", (char*)(&a3 + 1) - (char*)&a3);
    printf("%d \n", (char*)(&a + 1) - (char*)&a);

    printf("%d ", (char*)(a1 + 1) - (char*)a1);
    printf("%d ", (char*)(a2 + 1) - (char*)a2);
    printf("%d ", (char*)(a3 + 1) - (char*)a3);
    printf("%d \n", (char*)(a + 1) - (char*)a);

    printf("%d ", (char*)(&a[0][0][0] + 1) - (char*)&a[0][0][0]);
    printf("%d ", (char*)(&a[0][0] + 1) - (char*)&a[0][0]);
    printf("%d ", (char*)(&a[0] + 1) - (char*)&a[0]);
    printf("%d \n", (char*)(&a + 1) - (char*)&a);

    printf("%d ", (a[0][0][0] + 1) - a[0][0][0]);
    printf("%d ", (char*)(a[0][0] + 1) - (char*)a[0][0]);
    printf("%d ", (char*)(a[0] + 1) - (char*)a[0]);
    printf("%d \n", (char*)(a + 1) - (char*)a);
}
```

输出:

```cpp
480 8 8 8
8 8 8 480
4 8 8 120
4 24 120 480
1 4 24 120

```

**相关文章:**

*   [指针测验](https://www.geeksforgeeks.org/c-language-2-gq/pointers-gq/)
*   [悬空、无效、空和野指针](https://www.geeksforgeeks.org/dangling-void-null-wild-pointers/)

本文由 **Subham Jain** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
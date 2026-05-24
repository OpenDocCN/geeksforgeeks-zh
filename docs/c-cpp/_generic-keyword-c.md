# _ C

中的通用关键字

> 原文:[https://www.geeksforgeeks.org/_generic-keyword-c/](https://www.geeksforgeeks.org/_generic-keyword-c/)

C/C++ 中[宏的一个主要缺点是参数是强类型检查的，即一个宏可以操作不同类型的变量(如 char，int，double，..)而不进行类型检查。](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)

```cpp
// C program to illustrate macro function.
#include<stdio.h>
#define INC(P) ++ P
int main()
{
    char *p = "Geeks";
    int x = 10;
    printf("%s  ", INC(p));
    printf("%d", INC(x));
    return 0;
}
```

输出:

```cpp
eeks 11

```

因此，我们避免使用宏。但是在 C 编程实现 C11 标准后，我们可以借助一个新的关键词即“_Generic”来使用 Macro。我们可以为不同类型的数据类型定义 MACRO。例如，以下宏 INC(x)根据 x 的类型转换为 INC(x)、INC(x)或 INCf(x):

```cpp
#define INC(x) _Generic((x), long double: INCl, \
                              default: INC, \
                              float: INCf)(x)

```

示例:-

```cpp
// C program to illustrate macro function.
#include <stdio.h>
int main(void)
{
    // _Generic keyword acts as a switch that chooses 
    // operation based on data type of argument.
    printf("%d\n", _Generic( 1.0L, float:1, double:2, 
                            long double:3, default:0));
    printf("%d\n", _Generic( 1L, float:1, double:2, 
                            long double:3, default:0));
    printf("%d\n", _Generic( 1.0L, float:1, double:2,  
                                      long double:3));
    return 0;
}
```

输出:
注意:如果你运行的是 C11 编译器，那么下面提到的输出就会出现。

```cpp
3
0
3

```

```cpp
// C program to illustrate macro function.
#include <stdio.h>
#define geeks(T) _Generic( (T), char: 1, int: 2, long: 3, default: 0)
int main(void)
{
    // char returns ASCII value which is int type. 
    printf("%d\n", geeks('A')); 

    // Here A is a string.
    printf("%d",geeks("A"));

    return 0;
}
```

输出:

```cpp
2
0

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
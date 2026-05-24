# C

中全局和静态变量的初始化

> 原文:[https://www . geesforgeks . org/initialization-global-static-variables-c/](https://www.geeksforgeeks.org/initialization-global-static-variables-c/)

预测以下 C 程序的输出。

```cpp
// PROGRAM 1
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   static int *p = (int*)malloc(sizeof(p));
   *p = 10;
   printf("%d", *p);
}
```

```cpp
// PROGRAM 2
#include <stdio.h>
#include <stdlib.h>
int *p = (int*)malloc(sizeof(p));

int main(void)
{
    *p = 10;
    printf("%d", *p);
}
```

以上两个程序都不是用 c 编译的，我们在 c 中得到如下编译错误

```cpp
error: initializer element is not constant
```

在 C 语言中，静态和全局变量由编译器自己初始化。因此，它们必须用常数值初始化。

注意，以上程序在 C++ 中编译运行良好，输出结果为 10。

作为练习，用 C 和 C++ 预测下面程序的输出。

```cpp
#include <stdio.h>
int fun(int x)
{
    return (x+5);
}

int y = fun(20);

int main()
{
    printf("%d ", y);
}
```

本文由 Shankar Shastri 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# C 中静态变量的初始化

> 原文:[https://www.geeksforgeeks.org/g-fact-80/](https://www.geeksforgeeks.org/g-fact-80/)

在 C 语言中，静态变量只能使用常量来初始化。例如，以下程序编译失败。

```cpp
#include<stdio.h>
int initializer(void)
{
    return 50;
}

int main()
{
    static int i = initializer();
    printf(" value of i = %d", i);
    getchar();
    return 0;
}
```

如果我们把程序改成如下，那么它就可以正常工作了。

```cpp
#include<stdio.h>
int main()
{
    static int i = 50;
    printf(" value of i = %d", i);
    getchar();
    return 0;
}
```

原因很简单:在开始执行 main()之前，必须初始化所有具有静态存储持续时间的对象(设置为它们的初始值)。因此，在转换时未知的值不能用于静态变量的初始化。

感谢文基和普拉泰克的贡献。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
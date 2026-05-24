# 逗号运算符问题

> 原文:[https://www.geeksforgeeks.org/a-comma-operator-question/](https://www.geeksforgeeks.org/a-comma-operator-question/)

考虑以下 C 程序。

```cpp
// PROGRAM 1
#include<stdio.h>

int main(void)
{
    int a = 1, 2, 3;
    printf("%d", a);
    return 0;
}
```

上面的程序编译失败，但是下面的程序编译很好，打印了 1。

```cpp
// PROGRAM 2
#include<stdio.h>

int main(void)
{
    int a;
    a = 1, 2, 3;
    printf("%d", a);
    return 0;
}
```

下面的程序打印 3，为什么？

```cpp
// PROGRAM 3
#include<stdio.h>

int main(void)
{
    int a;
    a = (1, 2, 3);
    printf("%d", a);
    return 0;
}
```

在 C/C++ 程序中，逗号用于两种上下文:(1)分隔符(2)运算符。(详见[本](https://www.geeksforgeeks.org/comna-in-c-and-c/))。

逗号在程序 1 中只是一个分隔符，我们在这个程序中得到编译错误。

逗号在程序 2 中充当运算符。[逗号运算符的优先级在运算符优先级表](https://www.geeksforgeeks.org/g-fact-41/)中最少。所以赋值操作符优先于逗号，表达式“a = 1，2，3”就变成等价于“(a = 1，2，3)”。这就是为什么我们在第二个程序中得到输出 1。

在程序 3 中，括号被使用，所以逗号操作符首先被执行，我们得到的输出是 3(更多细节见维基页面中的[)。](http://en.wikipedia.org/wiki/Comma_operator)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
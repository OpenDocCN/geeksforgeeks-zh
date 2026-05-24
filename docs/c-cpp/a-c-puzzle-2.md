# 一个 C 字谜

> 原文:[https://www.geeksforgeeks.org/a-c-puzzle-2/](https://www.geeksforgeeks.org/a-c-puzzle-2/)

要写什么代码来代替“//你的代码”，以便下面的代码打印 20。

```cpp
#include <stdio.h>
int f();

int main()
{
    int a = 0;
    f();
    printf("%d",a);
    return 0;
}

int f()
{
   // your code
}
```

输出:

```cpp
20 
```

**我们强烈建议您最小化浏览器，先自己尝试一下**

这个问题似乎是一个技巧性的问题，因为在不发送的情况下不可能更新函数中的局部变量，我们不能将“a”的值设为 20，但是为了输出 20，我们可以将函数 f 写成如下–

```cpp
#include <stdio.h>
int f();

int main()
{
    int a = 0;
    f();
    printf("%d",a);
    return 0;
}

int f()
{
    printf("2");
}
```

f()将打印 2，a 将打印 0

感谢乌卡什·特里维迪提出上述解决方案。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
# 一个 C 语言编程难题

> 原文:[https://www.geeksforgeeks.org/a-c-puzzle/](https://www.geeksforgeeks.org/a-c-puzzle/)

给出 a = 12 和 b = 36 写一个 C 函数/宏，返回 3612，不使用算术、字符串和预定义函数。

**我们强烈建议你尽量减少浏览器，先自己试试这个。**

下面是一个使用 C 宏的字符串[标记粘贴操作符](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/) (##)的解决方案。例如，表达式“a##b”打印“a”和“b”的连接。

下面是一个工作的 C 代码。

```cpp
#include <stdio.h>
#define merge(a, b) b##a
int main(void)
{
    printf("%d ", merge(12, 36));
    return 0;
}
```

输出:

```cpp
3612
```

感谢一位匿名用户提出这个解决方案。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
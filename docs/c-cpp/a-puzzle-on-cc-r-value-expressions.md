# C/c++ R 值表达式的一个谜题

> 原文:[https://www . geesforgeks . org/a-拼图-on-cc-r-value-expressions/](https://www.geeksforgeeks.org/a-puzzle-on-cc-r-value-expressions/)

以下程序的输出会是什么？

```cpp
#include <stdio.h>
int main()
{
   int i = 0xAA;
   ~i, printf("%X\n", i);

   return 0;
}
```

输出: 0xAA

*i* 值没有变化，重点是 l 值和 r 值表达式。表达式 *~i* 是一个 r 值，它必须被赋给一个 l 值以保留变化。

由**文基**表述的谜题。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
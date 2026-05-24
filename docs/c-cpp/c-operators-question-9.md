# C |操作员|问题 9

> 原文:[https://www.geeksforgeeks.org/c-operators-question-9/](https://www.geeksforgeeks.org/c-operators-question-9/)

以下程序的输出？

```cpp
#include <stdio.h>
int f1() { printf ("Geeks"); return 1;}
int f2() { printf ("Quiz"); return 1;}

int main()
{
  int p = f1() + f2();
  return 0;
}
```

**(A)**geek squiz
**(B)**QuizGeeks
**(C)**编译器依赖
**(D)** 编译器错误

**答案:****(C)**

**解释:**运算符“+”对其操作数没有标准定义的求值顺序。可以先执行 f1()或 f2()。因此，编译器可能会选择输出“极客”或“极客”。
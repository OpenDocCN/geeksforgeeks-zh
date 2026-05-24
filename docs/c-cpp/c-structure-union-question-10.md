# C |结构&联盟|问题 10

> 原文:[https://www . geesforgeks . org/c-structure-union-question-10/](https://www.geeksforgeeks.org/c-structure-union-question-10/)

预测以下 C 程序的输出

```cpp
#include<stdio.h>
struct Point
{
  int x, y, z;
};

int main()
{
  struct Point p1 = {.y = 0, .z = 1, .x = 2};
  printf("%d %d %d", p1.x, p1.y, p1.z);
  return 0;
}
```

**(A)** 编译器错误
**(B)**2 0 1
**(C)**0 1 2
**(D)**2 1 0

**答案:****(B)**

**解释:**参考这里讨论的指定初始化。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/structure-union-gq/)
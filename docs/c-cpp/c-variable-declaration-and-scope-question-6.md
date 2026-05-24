# C |变量声明和范围|问题 6

> 原文:[https://www . geesforgeks . org/c-variable-declaration-and-scope-question-6/](https://www.geeksforgeeks.org/c-variable-declaration-and-scope-question-6/)

输出？

```cpp
#include <stdio.h>
int main()
{
  int x = 1, y = 2, z = 3;
  printf(" x = %d, y = %d, z = %d \n", x, y, z);
  {
       int x = 10;
       float y = 20;
       printf(" x = %d, y = %f, z = %d \n", x, y, z);
       {
             int z = 100;
             printf(" x = %d, y = %f, z = %d \n", x, y, z);
       }
  }
  return 0;
}
```

**(甲)**

```cpp
 x = 1, y = 2, z = 3
 x = 10, y = 20.000000, z = 3
 x = 1, y = 2, z = 100
```

**(B)** 编译错误
**(C)**

```cpp
 x = 1, y = 2, z = 3
 x = 10, y = 20.000000, z = 3
 x = 10, y = 20.000000, z = 100 
```

**(D)**

```cpp
 x = 1, y = 2, z = 3
 x = 1, y = 2, z = 3
 x = 1, y = 2, z = 3
```

**答案:** **(C)**

**说明:**详见 C

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)
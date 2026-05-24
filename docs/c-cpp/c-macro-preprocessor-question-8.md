# C |宏&预处理器|问题 8

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-8/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-8/)

```cpp
#include <stdio.h>
#define a 10
int main()
{
  printf("%d ",a);

  #define a 50

  printf("%d ",a);
  return 0;
}
```

**(A)** 编译器错误
**(B)**10 50
**(C)**50 50
**(D)**10 10

**回答:****(B)**

**解释:**如果我们重新定义预处理器指令，预处理器不会给出任何错误。但它可能会发出警告。预处理器在使用之前获取最新的值，并将其放在。
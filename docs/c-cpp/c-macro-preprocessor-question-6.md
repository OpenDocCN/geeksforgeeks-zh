# C |宏&预处理器|问题 6

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-6/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-6/)

```cpp
#include <stdio.h>
#define square(x) x*x
int main()
{
  int x;
  x = 36/square(6);
  printf("%d", x);
  return 0;
}
```

**(A)**1
**(B)**36
**(C)**0
**(D)**编译器错误

**答案:****(B)**

**解释:**预处理器将方块(6)替换为 6*6，表达式变为 x = 36/6*6，x 的值计算为 36。请注意，对于表达式“x = square(6-2)”，宏也将失败

如果我们想要宏方块(x)的正确行为，我们应该将宏声明为

```cpp
#define square(x) ((x)*(x))  

```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)
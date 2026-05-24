# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-10/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-10/)

```cpp
#include <stdio.h>
int main() 
{ 
  int x = 10; 
  static int y = x; 

  if(x == y) 
     printf("Equal"); 
  else if(x > y) 
     printf("Greater"); 
  else
     printf("Less"); 
  return 0; 
}
```

**(A)** 编译器错误
**(B)** 相等
**(C)** 更大
**(D)** 更小

**答案:****(A)**

**说明:**在 C 语言中，静态变量只能使用常量文字初始化。这在 C++ 中是允许的。详见[本](https://www.geeksforgeeks.org/g-fact-80/) GFact。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/storage-classes-gq/)
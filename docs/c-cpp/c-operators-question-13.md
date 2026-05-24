# C |操作员|问题 13

> 原文:[https://www.geeksforgeeks.org/c-operators-question-13/](https://www.geeksforgeeks.org/c-operators-question-13/)

```cpp
#include<stdio.h> 
int main(void) 
{ 
  int a = 1; 
  int b = 0; 
  b = a++ + a++ ; 
  printf("%d %d",a,b); 
  return 0; 
}
```

**(A)** 3 6
**(B)** 编译器从属
**(C)**3 4
**(D)**3 3

**答案:****(B)**

**解释:**详见[https://www.geeksforgeeks.org/sequence-points-in-c-set-1/](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)解释。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)
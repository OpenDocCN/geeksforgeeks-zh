# C |循环&控制结构|问题 12

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-12/](https://www.geeksforgeeks.org/c-loops-control-structure-question-12/)

```cpp
#include <stdio.h>   
int main() 
{ 
  int i;   
  for (i = 1; i != 10; i += 2) 
    printf(" GeeksQuiz "); 
  return 0; 
}
```

**(A)** 极客 sQuiz 极客 sQuiz 极客 sQuiz 极客 sQuiz
**(B)** 极客 sQuiz 极客 sQuiz 极客 sQuiz。无限次
**(C)**geek squiz geek squiz geek squiz
**(D)**geek squiz geek squiz geek squiz geek squiz geek squiz

**答案:****(B)**

**解释:**循环终止条件永远不会变为真，循环打印 *GeeksQuiz* 无限次。一般来说，如果 for 或 while 语句使用循环计数器，那么使用关系运算符(如<)来终止循环比使用不等式运算符(运算符！=).
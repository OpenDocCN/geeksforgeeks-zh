# C |字符串|问题 3

> 原文:[https://www.geeksforgeeks.org/c-string-question-3/](https://www.geeksforgeeks.org/c-string-question-3/)

以下程序的输出是什么？

```cpp
#include<stdio.h>
void swap(char *str1, char *str2)
{
  char *temp = str1;
  str1 = str2;
  str2 = temp;
}  

int main()
{
  char *str1 = "Geeks";
  char *str2 = "Quiz";
  swap(str1, str2);
  printf("str1 is %s, str2 is %s", str1, str2);
  return 0;
}
```

**(A)** str1 是 quick，str2 是 Geeks
**(B)** str1 是 Geeks，str2 是 quick
**(C)**str 1 是 Geeks，str2 是 Geeks
**(D)** str1 是 quick，str2 是 quick

**答案:****(B)**

**说明:【T0 该函数只改变局部指针变量，这些改变不会反映在函数外部。详情见下文。**

[https://www.geeksforgeeks.org/swap-strings-in-c/](https://www.geeksforgeeks.org/swap-strings-in-c/)
# C |字符串|问题 4

> 原文:[https://www.geeksforgeeks.org/c-string-question-4/](https://www.geeksforgeeks.org/c-string-question-4/)

预测产量？

```cpp
#include <stdio.h>
int fun(char *str1)
{
  char *str2 = str1;
  while(*++ str1);
  return (str1-str2);
}

int main()
{
  char *str = "GeeksQuiz";
  printf("%d", fun(str));
  return 0;
}
```

**(A)**10
**(B)**9
**(C)**8
**(D)**随机数

**答案:****(B)**

**说明:**函数 fun()基本统计输入字符串中的字符数。在 fun()内部，指针 str2 被初始化为 str1。while 语句(*++ ST R1)；递增 str1，直到达到“\0”。str1 递增 9。最后，返回 str2 和 str1 之间的差值，即 9。
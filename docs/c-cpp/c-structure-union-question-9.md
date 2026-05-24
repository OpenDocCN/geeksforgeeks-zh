# C |结构&联合|问题 9

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-9/](https://www.geeksforgeeks.org/c-structure-union-question-9/)

```cpp
# include <iostream>
# include <string.h>
using namespace std;

struct Test
{
  char str[20];
};

int main()
{
  struct Test st1, st2;
  strcpy(st1.str, "GeeksQuiz");
  st2 = st1;
  st1.str[0] = 'S';
  cout << st2.str;
  return 0;
}
```

**(A)** 分段错误
**(B)**seeks quick
**(C)**geek squiz
**(D)**编译器错误

**答案:****(C)**

**解释:**将一个结构变量赋给另一个结构变量时，会深度复制数组成员。参见[数组成员是否被深度复制？](https://www.geeksforgeeks.org/are-array-members-deeply-copied/)了解更多详情。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)
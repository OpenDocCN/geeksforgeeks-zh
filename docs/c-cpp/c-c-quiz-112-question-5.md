# C 小测验–112 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-112-question-5/](https://www.geeksforgeeks.org/c-c-quiz-112-question-5/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

int main()
{
 union {int i1; int i2;} myVar = {.i2 =100};
 printf("%d %d",myVar.i1, myVar.i2);
 return 0;
}
```

**(A)** 初始化语法不正确导致编译错误。
**(B)** 没有编译错误，会打印“0 100”。
**(C)** 无编译错误，打印“100 100”。

**回答:****(C)**

**解释:**由于联盟的字段/成员共享相同的内存，所以 i1 和 i2 都指相同的位置。此外，由于 i1 和 i2 属于同一类型，初始化其中一个也会隐式初始化另一个。所以这个问题的答案是

[小测验](https://www.geeksforgeeks.org/c-quiz-112-gq/)
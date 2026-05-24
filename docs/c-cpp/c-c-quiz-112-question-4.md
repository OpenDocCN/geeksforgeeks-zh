# C 小测验–112 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-112-question-4/](https://www.geeksforgeeks.org/c-c-quiz-112-question-4/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

int main()
{
 struct {int i; char c;} myVar = {.c ='A',.i = 100};
 printf("%d %c",myVar.i, myVar.c);
 return 0;
}
```

**(A)** 编译错误，因为结构类型(包含两个不同类型的字段，即一个 int 和一个 char)与该结构类型的 myVar 的定义一起被提及。
**(二)**因 myVar 初始化语法不正确导致编译错误。基本上，操作员成员(即点。)已在没有 myVar 的情况下使用。
**(C)** 编译错误不仅针对 B，还针对 myVar 中不正确的字段顺序，即首先初始化了字段 C，然后初始化了字段 I。
**(D)** 无编译错误，会打印 100 A.

**答案:****(D)**

**说明:**按照 C 语言，完整数据类型的变量初始化可以在定义本身的时候完成。此外，结构字段/成员可以使用字段名无序初始化，使用不带 myVar 的点运算符也可以，如 c 所示。正确答案是 d。

[本题测验](https://www.geeksforgeeks.org/c-quiz-112-gq/)
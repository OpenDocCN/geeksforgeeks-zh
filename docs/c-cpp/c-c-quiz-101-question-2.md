# C 小测验–101 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-101-question-2/](https://www.geeksforgeeks.org/c-c-quiz-101-question-2/)

假设 *int* 为 4 字节， *char* 为 1 字节， *float* 为 4 字节。此外，假设指针大小为 4 字节(即典型情况)

```cpp
char *pChar;
int *pInt;
float *pFloat;

sizeof(pChar);
sizeof(pInt);
sizeof(pFloat);
```

sizeof()运算符返回的大小是多少？
**(A)**4 4
**(B)**1 4 4
**(C)**1 4 8
**(D)**以上都不是

**答案:****(A)**

**说明:**无论指针的类型如何，指针的大小总是相同的。因此，无论是指向 char 的指针还是指向 float 的指针，任何指针的大小都是相同的。甚至指向用户定义的数据类型(例如结构)的指针的大小也是相同的。

[本题小考](https://www.geeksforgeeks.org/c-quiz-101-gq/)
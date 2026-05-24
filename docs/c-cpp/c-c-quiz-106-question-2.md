# C 小测验–106 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-106-question-2/](https://www.geeksforgeeks.org/c-c-quiz-106-question-2/)

C 语言中跟随声明是什么意思？

```cpp
int (*p)[5];
```

**(A)** 会导致编译错误，因为不应该有任何括号，即“int *p[5]”有效。
**(B)** p 是 5 个整数的指针。
**(C)** p 是整数数组的指针。
**(D)** p 是 5 个指向整数的指针的数组。
**(E)** p 是 5 个整数数组的指针

**回答:****(E)**

**说明:**这里 p 基本上是 5 个整数的整数数组的指针。在“int *p[5]”的情况下，p 是指向整数的 5 个指针的数组。

[本题小考](https://www.geeksforgeeks.org/c-quiz-106-gq/)
# C 小测验–106 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-106-question-5/](https://www.geeksforgeeks.org/c-c-quiz-106-question-5/)

对于 C 语言中的以下“typedef”，选择最好的语句

```cpp
typedef int INT, *INTPTR, ONEDARR[10], TWODARR[10][10];
```

**(A)** 会导致编译错误，因为 typedef 正在同一个语句中被用来定义多个不兼容类型的别名。
**(B)**“INT x”将定义 INT 类型的 x。语句的剩余部分将被忽略。
**(C)**“INT x”将定义 INT 类型的 x，“INTPTR y”将定义 int *类型的指针 y。语句的剩余部分将被忽略。
**(D)**“INT x”将定义 INT 类型的 x。“INTPTR y”将定义 int *类型的指针 y。ONEDARR 是一个 10 个整数数组。TWODARR 是一个 10 乘 10 整数的 2D 数组。

**(E)**“INT x”将定义 INT 类型的 x。“INTPTR *y”将定义 int **类型的指针 y。“ONEDARR z”将 z 定义为 10 个整数的数组。“TWODARR t”将 t 定义为 10 乘 10 整数的数组。

**回答:** **(E)**

**说明:**这里，int 是 INT 的别名。INTPTR 是 int *的别名。这就是为什么 INTPTR *会是 int **的别名。同样，ONEDARR 定义的是别名，而不是数组本身。ONEDARR 是 int [10]的别名。这就是为什么“ONEDARR z”会定义 int [10]的数组 z。类似地，TWODARR 也是 int [10][10]的别名。因此“TWODARR t”将定义 int [10][10]的数组 t。我们可以看到 typedef 可以用来创建其他类型的别名或同义词。

[本题小考](https://www.geeksforgeeks.org/c-quiz-106-gq/)
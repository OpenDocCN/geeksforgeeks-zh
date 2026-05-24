# C 小测验–110 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-110-question-1/](https://www.geeksforgeeks.org/c-c-quiz-110-question-1/)

假设有人以下列方式编写增量宏(即，将值增加 1):

```cpp
#define INC1(a) ((a)+1)

#define INC2 (a) ((a)+1)

#define INC3( a ) (( a ) + 1)

#define INC4 ( a ) (( a ) + 1)
```

为以上宏选择正确的语句。
**(A)** 只有 INC1 是正确的。
**(B)** 全部(即 INC1、INC2、INC3、INC4)正确。
**(C)** 只有 INC1 和 INC3 是正确的。
**(D)** 只有 INC1 和 INC2 是正确的。

**回答:****(C)**

**说明:**在 C 语言中，对于带自变量的宏，*宏名*和*开括号*之间不能有空格。这就是为什么只有 INC1 和 INC3 是正确的。基本上，“#定义 INC2 (a) ((a)+1)”导致“INC2”扩展到“(a) ((a)+1)”，这不是期望的扩展。

[本题小考](https://www.geeksforgeeks.org/c-quiz-110-gq/)
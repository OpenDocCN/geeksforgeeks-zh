# C 小测验–101 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-101-question-1/](https://www.geeksforgeeks.org/c-c-quiz-101-question-1/)

假设在一个 C 程序片段中，使用了以下语句。

```cpp
i) sizeof(int);
ii) sizeof(int*);
iii) sizeof(int**);
```

假设指针的大小是 4 字节，int 的大小也是 4 字节，从给定的选项中选出最正确的答案。
**(A)** 只有我)会编译成功，它会返回大小为 4。
**(B)** i)、ii)和 iii)将成功编译，并且每个的大小将相同，即 4
**(C)** i)、ii)和 iii)将成功编译，但是每个的大小将不同，并且将在运行时决定。
**(D)** ii)和 iii)将导致编译错误，但 I)将编译并导致大小为 4。

**回答:****(B)**

**说明:**所有指针类型大小相同。

无论是“指向 char 的指针”还是“指向 int 的指针”或“指向 int 的指针”，大小始终保持不变。

这就是为什么所有 I)、ii)和 iii)都将成功编译，并产生相同的大小值 4。

[本题小考](https://www.geeksforgeeks.org/c-quiz-101-gq/)
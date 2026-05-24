# C 小测验–107 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-107-question-4/](https://www.geeksforgeeks.org/c-c-quiz-107-question-4/)

选择 const 和 volatile 的正确语句。
**(A)** const 是 volatile 的反义词，反之亦然。
**(B)** const 和 volatile 不能用于 struct 和 union。
**(C)** const 和 volatile 不能用于枚举。
**(D)** const 和 volatile 不能用于 typedef。
**(E)** const 和 volatile 是独立的，即一个变量有可能同时被定义为 const 和 volatile。

**回答:****(E)**

**说明:**在 C 语言中，const 和 volatile 是类型限定词，这两个是独立的。基本上，const 意味着该值不能被程序修改。而 volatile 意味着值会突然改变(可能来自程序外部)。事实上，C 标准提到了一个有效声明的例子，它既有常量又有变量。例如“外部常量易失性内部实时时钟；”其中 real_time_clock 可以由硬件修改，但是不能被分配、递增或递减。所以我们应该把 const 和 volatile 分开处理。此外，这些类型限定符也适用于 struct、union、enum 和 typedef。

[本题小考](https://www.geeksforgeeks.org/c-quiz-107-gq/)
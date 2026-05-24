# C 小测验–110 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-110-question-4/](https://www.geeksforgeeks.org/c-c-quiz-110-question-4/)

下面的程序会给出编译错误，因为在 foo()之后使用了逗号。相反，应该使用分号，即在 bar()之后使用分号的方式。

这就是为什么如果我们在 foo()后使用分号，程序将在打印“GeeksQuiz”时编译并成功运行

```cpp
#include "stdio.h"

void foo(void)
{
 printf("Geeks");
}
void bar(void)
{
 printf("Quiz");
}

int main()
{
 foo(), bar();
 return 0;
}
```

**(A)**TRUE
**(B)**FALSE

**答案:** **(B)**

**说明:**在这里，逗号是充当运算符而不是分隔符。对于 C 语言中的逗号运算符，首先计算左操作数，然后计算右操作数。这就是为什么 foo()会被调用，后跟 bar()。给定的程序没有问题。它将编译并打印“极客 sQuiz”，本身没有任何修改。

[本题小考](https://www.geeksforgeeks.org/c-quiz-110-gq/)
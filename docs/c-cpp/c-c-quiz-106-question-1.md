# C 小测验–106 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-106-question-1/](https://www.geeksforgeeks.org/c-c-quiz-106-question-1/)

假设 int 大小为 4 字节，当我们编译并运行以下程序时会发生什么？

```cpp
#include “stdio.h”
int main()
{
  printf(“GeeksQuiz\n”);
  main();
  return 0;
}
```

**(A)** 我们不能在 main()内部使用 main()，编译器会通过显示编译器错误来捕捉它。
**(B)** 极客 sQuiz 将被打印 2147483647 次，即(2 的 31 次方)–1。
**(C)** 它将无限次打印极客 sQuiz，即程序将永远继续运行，直到它被其他方式终止，如 CTRL+C 或 CTRL+Z 等。
**(D)** 极客 sQuiz 只会打印一次。因为当 main()在 main()内部使用时，编译器会在运行时忽略它。这是为了确保 main()只被调用一次。
**(E)** 极客 sQuiz 将被打印，直到该程序发生堆栈溢出。

**回答:****(E)**

**解释:**首先，main()调用 main()没有限制，即递归也可以发生在 main()上。但是这里没有明确提到这个递归的终止条件。所以 main()会在打印完 GeeksQuiz 后调用 main()。这将一直持续到程序的堆栈被完全填满。请注意，堆栈(运行程序的内部)存储调用函数序列，即哪个函数调用了哪个函数，以便被调用函数返回时可以返回控件。这就是为什么在程序中，main()会继续调用 main()，直到整个堆栈结束，即发生堆栈溢出。

[本题小考](https://www.geeksforgeeks.org/c-quiz-106-gq/)
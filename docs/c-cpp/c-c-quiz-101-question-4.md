# C 小测验–101 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-101-question-4/](https://www.geeksforgeeks.org/c-c-quiz-101-question-4/)

```cpp
#include "stdio.h" 
int main()
{
 void *pVoid;
 pVoid = (void*)0;
 printf("%lu",sizeof(pVoid));
 return 0;
}
```

为上面的 C 程序片段挑选最佳语句。
**(A)** 将(void *)0 分配给 pVoid 是不正确的，因为内存尚未分配。这就是为什么没有编译错误，但会导致运行时错误。
**(B)** 将(void *)0 分配给 pVoid 是不正确的，因为硬编码值(这里是零，即 0)不能分配给任何指针。这就是为什么它会导致编译错误。
**(C)** 无编译问题，无运行时问题。空指针的大小，即 pVoid 等于 int 的大小。
**(D)** sizeof()运算符不是为 void 类型的指针定义的。

**回答:****(C)**

**说明:** (void *)0 基本上是 NULL 指针，在 C 中有很多用途，请注意，无论指针是什么类型，每个指针都保存一些地址，每个指针的大小都等于 sizeof(int)。所以 D)不正确。绝对地址可以分配给任何指针，尽管如果地址非法，可能会导致运行时出现问题。因为 0 是合法地址，所以将(void *)0 分配给 pVoid 就可以了。所以 B)不正确。我们在这里没有对 pVoid 进行任何非法操作。所以它不会导致任何编译/运行时错误。所以 A)不正确。例如，如果我们对 pVoid 执行非法操作，例如取消空指针即*pVoid 的引用，这将导致错误。上述程序将编译/运行没有任何问题。所以 C)是正确的。

[本题小考](https://www.geeksforgeeks.org/c-quiz-101-gq/)
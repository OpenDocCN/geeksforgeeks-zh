# C 小测验–111 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-111-question-2/](https://www.geeksforgeeks.org/c-c-quiz-111-question-2/)

为以下程序片段选择最佳语句:

```cpp
#include "stdio.h"
void foo(void)
{
 static int staticVar;
 staticVar++ ;
 printf("foo: %d\n",staticVar);
}

void bar(void)
{
 static int staticVar;
 staticVar++ ;
 printf("bar: %d\n",staticVar);
}

int main()
{
 foo(), bar(), foo();
 return 0;
}
```

**(A)** 编译错误，因为 foo 和 bar 中使用了相同的静态变量名。因为这些静态变量即使在函数结束后也保留它们的值，所以不能在两个函数中使用相同的名称。

**(B)** 编译错误，因为在侧主函数中调用 foo()和 bar()时没有使用分号。
**(C)** 没有编译错误，两个函数之间只使用一个 staticVar 副本，这就是为什么单个 staticVar 的最终值是 3。
**(D)** 没有编译错误，staticVar 的单独副本将在两个函数中使用。这就是为什么 foo()中的 staticVar 是 2，而 bar()中的 staticVar 是 1。

**回答:****(D)**

**说明:**在这里，虽然静态变量的生命跨越了函数调用，但它们的范围仅是各自对应的函数体。这就是为什么每个函数的 staticVar 都有独立的副本，它们的生命周期跨越函数调用。d 是正确的。

[本题小测验](https://www.geeksforgeeks.org/c-quiz-111-gq/)
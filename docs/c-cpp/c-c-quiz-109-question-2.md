# C 小测验–109 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-109-question-2/](https://www.geeksforgeeks.org/c-c-quiz-109-question-2/)

为下面的程序选择最佳语句。

```cpp
#include "stdio.h"

int foo(int a)
{
 printf("%d",a);
 return 0;
}

int main()
{
 foo;
 return 0;
}
```

**(A)** 会导致编译错误，因为 foo 没有括号。
**(B)** 没有编译错误，一些垃圾值会传递给 foo 函数。这将使 foo 以输出“垃圾整数”执行。
**(C)** 没有编译错误但是 foo 函数不会被执行。程序不会打印任何东西。
**(D)** 没有编译错误，零(即 0)将被传递给 foo 函数。这将使 foo 以输出 0 执行。

**答案:****(C)**

**解释:**在 C 语言中，如果使用不带括号的函数名，对函数名的引用只是生成一个指向该函数的指针，然后被丢弃。所以上面的程序会编译，但不会打印任何东西。

[本题小考](https://www.geeksforgeeks.org/c-quiz-109-gq/)
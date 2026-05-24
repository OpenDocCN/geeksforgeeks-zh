# C 小测验–109 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-109-question-3/](https://www.geeksforgeeks.org/c-c-quiz-109-question-3/)

找出以下程序的正确语句。

```cpp
#include "stdio.h"

typedef int (*funPtr)(int);

int inc(int a)
{
 printf("Inside inc() %d\n",a);
 return (a+1);
}

int main()
{

 funPtr incPtr1 = NULL, incPtr2 = NULL;

 incPtr1 = &inc; /* (1) */
 incPtr2 = inc; /* (2) */

 (*incPtr1)(5); /* (3) */
 incPtr2(5); /* (4)*/

 return 0;
}
```

**(A)** 带注释(1)的行会给出编译错误。
**(B)** 行带注释(2)会给出编译错误。
**(C)** 行用(1) & (3)会给出编译错误。
**(D)** 行用(2) & (4)会给出编译错误。
**(E)** 无编译错误，程序运行不会出现任何问题。

**回答:****(E)**

**说明:**在给函数指针赋值任何函数时，&是可选的。同样，通过函数指针调用函数时，*是可选的。

[本题小考](https://www.geeksforgeeks.org/c-quiz-109-gq/)
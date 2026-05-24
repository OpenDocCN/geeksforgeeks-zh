# C 小测验–110 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-110-question-3/](https://www.geeksforgeeks.org/c-c-quiz-110-question-3/)

通常，C 语言(例如 stdio.h)中的库头文件不仅包含函数和宏定义的声明，还包含用户定义的数据类型(例如 struct、union 等)的定义、typedefs 以及全局变量的定义。因此，如果我们在一个 C 程序中不止一次地包含同一个头文件，这将导致编译问题，因为头文件的许多结构将会重新定义。这意味着下面的程序会给出编译错误。

```cpp
#include “stdio.h”
#include “stdio.h”
#include “stdio.h”

int main()
{
 printf(“Whether this statement would be printed?”)
 return 0;
}
```

**(A)**TRUE
**(B)**FALSE

**答案:** **(B)**

**说明:**程序中多次包含库头文件没关系。但实际上头文件的内容只包含一次。它的实现方式是由于使用了“#ifndef”、“#define”和“#endif”。这就是为什么建议在用户定义的头文件中使用这些预处理器或宏。关于这个的例子和用法，请查看这个问题的“讨论它”。

[本题小考](https://www.geeksforgeeks.org/c-quiz-110-gq/)
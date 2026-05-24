# C |操作员|问题 2

> 原文:[https://www.geeksforgeeks.org/c-operators-question-2/](https://www.geeksforgeeks.org/c-operators-question-2/)

```cpp

#include <stdio.h>

int main()
{
    int i = 1, 2, 3;

    printf("%d", i);

    return 0;
}

```

**(一)** 1

**(B)** 3
**(C)** 垃圾值
**(D)** 编译时错误

**回答:****(D)**

**解释:**逗号在这里充当分隔符。编译器创建一个整数变量，并用 1 初始化它。编译器无法创建整数变量 2，因为 2 不是有效的标识符。

[本题小考](https://www.geeksforgeeks.org/java-gq/operators-gq/)
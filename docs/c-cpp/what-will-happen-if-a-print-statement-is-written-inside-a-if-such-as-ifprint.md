# 如果在 if()如 if(print())

中写入 print()语句会发生什么

> 原文:[https://www . geeksforgeeks . org/如果打印语句被写在 ifprint 之类的 if 中会发生什么/](https://www.geeksforgeeks.org/what-will-happen-if-a-print-statement-is-written-inside-a-if-such-as-ifprint/)

**先决条件:** [否则](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/)

本文主要讨论在 if-else 条件语句中使用 print 语句时会发生什么。

**例如:**考虑下面的代码并预测输出。

## C

```cpp
// C program

#include <stdio.h>

// Driver code
int main()
{
    // if statement
    if (printf("I'm Awesome!\n"))

        // calling main() function
        main();

    // else-if statement
    else if (printf("I'm Not Awesome\n"))

        // calling main() function
        main();
}
```
# 如何用 C 语言清除控制台？

> 原文:[https://www.geeksforgeeks.org/clear-console-c-language/](https://www.geeksforgeeks.org/clear-console-c-language/)

这是程序可能需要的基本需求之一，即在执行期间清除控制台。
有一个名为**clr srcr()**的函数，它包含在 conio.h 中，是一个非标准函数，存在于 conio.h 头文件中，该头文件大部分是像 Turbo C 这样的 MS-DOS 编译器使用的，它不是 C 标准库或 ISO C 的一部分，也不是 POSIX 定义的。
那么我们应该在那里使用什么呢？
还有两种方法可以清除控制台:

1.  通过使用系统(“清除”)
2.  通过使用正则表达式“\ e[1；1H \ e[2J]

现在问题来了，我们应该使用哪个，为什么:
使用正则表达式是更好的方法。原因是它的执行速度更快。通过使用 regex，与使用 system(“clear”)相比，我们可以非常快速地执行清晰屏幕操作。
下面的 c 程序将演示 regex 有多快，然后系统(“清除”)
系统(“清除”)包含在 stdlib.h 中，并且也只在 linux 系统中工作，以在窗口使用系统(“cls”)中使用它。

## C

```cpp
// C program for clearing console and
// comparing two different methods
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
    int i = 0;
    double time_taken;
    clock_t t1, t2;

    // a loop for showing geeks for geeks
    // repeating by clearing console using
    // system("clear")

    // Noting start time
    t1 = clock();
    for (i; i < 10000; i++)
    {
        system("clear");
        printf("geeks for geeks %d\n", i);
    }

    // Calculating total time taken by
    // system("clear")
    t1 = clock() - t1;

    i = 0;
    // Noting start time of regex
    t2 = clock();
    for (i; i < 10000; i++)
    {
        printf("\e[1;1H\e[2J");
        printf("geeks for geeks %d\n", i);
    }

    // calculating total time taken by regex
    t2 = clock() - t2;

    // printing taken by both
    printf("Time taken by system\(\"clear\") %f\n",
           ((double)t1) / CLOCKS_PER_SEC);
    printf("Time taken regex %f",
           ((double)t2) / CLOCKS_PER_SEC);

    return 0;
}
```

**输出:**

```cpp
geeks for geeks 9999
Time taken by system("clear") 0.934388
Time taken by regex 0.000001

```

**注意:**输出时间可能不同，但两个时间的差异总是很大。并且只在你的系统控制台运行这个程序，而不是在这里。
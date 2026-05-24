# C 中的时间延迟

> 原文:[https://www.geeksforgeeks.org/time-delay-c/](https://www.geeksforgeeks.org/time-delay-c/)

在这篇文章中，我们将看到如何在 C 代码中给出时间延迟。基本思想是获取当前时钟，并在该时钟上增加所需的延迟，直到当前时钟小于所需时钟，然后运行一个空循环。

这是一个延迟函数的实现。

```cpp
// C function showing how to do time delay
#include <stdio.h>
// To use time library of C
#include <time.h>

void delay(int number_of_seconds)
{
    // Converting time into milli_seconds
    int milli_seconds = 1000 * number_of_seconds;

    // Storing start time
    clock_t start_time = clock();

    // looping till required time is not achieved
    while (clock() < start_time + milli_seconds)
        ;
}

// Driver code to test above function
int main()
{
    int i;
    for (i = 0; i < 10; i++) {
        // delay of one second
        delay(1);
        printf("%d seconds have passed\n", i + 1);
    }
    return 0;
}
```

输出:

本文由 [**普拉蒂克·查哈尔**](https://github.com/pratik-chhajer) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
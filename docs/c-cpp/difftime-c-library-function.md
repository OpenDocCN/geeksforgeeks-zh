# difftime() C 库函数

> 原文:[https://www.geeksforgeeks.org/difftime-c-library-function/](https://www.geeksforgeeks.org/difftime-c-library-function/)

C 库函数 **difftime()** 返回*秒*开始时间和*结束时间之间的差值。* ( **结束时间-开始时间** )

```cpp
// It is present in time.h header file
#include 

Syntax : 
double difftime(time_t time2, time_t time1);

Parameters:
time1 : Lower bound of the time interval
        whose length is calculated.
time2 : Higher bound of the time interval
        whose length is calculated.

Return value : 
Returns the difference between time1 and 
time2 (as measured in seconds).

```

```cpp
// C program to demonstrate working of
// difftime()
#include <time.h>
#include <stdio.h>
#include <unistd.h>
int main()
{
    int sec;
    time_t time1, time2;

    // Current time
    time(&time1); 
    for (sec = 1; sec <= 6; sec++) 
        sleep(1);

    // time after sleep in loop.
    time(&time2);
    printf("Difference is  %.2f seconds", 
                 difftime(time2, time1));

    return 0;
}
```

输出:

```cpp
Difference is 6.00 seconds

```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
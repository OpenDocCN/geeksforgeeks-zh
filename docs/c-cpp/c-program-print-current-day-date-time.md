# C++ 程序打印当前日期和时间

> 原文:[https://www . geesforgeks . org/c-program-print-current-day-date-time/](https://www.geeksforgeeks.org/c-program-print-current-day-date-time/)

为了方便查找当前的本地日、日期和时间，C++ 在头文件中定义了几个函数，因此有助于我们实现查找本地日、日期和时间目标的函数有:

**时间():**

*   Used to find **the current calendar time** .
*   Its return type is **time _ t** , which is an arithmetic data type that can store the time returned by this function.
*   If its parameter is not empty, it assigns the same value to its parameter as the return value.

**localtime():**

*   It uses the same time () parameter as the return value of time (), and **fills a structure** with date and time as its components, and the corresponding time is in the local time zone.

asctime():

*   用于将 **localtime 填充的结构中的内容转换为人类可读的版本**，最终以给定的格式返回日、日、时:

    ```cpp
    Day Month Date hh:mm:ss Year

    ```

```cpp
// C++ program to find Current Day, Date
// and Local Time
#include<iostream>
#include<ctime>
using namespace std;
int main()
{
    // Declaring argument for time()
    time_t tt;

    // Declaring variable to store return value of
    // localtime()
    struct tm * ti;

    // Applying time()
    time (&tt);

    // Using localtime()
    ti = localtime(&tt);

    cout << "Current Day, Date and Time is = " 
         << asctime(ti);

  return 0;
}
```

输出:

```cpp
It will show the current day, date and localtime, in the
format Day Month Date hh:mm:ss Year

```

**需要记住的点:**

1.  This program will give different outputs according to the time in different time zones.
2.  The output date, date and hour is **, which has nothing to do with the system date, date and hour** . You can change the system date and time settings, but the output will not be affected and the correct information will be given.

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
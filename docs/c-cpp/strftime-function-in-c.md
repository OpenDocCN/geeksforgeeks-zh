# C/c++

中的 strftime()函数

> 原文:[https://www.geeksforgeeks.org/strftime-function-in-c/](https://www.geeksforgeeks.org/strftime-function-in-c/)

strftime()是 C 语言中的一个函数，用来格式化日期和时间。它位于头文件 time.h 下，该文件还包含一个名为 struct tm 的结构，用于保存时间和日期。strftime()的语法如下所示:

```cpp
size_t strftime(char *s, size_t max, const char *format, 
                                          const struct tm *tm); 
```

strftime()函数根据在 format 中指定的格式化规则格式化分解的时间 tm，并将其存储在字符数组 s 中。
**strftime()的一些格式说明符如下所示:**
%x =首选日期表示法
%I =十进制数形式的小时(12 小时制时钟)。
%M =从 00 到 59 的十进制分钟数。
%p =根据给定的时间值选择“上午”或“下午”等。
%a =缩写的工作日名称

%^a =大写字母缩写的工作日名称
%A =完整的工作日名称
%b =缩写的月份名称

%^b =大写字母缩写的月份名称
%B =完整的月份名称三月
%c =日期和时间表示
%d =一个月中的某一天(01-31)
% h = 24 小时格式的小时(00-23)
% I = 12 小时格式的小时(01-12)
%j =一年中的某一天(001-366)
%m =以十进制数表示的月份(01-12)
%M =分钟(分钟

```cpp
struct tm 
{
   int tm_sec;         // seconds
   int tm_min;         // minutes
   int tm_hour;        // hours
   int tm_mday;        // day of the month
   int tm_mon;         // month
   int tm_year;        // The number of years since 1900
   int tm_wday;        // day of the week
   int tm_yday;        // day in the year
   int tm_isdst;       // daylight saving time    
};
```

## C

```cpp
// C program to demonstrate the
// working of strftime()
#include <stdlib.h>
#include <stdio.h>
#include <time.h>
#define Size 50

int main ()
{
    time_t t ;
    struct tm *tmp ;
    char MY_TIME[Size];
    time( &t );

    //localtime() uses the time pointed by t ,
    // to fill a tm structure with the
    // values that represent the
    // corresponding local time.

    tmp = localtime( &t );

    // using strftime to display time
    strftime(MY_TIME, sizeof(MY_TIME), "%x - %I:%M%p", tmp);

    printf("Formatted date & time : %s\n", MY_TIME );
    return(0);
}
```

```cpp
Formatted date & time : 03/20/17 - 02:55PM
```

**我们为什么以及什么时候使用 strftime()？**

当我们制作一个软件/应用程序时，它将根据用户的需求以多种不同的格式输出当前时间和最重要的信息。那么在这种情况下，我们将使用这个函数。它的特长是我们可以以多种[不同的](http://man7.org/linux/man-pages/man3/strftime.3.html)格式显示日期和时间。
**参考:**[http://man7.org/linux/man-pages/man3/strftime.3.html>Linux Man Page](http://man7.org/linux/man-pages/man3/strftime.3.html)
本文由 MAZHAR IMAM KHAN 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。
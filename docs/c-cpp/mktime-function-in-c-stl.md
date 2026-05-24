# c++ STL 中的 mktime()函数

> 原文:[https://www.geeksforgeeks.org/mktime-function-in-c-stl/](https://www.geeksforgeeks.org/mktime-function-in-c-stl/)

**mktime()** 是一个内置的 C++ 函数，它将本地日历时间转换为自纪元以来的时间，并将该值作为类型为 **time_t.** 的对象返回

**语法:**

```cpp
time_t  mktime( struct tm  *time_ptr )
```

**参数:**该函数接受一个强制参数指针 *time_ptr* ，该指针指向一个包含要转换的日历时间的 tm 对象结构。

**返回值:**该函数返回两种类型的值，如下所述:

*   如果传递的参数成功，它会将自 epoch 以来的时间作为 time_t 类型的对象返回。
*   失败时返回-1。

下面的程序说明了 mktime()函数:

## C++

```cpp
// C++ program to demonstrate the
// mktime() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    time_t tim;
    tm* time_ptr;
    char weekday[7][20] = { "Sunday",
                            "Monday",
                            "Tuesday",
                            "Wednesday",
                            "Thursday",
                            "Friday",
                            "Saturday" };

    // Date
    int year = 2018;
    int month = 6;
    int day = 18;

    time(&tim);
    time_ptr = localtime(&tim);

    // tm_year is time since 1900
    time_ptr->tm_year = year - 1900;

    // Months calculated since January
    time_ptr->tm_mon = month - 1;

    // Day calculated in the month
    time_ptr->tm_mday = day;

    // time_ptr pointer to be pass
    mktime(time_ptr);

    cout << "The Day on 18th June 2018 was "
         << weekday[time_ptr->tm_wday];

    return 0;
}
```

**Output**

```cpp
The Day on 18th June 2018 was Monday
```
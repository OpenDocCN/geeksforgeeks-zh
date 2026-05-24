# c++ 中的 localtime()函数

> 原文:[https://www.geeksforgeeks.org/localtime-function-in-c/](https://www.geeksforgeeks.org/localtime-function-in-c/)

**localtime()** 函数在 **ctime** 头文件中定义。localtime()函数将自纪元以来的给定时间转换为表示为本地时间的日历时间。

**语法:**

```cpp
tm* localtime(const time_t* time_ptr);
```

**参数:**该函数接受一个参数 **time_ptr** ，该参数代表指向 time_t 对象的指针。

**返回值:**该函数成功返回一个指向 **tm** 对象的指针，否则返回 NullPointerException。

下面的程序说明了 C++ 中的 localtime()函数:

**例:-**

```cpp
// c++ program to demonstrate
// example of localtime() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    time_t time_ptr;
    time_ptr = time(NULL);

    // Get the localtime
    tm* tm_local = localtime(&time_ptr);

    cout << "Current local time is = "
         << tm_local->tm_hour << ":"
         << tm_local->tm_min << ":"
         << tm_local->tm_sec;

    return 0;
}
```

**输出:**

```cpp
Current local time is = 10:8:10

```
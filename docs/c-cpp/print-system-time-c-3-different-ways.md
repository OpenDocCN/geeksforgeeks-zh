# 用 C++ 打印系统时间(3 种不同方式)

> 原文:[https://www . geesforgeks . org/print-system-time-c-3-differential-way/](https://www.geeksforgeeks.org/print-system-time-c-3-different-ways/)

**第一种方法**
[使用时间()打印当前日期和时间](https://www.geeksforgeeks.org/c-program-print-current-day-date-time/)

**第二种方法**

```cpp
// CPP program to print current date and time
// using time and ctime.
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    // declaring argument of time()
    time_t my_time = time(NULL);

    // ctime() used to give the present time
    printf("%s", ctime(&my_time));
    return 0;
}
```

输出:

```cpp
It will show the current day, date and localtime, 
in the format Day Month Date hh:mm:ss Year

```

**第三种方法**
这里我们已经使用 **[时辰库](https://www.geeksforgeeks.org/chrono-in-c/)** 来打印当前日期和时间。chrono 库是一个灵活的类型集合，以不同的精度跟踪时间。
chrono 库定义了三种主要类型以及实用函数和常见类型定义。
**- >时钟
- >时间点
- >持续时间**

打印当前日期、日期和时间的代码。

```cpp
// CPP program to print current date and time
// using chronos.
#include <chrono>
#include <ctime>
#include <iostream>

using namespace std;

int main()
{
    // Here system_clock is wall clock time from
    // the system-wide realtime clock
    auto timenow =
      chrono::system_clock::to_time_t(chrono::system_clock::now());

    cout << ctime(&timenow) << endl;
}
```

输出:

```cpp
It will show the current day, date and localtime, 
in the format Day Month Date hh:mm:ss Year

```
# C 中的 time.h localtime()函数，示例

> 原文:[https://www . geesforgeks . org/time-h-local time-function-in-c-with-examples/](https://www.geeksforgeeks.org/time-h-localtime-function-in-c-with-examples/)

**localtime()函数**在 [time.h 头文件](https://www.geeksforgeeks.org/time-h-header-file-in-c-with-examples/)中定义。localtime()函数返回用户的本地时间，即出现在计算机任务栏上的时间。

**语法:**

```cpp
tm* localtime(const time_t* t_ptr);
```

**参数:**该函数接受一个参数 **t_ptr** ，该参数代表指向 time_t 对象的指针。

**返回值:**该函数返回一个指向**结构 tm** 对象的指针。

下面程序用 C 语言说明 localtime()函数:

```cpp
// C program to demonstrate
// example of localtime() function.

#include <stdio.h>
#include <time.h>

int main()
{

    struct tm* local;
    time_t t = time(NULL);

    // Get the localtime
    local = localtime(&t);

    printf("Local time and date: %s\n",
           asctime(local));

    return 0;
}
```

**输出:**

```cpp
Local time and date: Mon Sep 23 08:25:53 2019

```

**注意:**要清楚了解该功能，请更改计算机系统的时间和日期，然后再次运行代码。
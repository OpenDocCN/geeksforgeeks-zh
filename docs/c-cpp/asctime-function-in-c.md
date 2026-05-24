# c++ 中的 asctime()函数

> 原文:[https://www.geeksforgeeks.org/asctime-function-in-c/](https://www.geeksforgeeks.org/asctime-function-in-c/)

**asctime()** 功能在 **ctime** 头文件中定义。asctime()函数将结构 tm 的给定日历时间转换为字符表示形式，即人类可读的形式。

**语法:**

```cpp
char* asctime(const struct tm * time_ptr);
```

**参数:**该函数接受单个参数 **time_ptr** ，即指向要转换的 tm 对象的指针。

**返回值:**该函数以“Www Mmm dd hh:mm:ss yyyy”的形式返回**日历时间**

下面的程序说明了 C++ 中的 asctime()函数:

**例:-**

## c++

```cpp
// c++ program to demonstrate
// example of asctime() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    time_t time_ptr;

    time(&time_ptr);
    cout << "Current date and time = "
         << asctime(localtime(&time_ptr));

    return 0;
}
```

**输出:**

```cpp
Current date and time = Mon Oct  1 10:21:26 2018
```
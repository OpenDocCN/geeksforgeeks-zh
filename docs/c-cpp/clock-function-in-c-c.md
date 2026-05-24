# C/c++ 中的 clock()函数

> 原文:[https://www.geeksforgeeks.org/clock-function-in-c-c/](https://www.geeksforgeeks.org/clock-function-in-c-c/)

在 *ctime* 头文件中定义了 clock()函数。clock()函数返回程序消耗的近似处理器时间。时钟()时间取决于操作系统如何为进程分配资源，这就是为什么时钟()时间可能比实际时钟慢或快。

**语法:**

```cpp
clock_t clock( void );
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回程序消耗的近似处理器时间，失败时函数返回-1。

**下面程序说明了时钟()功能的实现:**

```cpp
// C++ program to demonstrate
// example of clock() function.

#include<bits/stdc++.h>
using namespace std;

int main ()
{
    float a;
    clock_t time_req;

    // Without using pow function
    time_req = clock();
    for(int i=0; i<200000; i++)
    {
        a = log(i*i*i*i);
    }
    time_req = clock()- time_req;
    cout << "Processor time taken for multiplication: "
        << (float)time_req/CLOCKS_PER_SEC << " seconds" << endl;

    // Using pow function
    time_req = clock();
    for(int i=0; i<200000; i++)
    {
        a = log(pow(i, 4));
    }
    time_req = clock() - time_req;
    cout << "Processor time taken in pow function: "
        << (float)time_req/CLOCKS_PER_SEC << " seconds" << endl;

    return 0;
}
```

**输出:**

```cpp
Processor time taken for multiplication: 0.006485 seconds
Processor time taken in pow function: 0.022251 seconds

```
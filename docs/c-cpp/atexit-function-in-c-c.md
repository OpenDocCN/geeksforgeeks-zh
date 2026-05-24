# C/c++

中的 atexit()函数

> 原文:[https://www.geeksforgeeks.org/atexit-function-in-c-c/](https://www.geeksforgeeks.org/atexit-function-in-c-c/)

当程序正常终止时， *atexit()* 指向的函数被自动调用，没有参数。如果对 *atexit()* 函数的不同调用指定了多个函数，则所有函数都按照[堆栈](https://www.geeksforgeeks.org/stack-data-structure/)的顺序执行(即指定的最后一个函数是退出时首先执行的函数)。单个函数可以注册为在退出时执行多次。
**语法:**

```cpp
extern "C" int atexit (void (*func)(void)) noexcept;
extern "C++" int atexit (void (*func)(void)) noexcept
```

**注意:** **extern** 指的是名字将要指代的，整个程序中的同一个对象。
**参数:**该函数接受单个强制参数 **func** ，该参数指定正常程序终止时要调用的函数(要调用的函数)的指针。
**返回值:**该函数返回以下值:

*   零，如果函数注册成功
*   非零，如果函数注册失败

以下程序说明上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// atexit() function
#include <bits/stdc++.h>
using namespace std;

// Returns no value, and takes nothing as a parameter
void done()
{
    cout << "Exiting Successfully"
         << "\n"; // Executed second
}
// Driver Code
int main()
{
    int value;
    value = atexit(done);

    if (value != 0) {
        cout << "atexit () function registration failed";
        exit(1);
    }
    cout << " Registration successful"
         << "\n"; // Executed First
    return 0;
}
```

**Output:** 

```cpp
Registration successful
Exiting Successfully
```
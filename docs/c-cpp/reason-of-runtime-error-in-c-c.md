# C/c++ 运行时错误原因

> 原文:[https://www . geesforgeks . org/运行时出错原因-c-c/](https://www.geeksforgeeks.org/reason-of-runtime-error-in-c-c/)

在本文中，我们将讨论运行时错误的原因及其解决方案。

**[运行时错误](https://www.geeksforgeeks.org/runtime-errors/) :** 程序中的运行时错误是一个[错误](https://www.geeksforgeeks.org/errors-in-cc/)，它发生在程序成功编译后运行的时候。以下是确定运行时错误背后原因的一些方法:

**方法 1:** 当[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)的索引被赋予负索引时，会导致运行时错误期间无效的内存访问。下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来说明运行时无效的[内存](https://www.geeksforgeeks.org/introduction-to-memory-and-memory-units/)访问:

## c++

```cpp
// C++ program to illustrate invalid
// memory access during run-time
#include <iostream>
using namespace std;

// Global declaration
int arr[5];

// Driver Code
int main()
{
    int answer = arr[-10];
    cout << answer;

    return 0;
}
```

**输出:**

```cpp
1736487104

```
# 超出内存限制错误

> 原文:[https://www.geeksforgeeks.org/memory-limit-exceeded-error/](https://www.geeksforgeeks.org/memory-limit-exceeded-error/)

**内存限制超出** [**错误**](https://www.geeksforgeeks.org/errors-in-cc/) **:** 通常在没有设置内存限制时出现。这意味着程序试图为特定问题分配超过内存限制的内存。例如，如果内存限制是 **256 MB** ，那么就不需要编写需要超过 256 MB 内存的代码。一般所有在线平台的内存限制都和**一样，都是 256 MB** 。可能有更多的原因导致此错误的发生。

**程序 1:**

下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来声明一个 10 <sup>7</sup> 大小的全局 1D [数组](https://www.geeksforgeeks.org/introduction-to-arrays/):

T8】c++ T10

```cpp
// C++ program to declare the array
// of size 10^7 globally

#include <bits/stdc++.h>
using namespace std;

// Variable N initialized
const int N = 1e7;

// Global array is declared
int a[N];

// Driver Code
int main()
{
    for (int i = 0; i < N; ++ i) {
        a[i] = i;
    }
    cout << a[N - 1];

    return 0;
}
```

T11T13**输出:**T16】

```cpp
9999999
```
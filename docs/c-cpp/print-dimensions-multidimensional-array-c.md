# 如何在 C++ 中打印多维数组的维度

> 原文:[https://www . geesforgeks . org/print-dimensions-多维-array-c/](https://www.geeksforgeeks.org/print-dimensions-multidimensional-array-c/)

创建一个按维度打印多维数组大小的函数，即:

示例:

```cpp
Input : 
int a[2][3][4];
printDimensions(a);
Output :
2x3x4

Input :
int b[5][6];
printDimensions(a);
Output :
5x6

```

为了解决这个问题，我们应该使用[模板函数](https://www.geeksforgeeks.org/templates-cpp/)来计算当前数组的大小。然后我们递归调用这个函数，直到最后一个维度。对于最后一个维度，应使用边界覆盖模板函数。实施思路:

```cpp
// C++ program to print dimensions of a
// multidimensional array
#include <iostream>

template <typename T, size_t N>
void printDimensions(const T (&a)[N])
{
    std::cout << N;
}

template <typename T, size_t N, size_t M>
void printDimensions(const T (&a)[N][M])
{
    std::cout << N << "x";
    printDimensions(a[0]);
}

int main()
{
    int a[2][3][4];
    printDimensions(a);
    return 0;
}
```

**输出:**

```cpp
2x3x4

```
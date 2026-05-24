# 使用指针算法的数组之和

> 原文:[https://www . geesforgeks . org/使用指针算术的数组求和/](https://www.geeksforgeeks.org/sum-of-array-using-pointer-arithmetic/)

给定一个数组，编写一个程序，用指针算法求数组的和。

在这个程序中，我们使用*运算符。*(星号)运算符表示变量值。声明时的*运算符表示这是一个指针，否则它表示指针所指向的内存位置的值。
**sum()** 函数用于通过指针找到数组的和。

示例:

```cpp
Input : array = 2, 4, -6, 5, 8, -1
Output : sum = 12

Input :  array = 1, 4, -6, 8, -10, -12
Output : sum = -15

```

```cpp
// CPP program to find sum of array using pointers
#include <iostream>
using namespace std;

// Function to find the sum of the array
void sum(int* array, int length)
{
    int i, sum_of_array = 0;
    for (i = 0; i < length; i++)
        sum_of_array = sum_of_array + *(array + i);
    cout << "sum of array is = " << sum_of_array;
}
// Driver function
int main()
{
    // Array to hold the values
    int array[] = { 2, 4, -6, 5, 8, -1 };
    sum(array, 6);
    return 0;
}
```

输出:

```cpp
sum of array is = 12

```
# 用 C++ 中的 STL 找到可以被 N 整除的数组元素

> 原文:[https://www . geesforgeks . org/find-数组中可被 n 整除的元素-使用-stl-in-c/](https://www.geeksforgeeks.org/find-elements-of-an-array-which-are-divisible-by-n-using-stl-in-c/)

给定一个数组和一个整数 N，用 C++ 中的 STL 找到能被 N 整除的元素

**例:**

```cpp
Input: a[] = {1, 2, 3, 4, 5, 10}, N = 2
Output: 3
Explanation:
As 2, 4, and 10 are divisible by 2
Therefore the output is 3

Input:a[] = {4, 3, 5, 9, 11}, N = 5
Output: 1
Explanation:
As only 5 is divisible by 5
Therefore the output is 3

```

**方法:**这可以使用 C++ 中的 [count_if()](https://www.geeksforgeeks.org/count_if-in-c/) 方法来实现

**语法:**

```cpp
count_if(lower_bound, upper_bound, function)

```

其中**函数**将给定序列的元素逐个作为参数，并根据该函数中指定的条件返回一个布尔值。

在这种情况下，函数将是:

```cpp
bool isDiv(int i)
{
    if (i % N == 0)
        return true;
    else
        return false;
}

```

下面是上述方法的实现:

```cpp
// C++ simple program to
// find elements which are
// divisible by N

#include <bits/stdc++.h>
using namespace std;

int N;

// Function to check
// if the element is divisible by N
bool isDiv(int i)
{
    if (i % N == 0)
        return true;
    else
        return false;
}

// Driver code
int main()
{
    int a[] = { 1, 2, 6, 3, 4, 5 };
    N = 2;

    int n = sizeof(a) / sizeof(a[0]);

    int count = count_if(a, a + n, isDiv);

    cout << "Elements divisible by "
         << N << ": " << count;

    return 0;
}
```

**输出:**

```cpp
Elements divisible by 2: 3

```
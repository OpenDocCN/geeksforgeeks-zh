# 在 C++ 中使用 STL 查找奇数和偶数数组的元素

> 原文:[https://www . geeksforgeeks . org/find-array-elements-哪些是奇数和偶数-使用-stl-in-c/](https://www.geeksforgeeks.org/find-elements-of-an-array-which-are-odd-and-even-using-stl-in-c/)

给定一个数组，任务是使用 C++ 中的 STL 找到奇数和偶数元素

**例:**

```cpp
Input: a[] = {1, 2, 3, 4, 5, 10}
Output: Odd = 3, Even = 3

Input:a[] = {4, 3, 5, 9, 11}
Output: Odd = 4, Even = 1

```

**方法:**这可以使用 C++ 中的 [count_if()](https://www.geeksforgeeks.org/count_if-in-c/) 方法来实现

**语法:**

```cpp
count_if(lower_bound, upper_bound, function)

```

其中，**函数**将给定序列的元素逐一作为参数，并根据该函数中指定的条件返回一个布尔值。

在这种情况下，函数将是:

```cpp
bool isOdd(int i)
{
    if (i % 2 != 0)
        return true;
    else
        return false;
}

```

下面是上述方法的实现:

```cpp
// C++ simple program to
// find elements which are
// odd and even

#include <bits/stdc++.h>
using namespace std;

// Function to check 
// if the element is off or even
bool isOdd(int i)
{
    if (i % 2 != 0)
        return true;
    else
        return false;
}

// Driver code
int main()
{
    int a[] = { 1, 2, 6, 3, 4, 5 };

    int n = sizeof(a) / sizeof(a[0]);

    int count = count_if(a, a + n, isOdd);

    cout << "Odd: " << count << endl;
    cout << "Even: " << (n - count) << endl;

    return 0;
}
```

**输出:**

```cpp
Odd: 3
Even: 3

```
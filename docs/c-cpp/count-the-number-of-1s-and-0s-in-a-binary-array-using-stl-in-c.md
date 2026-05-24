# 用 C++ 中的 STL 计算二进制数组中 1 和 0 的个数？

> 原文:[https://www . geesforgeks . org/count-二进制数组中 1 和 0 的个数-使用-stl-in-c/](https://www.geeksforgeeks.org/count-the-number-of-1s-and-0s-in-a-binary-array-using-stl-in-c/)

给定一个二进制数组，任务是用 C++ 中的 STL 计算这个数组中 1 和 0 的个数。

**例:**

```cpp
Input:  arr[] = {1, 0, 0, 1, 0, 0, 1}
Output: 1's = 3, 0's = 4

Input:  arr[] = {1, 1, 1, 1, 0, 0, 1}
Output: 1's = 5, 0's = 2

```

**方法:**我们可以使用 C++ 的 STL 中存在的 [count_if()](https://www.geeksforgeeks.org/count_if-in-c/) 函数进行同样的计数。

**语法:**

```cpp
count_if(lower_bound, upper_bound, filter_function)

where filter_function is a condition
which filters out elements.

```

下面是上述方法的实现:

```cpp
// C++ program to Count
// the number of 1's and 0's
// in a binary array

#include <bits/stdc++.h>
using namespace std;

// Function to check
// if bit is 1 or not
bool isOne(int i)
{
    if (i == 1)
        return true;
    else
        return false;
}

// Driver Code
int main()
{

    int a[] = { 1, 0, 0, 1, 0, 0, 1 };

    int n = sizeof(a) / sizeof(a[0]);

    int count_of_one = count_if(a, a + n, isOne);

    cout << "1's: " << count_of_one << endl;
    cout << "0's: " << (n - count_of_one) << endl;

    return 0;
}
```

**输出:**

```cpp
1's: 3
0's: 4

```
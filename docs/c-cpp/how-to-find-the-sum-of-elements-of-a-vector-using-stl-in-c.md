# 如何用 C++ 中的 STL 求一个向量的元素之和？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 找到向量元素的和/](https://www.geeksforgeeks.org/how-to-find-the-sum-of-elements-of-a-vector-using-stl-in-c/)

给定一个向量，用 C++ 中的 STL 求出这个向量的元素之和。
**例:**

```cpp
Input: vec = {1, 45, 54, 71, 76, 12}
Output: 259

Input: vec = {1, 7, 5, 4, 6, 12}
Output: 35
```

**逼近:**可以借助 STL 中提供的累加()函数求和。
**语法:**

```cpp
accumulate(first_index, last_index, initial value of sum);
```

**时间复杂度:**在 first_index 和 last_index 之间的距离是线性的，即如果你的向量包含两个给定索引之间的 *n* 个元素，时间复杂度将为 O(n)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find the sum
// of Array using accumulate() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Get the vector
    vector<int> a = { 1, 45, 54, 71, 76, 12 };

    // Print the vector
    cout << "Vector: ";
    for (int i = 0; i < a.size(); i++)
        cout << a[i] << " ";
    cout << endl;

    // Find the sum of the vector
    cout << "\nSum = "
         << accumulate(a.begin(), a.end(), 0);
    return 0;
}
```

**Output:** 

```cpp
Vector: 1 45 54 71 76 12 

Sum = 259
```
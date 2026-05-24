# 如何在 C++ 中使用 STL 对一个向量进行降序排序？

> 原文:[https://www . geesforgeks . org/如何使用-stl-in-c 对向量进行降序排序/](https://www.geeksforgeeks.org/how-to-sort-a-vector-in-descending-order-using-stl-in-c/)

给定一个向量，用 C++ 中的 STL 对这个向量进行降序排序。

**例:**

```cpp
Input: vec = {1, 45, 54, 71, 76, 12}
Output: {76, 71, 54, 45, 12, 1}

Input: vec = {1, 7, 5, 4, 6, 12}
Output: {12, 7, 6, 5, 4, 1}
```

**方式:**排序可以借助 STL 中提供的 [sort()](https://www.geeksforgeeks.org/sort-c-stl/) 功能完成。

**语法:**

```cpp
sort(arr, arr + n, greater<T>()); 
```

## c++

```cpp
// C++ program to sort Vector
// in descending order
// using sort() in STL

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

    // Sort the vector in descending order
    sort(a.begin(), a.end(), greater<int>());

    // Print the reversed vector
    cout << "Sorted Vector in descending order:n";
    for (int i = 0; i < a.size(); i++)
        cout << a[i] << " ";
    cout << endl;

    return 0;
}
```

**输出**

```cpp
Vector: 1 45 54 71 76 12 
Sorted Vector in descending order:n76 71 54 45 12 1 
```
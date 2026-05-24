# 如何在 C++ 中使用 STL 反转一个向量？

> 原文:[https://www . geesforgeks . org/如何使用-stl-in-c/](https://www.geeksforgeeks.org/how-to-reverse-a-vector-using-stl-in-c/) 反转矢量

给定一个向量，用 C++ 中的 STL 反转这个向量。
**例:**

```cpp
Input: vec = {1, 45, 54, 71, 76, 12}
Output: {12, 76, 71, 54, 45, 1}

Input: vec = {1, 7, 5, 4, 6, 12}
Output: {12, 6, 4, 5, 7, 1}
```

**进场:**可以借助 STL 提供的 reverse()功能进行倒车。反向()的时间复杂度是 O(n)，其中 n 是字符串的长度。
**语法:**

```cpp
reverse(start_index, last_index);
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to reverse Vector
// using reverse() in STL

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

    // Reverse the vector
    reverse(a.begin(), a.end());

    // Print the reversed vector
    cout << "Reversed Vector: ";
    for (int i = 0; i < a.size(); i++)
        cout << a[i] << " ";
    cout << endl;

    return 0;
}
```

**Output:** 

```cpp
Vector: 1 45 54 71 76 12 
Reversed Vector: 12 76 71 54 45 1
```

时间复杂度:O(n)，其中 n 是字符串的长度。
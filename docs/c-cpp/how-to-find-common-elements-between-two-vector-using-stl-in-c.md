# 如何用 C++ 中的 STL 找到两个 Vector 之间的公共元素？

> 原文:[https://www . geesforgeks . org/如何使用-stl-in-c/](https://www.geeksforgeeks.org/how-to-find-common-elements-between-two-vector-using-stl-in-c/) 在两个向量之间查找公共元素

给定两个向量，用 C++ 中的 STL 找到这两个向量之间的公共元素。

**示例:**

> **输入:**
> vec1 = {1，45，54，71，76，12}，
> vec2 = {1，7，5，4，6，12}
> T5】输出: {1，12 }
> 
> **输入:**
> vec1 = {1，7，5，4，6，12}，
> vec2 = {10，12，11 }
> T5】输出: {1，4，12}

**方法:**借助 STL 中提供的 set _ 交集()函数，可以找到常用元素。

**语法:**

```cpp
set_intersection (InputIterator1 first1, InputIterator1 last1,
           InputIterator2 first2, InputIterator2 last2,
           OutputIterator result);

```

```cpp
// C++ program to find common elements
// between two Vectors using STL

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the vector
    vector<int> vector1 = { 1, 45, 54, 71, 76, 12 };
    vector<int> vector2 = { 1, 7, 5, 4, 6, 12 };

    // Sort the vector
    sort(vector1.begin(), vector1.end());
    sort(vector2.begin(), vector2.end());

    // Print the vector
    cout << "First Vector: ";
    for (int i = 0; i < vector1.size(); i++)
        cout << vector1[i] << " ";
    cout << endl;

    cout << "Second Vector: ";
    for (int i = 0; i < vector2.size(); i++)
        cout << vector2[i] << " ";
    cout << endl;

    // Initialise a vector
    // to store the common values
    // and an iterator
    // to traverse this vector
    vector<int> v(vector1.size() + vector2.size());
    vector<int>::iterator it, st;

    it = set_intersection(vector1.begin(),
                          vector1.end(),
                          vector2.begin(),
                          vector2.end(),
                          v.begin());

    cout << "\nCommon elements:\n";
    for (st = v.begin(); st != it; ++ st)
        cout << *st << ", ";
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
First Vector: 1 12 45 54 71 76 
Second Vector: 1 4 5 6 7 12 

Common elements:
1, 12,

```
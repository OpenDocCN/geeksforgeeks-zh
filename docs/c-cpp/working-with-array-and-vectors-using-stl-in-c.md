# 在 C++ 中使用 STL 处理数组和向量

> 原文:[https://www . geeksforgeeks . org/使用-stl-in-c/](https://www.geeksforgeeks.org/working-with-array-and-vectors-using-stl-in-c/) 处理数组和向量

使用 [STL 库](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)对数组进行排序、搜索、元素求和、求数组的最小和最大元素等基本操作非常容易。

**排序**

可以借助 [sort()](https://www.geeksforgeeks.org/sort-c-stl/) 功能进行排序。

**[排序(起始 _ 索引，最后 _ 索引)](https://www.geeksforgeeks.org/sort-c-stl/)**–对给定数组/向量进行排序。sort()函数适用于快速排序算法。C++ STL 提供了一个类似的函数排序，可以对向量或数组(随机访问的项目)进行排序。它的复杂性是 O(nlogn)。

**示例:**

```cpp
Input: {1, 7, 2, 4, 8, 3}
Output: {1, 2, 3, 4, 7, 8}

```

## 排列

```cpp
// C++ program to sort Array
// using sort() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int a[] = { 1, 7, 2, 4, 8, 3 };
    int l = sizeof(a) / sizeof(a[0]);
    sort(a, a + l);
    for (int i; i < l; i++)
        cout << a[i] << " ";
    return 0;
}
```

## 矢量

```cpp
// C++ program to sort Vector
// using sort() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> a = { 1, 7, 2, 4, 8, 3 };
    sort(a.begin(), a.end());
    for (int i; i < a.size(); i++)
        cout << a[i] << " ";
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 7 8

```

**反转**

倒车可以借助倒车()功能完成。

**反转(start_index，last_index)** :反转给定的数组/向量。

**示例:**

```cpp
Input: {1, 7, 2, 4, 8, 3}
Output: {3, 8, 4, 2, 7, 1}

```

## 排列

```cpp
// C++ program to reverse Array
// using reverse() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int a[] = { 1, 7, 2, 4, 8, 3 };
    int l = sizeof(a) / sizeof(a[0]);
    reverse(a, a + l);
    for (int i = 0; i < l; i++)
        cout << a[i] << " ";
    return 0;
}
```

## 矢量

```cpp
// C++ program to reverse Vector
// using reverse() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> a = { 1, 7, 2, 4, 8, 3 };
    reverse(a.begin(), a.end());
    for (int i; i < a.size(); i++)
        cout << a[i] << " ";
    return 0;
}
```

**Output:**

```cpp
3 8 4 2 7 1

```

**求和、最大和最小元素**

STL 中完成上述工作的功能有:

*   **累加(first_index，last_index，sum 的初始值):**这个函数返回一个数组/向量的所有元素的和。
*   ***max_element (first_index，last_index):** 求数组/向量的最大元素。
*   ***min_element (first_index，last_index):** 求数组/向量的最小元素。

## 排列

```cpp
// C++ program to find sum, max and min
// element of Array using STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int a[] = { 1, 7, 2, 4, 8, 3 };
    int l = sizeof(a) / sizeof(a[0]);
    cout << "\nsum of array: "
         << accumulate(a, a + l, 0);
    cout << "\nMaximum element in array: "
         << *max_element(a, a + l);
    cout << "\nMinimum element in array: "
         << *min_element(a, a + l);
    return 0;
}
```

## 矢量

```cpp
// C++ program to find sum, max and min
// element of Vector using STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> a = { 1, 7, 2, 4, 8, 3 };
    cout << "\nsum of vector: "
         << accumulate(a.begin(), a.end(), 0);
    cout << "\nMaximum element in vector: "
         << *max_element(a.begin(), a.end());
    cout << "\nMinimum element in vector: "
         << *min_element(a.begin(), a.end());
    return 0;
}
```

**Output:**

```cpp
sum of array: 25
Maximum element in array: 8
Minimum element in array: 1

```
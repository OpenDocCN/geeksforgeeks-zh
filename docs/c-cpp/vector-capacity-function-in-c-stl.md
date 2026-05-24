# c++ STL 中的向量容量()函数

> 原文:[https://www . geesforgeks . org/vector-capacity-function-in-c-STL/](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/)

**向量::capacity()** 函数是一个内置函数，它返回当前为向量分配的存储空间的大小，用元素表示。这个容量不一定等于向量大小。它可以等于或大于，额外的空间可以适应增长，而无需在每次插入时重新分配。容量并不限制向量的大小。当容量耗尽并且需要更多容量时，它会被容器自动扩展(重新分配存储空间)。向量大小的理论极限由成员 max_size 给出。

**语法:**

```cpp
vector_name.capacity()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前为向量分配的存储空间大小，用元素表示。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// vector::capacity() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v;

    // inserts elements
    for (int i = 0; i < 10; i++) {
        v.push_back(i * 10);
    }

    cout << "The size of vector is " << v.size();
    cout << "\nThe maximum capacity is " << v.capacity();
    return 0;
}
```

**Output:**

```cpp
The size of vector is 10
The maximum capacity is 16

```

**程序 2:**

```cpp
// C++ program to illustrate the
// vector::capacity() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v;

    // inserts elements
    for (int i = 0; i < 100; i++) {
        v.push_back(i * 10);
    }

    cout << "The size of vector is " << v.size();
    cout << "\nThe maximum capacity is " << v.capacity();
    return 0;
}
```

**Output:**

```cpp
The size of vector is 100
The maximum capacity is 128

```
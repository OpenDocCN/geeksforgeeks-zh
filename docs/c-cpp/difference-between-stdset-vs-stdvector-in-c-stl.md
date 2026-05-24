# c++ STL 中 std::set 与 std::vector 的区别

> 原文:[https://www . geesforgeks . org/difference-stdset-vs-stdvector-in-c-STL/](https://www.geeksforgeeks.org/difference-between-stdset-vs-stdvector-in-c-stl/)

[**【向量】**](https://www.geeksforgeeks.org/vector-in-cpp-stl/) :向量是类似于[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)的容器，可以在插入或删除新元素时调整大小。它是[标准模板库或 **STL**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的模板，为程序提供了更多的灵活性。向量的元素被放置在[连续存储](https://www.geeksforgeeks.org/difference-between-contiguous-and-noncontiguous-memory-allocation/)中，并使用[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)遍历。

**示例:**

```cpp
vector <int> v;
v.push_back(1);
v.push_back(2);
v.clear();

```

下面是向量在 C++ 中的实现:

## C++

```cpp
// C++ program to demonstrate the
// working of vector in cpp
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    vector<int> v;

    // Inserting elements in vector
    v.push_back(11);
    v.push_back(6);
    v.push_back(12);
    v.push_back(0);
    v.push_back(0);

    // Elements are stored in the
    // order of insertion with the
    // duplicate element
    cout << "Elements in vector are:\n";
    for (auto it : v) {
        cout << it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
Elements in vector are:
11 6 12 0 0

```
# 在 C++ STL 中设置::swap()

> 哎哎哎::1230【https://www . geeksforgeeks . org/setswap-c-STL/

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**集::swap()**
此功能用于交换两套的内容，但两套必须是**相同类型的**，尽管大小可能不同。

**语法:**

```cpp
set1.swap(set2)

```

**返回值:**无

**示例:**

```cpp
Input  : set1 = {1, 2, 3, 4}
         set2 = {5, 6, 7, 8}
         set1.swap(set2);
Output : set1 = {5, 6, 7, 8}
         set2 = {1, 2, 3, 4}

Input  : set1 = {'a', 'b', 'c', 'd'}
         set2 = {'w', 'x', 'y', 'z'}
         set1.swap(set2);
Output : set1 = {'w', 'x', 'y', 'z'}
         set2 = {'a', 'b', 'c', 'd'}

```

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two sets
    set<int> set1{ 1, 2, 3, 4 };
    set<int> set2{ 5, 6, 7, 8 };

    // Swap elements of sets
    set1.swap(set2);

    // Print the first set
    cout << "set1 = ";
    for (auto it = set1.begin();
         it != set1.end(); ++ it)
        cout << ' ' << *it;

    // Print the second set
    cout << endl
         << "set2 = ";
    for (auto it = set2.begin();
         it != set2.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
set1 =  5 6 7 8
set2 =  1 2 3 4

```

**时间复杂度:**常数
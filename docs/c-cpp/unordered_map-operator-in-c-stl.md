# c++ STL 中的无序 _ 映射运算符[]

> 原文:[https://www . geesforgeks . org/unordered _ map-operator-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-operator-in-c-stl/)

**STD::unordered _ map::operator[]**是 C++ STL 中的内置函数，如果容器中的键匹配，则返回值的引用。如果没有找到密钥，它会将该密钥插入容器。
**语法:**

```cpp
mapped_type& operator[](key_type&& k);

```

**参数:**以参数为键，访问其映射值。
**返回类型:**返回与该键关联的引用。

**例 1**

```cpp
// C++ code to illustrate the method
// unordered_map operator[]
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_map<int, int> sample;

    // Map initialization
    sample = { { 1, 2 }, { 3, 4 }, { 5, 6 } };

    // print element before doing
    // any operations
    for (auto& it : sample)
        cout << it.first << " : " << it.second << endl;

    // existing element is read
    int m = sample[1];

    // existing element is written
    sample[3] = m;

    // existing elements are accessed
    sample[5] = sample[1];

    // non existing element
    // new element 25 will be inserted
    m = sample[25];

    // new element 10 will be inserted
    sample[5] = sample[10];

    // print element after doing
    // operations
    for (auto& it : sample)
        cout << it.first << " : " << it.second << endl;
    return 0;
}
```

**Output:**

```cpp
5 : 6
3 : 4
1 : 2
10 : 0
1 : 2
5 : 0
3 : 2
25 : 0

```
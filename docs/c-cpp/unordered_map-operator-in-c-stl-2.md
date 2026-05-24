# 无序 _ 映射运算符=在 C++ STL 中

> 原文:[https://www . geesforgeks . org/unordered _ map-operator-in-c-STL-2/](https://www.geeksforgeeks.org/unordered_map-operator-in-c-stl-2/)

“=”是 C++ STL 中的一个运算符，它将一个无序 _ 映射复制(或移动)到另一个无序 _ 映射，而无序 _ 映射::运算符=是对应的运算符函数。这个函数有三个版本。

1.  第一个版本将无序映射的引用作为参数，并将其复制到无序映射中。
2.  第二个版本执行移动分配，即将无序映射的内容移动到另一个无序映射。
3.  第三个版本将初始化列表的内容分配给无序映射。

**语法**

```cpp
ump.operator= ( unordered_map& ump )
ump.operator= ( unordered_map&& ump )
ump.operator= ( initializer list )

```

**参数:**

1.  第一个版本以无序映射的引用作为参数。
2.  第二个版本将无序 _map 的 r 值引用作为参数。
3.  第三个版本以初始化列表作为参数。

**返回值:**都返回这个指针的值(*this)。

下面的程序举例说明了 C++ 中的无序 _map::operator=。
**例**

```cpp
// C++ code to illustrate the method
// unordered_map::operator=()
#include <bits/stdc++.h>
using namespace std;

// merge function
template <class T>
T merge(T a, T b)
{
    T t(a);
    t.insert(b.begin(), b.end());
    return t;
}

int main()
{
    unordered_map<int, int> sample1, sample2, sample3;

    // List initialization
    sample1 = { { 1, 2 }, { 3, 4 }, { 5, 6 } };
    sample2 = { { 7, 8 }, { 9, 10 }, { 11, 12 } };
    // Merge both lists
    sample3 = merge(sample1, sample2);

    // copy assignment
    sample1 = sample3;

    // Print the unordered_map list
    for (auto& it : sample1)
        cout << it.first << " : " << it.second << endl;

    for (auto& it : sample2)
        cout << it.first << " : " << it.second << endl;

    for (auto& it : sample3)
        cout << it.first << " : " << it.second << endl;
    return 0;
}
```

**Output:**

```cpp
7 : 8
9 : 10
11 : 12
1 : 2
3 : 4
5 : 6
11 : 12
9 : 10
7 : 8
7 : 8
9 : 10
11 : 12
1 : 2
3 : 4
5 : 6

```
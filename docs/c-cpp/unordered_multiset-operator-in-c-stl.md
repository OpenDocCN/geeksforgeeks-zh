# c++ STL 中的无序 _ 多集运算符=

> 原文:[https://www . geesforgeks . org/unordered _ multist-operator-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-operator-in-c-stl/)

**'='** 是 **C++ STL** 中的一个运算符，它将一个**无序 _ 多集**复制(或移动)到另一个无序 _ 多集，而无序 _ 多集::运算符=是对应的运算符函数。该功能有三个版本:

*   The first version takes reference of an unordered_multiset as an argument and copies it to an unordered_multiset.

    **语法:**

    ```cpp
    ums1.operator=(unordered_multiset &ums2)
    ```

    **参数:**第一个版本以一个无序 _ 多集的引用作为参数。

*   The second version performs a move assignment i.e it moves the content of an unordered_multiset to another unordered_multiset.

    **语法:**

    ```cpp
    ums1.operator=(unordered_multiset &&ums2)
    ```

    **参数:**第二个版本以无序多集的 r 值引用作为参数

*   The third version assigns contents of an initializer list to an unordered_multiset.

    **语法:**

    ```cpp
    ums1.operator=(initializer list)
    ```

    **参数:**第三个版本以一个初始化列表作为参数。

**返回值:**都返回这个指针的值(*this)。

以下程序说明了无序 _ 多集::运算符=。

```cpp
// C++ code to illustrate the method
// unordered_multiset::operator=()

#include <iostream>
#include <unordered_set>
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
    unordered_multiset<int> sample1, sample2, sample3;

    // List initialization
    sample1 = { 1, 2, 2, 3, 3, 4, 4, 4, 3, 4 };
    sample2 = { 1, 2, 3, 1, 4 };

    // Merge both unordered_multisets and
    // move the result to sample1
    sample3 = merge(sample1, sample2);

    // copy assignment
    sample1 = sample3;

    // Print the unordered_set list
    for (auto it = sample1.begin(); it != sample1.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample2.begin(); it != sample2.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample3.begin(); it != sample3.end(); ++ it)
        cout << *it << " ";
    cout << endl;
}
```

**Output:**

```cpp
1 1 1 2 2 2 3 3 3 3 4 4 4 4 4 
4 3 2 1 1 
1 1 1 2 2 2 3 3 3 3 4 4 4 4 4

```
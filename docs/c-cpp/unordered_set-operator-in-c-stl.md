# c++ STL 中的无序 _ 集合运算符=

> 原文:[https://www . geesforgeks . org/unordered _ set-operator-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl/)

“=”是 C++ STL 中的一个运算符，它将一个无序 _ 集复制(或移动)到另一个无序 _ 集，而无序 _ 集::运算符=是对应的运算符函数。这个函数有三个版本。

*   第一个版本以无序集的引用作为参数，并将其复制到无序集。
*   第二个版本执行移动分配，即将无序集的内容移动到另一个无序集。
*   第三个版本将初始值设定项列表的内容分配给无序集。

**语法**

```cpp
uset.operator= ( unordered_set& us )
uset.operator= ( unordered_set&& us )
uset.operator= ( initializer list )

```

**参数:**

*   第一个版本以无序集的引用作为参数。
*   第二个版本将无序集的 r 值引用作为参数。
*   第三个版本以初始化列表作为参数。

**返回值:**都返回这个指针的值(*this)。

下面的程序举例说明了 C++ 中的**无序 _ 集合::运算符=** 。
T3】节目:

```cpp
// C++ code to illustrate the method 
// unordered_set::operator=()
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
    unordered_set<int> sample1, sample2, sample3;

    // List initialization
    sample1 = { 7, 8, 9 };
    sample2 = { 9, 10, 11, 12 };

    // Merge both lists
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
10 11 12 7 8 9 
12 11 10 9 
10 11 12 7 8 9

```
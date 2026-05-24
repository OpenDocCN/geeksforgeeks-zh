# 在 C++ STL 中设置下界()函数

> 原文:[https://www . geesforgeks . org/set-下界 _ function-in-c-STL/](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/)

**set::lower_bound()** 是 C++ STL 中的一个内置函数，它返回一个指向容器中元素的迭代器，该元素相当于参数中传递的 k。如果集合容器中不存在 k，则函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大值，则返回的迭代器指向集合容器中最后一个元素之外的元素。
**语法:**

```cpp
set_name.lower_bound(key)

```

**参数:**该函数接受一个强制参数*键*，该键指定要返回其下限的元素。
**返回值:**函数返回一个迭代器，指向容器中的元素，相当于参数中传递的 k。如果集合容器中不存在 k，则函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大值，则返回的迭代器相当于 s.end()(一个特殊的迭代器指向最后一个元素之外)。
以下程序说明上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// set::lower_bound() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    set<int> s;

    // Function to insert elements
    // in the set container
    s.insert(1);
    s.insert(4);
    s.insert(2);
    s.insert(5);
    s.insert(6);

    cout << "The set elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // when 2 is present
    auto it = s.lower_bound(2);
    if (it != s.end()) {
        cout << "\nThe lower bound of key 2 is ";
        cout << (*it) << endl;
    }
    else
        cout << "The element entered is larger than the "
                "greatest element in the set"
             << endl;
    // when 3 is not present
    // points to next greater after 3
    it = s.lower_bound(3);
    if (it != s.end()) {
        cout << "The lower bound of key 3 is ";
        cout << (*it) << endl;
    }
    else
        cout << "The element entered is larger than the "
                "greatest element in the set"
             << endl;

    // when 8 exceeds the max element in set
    it = s.lower_bound(8);
    if (it != s.end()) {
        cout << "The lower bound of key 8 is ";
        cout << (*it) << endl;
    }
    else
        cout << "The element is larger than the greatest "
                "element in the set"
             << endl;

    return 0;
}
```

**Output:** 

```cpp
The set elements are: 1 2 4 5 6 
The lower bound of key 2 is 2
The lower bound of key 3 is 4
The element is larger than the greatest element in the set

```
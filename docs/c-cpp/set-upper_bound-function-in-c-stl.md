# 在 C++ STL 中设置 upper_bound()函数

> 原文:[https://www . geesforgeks . org/set-upper _ bound-function-in-c-STL/](https://www.geeksforgeeks.org/set-upper_bound-function-in-c-stl/)

**set::upper_bound()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向刚好大于 k 的下一个元素，如果传入参数的键超过了容器中的最大键，那么返回的迭代器指向 set 容器中的**倒数第二个**元素(可以使用 set end()函数识别)。

**语法:**

```cpp
set_name.upper_bound(key)
```

**参数:**该函数接受单个强制参数*键*，该键指定要返回其上限的元素。

**返回值:**函数返回一个迭代器，指向刚好大于 k 的下一个元素，如果传入参数的键超过了容器中的最大键，那么迭代器指向 std::end()，指向集合最后一个元素旁边的元素。

**例 1:** 下面的程序说明了上述功能:

```cpp
// CPP program to demonstrate the
// set::upper_bound() function
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
    // points to next element after 2
    auto it = s.upper_bound(2);
    cout << "\nThe upper bound of key 2 is ";
    cout << (*it) << endl;

    // when 3 is not present
    // points to next greater after 3
    it = s.upper_bound(3);
    cout << "The upper bound of key 3 is ";
    cout << (*it) << endl;

    return 0;
}
```

**Output:**

```cpp
The set elements are: 1 2 4 5 6 
The upper bound of key 2 is 4
The upper bound of key 3 is 4

```

**示例 2:** 下面是一个更好的代码，它还检查给定的元素是否大于或等于最大值。

```cpp
// CPP program to demonstrate the
// set::upper_bound() function
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

    int key = 8;
    auto it = s.upper_bound(key);
    if (it == s.end())
        cout << "The given key is greater "
                "than or equal to the largest element \n";
    else
        cout << "The immediate greater element "
             << "is " << *it << endl;

    key = 3;
    it = s.upper_bound(key);
    if (it == s.end())
        cout << "The given key is greater "
                "than or equal to the largest element \n";
    else
        cout << "The immediate greater element "
             << "is " << *it << endl;

    return 0;
}
```

**Output:**

```cpp
The given key is greater than or equal to the largest element 
The immediate greater element is 4

```
# c++ STL 中的多集下界()，示例

> 原文:[https://www . geesforgeks . org/multist-下界 _ in-CPP-STL-with-examples/](https://www.geeksforgeeks.org/multiset-lower_bound-in-cpp-stl-with-examples/)

**多集::下界()**是 C++ STL 中的一个内置函数，它返回一个指向容器中第一个元素的迭代器，该元素相当于参数中传递的 k。如果集合容器中不存在 k，函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过容器中的最大值，则返回的迭代器打印容器中的元素数。

**语法:**

```cpp
multiset_name.lower_bound(key)
```

**参数:**该函数接受一个强制参数键，该键指定要返回其下界的元素。

**返回值:**函数返回一个迭代器。

下面的程序说明了上面的功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::lower_bound() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the multiset container
    s.insert(1);
    s.insert(2);
    s.insert(2);
    s.insert(1);
    s.insert(4);

    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // when 2 is present
    auto it = s.lower_bound(2);
    cout << "\nThe lower bound of key 2 is ";
    cout << (*it) << endl;

    // when 3 is not present
    // points to next greater after 3
    it = s.lower_bound(3);
    cout << "The lower bound of key 3 is ";
    cout << (*it) << endl;

    // when 5 exceeds the max element in multiset
    it = s.lower_bound(7);
    cout << "The lower bound of key 7 is ";
    cout << (*it) << endl;

    return 0;
}
```

**Output:**

```cpp
The multiset elements are: 1 1 2 2 4 
The lower bound of key 2 is 2
The lower bound of key 3 is 4
The lower bound of key 7 is 5

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// multiset::lower_bound() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the multiset container
    s.insert(1);
    s.insert(3);
    s.insert(3);
    s.insert(5);
    s.insert(4);

    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // when 3 is present
    auto it = s.lower_bound(3);
    cout << "\nThe lower bound of key 3 is ";
    cout << (*it) << endl;

    // when 2 is not present
    // points to next greater after 2
    it = s.lower_bound(2);
    cout << "The lower bound of key 2 is ";
    cout << (*it) << endl;

    // when 10 exceeds the max element in multiset
    it = s.lower_bound(10);
    cout << "The lower bound of key 10 is ";
    cout << (*it) << endl;

    return 0;
}
```

**Output:**

```cpp
The multiset elements are: 1 3 3 4 5 
The lower bound of key 3 is 3
The lower bound of key 2 is 3
The lower bound of key 10 is 5

```
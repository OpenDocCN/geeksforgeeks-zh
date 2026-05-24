# c++ STL 中的多集上界()，示例

> 原文:[https://www . geesforgeks . org/multist-upper _ bound-in-CPP-STL-with-examples/](https://www.geeksforgeeks.org/multiset-upper_bound-in-cpp-stl-with-examples/)

**multist::upper _ bound()**是 C++ STL 中的一个内置函数，它返回一个迭代器，该迭代器指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大键，则迭代器返回的元素指向容器中最后一个元素之后的位置。

**语法:**

```cpp
multiset_name.upper_bound(key)
```

**参数:**该函数接受一个强制参数键，指定要返回其上限的元素。

**返回值:**函数返回一个迭代器。

以下程序说明了上述功能:

**程序 1:**

## c++

```cpp
// C++ program to demonstrate the
// multiset::upper_bound() function
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
    auto it = s.upper_bound(3);
    cout << "\nThe upper bound of key 3 is ";
    cout << (*it) << endl;

    // when 2 is not present
    // points to next greater after 2
    it = s.upper_bound(2);
    cout << "The upper bound of key 2 is ";
    cout << (*it) << endl;

    // when 10 exceeds the max element in multiset
    it = s.upper_bound(10);
    cout << "The upper bound of key 10 is ";
    cout << (*it) << endl;

    return 0;
}
```

**输出:**

```cpp
The multiset elements are: 1 3 3 4 5 
The upper bound of key 3 is 4
The upper bound of key 2 is 3
The upper bound of key 10 is 5
```

**程序二:**

## c++

```cpp
// C++ program to demonstrate the
// multiset::upper_bound() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the multiset container
    s.insert(10);
    s.insert(13);
    s.insert(13);
    s.insert(25);
    s.insert(24);

    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // when 10 is present
    auto it = s.upper_bound(10);
    cout << "\nThe upper bound of key 10 is ";
    cout << (*it) << endl;

    // when 2 is not present
    // points to next greater after 2
    it = s.upper_bound(2);
    cout << "The upper bound of key 2 is ";
    cout << (*it) << endl;

    // when 24 exceeds is the max element
    it = s.upper_bound(24);
    cout << "The upper bound of key 24 is ";
    cout << (*it) << endl;

    return 0;
}
```

**输出**

```cpp
The multiset elements are: 10 13 13 24 25 
The upper bound of key 10 is 13
The upper bound of key 2 is 10
The upper bound of key 24 is 25
```

[多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)的所有功能
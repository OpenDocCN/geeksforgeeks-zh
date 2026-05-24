# c++ STL 中的多集 equal_range()函数

> 原文:[https://www . geesforgeks . org/multist-equal _ range-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-equal_range-function-in-c-stl/)

**多集::equal_range()** 是 C++ STL 中的一个内置函数，它返回一个对的迭代器。该对指的是包含容器中所有元素的范围，这些元素的键等价于 K。下限将是元素本身，上限将指向键 K 之后的下一个元素。如果没有元素匹配键 K，则返回的范围长度为 0，根据容器的内部比较对象(key_comp)，两个迭代器都指向大于 K 的第一个元素。如果键超过集合容器中的最大元素，它将返回一个迭代器，指向多集合容器中的最后一个元素。

**语法:**

```cpp
multiset_name.equal_range(key) 

```

**参数:**该函数接受一个强制参数*键*，该参数指定要返回其在多集容器中的范围的键。

**返回值:**函数返回一对迭代器。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::equal_range() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Inserts elements
    s.insert(1);
    s.insert(6);
    s.insert(2);
    s.insert(5);
    s.insert(3);
    s.insert(3);
    s.insert(5);
    s.insert(3);

    // prints the multiset elements
    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // Function returns lower bound and upper bound
    auto it = s.equal_range(3);
    cout << "\nThe lower bound of 3 is " << *it.first;
    cout << "\nThe upper bound of 3 is " << *it.second;

    // Function returns the last element
    it = s.equal_range(10);
    cout << "\nThe lower bound of 10 is " << *it.first;
    cout << "\nThe upper bound of 10 is " << *it.second;

    // Function returns the range where the
    // element greater than 0 lies
    it = s.equal_range(0);
    cout << "\nThe lower bound of 0 is " << *it.first;
    cout << "\nThe upper bound of 0 is " << *it.second;

    return 0;
}
```

**Output:**

```cpp
The multiset elements are: 1 2 3 3 3 5 5 6 
The lower bound of 3 is 3
The upper bound of 3 is 5
The lower bound of 10 is 8
The upper bound of 10 is 8
The lower bound of 0 is 1
The upper bound of 0 is 1

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// multiset::equal_range() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Inserts elements
    s.insert(1);
    s.insert(6);
    s.insert(2);
    s.insert(5);
    s.insert(3);
    s.insert(3);
    s.insert(5);
    s.insert(3);

    // prints the multiset elements
    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // Function returns lower bound and upper bound
    auto it = s.equal_range(3);
    cout << "\nThe lower bound of 3 is " << *it.first;
    cout << "\nThe upper bound of 3 is " << *it.second;

    s.erase(it.first, it.second);

    // prints the multiset elements after erasing the
    // range
    cout << "\nThe multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The multiset elements are: 1 2 3 3 3 5 5 6 
The lower bound of 3 is 3
The upper bound of 3 is 5
The multiset elements are: 1 2 5 5 6

```
# c++ STL 中的多集 crbegin()和 crend()函数

> 原文:[https://www . geesforgeks . org/multist-Cr begin-and-crend-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-crbegin-and-crend-function-in-c-stl/)

**multist::Cr begin()**是 C++ STL 中的一个内置函数，它返回一个指向容器中最后一个元素的常量反向迭代器。迭代器不能用于修改多集容器中的元素。迭代器可以相应地增加或减少来遍历集合。

**语法:**

```cpp
constant_reverse_iterator multiset_name.crbegin()

```

**参数:**函数不取任何参数。

**返回值:**函数返回指向容器中最后一个元素的常量迭代器。

下面的程序说明了 multist::Cr begin()方法。

## c++

```cpp
// C++ program to demonstrate the
// multiset::crbegin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 10, 15, 11, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 5);

    cout << "The last element: " << *(s.crbegin()) << endl;
    // prints all elements in set
    for (auto it = s.crbegin(); it != s.crend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The last element: 15
15 14 11 10 10

```

**multist::crend()**是 C++ STL 中的一个内置函数，它返回一个指向容器中第一个元素之前的位置的常量反向迭代器。迭代器不能用于修改多集容器中的元素。迭代器可以相应地增加或减少来遍历集合。

**语法:**

```cpp
constant_reverse_iterator multiset_name.crend()

```

**参数:**函数不取任何参数。

**返回值:**函数返回一个常量迭代器，指向多集容器中第一个元素之前的位置。

下面的程序说明了 multist::crend()方法。

## c++

```cpp
// C++ program to demonstrate the
// multiset::crend() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 12, 15, 11, 10, 10, 16, 16 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 8);

    // prints all elements in set
    for (auto it = s.crbegin(); it != s.crend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
16 16 15 14 12 11 10 10

```
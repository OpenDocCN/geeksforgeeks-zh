# c++ STL 中的多集 cbegin()和 cend()函数

> 原文:[https://www . geesforgeks . org/multist-CBE gin-and-cend-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-cbegin-and-cend-function-in-c-stl/)

**multist::CBE gin()**是 C++ STL 中的内置函数，它返回指向容器中第一个元素的常量迭代器。迭代器不能用于修改集合容器中的元素。迭代器可以相应地增加或减少来遍历集合。

**语法:**

```cpp
constant_iterator multiset_name.cbegin()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回指向容器中第一个元素的常量迭代器。

下面的程序说明了 multist::CBE gin()方法。

## c++

```cpp
// C++ program to demonstrate the
// multiset::cbegin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 10, 15, 11, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 5);

    // Prints the first element
    cout << "The first elements is: " << *(s.cbegin()) << endl;

    // prints all elements in set
    for (auto it = s.cbegin(); it != s.cend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The first elements is: 10
10 10 11 14 15

```

**多集::cend()** 是 C++ STL 中的一个内置函数，它返回一个指向容器中最后一个元素之后的位置的常量迭代器。迭代器不能用于修改集合容器中的元素。迭代器可以相应地增加或减少遍历集合。

**语法:**

```cpp
constant_iterator multiset_name.cend()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个常量迭代器，指向容器中容器最后一个元素的位置。

下面的程序说明了 multist::cend()方法。

## c++

```cpp
// C++ program to demonstrate the
// multiset::cend() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 10, 15, 11, 10, 15, 17, 17 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 8);

    // prints all elements in set
    for (auto it = s.cbegin(); it != s.cend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
10 10 11 14 15 15 17 17

```
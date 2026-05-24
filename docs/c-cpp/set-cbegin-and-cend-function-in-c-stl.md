# 在 C++ STL 中设置 cbegin()和 cend()函数

> 原文:[https://www . geesforgeks . org/set-CBE gin-and-cend-function-in-c-STL/](https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/)

**set::cbegin()** 是 C++ STL 中的内置函数，它返回指向容器中第一个元素的常量迭代器。迭代器不能用于修改集合容器中的元素。迭代器可以相应地增加或减少来遍历集合。

**语法:**

```cpp
constant_iterator set_name.cbegin()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回指向容器中第一个元素的常量迭代器。

演示 set::cbegin()方法的程序。

## c++

```cpp
// C++ program to demonstrate the
// set::cbegin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 12, 15, 11, 10 };

    // initializes the set from an array
    set<int> s(arr, arr + 5);

    // prints all elements in set
    for (auto it = s.cbegin(); it != s.cend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
10 11 12 14 15

```

**set::cend()** 是 C++ STL 中的内置函数，返回指向容器中最后一个元素之后的位置的常量迭代器。迭代器不能用于修改集合容器中的元素。迭代器可以相应地增加或减少遍历集合。

**语法:**

```cpp
constant_iterator set_name.cend()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个常量迭代器，指向容器中容器最后一个元素的位置。

演示 set::cend()方法的程序。

## c++

```cpp
// C++ program to demonstrate the
// set::cend() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 12, 15, 11, 10 };

    // initializes the set from an array
    set<int> s(arr, arr + 5);

    // prints all elements in set
    for (auto it = s.cbegin(); it != s.cend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
10 11 12 14 15

```
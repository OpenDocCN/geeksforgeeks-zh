# 在 C++ STL 中设置 value_comp()函数

> 原文:[https://www . geesforgeks . org/set-value _ comp-function-in-c-STL/](https://www.geeksforgeeks.org/set-value_comp-function-in-c-stl/)

**set::value_comp()** 是 cpp 中的一个内置函数，它返回容器使用的比较对象的副本。这个对象决定了容器中元素的顺序。它是一个函数指针或函数对象，接受与容器元素相同类型的两个参数，如果第一个参数被认为在其定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。如果 value_comp 反身返回 false(即，无论元素作为参数传递的顺序如何)，则集合中的两个元素被认为是等价的。

**语法:**

```cpp
value_compare set_name.value_comp() 

```

**参数:**此功能不接受任何参数。

**返回值:**函数返回容器使用的比较对象的副本。

下面的程序说明了上面的功能。

```cpp
// CPP program to demonstrate the
// set::value_comp()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising set a
    set<int> a;

    set<int>::value_compare comp = a.value_comp();

    // inserting elements to set a
    for (int i = 0; i <= 10; i++)
        a.insert(i);

    cout << "Set a has the numbers ";

    // start stores value of the last element of set a
    int start = *a.rbegin();

    // initialising iterator it
    set<int>::iterator it = a.begin();

    // Function that prints all the numbers in set
    do {
        std::cout << *it << " ";
    } while (comp(*(++ it), start));

    std::cout << '\n';

    return 0;
}
```

**输出:**

```cpp
Set a has the numbers 0 1 2 3 4 5 6 7 8 9

```
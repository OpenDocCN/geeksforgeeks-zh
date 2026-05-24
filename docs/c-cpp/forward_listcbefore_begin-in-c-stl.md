# c++ STL 中的 forward_list::cbefore_begin()

> 原文:[https://www . geesforgeks . org/forward _ listcbefore _ begin-in-c-STL/](https://www.geeksforgeeks.org/forward_listcbefore_begin-in-c-stl/)

**forward_list::CBE fore _ begin()**是 CPP STL 中的一个内置函数，它返回一个常量随机访问迭代器，该迭代器指向 forward _ list 第一个元素之前的位置。此函数获得的迭代器可用于在容器中进行迭代，但不能用于修改它所指向的对象的内容，即使对象本身不是常数。

**语法:**

```cpp
forwardlist_name.cbefore_begin()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个常量随机访问迭代器，指向 forward_list 第一个元素之前的位置。

下面程序演示了上面的功能:

```cpp
// C++ program to illustrate the
// cbefore_begin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the forward list
    forward_list<int> fl = { 20, 30, 40, 50 };

    // performing cbefore_begin function
    auto it = fl.cbefore_begin();

    // inserting element before the first element
    fl.insert_after(it, 10);

    cout << "Element of the list are:" << endl;

    // loop to print the elements of the list
    for (auto it = fl.begin(); it != fl.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
Element of the list are:
10 20 30 40 50

```
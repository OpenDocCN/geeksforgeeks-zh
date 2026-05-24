# c++ STL 中的 forward_list resize()函数

> 原文:[https://www . geesforgeks . org/forward _ list-resize-function-in-c-STL/](https://www.geeksforgeeks.org/forward_list-resize-function-in-c-stl/)

**forward_list::resize()** 是 C++ STL 中的一个内置函数，可以改变 forward_list 的大小。如果给定的大小大于当前大小，则在 forward_list 的末尾插入新元素。如果给定的大小小于当前大小，那么额外的元素将被销毁。

**语法:**

```cpp
forwardlist_name.resize(n)
```

**参数:**该函数只接受一个指定转发列表新大小的强制参数 n。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// forward_list::resize() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    forward_list<int> fl = { 10, 20, 30, 40, 50 };

    // Prints the forward list elements
    cout << "The contents of forward list :";
    for (auto it = fl.begin(); it != fl.end(); ++ it)
        cout << *it << " ";

    cout << endl;

    // resize to 7
    fl.resize(7);

    // // Prints the forward list elements after resize()
    cout << "The contents of forward list :";
    for (auto it = fl.begin(); it != fl.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The contents of forward list :10 20 30 40 50 
The contents of forward list :10 20 30 40 50 0 0

```

**程序 2:**

```cpp
// C++ program to illustrate the
// forward_list::resize() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    forward_list<int> fl = { 10, 20, 30, 40, 50 };

    // Prints the forward list elements
    cout << "The contents of forward list :";
    for (auto it = fl.begin(); it != fl.end(); ++ it)
        cout << *it << " ";

    cout << endl;

    // resize to 3
    fl.resize(3);

    // Prints the forward list elements after resize()
    cout << "The contents of forward list :";
    for (auto it = fl.begin(); it != fl.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The contents of forward list :10 20 30 40 50 
The contents of forward list :10 20 30

```
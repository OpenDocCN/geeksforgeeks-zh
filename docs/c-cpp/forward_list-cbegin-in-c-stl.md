# c++ STL 中的 forward_list cbegin()

> 原文:[https://www.geeksforgeeks.org/forward_list-cbegin-in-c-stl/](https://www.geeksforgeeks.org/forward_list-cbegin-in-c-stl/)

forward_list::cbegin()是 C++ STL 中的一个函数，它返回一个指向 forward_list 第一个元素的常量迭代器。

**语法:**

```cpp
forward_list_name.cbegin()
```

**参数:**此功能不接受任何参数。

**返回值:**这个函数返回一个指向常量内容的迭代器。因为迭代器不是常数，所以它可以增加或减少或修改，但是因为它不能用于修改它的内容，即使转发列表不是常数。如果转发列表为空，函数返回的迭代器将不会被取消引用。

以下程序说明了该功能的使用:

**程序 1:**

```cpp
// CPP program to illustrate
// forward_list::cbegin();

#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> sample = { 45, 87, 6 };

    // Get the first element by
    // dereferencing the iterator
    // returned by sample.cbegin()
    cout << "1st element of sample: ";
    cout << *sample.cbegin();
}
```

**Output:**

```cpp
1st element of sample: 45

```

**程序 2:**

```cpp
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> sample = { 7, 4, 9, 15 };

    // Display the elements

    cout << "sample: ";
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << *it << " ";
}
```

**Output:**

```cpp
sample: 7 4 9 15

```
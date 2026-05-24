# c++ STL 中的多集 max_size()

> 原文:[https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/](https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/)

**多集::max_size()** 是 C++ STL 中的一个观察器函数，它返回一个容器可以容纳的最大元素数量。这个限制可能是由于系统或库的实现。作为一个观察函数，它不会以任何方式修改多集。

**语法:**

```cpp
multiset_name.max_size()
```

**参数:**此功能不接受任何参数。

**返回值:**这个方法返回一个正整数，表示容器可以容纳的最大元素数量。

**注意:**这个函数返回的值通常是容器大小的**理论极限**。但是，在运行时，由于**内存限制**，容器的大小可能被限制为小于 max_size()函数返回的值。

下面的程序演示了无序 _ 多集::max_size()

```cpp
// C++ program to demonstrate the use of
// multiset max_size()

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    // declaring unordered multiset gfg
    unordered_multiset<int> gfg;
    unsigned int max_elements;

    // calculating the max size of multiset gfg
    max_elements = gfg.max_size();

    cout << "Number of elements "
         << "the multiset can hold is: "
         << max_elements << endl;
    return 0;
}
```

**输出:**

```cpp
Number of elements the multiset can hold is: 4294967295

```
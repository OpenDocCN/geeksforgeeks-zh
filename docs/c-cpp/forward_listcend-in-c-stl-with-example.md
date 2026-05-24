# c++ STL 中的 forward_list::cend()，示例

> 原文:[https://www . geeksforgeeks . org/forward _ listcend-in-c-STL-with-example/](https://www.geeksforgeeks.org/forward_listcend-in-c-stl-with-example/)

**forward_list::cend()** 是 C++ STL 中的一个函数，它返回一个指向 forward_list 最后一个元素的常量迭代器。函数返回的迭代器不指向容器中的任何元素，而是指向转发列表容器最后一个元素后面的位置。

函数返回的迭代器指向常量内容。因为迭代器本身不是常数，所以它可以增加或减少或修改，但是即使转发列表不是常数，也不能用来修改它的内容。
由于迭代器不指向正向列表的任何元素，因此在任何情况下都不能取消对它的引用。

**语法:**

```cpp
forward_list_name.cend()
```

**参数:**函数不取任何参数。

**返回值:**函数返回一个**迭代器**，指向前向列表容器的结束元素。

以下程序说明了 forward_list::cend()函数的使用:

```cpp
// CPP program to illustrate
// forward_list::cend();

#include <forward_list>
#include <iostream>
using namespace std;

int main()
{

    // Initializing the forward list
    forward_list<int> sample = { 7, 54, 47, 48 };

    // Display sample
    cout << "sample: ";
    for (auto it = sample.cbegin();
         it != sample.cend();
         it++)
        cout << *it << " ";
}
```

**Output:**

```cpp
sample: 7 54 47 48

```
# forward_list中的emplace_after()和emplace_front()

> 原文：[https://www.geeksforgeeks.org/forward_list-emplace_after-and-emplace_front-in-c-stl/](https://www.geeksforgeeks.org/forward_list-emplace_after-and-emplace_front-in-c-stl/)

## forward_list::emplace_after()

`forward_list::emplace_after()` 是 C++ STL 中的一个内置函数，用于在参数指定的位置之后插入一个新元素。此操作会使容器的大小增加一。

**语法：**

```cpp
forward_list_name.emplace_after(iterator position, elements)
```

**参数：** 该函数接受两个强制参数，如下所述：

*   `position`：它指定一个迭代器，该迭代器指向容器中将在其后插入新元素的位置。
*   `elements`：指定要在位置后插入的新元素。

**返回值：** 这个函数返回一个迭代器，指向新插入的元素。

下面的程序说明了上述功能：

```cpp
// C++ program to illustrate the
// forward_list::emplace_after() function
#include <forward_list>
#include <iostream>

using namespace std;

int main()
{

    forward_list<int> fwlist = { 1, 2, 3, 4, 5 };

    auto it_new = fwlist.before_begin();

    // use of emplace_after function
    // inserts elements at positions
    it_new = fwlist.emplace_after(it_new, 8);
    it_new = fwlist.emplace_after(it_new, 10);

    cout << "The elements are: ";
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**输出：**

```cpp
The elements are: 8 10 1 2 3 4 5
```

## forward_list::emplace_front()

`forward_list::emplace_front()` 是 C++ 中的一个内置函数，用于在 `forward_list` 的开头、第一个元素之前插入一个新元素。这会使容器的大小增加一。

**语法：**

```cpp
forward_list_name.emplace_front(elements)
```

**参数：** 该函数接受一个强制参数 `elements`，该元素将在容器的开始处插入。

**返回值：** 不返回任何内容。

下面的程序说明了上面的功能。

```cpp
// C++ program to illustrate the
// forward_list::emplace_front() function
#include <forward_list>
#include <iostream>

using namespace std;

int main()
{

    forward_list<int> fwlist = { 1, 2, 3, 4, 5 };

    // use of emplace_front function
    // inserts elements at front
    fwlist.emplace_front(8);
    fwlist.emplace_front(10);

    cout << "Elements are: ";
    // Auto iterator
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**输出：**

```cpp
Elements are: 10 8 1 2 3 4 5
```
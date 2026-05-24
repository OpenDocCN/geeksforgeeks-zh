# 如何在 C++ 中获取列表中特定位置的元素

> 原文:[https://www . geeksforgeeks . org/如何获取 c 列表中特定位置的元素/](https://www.geeksforgeeks.org/how-to-get-element-at-specific-position-in-list-in-c/)

该列表没有[随机访问运算符](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/) []来通过索引访问元素，因为 **std::list** 在内部将元素存储在[双链表](https://www.geeksforgeeks.org/doubly-linked-list/)中。所以，要在任意**K**位置访问一个元素，思路是从开始到**K**元素逐一迭代。而不是迭代 **K** 次。为此，使用一个[**STL**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)[STD::advance()](https://www.geeksforgeeks.org/stdadvance-in-cpp/)函数在线性时间内找到它。

**语法:**

```cpp
advance(InputIterator& it, Distance N)
```

**参数:**这个函数接受两个参数，即遍历列表的迭代器和要移动到的位置。对于[随机访问](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)和[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)，位置可以为负。

**返回类型:**该功能没有返回类型。

下面是上述方法的 C++ 实现:

## c++

```cpp
// C++ program to access  Kth element
// of the list using advanced
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Create list with initial value 100
    list<int> li(5, 100);

    // Insert 20 and 30 to the list
    li.push_back(20);
    li.push_back(30);

    // Elements of list are
    // 100, 100, 100, 100, 100, 20, 30

    // Initialize iterator to list
    list<int>::iterator it = li.begin();

    // Move the iterator by 5 elements
    advance(it, 5);

    // Print the element at the it
    cout << *it;

    return 0;
}
```

**输出:**

```cpp
20

```
# 如何在 C++ STL 中找到 std::forward_list 的大小

> 原文:[https://www . geesforgeks . org/how-to-find-size-of-stdforward _ list-in-c-STL/](https://www.geeksforgeeks.org/how-to-find-size-of-stdforward_list-in-c-stl/)

[在](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 的[标准模板库](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)中转发列表。它位于#include < forward_list >头文件下。实现为[单链表](https://www.geeksforgeeks.org/data-structures/linked-list/singly-linked-list/)。首次在 [C++ 11](https://www.geeksforgeeks.org/c-11-vs-c-14-vs-c-17/) 中引入。转发列表是序列容器，允许从序列中的任何位置进行恒定时间的插入和擦除操作。对于转发列表，不支持快速随机访问。

> 与其他 STL 库不同，std::forward_list 没有任何 size()方法。因此，在本文中，我们将向您展示如何在 C++ STL 中获取 std::forward_list 的大小。

检索转发列表的大小时出现问题，因为 std::forward_list 没有任何 std::size()成员函数。要获取转发列表的大小，可以使用 [std::distance()函数](https://www.geeksforgeeks.org/stddistance-in-c/)。

**进场:**

由于 std::distance()函数采用两个迭代器作为参数，并返回一个整数，因此可以传递 [std::begin()](https://www.cplusplus.com/reference/iterator/begin/) 和 [std::end()](https://www.cplusplus.com/reference/iterator/end/) 函数，它们指向第一项的地址和最后一项之后的地址。

**语法:**

> size = distance(forward _ list . begin()、forward _ list . end())；

下面是实现上述方法的 C++ 代码:

## C++ 14

```cpp
// C++ program to implement
// the above approach

#include <forward_list>
#include <iostream>
using namespace std;

// Driver code
int main()
{

    forward_list<int> l1 = { 3, 5, 6, 9, 6 };

    // l.size() will throw an error, since
    // there is no size() method for
    // forward_list. So, to calculate the
    // size, we will use std::distance(iterator1,
    // iterator2), where iterator1 will be
    // l.begin() and iterator2 will be l.end()
    int size = distance(l1.begin(),
                        l1.end());

    cout << "Size of l1 is : " << size << endl;

    l1.remove(6);

    // It will erase all instances of 6
    // from the list
    size = distance(l1.begin(), l1.end());

    cout << "Size of l1, after removing all"
         << " instances of 6 is : " << size << endl;

    forward_list<int> l2 = { 6, 11, 0 };

    int size2 = distance(l2.begin(),
                         l2.end());

    cout << "Size of l2, before assigning"
         << " it to l1 : " << size2
         << endl;

    l1.splice_after(l1.begin(), l2);

    // It will assign l2 to l at the
    // provided iterator, making l1
    // as empty.
    size = distance(l1.begin(),
                    l1.end());
    size2 = distance(l2.begin(),
                     l2.end());

    cout << "Size of l1, after assigning"
         << " l2 to it : " << size << endl;

    cout << "Size of l2, after assigning"
         << " it to l1 : " << size2 << endl;
}
```

**Output:** 

```cpp
Size of l1 is : 5
Size of l1, after removing all instances of 6 is : 3
Size of l2, before assigning it to l1 : 3
Size of l1, after assigning l2 to it : 6
Size of l2, after assigning it to l1 : 0
```
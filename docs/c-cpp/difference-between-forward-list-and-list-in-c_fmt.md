# C++ 中转发列表和列表的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-forward-list-and-list-in-c/](https://www.geeksforgeeks.org/difference-between-forward-list-and-list-in-c/)

[`转发列表`](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)是一个允许单向顺序访问其数据的序列容器。它包含相同类型的数据。在 [`STL`](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中，已经使用[单链表](https://www.geeksforgeeks.org/data-structures/linked-list/)实现，插入和删除需要恒定的时间。转发列表的元素分散在存储器中，并且通过经由链接将列表的每个元素与列表的下一个元素相关联来维持排序。因此，它可以有效地利用内存。它是从 C++ 11 版本引入的。

## 实现转发列表

```cpp
// CPP Program to demonstrate forward list
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Declaring forward list
    forward_list<int> flist1;

    // Assigning values using assign()
    flist1.assign({ 10, 12, 13, 15 });

    // Displaying forward list
    cout << "The elements of forward list are : ";
    for (auto a : flist1)
        cout << a << " ";
    return 0;
}
```

**输出：**

```cpp
The elements of forward list are : 10 12 13 15
```

[`List`](https://www.geeksforgeeks.org/list-cpp-stl/) 也是一个序列容器，允许对其数据进行双向顺序访问。它包含相同类型的数据。在 STL 中，已经使用[双链表](https://www.geeksforgeeks.org/doubly-linked-list/)实现，插入和删除需要恒定的时间。它允许非连续的内存分配。列表中的每个元素都与其前后元素的链接相关联。由于其恒定的插入和删除时间以及双向顺序访问，在[排序算法](https://www.geeksforgeeks.org/sorting-algorithms/)中被广泛使用。

## 实现列表

```cpp
// CPP Program to demonstrate list
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Declaring a list
    list<int> list1;

    // Assigning values using assign()
    list1.assign({ 1, 2, 10, 15 });

    // Displaying list
    cout << "The elements of list are : ";
    for (auto a : list1)
        cout << a << " ";
    return 0;
}
```

**输出：**

```cpp
The elements of list are : 1 2 10 15
```

### 转发列表和列表的区别

<figure class="table">

| 转发列表 | 列表 |
| --- | --- |
| 使用单链表 | 实现双链表 |
| 消耗相对较少的内存。 | 消耗相对更多的内存。 |
| 由于每个节点中的指针较少，插入和删除元素时的开销较小，因此性能更好。 | 由于每个节点有更多的指针，插入和删除元素的成本更高，因此性能较差。 |
| 前向顺序访问 | 前向和反向顺序访问 |
| 比转发列表更高效。 | 效率不如转发列表。 |
| 通常，当需要双向顺序访问时使用，例如在[哈希](https://www.geeksforgeeks.org/c-program-hashing-chaining/)和表示[图](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)的[邻接表](https://www.geeksforgeeks.org/graph-and-its-representations/)中实现链接。 | 通常，当需要单向顺序访问时使用，例如实现[二叉树](https://www.geeksforgeeks.org/binary-tree-data-structure/)、[哈希表](https://www.geeksforgeeks.org/hashing-data-structure/)、[栈](https://www.geeksforgeeks.org/stack-data-structure/)等。 |

</figure>
# c++ 中转发列表和列表的区别

> 原文:[https://www . geeksforgeeks . org/转发列表和 c 中列表的区别/](https://www.geeksforgeeks.org/difference-between-forward-list-and-list-in-c/)

[转发列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)是一个允许单向顺序访问其数据的序列容器。它包含相同类型的数据。在 [STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中，已经使用[单链表](https://www.geeksforgeeks.org/data-structures/linked-list/)实现，插入和删除需要恒定的时间。转发列表的元素分散在存储器中，并且通过经由链接将列表的每个元素与列表的下一个元素相关联来维持排序。因此，它可以有效地利用内存。它是从 C++ 11 版本引入的。

**实现转发列表:**

## c++

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

**输出:**

```cpp
The elements of forward list are : 10 12 13 15
```

[List](https://www.geeksforgeeks.org/list-cpp-stl/) 也是一个序列容器，允许对其数据进行双向顺序访问。它包含相同类型的数据。在 STL 中，已经使用[双链表](https://www.geeksforgeeks.org/doubly-linked-list/)实现，插入和删除需要恒定的时间。它允许非连续的内存分配。列表中的每个元素都与其前后元素的链接相关联。由于其恒定的插入和删除时间以及双向顺序访问，在[排序算法](https://www.geeksforgeeks.org/sorting-algorithms/)中被广泛使用。

**实现列表:**

## c++

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

**输出:**

```cpp
The elements of list are : 1 2 10 15
```

### 转发列表和列表的区别

<figure class="table">

| 

转发列表

 | 

列表

 |
| --- | --- |
| Use single linked list | Implement double linked list |
| Consume relatively little memory. | Consume relatively more memory. |
| Because there are fewer pointers in each node, there is less overhead when inserting and removing elements, so the performance is better. | Because each node has more pointers, the cost of inserting and removing elements is higher, so the performance is poor. |
| Forward sequential access | Forward and reverse sequential access |
| More efficient than forward list. | Efficiency is not as good as forwarding list. |
| Generally, it is used when two-way sequential access is needed, such as realizing links in [hash](https://www.geeksforgeeks.org/c-program-hashing-chaining/) and [adjacency table](https://www.geeksforgeeks.org/graph-and-its-representations/) representing [figure](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/) . | Generally, it is used when one-way sequential access is needed, such as implementing [binary tree](https://www.geeksforgeeks.org/binary-tree-data-structure/) , [hash table](https://www.geeksforgeeks.org/hashing-data-structure/) , [stack](https://www.geeksforgeeks.org/stack-data-structure/) and so on. |

</figure>
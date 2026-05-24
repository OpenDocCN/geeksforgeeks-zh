# `std::is_sorted_until` 在 C++ 中

> 原文：[https://www.geeksforgeeks.org/stdis_sorted_until-in-cpp/](https://www.geeksforgeeks.org/stdis_sorted_until-in-cpp/)

`std::is_sorted_until` 用于找出范围 `[first, last]` 中第一个未排序的元素。它返回一个迭代器到范围中第一个未排序的元素，所以 `first` 和返回的迭代器之间的所有元素都被排序。
也可以用来统计范围内排序元素的总数。它是在 `<algorithm>` 头文件中定义的。在这种情况下，整个范围被排序，它将返回一个指向 `last` 的迭代器。
有两种使用方式，如下图：

## 使用 “<” 比较元素

**语法：**

```cpp
template< class ForwardIterator >
ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last);
```

`first`: 指向列表中第一个元素的前向迭代器。
`last`: 指向列表中最后一个元素的前向迭代器。

**返回值：** 它返回一个指向列表中第一个未排序元素的迭代器。
如果列表中只有一个元素或所有元素都已排序，则返回 `last`。

### 示例 1

```cpp
// C++ program to demonstrate the use of std::is_sorted_until
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 1, 2, 3, 4, 7, 10, 8, 9 }, i;

    int* ip;

    // Using std::is_sorted_until
    ip = std::is_sorted_until(v, v + 8);

    cout << "There are " << (ip - v) << " sorted elements in "
         << "the list and the first unsorted element is " << *ip;

    return 0;
}
```

**输出：**

```cpp
There are 6 sorted elements in the list and the first unsorted element is 8
```

## 通过使用预定义函数进行比较

**语法：**

```cpp
template< class ForwardIterator, class Compare >
ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last,
                                 Compare comp);
```

这里，`first` 和 `last` 与之前的情况相同。

`comp`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。
返回的值表示传递的第一个参数是否被认为在特定严格弱序中排在第二个参数之前。
该函数不应修改其任何参数。
这可以是函数指针或函数对象。

**返回值：** 它返回一个指向列表中第一个未排序元素的迭代器。
如果列表中只有一个元素或所有元素都已排序，则返回 `last`。

### 示例 2

```cpp
// C++ program to demonstrate the use of std::is_sorted_until with a custom comparator
#include <algorithm>
#include <iostream>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b) { return (a < b); }
int main()
{
    int v[] = { 1, 3, 20, 10, 45, 33, 56, 23, 47 }, i;
    int* ip;

    // Using std::is_sorted_until
    ip = std::is_sorted_until(v, v + 9, comp);

    cout << "There are " << (ip - v)
         << " sorted elements in "
         << "the list and the first unsorted element is "
         << *ip;

    return 0;
}
```

**输出：**

```cpp
There are 3 sorted elements in the list and the first unsorted element is 10
```

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# std::iter_swap 在 C++ 中

> 原文: [https://www.geeksforgeeks.org/stditer_swap-in-cpp/](https://www.geeksforgeeks.org/stditer_swap-in-cpp/)

[`std::swap`](https://www.geeksforgeeks.org/quickly-swap-two-arrays-size-c/) 用于两个容器之间的元素交换。做同样事情的另一种方法是通过 `std::iter_swap` 来实现的，顾名思义，它用于在迭代器的帮助下交换元素。

它只是交换迭代器指向的元素的值。如果我们看看它的内部工作情况，就会发现这个函数本身使用的是 [`std::swap()`](https://www.geeksforgeeks.org/quickly-swap-two-arrays-size-c/)。

## 语法

```cpp
void iter_swap (ForwardIterator1 a, ForwardIterator2 b);
```

这里，`a` 和 `b` 是前向迭代器。

返回值：它具有 `void` 返回类型，因此不返回任何值。

## 示例

```cpp
// C++ program to demonstrate the use of std::iter_swap
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    // Declaring first vector
    vector<int> v1;
    int i;

    for (i = 0; i < 10; ++ i) {
        v1.push_back(i);
    }
    // v1 contains 0 1 2 3 4 5 6 7 8 9

    vector<int>::iterator i1, i2;

    i1 = v1.begin();
    i2 = v1.end() - 1;

    // Performing swap between first and last element
    // of vector
    std::iter_swap(i1, i2);

    // Displaying v1 after swapping
    for (i = 0; i < 10; ++ i) {
        cout << v1[i] << " ";
    }

    return 0;
}
```

输出：

```cpp
9 1 2 3 4 5 6 7 8 0
```

这里，在这个程序中，我们在两个迭代器的帮助下交换了 `v1` 中的元素，其中一个指向 `v1` 的开头，另一个指向 `v1` 的结尾。

## std::iter_swap vs. std::swap

知道 `iter_swap` 是用来交换值的，就像 `std::swap()` 一样，现在出现的问题是，如果我们已经有了一个叫做 `swap()` 的东西，为什么还要学习 `iter_swap`。支持 `iter_swap` 的一些理由是:

*   **基于节点序列的优化：** 大多数 STL 算法在迭代器范围内运行。因此，在这些范围内交换元素时，使用 `iter_swap` 来交换两个迭代器指向的元素是有意义的。这允许对基于节点的序列（如 [`std::list`](https://www.geeksforgeeks.org/list-cpp-stl/)）进行优化，其中节点只是重新链接，而不是实际交换数据。
*   **在 STL 定义中使用：** 一些 STL 算法，如 [`std::reverse`](https://www.geeksforgeeks.org/stdreverse-in-c/)，在其定义中使用了 `std::iter_swap`。因此，为了理解这些定义，人们应该对它们有所了解。

```cpp
    // Definition of std::reverse()
    template void reverse(BidirectionalIterator first, 
                           BidirectionalIterator last)
    {
        while ((first != last) && (first != --last)) 
        {
            std::iter_swap(first, last);
            ++ first;
        }
    }
```

*   **提供抽象：** `iter_swap` 有效地封装了可交换接口的一部分，否则你每次都需要实现它。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
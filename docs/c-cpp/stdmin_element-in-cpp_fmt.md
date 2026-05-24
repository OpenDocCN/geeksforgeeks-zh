# 标准::C++ 中的 min_element

> 原文: [https://www.geeksforgeeks.org/stdmin_element-in-cpp/](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

为了计算给定列表中所有元素中的最小元素，我们有 [`std::min`](https://www.geeksforgeeks.org/stdmin-in-cpp/)，但是如果我们想要找到的不是整个列表中的最小元素，而是列表的**子部分**中的最小元素，该怎么办。为了达到这个目的，我们在 C++ 中有 `std::min_element`。

`std::min_element` 在头文件 `<algorithm>` 中定义，它返回一个迭代器，指向范围 `[first, last]` 中值最小的元素。

不同于可以三种方式使用的 `std::min`，`std::min_element` 可以两种方式使用。可以使用运算符 `<`（第一个版本）或预定义函数（第二个版本）进行比较。如果一个以上的元素满足最小的条件，迭代器返回指向第一个这样的元素。

两个版本定义如下：

## 使用“<”比较元素

语法:

```cpp
template<class ForwardIterator>
ForwardIterator min_element (ForwardIterator first, ForwardIterator last);
```

`first`: Forward iterator 指向范围的开始。
`last`: Forward iterator 指向范围的结束。

**返回值:** 它返回一个指向范围内最小元素的指针，如果存在多个这样的元素，则指向第一个。如果范围为空，则指向 `last`。

```cpp
// C++ program to demonstrate the use of std::min_element
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 9, 4, 7, 2, 5, 10, 11, 12, 1, 3, 6 };

    // Finding the minimum value between the third and the
    // fifth element
    int* i1;
    i1 = std::min_element(v + 2, v + 5);

    cout << *i1 << "\n";
    return 0;
}
```

**输出:**

```cpp
2
```

## For comparison based on a pre-defined function

语法:

```cpp
template<class ForwardIterator, class Compare>
ForwardIterator min_element (ForwardIterator first, ForwardIterator last,
                             Compare comp);
```

这里，`first` 和 `last` 与之前的情况相同。
`comp`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。返回值指示作为第一个参数传递的元素是否被认为小于第二个。该函数不得修改其任何参数。这可以是函数指针或函数对象。

**返回值:** 它返回一个指向范围内最小元素的指针，如果存在多个这样的元素，则指向第一个。如果范围为空，则指向 `last`。

```cpp
// C++ program to demonstrate the use of std::min_element
#include <iostream>
#include <algorithm>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b)
{
    return (a < b);
}

int main()
{
    int v[] = { 9, 4, 7, 2, 5, 10, 11, 12, 1, 3, 6 };

    // Finding the minimum value between the third and the
    // ninth element
    int* i1;
    i1 = std::min_element(v + 2, v + 9, comp);

    cout << *i1 << "\n";
    return 0;
}
```

输出:

```cpp
1
```

**相关文章:**

*   [`std::max_element`](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)
    *   [`std::max`](https://www.geeksforgeeks.org/stdmax-in-cpp/)
    *   [`std::min`](https://www.geeksforgeeks.org/stdmin-in-cpp/)
    *   [`std::equal`](https://www.geeksforgeeks.org/stdequal-in-cpp/)

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [`contribute.geeksforgeeks.org`](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
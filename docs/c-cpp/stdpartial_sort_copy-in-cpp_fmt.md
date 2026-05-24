# std::partial_sort_copy 在 C++ 中

> 原文: [https://www.geeksforgeeks.org/stdpartial_sort_copy-in-cpp/](https://www.geeksforgeeks.org/stdpartial_sort_copy-in-cpp/)

[`std::partial_sort`](https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/) 用于对整个容器内的范围进行排序。因此，如果我们想保持原始容器的完整，而只是将容器的排序子部分复制到另一个容器中，那么为此，我们可以使用 `std::partial_sort_copy`。

就像 `std::partial_sort` 一样，`partial_sort_copy()` 可以通过两种方式使用，如下所示:

## 1. 使用 < 比较元素

语法:

```cpp
template
RandomAccessIterator partial_sort_copy (InputIterator first, InputIterator last,
                                        RandomAccessIterator result_first,
                                        RandomAccessIterator result_last);
```

- `first`: 指向容器中第一个元素的输入迭代器。
- `last`: 指向容器中最后一个元素的输入迭代器。
- `result_first`: 指向目标容器中初始位置的随机访问迭代器。
- `result_last`: 指向目标容器中最终位置的随机访问迭代器。

返回值: 返回一个迭代器，指向结果序列中最后一个写入元素之后的元素。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort_copy
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 1, 3, 10, 3, 3, 7, 7, 8 }, v1(3);

    vector<int>::iterator ip;

    // Using std::partial_sort_copy
    std::partial_sort_copy(v.begin(), v.end(), v1.begin(), v1.end());

    // Displaying the vector after applying
    // std::partial_sort_copy
    for (ip = v1.begin(); ip != v1.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出:

```cpp
1 1 3
```

在这里，因为我们声明 `v1` 的大小为 3，所以其中只存储了三个元素。

## 2. 使用预定义函数进行比较

语法:

```cpp
template
RandomAccessIterator partial_sort_copy (InputIterator first, InputIterator last,
                                         RandomAccessIterator result_first,
                                         RandomAccessIterator result_last,
                                         Compare comp);
```

这里，`first`、`last`、`result_first` 和 `result_last` 与前一种情况相同。

- `comp`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。返回值表示传递的第一个参数在特定严格弱序中是否被认为位于第二个参数之前。该函数不得修改其任何参数。这可以是函数指针或函数对象。

返回值: 返回一个迭代器，指向结果序列中最后一个写入元素之后的元素。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort_copy
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b)
{
    return (a < b);
}

int main()
{
    vector<int> v = { 1, 1, 3, 10, 3, 3, 7, 7, 8 }, v1(7);

    vector<int>::iterator ip;

    // Using std::partial_sort_copy
    std::partial_sort_copy(v.begin(), v.end(), v1.begin(),
                           v1.end(), comp);

    // Displaying the vector after applying
    // std::partial_sort_copy
    for (ip = v1.begin(); ip != v1.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出:

```cpp
1 1 3 3 3 7 7
```

## 用在哪里？

- **用于复制排序后的范围**：因此，当我们希望原始容器在排序后保持不变，并且希望将 `partial_sort` 的结果存储在另一个容器中时，我们可以使用这个函数。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort_copy
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 100, 45, 78, 23, 220 }, v1(5);

    vector<int>::iterator ip;

    // Using std::partial_sort_copy
    std::partial_sort_copy(v.begin(), v.end(), v1.begin(),
                           v1.end());

    // Displaying the vectors after applying
    // std::partial_sort_copy
    cout << "v = ";

    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    cout << "\nv1 = ";
    for (ip = v1.begin(); ip != v1.end(); ++ ip) {
        cout << *ip << " ";
    }
    return 0;
}
```

输出:

```cpp
v = 100 45 78 23 220
v1 = 23 45 78 100 220
```

所以，这里 `v` 保持不变，它的排序形式存储在 `v1` 中。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# std::partial_sort in C++

> 原文: [https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/](https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/)

[`std::sort`](https://www.geeksforgeeks.org/sort-c-stl/) 用于对容器内存在的元素进行排序。其中的一个变体是 `std::partial_sort`，它不是用于对整个范围进行排序，而是仅用于对其中的一个子部分进行排序。

它重新排列范围 `[first, last]` 中的元素，`middle` 之前的元素按升序排序，而 `middle` 之后的元素没有任何特定的顺序。

它有两种使用方式，如下所示：

## 使用比较元素

语法：

```cpp
template
void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                   RandomAccessIterator last);
```

`first`: 指向容器中第一个元素的随机访问迭代器。
`last`: 指向容器中最后一个元素的随机访问迭代器。
`middle`: 指向范围 `[first, last)` 中某个元素的随机访问迭代器，该元素用作待排序元素的上边界。

返回值：它具有 `void` 返回类型，因此不返回任何值。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 3, 1, 10, 3, 3, 7, 7, 8 }, i;

    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 3, v.end());

    // Displaying the vector after applying
    // std::partial_sort
    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出：

```cpp
1 1 3 10 3 3 7 7 8
```

这里只有前三个元素从 `first` 到 `middle` 排序，这里 `first` 是 `v.begin()`，`middle` 是 `v.begin() + 3`，其余都没有任何顺序。

## 通过使用预定义函数进行比较

语法：

```cpp
template
void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                   RandomAccessIterator last, Compare comp);
```

这里，`first`、`middle` 和 `last` 与之前的情况相同。

`comp`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。返回的值表示作为第一个参数传递的元素是否被认为在它定义的特定严格弱序中排在第二个参数之前。
该函数不得修改其任何参数。
这可以是函数指针或函数对象。

返回值：它具有 `void` 返回类型，因此不返回任何值。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
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
    vector<int> v = { 1, 3, 1, 10, 3, 3, 7, 7, 8 }, i;

    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 3, v.end(), comp);

    // Displaying the vector after applying
    // std::partial_sort
    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出：

```cpp
1 1 3 10 3 3 7 7 8
```

## 哪里可以用？

1.  **查找最大元素**：因为使用 `std::partial_sort`，我们可以部分排序容器到我们想要的任何位置。所以，如果我们只**对第一个位置排序并使用一个函数对象**，我们就可以找到最大元素，而无需对整个容器进行排序。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v = { 10, 45, 60, 78, 23, 21, 30 };

    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 1, v.end(),
                      greater<int>());

    // Displaying the largest element after applying
    // std::partial_sort

    ip = v.begin();
    cout << "The largest element is = " << *ip;

    return 0;
}
```

输出：

```cpp
The largest element is = 78
```

2.  **查找最小元素**：类似于查找最大元素，我们也可以在前面的例子中找到容器中的最小元素。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v = { 10, 45, 60, 78, 23, 21, 3 };

    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 1, v.end());

    // Displaying the smallest element after applying
    // std::partial_sort

    ip = v.begin();
    cout << "The smallest element is = " << *ip;

    return 0;
}
```

输出：

```cpp
The smallest element is = 3
```

## 点记

*   **`std::sort()` vs `std::partial_sort()`**：你们中的一些人可能会想，为什么我们要使用 `std::partial_sort`，而我们可以使用 `std::sort()` 来处理有限的范围，但请记住，如果我们对部分范围使用 `std::sort`，那么只有该范围内的元素会被考虑排序，而该范围之外的所有其他元素都不会被考虑，而使用 `std::partial_sort()`，所有元素都会被考虑排序。

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v = { 10, 45, 60, 78, 23, 21, 3 }, v1;

    int i;
    v1 = v;
    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 2, v.end());

    // Using std::sort()
    std::sort(v1.begin(), v1.begin() + 2);

    cout << "v = ";
    for (i = 0; i < 2; ++ i) {
        cout << v[i] << " ";
    }

    cout << "\nv1 = ";
    for (i = 0; i < 2; ++ i) {
        cout << v1[i] << " ";
    }

    return 0;
}
```

输出：

```cpp
v = 3 10
v1 = 10 45
```

**说明**：这里，我们对 `v` 应用了 `std::partial_sort`，对 `v1` 应用了 `std::sort`，一直到第二个位置。现在，您可以理解 `std::sort` 只对给定范围内的元素进行排序，而 `partial_sort` 考虑了整个容器，但只对前两个位置进行排序。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
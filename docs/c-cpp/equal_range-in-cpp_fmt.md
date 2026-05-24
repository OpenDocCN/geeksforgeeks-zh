# std::equal_range in C++

> 原文: [https://www.geeksforgeeks.org/equal_range-in-cpp/](https://www.geeksforgeeks.org/equal_range-in-cpp/)

`std::equal_range` 用于查找给定范围 `[first, last]` 内的子范围，其所有元素都等于给定值。它返回这样一个子范围的初始和最终界限。

此函数要求根据某个条件对范围进行排序或分区，以便条件评估为 `true` 的所有元素都位于给定值的左侧，其余元素都位于其右侧。

它有两种使用方式，如下所示：

## 使用 `<` 比较元素

语法：

```cpp
template <class ForwardIterator, class T>
pair<ForwardIterator, ForwardIterator>
    equal_range (ForwardIterator first, ForwardIterator last, const T& val);
```

- `first`: 指向范围中第一个元素的前向迭代器。
- `last`: 指向范围中最后一个元素的后一个位置的前向迭代器。
- `val`: 要在范围中搜索的子范围的值。

返回值：它返回一个 `pair` 对象，其成员 `pair::first` 是一个指向等效值子范围下界的迭代器，`pair::second` 是其上界。
如果没有元素等效于 `val`，则 `first` 和 `second` 都指向大于 `val` 的最近元素，或者如果 `val` 大于任何其他值，则它们都指向 `last`。

```cpp
// C++ program to demonstrate the use of std::equal_range
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 10, 10, 30, 30, 30, 100, 10,
                      300, 300, 70, 70, 80 };

    // Declaring an iterator to store the
    // return value of std::equal_range
    std::pair<std::vector<int>::iterator,
              std::vector<int>::iterator> ip;

    // Sorting the vector v
    sort(v.begin(), v.end());
    // v becomes 10 10 10 30 30 30 70 70 80 100 300 300

    // Using std::equal_range and comparing the elements
    // with 30
    ip = std::equal_range(v.begin(), v.begin() + 12, 30);

    // Displaying the subrange bounds
    cout << "30 is present in the sorted vector from index "
         << (ip.first - v.begin()) << " till "
         << (ip.second - v.begin());

    return 0;
}
```

输出：

```cpp
30 is present in the sorted vector from index 3 till 6
```

**说明：** 在对向量 `v` 进行排序之后，我们检查了存在 `30` 的界限，即从索引 `3` 到索引 `6`。

## 通过预定义函数比较

语法：

```cpp
template <class ForwardIterator, class T, class Compare>
pair<ForwardIterator, ForwardIterator>
    equal_range (ForwardIterator first, ForwardIterator last,
                 const T& val, Compare comp);
```

这里，`first`、`last` 和 `val` 与之前的情况相同。

- `comp`: 二元函数，接受两个由 `ForwardIterator` 指向的类型（以及类型 `T`）的参数，并返回可转换为 `bool` 的值。返回的值表示第一个参数是否被认为排在第二个参数之前。
    该函数不得修改其任何参数。
    这可以是函数指针或函数对象。

返回值：它返回一个 `pair` 对象，其成员 `pair::first` 是一个指向等效值子范围下界的迭代器，`pair::second` 是其上界。
如果没有元素等效于 `val`，则 `first` 和 `second` 都指向大于 `val` 的最近元素，或者如果 `val` 大于任何其他值，则它们都指向 `last`。

```cpp
// C++ program to demonstrate the use of std::equal_range
#include <iostream>
#include <algorithm>
#include <string>
#include <vector>
#include <functional>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b)
{
    return (a > b);
}
int main()
{
    vector<int> v = { 10, 10, 30, 30, 30, 100, 10,
                      300, 300, 70, 70, 80 };

    // Declaring an iterator to store the
    // return value of std::equal_range
    std::pair<std::vector<int>::iterator,
              std::vector<int>::iterator> ip;

    // Sorting the vector v in descending order
    sort(v.begin(), v.end(), greater<int>());
    // v becomes 300 300 100 80 70 70 30 30 30 10 10 10

    // Using std::equal_range and comparing the elements
    // with 10
    ip = std::equal_range(v.begin(), v.begin() + 12, 10, comp);

    // Displaying the subrange bounds
    cout << "10 is present in the sorted vector from index "
         << (ip.first - v.begin()) << " till "
         << (ip.second - v.begin());

    return 0;
}
```

输出：

```cpp
10 is present in the sorted vector from index 9 till 12
```

## 哪里可以用？

1.  **同时使用 `std::lower_bound` 和 `std::upper_bound`**：如果我们想同时使用 `std::lower_bound` 和 `std::upper_bound`，可以使用此函数，因为它的第一个指针将与 `std::lower_bound` 相同，第二个指针将与 `std::upper_bound` 相同。所以，如果我们有 `std::equal_range`，就没有必要单独使用它们。

```cpp
// C++ program to demonstrate the use of std::equal_range
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 2, 3, 4, 5, 5, 6, 7 };

    // Declaring an iterator to store the
    // return value of std::equal_range
    std::pair<std::vector<int>::iterator,
              std::vector<int>::iterator> ip;

    // Using std::equal_range and comparing the elements
    // with 5
    ip = std::equal_range(v.begin(), v.end(), 5);

    // Displaying the subrange bounds
    cout << "std::lower_bound should be equal to "
         << (ip.first - v.begin()) << " and std::upper_bound "
         << "should be equal to " << (ip.second - v.begin());

    vector<int>::iterator i1, i2;

    // Using std::lower_bound
    i1 = std::lower_bound(v.begin(), v.end(), 5);
    cout << "\nstd::lower_bound is = " << (i1 - v.begin());

    // Using std::upper_bound
    i2 = std::upper_bound(v.begin(), v.end(), 5);
    cout << "\nstd::upper_bound is = " << (i2 - v.begin());

    return 0;
}
```

输出：

```cpp
std::lower_bound should be equal to 4 and
std::upper_bound should be equal to 6
std::lower_bound is = 4
std::upper_bound is = 6
```

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
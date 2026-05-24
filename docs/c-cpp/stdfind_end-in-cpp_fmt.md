# std::find_end in C++

> 原文: [https://www.geeksforgeeks.org/stdfind_end-in-cpp/](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)

`std::find_end` 用于查找容器内子序列的最后一次出现。它在范围 `[first1, last1]` 中搜索由 `[first2, last2]` 定义的序列的最后一次出现，并返回一个迭代器到它的第一个元素，如果没有发现出现，则返回 `last1`。

它类似于 [`std::search`](https://www.geeksforgeeks.org/stdsearch-in-c/)，在 `std::search` 中，我们在另一个容器中寻找一个子序列的**第一个**出现，而在 `std::find_end` 中，我们寻找这个子序列的**最后一个**出现，如果找到了这个子序列，就返回一个迭代器到第一个元素。

它有两种使用方式，如下所示：

## 1. 使用 `==` 比较元素

语法：

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,
                           ForwardIterator2 first2, ForwardIterator2 last2);
```

- `first1`: 指向第一个范围中首元素的前向迭代器。
- `last1`: 指向第一个范围中末元素的后一个位置的前向迭代器。
- `first2`: 指向第二个范围中首元素的前向迭代器。
- `last2`: 指向第二个范围中末元素的后一个位置的前向迭代器。

**返回值**：它返回一个迭代器，指向 `[first1, last1)` 中 `[first2, last2)` 最后一次出现的首元素。如果未找到序列或 `[first2, last2)` 为空，则函数返回 `last1`。

```cpp
// C++ program to demonstrate the use of std::find_end
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

int main()
{
    // Defining first container
    vector<int> v = {1, 3, 10, 3, 10, 1, 3, 3, 10, 7, 8, 1, 3, 10};

    // Defining second container
    vector<int> v1 = {1, 3, 10};

    vector<int>::iterator ip;

    // Using std::find_end
    ip = std::find_end(v.begin(), v.end(), v1.begin(), v1.end());

    // Displaying the index where the last common occurrence begins
    cout << (ip - v.begin()) << "\n";
    return 0;
}
```

输出：

```cpp
11
```

## 2. 通过预定义函数进行比较

语法：

```cpp
template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,
                           ForwardIterator2 first2, ForwardIterator2 last2,
                           BinaryPredicate pred);
```

这里，`first1`、`last1`、`first2` 和 `last2` 与前一种情况相同。

- `pred`: 二元函数，接受两个参数（两个序列中各一个，顺序相同），并返回可转换为 `bool` 的值。返回值指示在此函数的上下文中元素是否被视为匹配。该函数不得修改其任何参数。这可以是函数指针或函数对象。

**返回值**：它返回一个迭代器，指向 `[first1, last1)` 中 `[first2, last2)` 最后一次出现的首元素。如果未找到序列或 `[first2, last2)` 为空，则函数返回 `last1`。

```cpp
// C++ program to demonstrate the use of std::find_end
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

// Defining the BinaryFunction
bool Pred(int a, int b)
{
    return (a == b);
}

int main()
{
    // Defining first container
    vector<int> v = {1, 5, 7, 11, 13, 15, 30, 30, 7}, i;

    // Defining second container
    vector<int> v1 = {13, 15};

    vector<int>::iterator ip;

    // Using std::find_end
    ip = std::find_end(v.begin(), v.end(), v1.begin(), v1.end(), Pred);

    // Displaying the index where the last common occurrence begins
    cout << (ip - v.begin()) << "\n";

    return 0;
}
```

输出：

```cpp
4
```

## 哪里可以用？

1.  **从末尾搜索**：它是 `std::search` 的反向变体，即 `std::search` 从列表开头搜索子序列，以便它可以返回该子序列的第一次出现。

    另一方面，`std::find_end` 可以用于如果我们想从列表的末尾搜索一个子序列，这个子序列将自动成为容器内任何子序列的最后一个出现。
    (如果你在想为什么叫 `std::find_end` 而不是 `std::search_end`，那就不是你一个人了！！！)

    所以，如果必须从头开始搜索的话，这是 `std::search` 的一个**可能的替代**。

```cpp
// C++ program to demonstrate the use of std::find_end
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v1 = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    vector<int> v2 = {3, 4, 5};

    // Using std::find_end to find the last occurrence
    auto it = std::find_end(v1.begin(), v1.end(), v2.begin(), v2.end());

    if (it != v1.end()) {
        cout << "Last occurrence found at index: " << (it - v1.begin()) << endl;
    } else {
        cout << "Sequence not found." << endl;
    }

    return 0;
}
```

# C++ 标准库算法：`std::search` 与 `std::find_end` 详解

## 1. 基本用法：查找子序列

`std::search` 用于在序列中查找子序列**第一次**出现的位置，而 `std::find_end` 用于查找子序列**最后一次**出现的位置。

### 1.1 示例代码

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    int i, j;

    // Declaring the sequence to be searched into
    vector<int> v1 = { 1, 2, 3, 4, 5, 6, 7, 3, 4, 5 };

    // Declaring the subsequence to be searched for
    vector<int> v2 = {3, 4};

    // Declaring an iterator for storing the returning pointer
    vector<int>::iterator i1;

    // Using std::search to find the first occurrence of v2
    i1 = std::search(v1.begin(), v1.end(), v2.begin(), v2.end());

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "vector2 is present firstly at index " << (i1 - v1.begin());
    } else {
        cout << "vector2 is not present in vector1";
    }

    // Using std::find_end to find the last occurrence of v2
    i1 = std::find_end(v1.begin(), v1.end(), v2.begin(), v2.end());

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "\nvector2 is present lastly at index " << (i1 - v1.begin());
    } else {
        cout << "vector2 is not present in vector1";
    }
    return 0;
}
```

### 1.2 输出

```cpp
vector2 is present firstly at index 2
vector2 is present lastly at index 7
```

## 2. 高级用法：查找最后一个满足条件的元素

由于 `std::find_end` 从末尾开始搜索，我们可以利用这一特性并自定义比较函数，来解决需要**查找最后一个满足条件元素**（如最后一个奇数、最后一个偶数等）的问题。

### 2.1 示例代码

```cpp
// C++ program to find the last occurrence of an odd and even number
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

// Defining the Predicate Function to find the last occurrence of an odd number
bool pred( int a, int b)
{
    if (a % b != 0) {
        return 1;
    } else {
        return 0;
    }
}

// Defining the Predicate Function to find the last occurrence of an even number
bool pred1( int a, int b)
{
    if (a % b == 0) {
        return 1;
    } else {
        return 0;
    }
}

int main()
{
    // Defining a vector
    vector<int>v1 = {1, 3, 4, 5, 6, 7, 8, 10};

    // Declaring a sub-sequence
    vector<int>v2 = {2};

    // Using std::find_end to find the last occurrence of an odd number
    vector<int>::iterator ip;
    ip = std::find_end(v1.begin(), v1.end(), v2.begin(), v2.end(), pred);

    // Displaying the index where the last odd number occurred
    cout << "Last odd no. occurs at " << (ip - v1.begin());

    // Using std::find_end to find the last occurrence of an even number
    ip = std::find_end(v1.begin(), v1.end(), v2.begin(), v2.end(), pred1);

    // Displaying the index where the last even number occurred
    cout << "\nLast even no. occurs at " << (ip - v1.begin());

    return 0;
}
```

### 2.2 输出

```cpp
Last odd no. occurs at 5
Last even no. occurs at 7
```

### 2.3 代码说明

这里，我们对 `Binary Function` 进行了操作，使得它搜索第一个容器中的元素是否是第二个容器中元素的倍数。在第二个容器中我们存储了 `2`，因此借助于此，我们能够找到奇数或偶数的最后一次出现。

## 相关文章

*   [`std::search`](https://www.geeksforgeeks.org/stdsearch-in-c/)
*   [`std::find`](https://www.geeksforgeeks.org/stdfind-in-c/)
*   [`std::find_if`, `std::find_if_not`](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
*   [`std::nth_element`](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
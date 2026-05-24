# std::search_n 用 C++ 举例

> 原文: [https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/](https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/)

先决条件: [`std::search`](https://www.geeksforgeeks.org/stdsearch-in-c/)

`std::search_n` 是在头文件 `<algorithm>` 中定义的 STL 算法，用于搜索给定元素是否与容器元素连续满足给定次数的谓词（如果未定义此类谓词，则等于）。

它在范围 `[first, last]` 中搜索 `count` 个元素序列，每个 `count` 元素都等于给定值（版本 1）或满足谓词（版本 2）。

如果没有找到这样的序列，这个函数返回一个迭代器到第一个这样的元素，或者一个迭代器到容器的最后一个元素。

`std::search_n` 的两个版本定义如下：

## 1. 使用 == 比较元素

语法:

```cpp
ForwardIterator search_n (ForwardIterator first, ForwardIterator last,
                          Size count, const T& val);
```

- `first`: 指向待搜索容器起始位置的前向迭代器。
- `last`: 指向待搜索容器结束位置的前向迭代器。
- `count`: 要匹配的连续元素的最小数量。`Size` 应是（可转换为）整型。
- `val`: 要比较的单个值。
- 返回值: 返回指向序列第一个元素的迭代器。如果未找到这样的序列，则函数返回 `last`。

```cpp
// C++ program to demonstrate the use of std::search_n
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    int i, j;

    // Declaring the sequence to be searched into
    vector<int> v1 = { 1, 2, 3, 4, 5, 3, 3, 6, 7 };

    // Declaring the value to be searched for
    int v2 = 3;

    // Declaring an iterator for storing the returning pointer
    vector<int>::iterator i1;

    // Using std::search_n and storing the result in iterator i1
    i1 = std::search_n(v1.begin(), v1.end(), 2, v2);

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "v2 is present consecutively 2 times at index "
             << (i1 - v1.begin());
    } else {
        cout << "v2 is not present consecutively 2 times in "
             << "vector v1";
    }

    return 0;
}
```

输出:

```cpp
v2 is present consecutively 2 times at index 5
```

## 2. 使用谓词比较元素

语法:

```cpp
ForwardIterator search_n ( ForwardIterator first, ForwardIterator last,
                           Size count, const T& val, BinaryPredicate pred );
```

所有参数与上一个模板相同，只是多了一个参数 `pred`。

- `pred`: 二元函数，接受两个参数（序列中的一个元素作为第一个参数，`val` 作为第二个参数），并返回可转换为 `bool` 的值。返回值表示在此函数上下文中该元素是否被视为匹配。该函数不得修改其任何参数。这可以是函数指针或函数对象。
- 返回值: 返回值与上一个版本相同，即指向序列第一个元素的迭代器，该元素满足与给定值相关的条件。如果未找到这样的序列，则函数返回 `last`。

```cpp
// C++ program to demonstrate the use of std::search_n
// with binary predicate
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// Defining the BinaryPredicate function
bool pred(int i, int j)
{
    if (i == j) {
        return 1;
    } else {
        return 0;
    }
}

int main()
{
    int i, j;

    // Declaring the sequence to be searched into
    vector<int> v1 = { 1, 2, 3, 4, 5, 3, 3, 6, 7 };

    // Declaring the value to be compared to v1 based
    // on a given predicate
    int v2 = 3;

    // Declaring an iterator for storing the returning pointer
    vector<int>::iterator i1;

    // Using std::search_n and storing the result in iterator i1
    i1 = std::search_n(v1.begin(), v1.end(), 2, v2, pred);

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "v2 is present consecutively 2 times at index "
             << (i1 - v1.begin());
    } else {
        cout << "v2 is not present consecutively 2 times "
             << "in vector v1";
    }

    return 0;
}
```

输出:

```cpp
v2 is present consecutively 2 times at index 5
```

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
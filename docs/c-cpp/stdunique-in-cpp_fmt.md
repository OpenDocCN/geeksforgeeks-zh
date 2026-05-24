# std::unique 在 C++ 中的使用

> 原文链接：[https://www.geeksforgeeks.org/stdunique-in-CPP/](https://www.geeksforgeeks.org/stdunique-in-CPP/)

`std::unique` 用于删除某个范围内连续出现的任何元素的重复项 `[first, last]`。它对连续出现相同元素的范围内的所有子组执行此任务。

*   它不会删除所有重复的元素，但它会通过用序列中的下一个元素替换这些元素来消除重复，该元素与被替换的当前元素不重复。所有被替换的元素都处于**未指定状态**。
*   这个函数的另一个有趣的特性是**它不改变容器的大小**。在删除元素后，它只是返回一个指向容器新端的迭代器，基于此我们必须调整容器的大小，或者删除垃圾元素。

**有两种使用方式，如下所示：**

## 1. 使用 `==` 比较元素

语法：

```cpp
template<class ForwardIterator>
ForwardIterator unique (ForwardIterator first, ForwardIterator last);
```

*   `first`: 指向容器中第一个元素的前向迭代器。
*   `last`: 指向容器中最后一个元素之后位置的前向迭代器。

返回值：它返回一个迭代器，指向最后一个未被移除的元素之后的位置。从 `first` 到这个迭代器之间的范围包含了序列中所有未被移除的非重复元素。

```cpp
// C++ program to demonstrate the use of std::unique
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 1, 3, 3, 3, 10, 1, 3, 3, 7, 7, 8 }, i;

    vector<int>::iterator ip;

    // Using std::unique
    ip = std::unique(v.begin(), v.begin() + 12);
    // Now v becomes {1 3 10 1 3 7 8 * * * * *}
    // * means undefined

    // Resizing the vector so as to remove the undefined terms
    v.resize(std::distance(v.begin(), ip));

    // Displaying the vector after applying std::unique
    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出：

```cpp
1 3 10 1 3 7 8
```

这里，在该向量中，具有连续重复元素的所有子组已经被简化为仅一个元素。请注意，稍后是否出现相同的元素并不重要，这个函数只处理连续出现的重复元素。

## 2. 使用预定义函数进行比较

语法：

```cpp
template <class ForwardIterator, class BinaryPredicate>
ForwardIterator unique (ForwardIterator first, ForwardIterator last,
                        BinaryPredicate Pred);
```

这里，`first` 和 `last` 与上一种情况相同。

*   `Pred`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。返回值指示两个参数是否被视为等效（如果为 `true`，则它们等效并移除其中一个）。该函数不应修改其任何参数。这可以是函数指针或函数对象。

返回值：它返回一个迭代器，指向最后一个未被移除的元素之后的位置。从 `first` 到这个迭代器之间的范围包含了序列中所有未被移除的非重复元素。

```cpp
// C++ program to demonstrate the use of std::unique
#include <iostream>
#include <algorithm>
#include <string>
using namespace std;

// Defining the BinaryFunction
bool Pred(char a, char b)
{
    // Checking if both the arguments are same and equal
    // to 'G' then only they are considered same
    // and duplicates are removed
    if (a == b && a == 'G') {
        return 1;
    } else {
        return 0;
    }
}
int main()
{
    // Declaring a string
    string s = "You arre vvvisiting GGGGFGGGG";

    // Using std::unique to remove the consecutive
    // G in the word
    auto ip = std::unique(s.begin(), s.end(), Pred);

    // Displaying the corrected string
    cout << string(s.begin(), ip);
    return 0;
}
```

输出：

```cpp
You arre vvvisiting GFG
```

在这里，我们对二进制函数进行了这样的操作：只有当两个 `G` 作为参数传递时，它们才会被认为是相同的，如果任何其他字符连续出现，那么它将不受影响，并且不会被移除（就像 `arre` 中的 `r`，`visiting` 中的 `v`）。

## 可以使用 `std::unique` 的地方？

### 1. 从容器中移除所有重复元素

许多人搜索 `std::unique` 时可能期望它能移除容器中所有的重复元素，现在你可能会有点失望地知道它只移除连续的重复元素。但是，尽管 `std::unique` 按其定义无法做到这一点，但应用一点逻辑，我们可以实现这个功能。我们需要做的就是在应用 `std::unique` 之前对数组进行排序，使得所有相等的元素变得连续，然后我们就可以用 `std::unique` 来移除所有连续的重复元素。

所以，`std::unique` 也可以用来**移除容器中所有重复的元素**。

```cpp
// C++ program to demonstrate the use of std::unique
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 2, 3, 3, 3, 10, 1, 2, 3, 7, 7, 8 };

    vector<int>::iterator ip;

    // Sorting the array
    std::sort(v.begin(), v.end());
    // Now v becomes 1 1 2 2 3 3 3 3 7 7 8 10

    // Using std::unique
    ip = std::unique(v.begin(), v.begin() + 12);
    // Now v becomes {1 2 3 7 8 10 * * * * * *}
    // * means undefined

    // Resizing the vector so as to remove the undefined terms
    v.resize(std::distance(v.begin(), ip));

    // Displaying the vector after applying std::unique
    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出：

```cpp
1 2 3 7 8 10
```

**解释：** 首先，我们对数组进行排序，使得所有相等的重复元素都变成连续的，现在对其应用 `std::unique`，从而消除重复，这样我们就从容器中移除了所有重复元素，无论是否连续。

### 2. 统计唯一元素的数量

如果我们想统计容器中唯一元素的总数，也可以使用它。

```cpp
// C++ program to demonstrate the use of std::unique
#include <iostream>
#include <iterator>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 1, 3, 3, 3, 10, 1, 3, 3, 7, 7, 8 };

    vector<int>::iterator ip;

    int count;
    sort(v.begin(), v.end());

    // Using std::unique and std::distance to count
    // unique elements in a container
    count = std::distance(v.begin(),
                          std::unique(v.begin(), v.begin() + 12));

    // Displaying the value of count
    cout << "Total no. of unique elements = " << count;

    return 0;
}
```

输出：

```cpp
Total no. of unique elements = 5
```

**解释：** 由于我们知道 `std::unique` 在移除重复元素后会返回一个迭代器，指向容器的新结尾应该是什么，所以仅仅是在 `std::distance` 的帮助下计算从开始到这个新结尾的元素总数，应该就能给出容器中唯一元素的总数。

---

本文由 **Mridul Singh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在 GeeksforGeeks 主页上，帮助其他 Geeks。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
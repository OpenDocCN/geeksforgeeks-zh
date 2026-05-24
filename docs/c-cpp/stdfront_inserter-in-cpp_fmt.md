# std::front_inserter in C++

> 原文: [https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/](https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/)

`std::front_inserter` 构造一个 front-insert 迭代器，在应用它的容器的前面插入新元素。它在 `<iterator>` 头文件中定义。

前置插入迭代器是一种特殊类型的输出迭代器，旨在允许通常覆盖元素（如复制）的算法在容器的开头自动插入新元素。它与 `std::back_inserter` 完全相反。

## 语法

```cpp
std::front_inserter (Container& x);
```

`x`: Container in which new elements will be inserted at the beginning.

Returns: A `front_insert_iterator` that inserts elements at the beginning of container `x`.

## 示例

```cpp
// C++ program to demonstrate std::front_inserter
#include <iostream>
#include <iterator>
#include <deque>
#include <algorithm>
using namespace std;
int main()
{
    // Declaring first container
    deque<int> v1 = { 1, 2, 3 };

    // Declaring second container for
    // copying values
    deque<int> v2 = { 4, 5, 6 };

    // Using std::front_inserter inside std::copy
    std::copy(v1.begin(), v1.end(), std::front_inserter(v2));
    // v2 now contains 3 2 1 4 5 6

    // Displaying v1 and v2
    cout << "v1 = ";
    int i;
    for (i = 0; i < 3; ++ i) {
        cout << v1[i] << " ";
    }

    cout << "\nv2 = ";
    for (i = 0; i < 6; ++ i) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
v1 = 1 2 3
v2 = 3 2 1 4 5 6
```

## 有什么帮助？

*   **反转容器：** 因为 `std::front_inserter` 在容器的开头插入新元素，我们可以借助 `copy()` 来执行 `reverse_copy()` 的任务，从而创建一个包含当前容器反转内容的新容器。

```cpp
// C++ program to demonstrate std::front_inserter
#include <iostream>
#include <iterator>
#include <deque>
#include <algorithm>
using namespace std;
int main()
{
    // Declaring first container
    deque<int> v1 = { 1, 2, 3 };

    // Declaring second container
    // for storing the reverse
    deque<int> v2;

    // Using std::front_inserter inside std::copy
    std::copy(v1.begin(), v1.end(), std::front_inserter(v2));
    // v2 now contains 3 2 1

    // Displaying v1 and v2
    cout << "v1 = ";
    int i;
    for (i = 0; i < 3; ++ i) {
        cout << v1[i] << " ";
    }

    cout << "\nv2 = ";
    for (i = 0; i < 3; ++ i) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
v1 = 1 2 3
v2 = 3 2 1
```

**解释：** 这里，我们开始将 `v1` 复制到 `v2`，但是从开头开始，所以每次新元素到来时，它都被插入到开头，最后插入的元素成为新容器中的第一个元素，这样我们就可以反转容器的内容。

## 要记住的要点

1.  `std::front_inserter` 的一个陷阱是它只能与使用 `push_front` 作为其方法之一的容器一起使用，就像 `list` 和 `deque` 的情况一样，它不能与 `vector` 一起使用。
2.  **`push_front()` vs `front_inserter()`：** 现在，你可能会认为 `push_front()` 和 `front_inserter` 是相似的，但它们不是。当你需要在算法中传递一个迭代器时，你应该使用 `front_inserter`，如上面的例子所示，而为了在容器的开头正常插入值，你可以使用 `push_front()`。
3.  代替使用 `std::front_inserter`，我们可以创建一个 `front_insert_iterator` 然后使用它，因为最终 `std::front_inserter` 只返回一个 `front_insert_iterator`。

```cpp
// C++ program to demonstrate front_insert_iterator
#include <iostream>
#include <iterator>
#include <deque>
#include <algorithm>
using namespace std;
int main()
{
    // Declaring first container
    deque<int> v1 = { 1, 2, 3 };

    // Declaring second container for
    // copying values
    deque<int> v2 = { 4, 5, 6 };

    // Declaring a front_insert_iterator
    std::front_insert_iterator<std::deque<int> > front_i1(v2);

    // Using the iterator in the copy()
    std::copy(v1.begin(), v1.end(), front_i1);
    // v2 now contains 3 2 1 4 5 6

    // Displaying v1 and v2
    cout << "v1 = ";
    int i;
    for (i = 0; i < 3; ++ i) {
        cout << v1[i] << " ";
    }

    cout << "\nv2 = ";
    for (i = 0; i < 6; ++ i) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
v1 = 1 2 3
v2 = 3 2 1 4 5 6
```

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
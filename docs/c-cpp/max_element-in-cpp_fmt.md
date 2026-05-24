# C++ 中的 `max_element`

> 原文: [https://www.geeksforgeeks.org/max_element-in-cpp/](https://www.geeksforgeeks.org/max_element-in-cpp/)

我们有 [`std::max`](https://www.geeksforgeeks.org/stdmax-in-cpp/) 来查找最多 2 个或更多的元素，但是如果我们想在数组、向量、列表或子节中查找最大的元素呢。为了达到这个目的，我们在 C++ 中有 `std::max_element`。
`std::max_element` 在头文件`<algorithm>`中定义，它返回一个迭代器，指向范围【`first`， `last`】中值最大的元素。

`std::max_element` 有两种使用方式。可以使用`运算符<` (第一版)或使用`预定义函数`(第二版)进行比较。如果一个以上的元素满足最大的条件，迭代器返回指向第一个这样的元素。

## 这两个版本的定义如下:

### 1. 使用 `<` 语法来比较元素

```cpp
template <class ForwardIterator>
ForwardIterator max_element (ForwardIterator first, ForwardIterator last);
```

`first`: 指向范围起始的 Forward iterator。
`last`: 指向范围结束的 Forward iterator。

**返回值**: 它返回一个指向范围内最大元素的指针，如果存在多个这样的元素，则指向第一个。
如果范围为空，则指向 `last`。

```cpp
// C++ program to demonstrate the use of std::max_element
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 'a', 'c', 'k', 'd', 'e', 'f', 'h' };

    // Finding the maximum value between the first and the
    // fourth element
    int* i1;
    i1 = std::max_element(v, v + 4);

    cout << char(*i1) << "\n";
    return 0;
}
```

输出:

```cpp
k
```

### 2. 基于预定义函数进行比较

语法:

```cpp
template <class ForwardIterator, class Compare>
ForwardIterator max_element (ForwardIterator first, ForwardIterator last,
                             Compare comp);
```

这里，`first` 和 `last` 与之前的情况相同。
`comp`: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 `bool` 的值。
返回值表示作为第一个参数传递的元素是否被认为小于第二个。
该函数不得修改其任何参数。这可以是函数指针或函数对象。

**返回值**: 它返回一个指向范围内最大元素的指针，如果存在多个这样的元素，则指向第一个。
如果范围为空，则指向 `last`。

```cpp
// C++ program to demonstrate the use of std::max_element
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

    // Finding the maximum value between the third and the
    // ninth element
    int* i1;
    i1 = std::max_element(v + 2, v + 9, comp);

    cout << *i1 << "\n";
    return 0;
}
```

输出:

```cpp
12
```

## 相关文章

*   [`std::max`](https://www.geeksforgeeks.org/stdmax-in-cpp/)
*   [`std::min`](https://www.geeksforgeeks.org/stdmin-in-cpp/)
*   [`std::equal`](https://www.geeksforgeeks.org/stdequal-in-cpp/)
*   [`std::min_element` in C++](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

本文由 **Mrigendra Singh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
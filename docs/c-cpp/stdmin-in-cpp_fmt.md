# 标准::C++ 中的最小值

> 原文:[https://www.geeksforgeeks.org/stdmin-in-cpp/](https://www.geeksforgeeks.org/stdmin-in-cpp/)

`std::min` 在头文件中定义，用于找出传递给它的数字中的最小值。如果有多个，它将返回其中的第一个。

**有以下 3 种用法:**

1.  它比较在其参数中传递的两个数字，返回两个中较小的一个，如果两者相等，则返回第一个。
2.  它还可以使用**二进制函数**来比较这两个数字，该函数由用户定义，然后在 `std::min()` 中作为参数传递。
3.  如果我们想在给定的列表中找到最小的元素，这也很有用，如果列表中存在多个元素，它会返回第一个元素。

**三个版本定义如下:**

## 1. 使用 `<` 比较元素

语法:

```cpp
template <class T>
constexpr const T& min (const T& a, const T& b);
```

`a` 和 `b` 是要比较的数字。
返回：两个值中较小的一个。

```cpp
// C++ program to demonstrate the use of std::min
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int a = 5;
    int b = 7;
    cout << std::min(a, b) << "\n";

    // Returns the first one if both the numbers
    // are same
    cout << std::min(7, 7);

    return 0;
}
```

输出:

```
5
7
```

## 2. 使用预定义函数比较元素

语法:

```cpp
template <class T, class Compare>
constexpr const T& min (const T& a, const T& b, Compare comp);
```

这里，`a` 和 `b` 是要比较的数字。
`comp`: 二进制函数，接受两个类型为 `T` 的值作为参数，并返回可转换为 `bool` 的值。返回的值表示传递的第一个参数是否被认为小于第二个。该函数不得修改其任何参数。这可以是函数指针或函数对象。
返回：两个值中较小的一个。

```cpp
// C++ program to demonstrate the use of std::min
#include <iostream>
#include <algorithm>
using namespace std;

// Defining the binary function
bool comp(int a, int b)
{
    return (a < b);
}
int main()
{
    int a = 5;
    int b = 7;
    cout << std::min(a, b, comp) << "\n";

    // Returns the first one if both the numbers
    // are same
    cout << std::min(7, 7, comp);

    return 0;
}
```

输出:

```
5
7
```

## 3. 在列表中查找最小元素

语法:

```cpp
template <class T>
constexpr T min (initializer_list<T> il, Compare comp);
```

`comp` 是可选的，可以省略。
`il`: 一个 `initializer_list` 对象。
返回：所有值中最小的一个。

```cpp
// C++ program to demonstrate the use of std::min
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

// Defining the binary function
bool comp(int a, int b)
{
    return (a < b);
}
int main()
{
    // Finding the smallest of all the numbers
    cout << std::min({ 1, 2, 3, 4, 5, 0, -1, 7 }, comp) << "\n";

    return 0;
}
```

输出:

```
-1
```

**相关文章:**

*   [标准::max_element](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)
*   [标准::最大值](https://www.geeksforgeeks.org/stdmax-in-cpp/)
*   [标准::相等](https://www.geeksforgeeks.org/stdequal-in-cpp/)
*   [标准::C++ 中的 min _ element](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
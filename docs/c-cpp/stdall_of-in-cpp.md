# std::all_of()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdall_of-in-cpp/](https://www.geeksforgeeks.org/stdall_of-in-cpp/)

C++ 函数在 STL 中的 **<算法>** 库中定义。该函数对整个数组元素范围进行操作，并且可以节省时间来运行循环来逐个检查每个元素。它检查每个元素的给定属性，当范围内的每个元素满足指定属性时返回 true，否则返回 false。
**语法:**

```cpp
template <class InputIterator, class UnaryPredicate>
bool all_of (InputIterator first, InputIterator last, UnaryPredicate pred);
first : Input iterators to the initial positions in a sequence.
last : Input iterators to the final positions in a sequence.
pred : An unary predicate function that accepts an element and returns a bool.
```

**异常:**如果谓词或迭代器上的操作引发异常，则引发异常。
**例:**

```cpp
// C++ code to demonstrate working of all_of()
#include <vector>
#include <algorithm>
#include <iostream>
int main()
{
    std::vector<int> v(10, 2);

    // illustrate all_of
    if (std::all_of(v.cbegin(), v.cend(), [](int i){ return i % 2 == 0; })) 
    {
        std::cout << "All numbers are even\n";
    }

}
```

输出:

```cpp
All numbers are even

```

```cpp
// C++ code to demonstrate working of all_of()
#include<iostream>
#include<algorithm> // for all_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, -6};

    // Checking if all elements are positive
    all_of(ar, ar+6, [](int x) { return x>0; })?
          cout << "All are positive elements" :
          cout << "All are not positive elements";

    return 0;

}
```

输出:

```cpp
All are not positive elements

```

在上面的代码中，-6 是一个否定的元素，否定了这个条件并返回 false。

[有用的数组算法 STL 函数](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/)

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 如何在 C++ 中快速交换两个大小相同的数组？

> 原文:[https://www . geesforgeks . org/quick-swap-two-array-size-c/](https://www.geeksforgeeks.org/quickly-swap-two-arrays-size-c/)

给定两个大小相同的数组 a[]和 b[]，我们需要交换它们的内容。

示例:

```cpp
Input : a[] = {1, 2, 3, 4}
        b[] = {5, 6, 7, 8}
Output : a[] = {5, 6, 7, 8}
         b[] = {1, 2, 3, 4}

```

一个简单的解决方案是迭代两个数组的元素并逐个交换它们。

一个快速的解决方案是使用 std::swap()。如果阵列大小相同，它可以直接交换阵列。

```cpp
// Illustrating the use of swap function
// to swap two arrays
#include <iostream>
#include <utility>
using namespace std;

// Driver Program
int main ()
{
    int a[] = {1, 2, 3, 4};
    int b[] = {5, 6, 7, 8};
    int n = sizeof(a)/sizeof(a[0]);

    swap(a, b);

    cout << "a[] = ";
    for (int i=0; i<n; i++)
        cout << a[i] << ", ";

    cout << "\nb[] = ";
    for (int i=0; i<n; i++)
        cout << b[i] << ", ";

    return 0;
}
```

输出:

```cpp
a[] = 5, 6, 7, 8, 
b[] = 1, 2, 3, 4,
```

本文由 **[香巴拉维·辛格](https://www.facebook.com/shambhavi.singh.1217)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
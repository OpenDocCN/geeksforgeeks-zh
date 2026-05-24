# 使用 C++ STL 中的 std::merge()快速合并两个排序后的数组

> 原文:[https://www . geesforgeks . org/quick-merging-two-sorted-arrays-using-stdmerge-c-STL/](https://www.geeksforgeeks.org/quickly-merging-two-sorted-arrays-using-stdmerge-c-stl/)

C++ 程序，用于按照排序顺序分别合并长度为“n”和“m”的两个排序数组。

示例:

```cpp
Input : A[] = {3, 6, 9}
        B[] = {2, 7, 11}
Output : C[] = {2, 3, 6, 7, 9, 11}

Input : A[] = {1, 1, 3, 6, 9}
        B[] = {1, 2, 7, 11, 11}
Output : C[] = {1, 1, 1, 2, 3, 6, 7, 9, 11, 11}

```

我们在下面的帖子中讨论了其他方法
[合并两个有 O(1)个额外空间的排序数组](https://www.geeksforgeeks.org/merge-two-sorted-arrays-o1-extra-space/)
[合并两个排序数组](https://www.geeksforgeeks.org/merge-two-sorted-arrays/)

我们可以使用 std::merge present 算法头文件快速合并两个排序的数组。

下面是使用 std :: merge 的实现

```cpp
// C++ program to merge two sorted arrays
// std::merge()
#include <iostream>
#include <algorithm>
using namespace std;

int main()
{
    int A[] = {1, 1, 9};
    int n = sizeof(A)/sizeof(A[0]);

    int B[] = {2, 7, 11, 11};
    int m  = sizeof(B)/sizeof(B[0]);

    /*Merging in sorted order*/
    int C[m + n];
    merge(A, (A + n), B, (B + m), C);

    // Print the merged array.
    for (int i = 0; i < (m + n); i++)
        cout << C[i] << " ";

    return 0;
}
```

输出:

```cpp
1 1 2 7 9 11 11 

```

通常，merge()的语法是

```cpp
// Merges elements from aFirst to aLast and bFirst
// to bLast into a result and returns iterator pointing
// to first element of result
OutputItr merge(InputItr1 aFirst, InputItr1 aLast,
                InputItr2 bFirst, InputItr2 bLast,
                OutputItr result);

We can use it for array of user defined objects
also by overloading < operator.

```

本文由 **[罗希特·塔普利亚尔](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 了解你的排序算法 | 集合 1 (编程语言使用的排序武器)

> 原文：[https://www.geeksforgeeks.org/know-sorting-algorithm-set-1-sorting-weapons-used-programming-languages/](https://www.geeksforgeeks.org/know-sorting-algorithm-set-1-sorting-weapons-used-programming-languages/)

有没有想过我们在 C++/Java 中使用的 `sort()` 函数或者 Python 中的 `sorted()` 函数是如何在内部工作的？

这里列出了不同编程语言的所有内置排序算法以及它们在内部使用的算法。

## C++ 的 `std::sort()` – Introsort (混合了 [快速排序](https://www.geeksforgeeks.org/quick-sort/)、[堆排序](https://www.geeksforgeeks.org/heap-sort/) 和 [插入排序](https://www.geeksforgeeks.org/insertion-sort/))

*   最优情况时间复杂度 - `O(NlogN)`
*   平均情况时间复杂度 - `O(NlogN)`
*   最坏情况时间复杂度 - `O(NlogN)`
*   辅助空间 - `O(logN)`
*   稳定性 - 否
*   自适应性 - 否

## Java 的 `Arrays.sort()` (对于原始类型) – 双轴快速排序

*   最优情况时间复杂度 - `O(NlogN)`
*   平均情况时间复杂度 - `O(NlogN)`
*   最坏情况时间复杂度 - `O(N^2)`
*   辅助空间 - `O(logN)`
*   稳定性 - 否
*   自适应性 - 否

## Java 6 的 `Arrays.sort()` – [归并排序](https://www.geeksforgeeks.org/merge-sort/) 和 [插入排序](https://www.geeksforgeeks.org/insertion-sort/) (TimSort)

*   最优情况时间复杂度 - `O(N)`
*   平均情况时间复杂度 - `O(NlogN)`
*   最坏情况时间复杂度 - `O(NlogN)`
*   辅助空间 - `O(N)`
*   稳定性 - 是
*   自适应性 - 是

## Python 的 `sorted()` – TimSort (混合了 [归并排序](https://www.geeksforgeeks.org/merge-sort/) 和 [插入排序](https://www.geeksforgeeks.org/insertion-sort/))

*   最优情况时间复杂度 - `O(N)`
*   平均情况时间复杂度 - `O(NlogN)`
*   最坏情况时间复杂度 - `O(NlogN)`
*   辅助空间 - `O(N)`
*   稳定性 - 是
*   自适应性 - 是

在接下来的几集里，我们将实现 Introsort ( C++的排序武器)和 Sleep sort、Gnome Sort 以及其他非常规的排序算法。

本文由 **拉希特·贝尔瓦亚尔** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。
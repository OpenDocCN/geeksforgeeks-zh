# 使用 C++ STL 中的集合计算反转

> 原文: [https://www.geeksforgeeks.org/counting-inversions-using-set-in-c-stl/](https://www.geeksforgeeks.org/counting-inversions-using-set-in-c-stl/)

## 数组的反转计数

数组的反转计数表示数组离排序有多远（或多近）。如果数组已经排序，则反转计数为 0。如果数组按相反顺序排序，则反转计数为最大值。

两个元素 `a[i]` 和 `a[j]` 形成一个反转，如果 `a[i] > a[j]` 且 `i < j`。为简单起见，我们可以假设所有元素都是唯一的。

示例：
输入：`arr[] = {8, 4, 2, 1}`
输出：6
给定数组有六个反转：`(8,4), (4,2), (8,2), (8,1), (4,1), (2,1)`。

我们已经在下面讨论了方法。
1.  [基于朴素和合并排序的方法。](https://www.geeksforgeeks.org/counting-inversions/)
2.  [基于 AVL 树的方法。](https://www.geeksforgeeks.org/count-inversions-in-an-array-set-2-using-self-balancing-bst/)

在这篇文章中，讨论了使用 C++ STL 中的 [`set`](https://www.geeksforgeeks.org/set-in-cpp-stl/) 实现方法 2 的简单方法。

## 算法步骤

1.  在 C++ STL 中创建一个空的 `Set`（注意，C++ STL 中的 `Set` 是使用自平衡二叉搜索树实现的）。并将数组的第一个元素插入到集合中。
2.  将反转计数初始化为 0。
3.  从 1 迭代到 n-1，并对 `arr[i]` 中的每个元素执行以下操作：
    a) 将 `arr[i]` 插入到集合中。
    b) 使用 `Set` STL 中定义的 `upper_bound()` 在集合中找到第一个大于 `arr[i]` 的元素。
    c) 找到上述找到的元素与集合中最后一个元素的距离，并将此距离加到反转计数上。
4.  返回反转计数。

## C++ 实现代码

```cpp
// A STL Set based approach for inversion count
#include<bits/stdc++.h>
using namespace std;

// Returns inversion count in arr[0..n-1]
int getInvCount(int arr[],int n)
{
    // Create an empty set and insert first element in it
    multiset<int> set1;
    set1.insert(arr[0]);

    int invcount = 0; // Initialize result

    multiset<int>::iterator itset1; // Iterator for the set

    // Traverse all elements starting from second
    for (int i=1; i<n; i++)
    {
        // Insert arr[i] in set (Note that set maintains
        // sorted order)
        set1.insert(arr[i]);

        // Set the iterator to first greater element than arr[i]
        // in set (Note that set stores arr[0],.., arr[i-1]
        itset1 = set1.upper_bound(arr[i]);

        // Get distance of first greater element from end
        // and this distance is count of greater elements
        // on left side of arr[i]
        invcount += distance(itset1, set1.end());
    }

    return invcount;
}

// Driver program to test above
int main()
{
    int arr[] = {8, 4, 2, 1};
    int n = sizeof(arr)/sizeof(int);
    cout << "Number of inversions count are : "
         << getInvCount(arr,n);
    return 0;
}
```

输出：

```cpp
Number of inversions count are : 6
```

## 复杂度分析

请注意，上述实现的最坏情况时间复杂度是 `O(n^2)`，因为 STL 中的 `distance` 函数在最坏情况下花费 `O(n)` 时间，但是这种实现比其他实现简单得多，并且平均比 Naive 方法花费的时间少得多。

本文由 **Abhiraj Smit** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。
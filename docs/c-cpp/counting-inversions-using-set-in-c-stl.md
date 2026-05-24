# 使用 C++ STL 中的集合计算反转

> 原文:[https://www . geesforgeks . org/counting-inversion-use-set-in-c-STL/](https://www.geeksforgeeks.org/counting-inversions-using-set-in-c-stl/)

数组的反转计数表示数组离排序有多远(或多近)。如果数组已经排序，则反转计数为 0。如果数组按相反顺序排序，则反转计数为最大值。

```cpp
    Two elements a[i] and a[j] form an inversion if 
     a[i] > a[j] and i < j. For simplicity, we may 
     assume that all elements are unique.

     Example:
     Input:  arr[] = {8, 4, 2, 1}
     Output: 6
     Given array has six inversions (8,4), (4,2),
     (8,2), (8,1), (4,1), (2,1).     

```

我们已经在下面讨论了方法。
1) [基于朴素和合并排序的方法。](https://www.geeksforgeeks.org/counting-inversions/)
2) [基于 AVL 树的方法。](https://www.geeksforgeeks.org/count-inversions-in-an-array-set-2-using-self-balancing-bst/)

在这篇文章中，讨论了使用 C++ STL 中的[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)实现方法 2 的简单方法。

```cpp
1) Create an empty Set in C++ STL (Note that a Set in C++ STL is 
   implemented using Self-Balancing Binary Search Tree). And insert
   first element of array into the set.

2) Initialize inversion count as 0.

3) Iterate from 1 to n-1 and do following for every element in arr[i]
     a) Insert arr[i] into the set.
     b) Find the first element greater than arr[i] in set
        using upper_bound() defined Set STL.
     c) Find distance of above found element from last element in set
        and add this distance to inversion count.

4) Return inversion count.

```

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

输出:

```cpp
Number of inversions count are : 6
```

请注意，上述实现的最坏情况时间复杂度是 O(n <sup>2</sup> )，因为 STL 中的距离函数在最坏情况下花费 O(n)个时间，但是这种实现比其他实现简单得多，并且平均比 Naive 方法花费的时间少得多。

本文由 **Abhiraj Smit** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
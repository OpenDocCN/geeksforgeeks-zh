# c++ STL 中的 stable_sort()

> 原文:[https://www.geeksforgeeks.org/stable_sort-c-stl/](https://www.geeksforgeeks.org/stable_sort-c-stl/)

像 [std::sort()](https://www.geeksforgeeks.org/sort-c-stl/) 一样，stable_sort 也对数组进行排序。语法也是一样的。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate default behaviour of
// sort() in STL.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };
    int n = sizeof(arr) / sizeof(arr[0]);

    stable_sort(arr, arr + n);

    cout << "\nArray after sorting using "
            "default sort is : \n";
    for (int i = 0; i < n; ++ i)
        cout << arr[i] << " ";

    return 0;
}
```

输出:

```cpp
Array after sorting using default sort is : 
0 1 2 3 4 5 6 7 8 9 
```

因此，默认情况下，sort()按升序对数组进行排序。
**如何降序排序？**
Like sort()，stable_sort()接受第三个参数，用于指定元素的排序顺序。我们可以通过“greater()”函数按降序排序。这个函数以一种把更大的元素放在前面的方式进行比较。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate descending order
// stable sort using greater<>().
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };
    int n = sizeof(arr) / sizeof(arr[0]);

    stable_sort(arr, arr + n, greater<int>());

    cout << "Array after sorting : \n";
    for (int i = 0; i < n; ++ i)
        cout << arr[i] << " ";

    return 0;
}
```

输出:

```cpp
Array after sorting : 
9 8 7 6 5 4 3 2 1 0 
```

**与 sort()相比，什么时候更喜欢稳定 _sort？**
有时我们希望确保排序数组中相等元素的顺序与原始数组中相同。如果这些值与其他字段相关联，这将非常有用。例如，考虑按分数对学生进行排序，如果两个学生有相同的分数，我们可能希望保持他们出现在输入中的顺序相同。详见排序算法中的[稳定性。
考虑以下例子。我们有按结束时间排序的时间间隔，我们想按开始时间排序。此外，如果两个开始时间相同，我们希望保持它们按结束时间排序。sort()不能保证这一点。](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/) 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to demonstrate STL stable_sort()
// to sort intervals according to start time.
// Given intervals are sorted according to
// ending time
#include <bits/stdc++.h>
using namespace std;

// An interval has start time and end time
struct Interval {
    int start, end;
};

// Compares two intervals according to starting
// times.
bool compareInterval(Interval i1, Interval i2)
{
    return (i1.start < i2.start);
}

int main()
{
    // Given intervals are sorted according to end time
    Interval arr[] = { {1, 3}, {2, 4}, {1, 7}, {2, 19} };
    int n = sizeof(arr) / sizeof(arr[0]);

    // sort the intervals in increasing order of
    // start time such that the start time intervals
    // appear in same order as in input.
    stable_sort(arr, arr + n, compareInterval);

    cout << "Intervals sorted by start time : \n";
    for (int i = 0; i < n; i++)
        cout << "[" << arr[i].start << ", " << arr[i].end
             << "] ";

    return 0;
}
```

输出:

```cpp
Intervals sorted by start time : 
[1, 3] [1, 7] [2, 4] [2, 19] 
```

**实现**
sort()函数通常使用 [Introsort](https://www.geeksforgeeks.org/know-your-sorting-algorithm-set-2-introsort-cs-sorting-weapon/) 。因此，sort()可能会保留语义等价值的物理顺序，但不能保证。
stable_sort()功能通常使用 [mergesort](https://www.geeksforgeeks.org/merge-sort/) 。因此，stable_sort()保持语义等价值的物理顺序及其保证。
**时间复杂度**
对于 sort()它是 O(n*log(n))
对于 stable_sort()它是 O(n*log^2(n))如果没有与长度成线性比例的额外内存可用。如果可用，则为 0(n * log(n))。
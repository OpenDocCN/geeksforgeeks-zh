# 在 C++ 中对向量进行排序

> 原文:[https://www.geeksforgeeks.org/sorting-a-vector-in-c/](https://www.geeksforgeeks.org/sorting-a-vector-in-c/)

先决条件:[标准::在 C++ 中排序](https://www.geeksforgeeks.org/sort-c-stl/)、[在 C++ 中向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)、[在 C++ 中初始化向量](https://www.geeksforgeeks.org/initialize-a-vector-in-cpp-different-ways/)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to sort a vector in non-decreasing
// order.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v{ 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };

    sort(v.begin(), v.end());

    cout << "Sorted \n";
    for (auto x : v)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
Sorted 
0 1 2 3 4 5 6 7 8 9 
```

**如何降序排序？**
sort()采用第三个参数，用于指定元素的排序顺序。我们可以通过“greater()”函数进行降序排序。这个函数以一种把更大的元素放在前面的方式进行比较。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to sort a vector in non-increasing
// order.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v{ 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };

    sort(v.begin(), v.end(), greater<int>());

    cout << "Sorted \n";
    for (auto x : v)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
Sorted 
9 8 7 6 5 4 3 2 1 0 
```

**如何按特定顺序排序？**
我们也可以编写自己的比较器函数，作为第三个参数传递。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to sort vector using
// our own comparator
#include <bits/stdc++.h>
using namespace std;

// An interval has start time and end time
struct Interval {
    int start, end;
};

// Compares two intervals according to starting times.
bool compareInterval(Interval i1, Interval i2)
{
    return (i1.start < i2.start);
}

int main()
{
    vector<Interval> v { { 6, 8 }, { 1, 9 }, { 2, 4 }, { 4, 7 } };

    // sort the intervals in increasing order of
    // start time
    sort(v.begin(), v.end(), compareInterval);

    cout << "Intervals sorted by start time : \n";
    for (auto x : v)
        cout << "[" << x.start << ", " << x.end << "] ";

    return 0;
}
```

输出:

```cpp
Intervals sorted by start time : 
[1, 9] [2, 4] [4, 7] [6, 8] 
```

**相关文章:**

[排序一对向量|集合 1](https://www.geeksforgeeks.org/sorting-vector-of-pairs-in-c-set-1-sort-by-first-and-second/)
[排序一对向量|集合 2](https://www.geeksforgeeks.org/sorting-vector-of-pairs-in-c-set-2-sort-in-descending-order-by-first-and-second/)
# c++ 中对向量下界()和上界()的实现

> 原文:[https://www . geesforgeks . org/c 对向量下界和上界的实现/](https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-in-vector-of-pairs-in-c/)

在本文中，我们将讨论[对的](https://www.geeksforgeeks.org/pair-in-cpp-stl/)[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)中[下界()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)和[上界()](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/)的实现。

*   **下界():**它返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于或等于给定值**【瓦尔】**。但是在向量对中**下界()**对于**对(x，y)** 将返回一个迭代器，指向第一个值大于或等于 **x** 而第二个值大于或等于 **y** 的对的位置。
    如果不满足上述标准，那么它返回一个迭代器到成对向量中的索引。

*   **upper_bound():** 它返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于给定值**【瓦尔】**。但是在向量对中**上限()**对于**对(x，y)** 将返回一个迭代器，指向第一个值大于 **x** 且第二个值大于 **y** 的对的位置。
    如果不满足上述标准，那么它返回一个迭代器到成对向量中的索引。

下面是演示成对向量中[下界()和上界()](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)的程序:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate lower_bound()
// and upper_bound() in Vectors of Pairs

#include <bits/stdc++.h>
using namespace std;

// Function to implement lower_bound()
void findLowerBound(vector<pair<int, int> >& arr,
                    pair<int, int>& p)
{
    // Given iterator points to the
    // lower_bound() of given pair
    auto low = lower_bound(arr.begin(), arr.end(), p);

    cout << "lower_bound() for {2, 5}"
         << " is at index: " << low - arr.begin() << endl;
}

// Function to implement upper_bound()
void findUpperBound(vector<pair<int, int> >& arr,
                    pair<int, int>& p)
{
    // Given iterator points to the
    // upper_bound() of given pair
    auto up = upper_bound(arr.begin(), arr.end(), p);

    cout << "upper_bound() for {2, 5}"
         << " is at index: " << up - arr.begin() << endl;
}

// Driver Code
int main()
{
    // Given sorted vector of Pairs
    vector<pair<int, int> > arr;
    arr = { { 1, 3 }, { 1, 7 }, { 2, 4 },
            { 2, 5 }, { 3, 8 }, { 8, 6 } };

    // Given pair {2, 5}
    pair<int, int> p = { 2, 5 };

    // Function Call to find lower_bound
    // of pair p in arr
    findLowerBound(arr, p);

    // Function Call to find upper_bound
    // of pair p in arr
    findUpperBound(arr, p);

    return 0;
}
```

**Output**

```cpp
lower_bound() for {2, 5} is at index: 3
upper_bound() for {2, 5} is at index: 4

```
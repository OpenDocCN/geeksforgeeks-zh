# c++ 中对列表下界()和上界()的实现

> 原文:[https://www . geesforgeks . org/c 对列表中下限和上限的实现/](https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-in-list-of-pairs-in-c/)

在本文中，我们将讨论在[对](https://www.geeksforgeeks.org/pair-in-cpp-stl/)的[列表](https://www.geeksforgeeks.org/list-cpp-stl/)中[下限()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)和[上限()](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/)的实现。

*   **下界():**它返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于或等于给定值**【瓦尔】**。但是在对列表**中，**对(x，y)** 的下界()**将返回一个迭代器，指向第一个值大于或等于 **x** 而第二个值大于或等于 **y** 的对的位置。
    如果不满足上述标准，那么它返回一个迭代器到从对列表中选择的索引。
*   **upper_bound():** 它返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于给定值**【瓦尔】**。但是在对列表**中，**对(x，y)** 的上限()**将返回一个迭代器，指向第一个值大于 **x** 而第二个值大于 **y** 的对的位置。
    如果不满足上述标准，那么它返回一个迭代器到从对列表中选出的索引。

下面是演示成对列表中的[下界()和上界()](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)的程序:

**程序:**

## C++

```cpp
// C++ program to demonstrate lower_bound()
// and upper_bound() in List of Pairs

#include <bits/stdc++.h>
using namespace std;

// Function to implement lower_bound()
void findLowerBound(
    list<pair<int, int> >& list,
    pair<int, int>& p)
{
    // Given iterator points to the
    // lower_bound() of given pair
    auto low = lower_bound(list.begin(),
                           list.end(), p);

    cout << "lower_bound() for {2, 5}"
         << " is at index: {"
         << (*low).first << ", "
         << (*low).second << " }"
         << endl;
}

// Function to implement upper_bound()
void findUpperBound(
    list<pair<int, int> >& list,
    pair<int, int>& p)
{
    // Given iterator points to the
    // upper_bound() of given pair
    auto up = upper_bound(list.begin(),
                          list.end(), p);

    cout << "upper_bound() for {2, 5}"
         << " is at index: {"
         << (*up).first << ", "
         << (*up).second << " }"
         << endl;
}

// Driver Code
int main()
{
    list<pair<int, int> > list;

    // Given sorted List of Pairs
    list.push_back(make_pair(1, 3));
    list.push_back(make_pair(1, 7));
    list.push_back(make_pair(2, 4));
    list.push_back(make_pair(2, 5));
    list.push_back(make_pair(3, 8));
    list.push_back(make_pair(8, 6));

    // Given pair {2, 5}
    pair<int, int> p = { 2, 5 };

    // Function Call to find lower_bound
    // of pair p in arr
    findLowerBound(list, p);

    // Function Call to find upper_bound
    // of pair p in arr
    findUpperBound(list, p);

    return 0;
}
```

**Output:**

```cpp
lower_bound() for {2, 5} is at index: {2, 5 }
upper_bound() for {2, 5} is at index: {3, 8 }

```
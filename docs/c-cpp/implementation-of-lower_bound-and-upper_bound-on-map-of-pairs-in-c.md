# c++ 中对映射的下界()和上界()的实现

> 原文:[https://www . geesforgeks . org/c 对地图上下限和上限的实现/](https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-on-map-of-pairs-in-c/)

**先决条件:**T2 在 C++ STL 中映射下界()函数，[在 C++ STL 中映射上界()函数](https://www.geeksforgeeks.org/map-upper_bound-function-in-c-stl/)

在本文中，我们将讨论[对](https://www.geeksforgeeks.org/pair-in-cpp-stl/)的[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)中[下界()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)和[上界()](https://www.geeksforgeeks.org/upper_bound-in-cpp/)的实现。

*   **lower_bound():** It returns an iterator pointing to the first element in the range **[first, last)** which has a value greater than or equals to the given value **“val”**. But in Map of Pairs **lower_bound()** for **pair(x, y)** will return an iterator pointing to the pair whose first value is greater than or equals **x** and second value is greater than equals to **y**.
    If the above-mentioned criteria are not met, then it returns an iterator which points to the pair **{Map.size(), 0}**.

    **语法:**

    ```cpp
    mp.lower_bound({a, b})

    where,
    mp is the map of pairs
    and {a, b} whose lower_bound
    is to be found

    ```

*   **upper_bound():** It returns an iterator pointing to the first element in the range **[first, last)** which has a value greater than the given value **“val”**. But in Map of Pairs **upper_bound()** for **pair(x, y)** will return an iterator pointing to the pair whose first value is greater than **x** and second value is greater than **y**.
    If the above-mentioned criteria are not met, then it returns an iterator which points to the pair **{Map.size(), 0}**.

    **语法:**

    ```cpp
    mp.upper_bound({a, b})

    where,
    mp is the map of pairs
    and {a, b} whose upper_bound
    is to be found

    ```

下面是演示成对映射中[下界()和上界()](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)的程序:

**程序 1:**

```cpp
// C++ program to demonstrate lower_bound()
// and upper_bound() in Map of Pairs

#include <bits/stdc++.h>
using namespace std;

// Function to implement lower_bound()
void findLowerBound(
    map<pair<int, int>, int>& mp,
    pair<int, int>& p)
{

    // This iterator points to the
    // lower_bound() of given pair
    auto low = mp.lower_bound(p);

    cout << "lower_bound() for {2, 5}"
         << " is: {"
         << (*low).first.first << ", "
         << (*low).first.second
         << "}" << endl;
}

// Function to implement upper_bound()
void findUpperBound(
    map<pair<int, int>, int>& mp,
    pair<int, int>& p)
{

    // This iterator points to the
    // upper_bound() of given pair
    auto up = mp.upper_bound(p);

    cout << "upper_bound() for {2, 5}"
         << " is: {"
         << (*up).first.first << ", "
         << (*up).first.second
         << "}" << endl;
}

// Driver Code
int main()
{
    // Declare map of Pairs
    map<pair<int, int>, int> mp;

    // Insert Pairs in Map
    mp.insert({ { 2, 3 }, 8 });
    mp.insert({ { 4, 1 }, 5 });
    mp.insert({ { 7, 1 }, 3 });
    mp.insert({ { 9, 3 }, 1 });
    mp.insert({ { 5, 0 }, 3 });

    // Given pair {2, 5}
    pair<int, int> p = { 2, 5 };

    // Function Call to find lower_bound
    // of pair p in map mp
    findLowerBound(mp, p);

    // Function Call to find upper_bound
    // of pair p in map mp
    findUpperBound(mp, p);

    return 0;
}
```

**Output:**

```cpp
lower_bound() for {2, 5} is: {4, 1}
upper_bound() for {2, 5} is: {4, 1}

```
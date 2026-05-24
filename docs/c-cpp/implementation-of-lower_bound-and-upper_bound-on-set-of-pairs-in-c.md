# c++ 中对集合的下界和上界的实现

> 原文:[https://www . geeksforgeeks . org/c 对集上下限和上限的实现/](https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-on-set-of-pairs-in-c/)

**先决条件:** [在 C++ STL 中设置下界()函数](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/)，[在 C++ STL 中设置上界()函数](https://www.geeksforgeeks.org/set-upper_bound-function-in-c-stl/)

**下界()**返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于或等于给定值**【瓦尔】**。但是在成对组**中，**对(x，y)** 的下界()**将返回一个迭代器，指向第一个值大于或等于 **x** 的对的位置。
如果第一个值相同，那么它将返回一个迭代器，指向第二个值大于或等于 **y** 的对的位置。
如果不满足上述标准，则返回一个迭代器，该迭代器指向集合的末尾(紧挨着集合中的最后一对)。

**语法:**使用下界()有两种方法:

> setName .下界({a，b})

> 下界(setName.begin()，setName.end()，对(a，b))

**upper_bound()** 返回一个迭代器，指向范围**【第一个，最后一个】**中的第一个元素，该元素的值大于给定值**【瓦尔】**。但是在成对组**中，**对(x，y)** 的上限()**将返回一个迭代器，指向第一个值大于 **x** 的成对位置。
如果第一个值相同，那么它将返回一个迭代器，指向第二个值大于 **y** 的对的位置。
如果不满足上述标准，则返回一个迭代器，该迭代器指向集合的末尾(紧挨着集合中的最后一对)。

**语法:**有两种方法可以将 upper_bound()与 Set 一起使用:

> setName.upper_bound({a，b})

> 上限(setName.begin()、setName.end()、对(a，b))

下面是演示[对集](https://www.geeksforgeeks.org/sets-of-pairs-in-c/)中[下界()和上界()](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)的程序:

```cpp
// C++ program to demonstrate lower_bound()
// and upper_bound() in set of Pairs

#include <bits/stdc++.h>
using namespace std;

// Function to implement lower_bound()
void findLowerBound(
    set<pair<int, int> >& arr,
    pair<int, int>& p)
{

    // Given iterator points to the
    // lower_bound() of given pair
    auto low = lower_bound(arr.begin(),
                           arr.end(), p);

    cout << "lower_bound() for {1, 2}"
         << " is: {" << (*low).first << ", "
         << (*low).second << "}" << endl;
}

// Function to implement upper_bound()
void findUpperBound(
    set<pair<int, int> >& arr,
    pair<int, int>& p)
{

    // Given iterator points to the
    // lower_bound() of given pair
    auto up = upper_bound(arr.begin(),
                          arr.end(), p);

    cout << "upper_bound() for {1, 2}"
         << " is: {" << (*up).first << ", "
         << (*up).second << "}" << endl;
}

// Driver Code
int main()
{

    // Given sorted vector of Pairs
    set<pair<int, int> > s;

    // Insert pairs in set
    s.insert(make_pair(1, 2));
    s.insert(make_pair(2, 4));
    s.insert(make_pair(3, 7));
    s.insert(make_pair(8, 9));

    // Given pair { 1, 2 }
    pair<int, int> p = { 1, 2 };

    // Function Call to find lower_bound
    // of pair p in arr
    findLowerBound(s, p);

    // Function Call to find upper_bound
    // of pair p in arr
    findUpperBound(s, p);

    return 0;
}
```

**Output:**

```cpp
lower_bound() for {1, 2} is: {1, 2}
upper_bound() for {1, 2} is: {2, 4}

```
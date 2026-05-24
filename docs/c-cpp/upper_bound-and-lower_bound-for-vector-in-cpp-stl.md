# c++ STL 中 Vector 的标准::上界和标准::下界

> 原文:[https://www . geeksforgeeks . org/CPP-STL 中矢量的上限和下限/](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)

点击此处获取向量的[集 1](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 和[集 2](https://www.geeksforgeeks.org/modifiers-for-vector-in-cpp-stl/) 。

## 向量–[上限](https://www.geeksforgeeks.org/set-upper_bound-function-in-c-stl/)和[下限](https://www.geeksforgeeks.org/lower_bound-in-cpp/)

迭代器下界(迭代器第一个，迭代器最后一个，常量值)
迭代器上界(迭代器第一个，迭代器最后一个，常量值)
下界返回一个指向范围[第一个，最后一个]中第一个元素的迭代器，其值**不**小于‘val’。
upper_bound 返回一个迭代器，指向范围[第一个，最后一个]中值大于“val”的第一个元素。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// lower_bound and upper_bound in vector
#include <algorithm> // for lower_bound, upper_bound and sort
#include <iostream>
#include <vector> // for vector

using namespace std;

int main()
{
    int gfg[] = { 5, 6, 7, 7, 6, 5, 5, 6 };

    vector<int> v(gfg, gfg + 8); // 5 6 7 7 6 5 5 6

    sort(v.begin(), v.end()); // 5 5 5 6 6 6 7 7

    vector<int>::iterator lower, upper;
    lower = lower_bound(v.begin(), v.end(), 6);
    upper = upper_bound(v.begin(), v.end(), 6);

    cout << "lower_bound for 6 at position "
         << (lower - v.begin() + 1) << '\n';
    cout << "upper_bound for 6 at position "
         << (upper - v.begin() + 1) << '\n';

    return 0;
}
```

**输出:**

```cpp
lower_bound for 6 at position 4
upper_bound for 6 at position 7

```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
# C++ STL 中 Vector 的 `upper_bound` 和 `lower_bound`

> 原文：[https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)

点击此处获取向量的[集 1](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 和[集 2](https://www.geeksforgeeks.org/modifiers-for-vector-in-cpp-stl/)。

## Vector – `upper_bound` 和 `lower_bound`

`lower_bound(iterator first, iterator last, const value)`
`upper_bound(iterator first, iterator last, const value)`

`lower_bound` 返回一个指向范围 `[first, last]` 中第一个元素的迭代器，其值**不**小于 `val`。
`upper_bound` 返回一个迭代器，指向范围 `[first, last]` 中值大于 `val` 的第一个元素。

## 示例代码

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

**输出：**

```
lower_bound for 6 at position 4
upper_bound for 6 at position 7
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。
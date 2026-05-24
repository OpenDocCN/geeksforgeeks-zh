# c++ 中向量的最后一个元素(访问和更新)

> 原文:[https://www . geeksforgeeks . org/CPP 中向量的最后一个元素-访问和更新/](https://www.geeksforgeeks.org/last-element-of-vector-in-cpp-accessing-and-updating/)

在 [C++ 向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)中，我们可以通过以下方式使用向量的大小来访问最后一个元素。

**1)使用尺寸()**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v{10, 20, 30, 40, 50};

    // Accessing last element
    int n = v.size();
    cout << v[n - 1] << endl;

    // modifying last element
    v[n - 1] = 100;

    cout << v[n - 1] << endl;
    return 0;
}
```

输出:

```cpp
50
100
```

**2)使用 back()** 我们可以使用 back()访问和修改最后一个值。

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v{10, 20, 30, 40, 50};

    // Accessing last element
    cout << v.back() << endl;

    // modifying last element
    v.back() = 100;

    cout << v.back() << endl;
    return 0;
}
```

输出:

```cpp
50
100
```
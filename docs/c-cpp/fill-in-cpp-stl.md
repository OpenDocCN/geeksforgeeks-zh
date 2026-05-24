# 填写 C++ STL

> 原文:[https://www.geeksforgeeks.org/fill-in-cpp-stl/](https://www.geeksforgeeks.org/fill-in-cpp-stl/)

“填充”函数将值“val”分配给范围[begin，end]中的所有元素，其中“begin”是初始位置，“end”是最后位置。

**注意:**请注意，范围中包含“开始”，但不包含“结束”。下面是一个演示“填充”的示例:

```cpp
// C++ program to demonstrate working of fill()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect(8);

    // calling fill to initialize values in the
    // range to 4
    fill(vect.begin() + 2, vect.end() - 1, 4);

    for (int i = 0; i < vect.size(); i++)
        cout << vect[i] << " ";

    return 0;
}
```

**Output:**

```cpp
0 0 4 4 4 4 4 0

```

我们也可以使用填充来填充数组中的值。

```cpp
// C++ program to demonstrate working of fill()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[10];

    // calling fill to initialize values in the
    // range to 4
    fill(arr, arr + 10, 4);

    for (int i = 0; i < 10; i++)
        cout << arr[i] << " ";

    return 0;
}
```

**Output:**

```cpp
4 4 4 4 4 4 4 4 4 4

```

用 C++ 填充[列表](https://www.geeksforgeeks.org/list-cpp-stl/)。

```cpp
// C++ program to demonstrate working of fill()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    list<int> ml = { 10, 20, 30 };

    fill(ml.begin(), ml.end(), 4);

    for (int x : ml)
        cout << x << " ";

    return 0;
}
```

**Output:**

```cpp
4 4 4

```
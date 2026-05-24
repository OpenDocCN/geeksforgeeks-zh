# 在 C++ 中交换不同容器的子范围

> 原文:[https://www . geeksforgeeks . org/从不同容器交换子范围-in-c/](https://www.geeksforgeeks.org/swapping-of-subranges-from-different-containers-in-c/)

容器是保存其他对象集合的容器对象。它们被实现为类模板，这允许作为元素支持的类型有很大的灵活性。

给定[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)和[列表](https://www.geeksforgeeks.org/list-cpp-stl/)中的一些元素，交换它们的一些元素。

```cpp
// C++ program to swap subranges from different containers
#include <algorithm>
#include <iostream>
#include <list>
#include <vector>
using namespace std;

int main()
{
    vector<int> v =  { -10, -15, -30, 20, 500 };
    list<int> lt = { 10, 50, 30, 100, 50 };

    /* swap_ranges() swaps the values starting from the beginning 
       to 3rd last values as per the parameters.
       Hence (-10, -15, -30) are swapped with (10, 50, 30). */
    swap_ranges(v.begin(), v.begin() + 3, lt.begin());

    for (int n : v)
        cout << n << ' ';
    cout << '\n';

    for (int n : lt)
        cout << n << ' ';
    cout << endl;
}
```

**Output:**

```cpp
10 50 30 20 500 
-10 -15 -30 100 50

```

我们也可以在两个向量中交换范围。

```cpp
// C++ program to swap subranges from different containers
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v1 = { -10, -15, -30, 20, 500 };
    vector<int> v2 = { 10, 50, 30, 100, 50 };

    /* swap_ranges() swaps the values starting from the beginning 
       to 3rd last values as per the parameters.
       Hence (-10, -15, -30) are swapped with (10, 50, 30). */
    swap_ranges(v1.begin(), v1.begin() + 3, v2.begin());

    for (int n : v1)
        cout << n << ' ';
    cout << '\n';

    for (int n : v2)
        cout << n << ' ';
    cout << endl;
}
```

**Output:**

```cpp
10 50 30 20 500 
-10 -15 -30 100 50

```
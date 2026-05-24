# c++ STL 中的数组 get()函数

> 原文:[https://www.geeksforgeeks.org/array-get-function-in-c-stl/](https://www.geeksforgeeks.org/array-get-function-in-c-stl/)

**数组::get()** 是 C++ STL 中的内置函数，它返回对数组容器第 I 个元素的引用。

**语法:**

```cpp
get(array_name)
```

**参数:**该函数接受两个强制参数，如下所述。

*   I–数组中某个元素的位置，第一个元素的位置为 0。
*   arr _ name–一个数组容器。

**返回值:**函数返回对数组中指定位置的元素的引用

**时间复杂度:** O(1)

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// array::get() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // array initialisation
    array<int, 3> arr = { 10, 20, 30 };

    // function call
    cout << "arr[0] = " << get<0>(arr) << "\n";
    cout << "arr[1] = " << get<1>(arr) << "\n";
    cout << "arr[2] = " << get<2>(arr) << "\n";

    return 0;
}
```

**Output:**

```cpp
arr[0] = 10
arr[1] = 20
arr[2] = 30

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// array::get() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // array initialisation
    array<char, 3> arr = { 'a', 'b', 'c' };

    // function call
    cout << "arr[0] = " << get<0>(arr) << "\n";
    cout << "arr[1] = " << get<1>(arr) << "\n";
    cout << "arr[2] = " << get<2>(arr) << "\n";

    return 0;
}
```

**Output:**

```cpp
arr[0] = a
arr[1] = b
arr[2] = c

```
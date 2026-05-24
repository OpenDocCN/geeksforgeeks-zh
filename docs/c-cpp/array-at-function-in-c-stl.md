# 数组 at()函数在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/array-at-function-in-c-stl/](https://www.geeksforgeeks.org/array-at-function-in-c-stl/)

**数组::at()** 是 C++ STL 中的内置函数，它返回对给定数组中位置 I 处元素的引用。

**语法:**

```cpp
array_name.at(i)
```

**参数:**该功能接受指定位置的单个强制参数 *i* 。

**返回值:**如果给定数组中的索引 I 是有效索引，则函数返回该索引 I 处的元素，否则将引发*超出范围*异常。

**时间复杂度:** O(1)

以下程序演示了**数组::at()** 功能:

**程序 1:**

```cpp
// CPP program to illustrate
// the array::at() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // array initialisation
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // prints the element at ith index
    // index starts from zero
    cout << "The element at index 2 is " << arr.at(2) << endl;

    return 0;
}
```

**Output:**

```cpp
The element at index 2 is 2

```

**Program 2 :** Illustrating function when it is implemented on lesser size array causing an error.

```cpp
// CPP program to illustrate
// the array::at() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // array initialisation
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // it is an exception
    cout << "The element at index 2 is " << arr.at(7) << endl;

    return 0;
}
```

**Output:**

```cpp
Abort signal from abort(3) (SIGABRT)

```
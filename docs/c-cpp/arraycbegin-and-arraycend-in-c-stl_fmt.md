# C++ STL 中的 `array::cbegin()` 和 `array::cend()`

> 原文: [https://www.geeksforgeeks.org/arraycbegin-and-arraycend-in-c-stl/](https://www.geeksforgeeks.org/arraycbegin-and-arraycend-in-c-stl/)

## `array::cbegin()`

`array::cbegin()` 是 C++ STL 中的一个内置函数，它返回一个指向数组中第一个元素的 `const_iterator`。它不能用于修改数组中的元素，而使用 `array::begin()` 则可以。

**语法:**

```cpp
array_name.cbegin()
```

**参数:** 函数不接受任何参数。

**返回值:** 函数返回一个指向数组中第一个元素的 `const_iterator`。

**程序 1:**

```cpp
// CPP program to illustrate
// the array::cbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // Prints the first element
    cout << "The first element is " << *(arr.cbegin()) << "\n";

    // Print all the elements
    cout << "The array elements are: ";
    for (auto it = arr.cbegin(); it != arr.cend(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
The first element is 1
The array elements are: 1 5 2 4 7
```

## `array::cend()`

`array::cend()` 是 C++ STL 中的一个内置函数，它返回一个指向数组中最后一个元素之后理论元素的 `const_iterator`。

**语法:**

```cpp
array_name.cend()
```

**参数:** 函数不接受任何参数。

**返回值:** 函数返回一个 `const_iterator`，指向数组中最后一个元素之后的理论元素。

**程序 1:**

```cpp
// CPP program to illustrate
// the array::cend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // prints all the elements
    cout << "The array elements are: ";
    for (auto it = arr.cbegin(); it != arr.cend(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
The array elements are: 1 5 2 4 7
```
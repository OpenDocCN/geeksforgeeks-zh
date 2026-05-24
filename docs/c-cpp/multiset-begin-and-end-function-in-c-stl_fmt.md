# C++ STL 中的 multiset begin() 和 end() 函数

> 原文：[https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)

## multiset::begin()

`multiset::begin()` 是 C++ STL 中的一个内置函数，返回一个指向 multiset 容器中第一个元素的迭代器。由于 multiset 总是按有序方式包含元素，`begin()` 总是根据排序标准指向第一个元素。

**语法：**

```cpp
iterator multiset_name.begin()
```

**参数：** 函数不接受任何参数。

**返回值：** 函数返回指向容器中第一个元素的迭代器。

下面的程序说明了上述功能：

```cpp
// CPP program to demonstrate the
// multiset::begin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int arr[] = { 14, 10, 15, 11, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 5);

    // Print the first element
    cout << "The first element is: " << *(s.begin()) << endl;

    // prints all elements in set
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出：**

```cpp
The first element is: 10
10 10 11 14 15
```

## multiset::end()

`multiset::end()` 是 C++ STL 中的一个内置函数，返回一个指向容器中最后一个元素之后位置的迭代器。

**语法：**

```cpp
iterator multiset_name.end()
```

**参数：** 函数不接受任何参数。

**返回值：** 函数返回一个迭代器，指向 multiset 容器中最后一个元素之后的位置。

下面的程序说明了上述功能：

```cpp
// CPP program to demonstrate the
// multiset::end() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int arr[] = { 14, 10, 15, 11, 10, 12, 17, 12 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 8);

    // prints all elements in set
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出：**

```cpp
10 10 11 12 12 14 15 17
```
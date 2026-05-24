# C++ STL 中的 multiset rbegin() 和 rend() 函数

> 原文: [https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/)

## multiset::rbegin()

`multiset::rbegin()` 是 C++ STL 中的一个内置函数，它返回一个反向迭代器，指向 multiset 容器中的最后一个元素。

**语法:**

```cpp
reverse_iterator multiset_name.rbegin()
```

**参数:** 函数不取任何参数。

**返回值:** 函数返回一个反向迭代器，指向容器中的最后一个元素。

下面的程序说明了 `multiset::rbegin()` 方法:

```cpp
// CPP program to demonstrate the
// multiset::rbegin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int arr[] = { 15, 12, 15, 11, 10, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 6);

    multiset<int>::reverse_iterator rit;

    // prints all elements in reverse order
    for (rit = s.rbegin(); rit != s.rend(); rit++)
        cout << *rit << " ";

    cout << "\nThe last element in multiset is " << *(s.rbegin());

    return 0;
}
```

**输出:**

```cpp
15 15 12 11 10 10 
The last element in multiset is 15
```

## multiset::rend()

`multiset::rend()` 是 C++ STL 中的一个内置函数，它返回一个反向迭代器，指向 multiset 容器中第一个元素之前的理论元素。

**语法:**

```cpp
reverse_iterator multiset_name.rend()
```

**参数:** 函数不接受任何参数。

**返回值:** 函数返回一个反向迭代器，指向多集容器中第一个元素之前的理论元素。

下面的程序说明了 `multiset::rend()` 函数:

```cpp
// CPP program to demonstrate the
// multiset::rend() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int arr[] = { 15, 13, 15, 11, 13, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 6);

    multiset<int>::reverse_iterator rit;

    // prints all elements in reverse order
    for (rit = s.rbegin(); rit != s.rend(); rit++)
        cout << *rit << " ";

    return 0;
}
```

**输出:**

```cpp
15 15 13 13 11 10
```
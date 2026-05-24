# c++ STL 中的多集空()函数

> 原文:[https://www . geesforgeks . org/multist-empty-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/)

**多集::empty()** 函数是 C++ STL 中的内置函数，用于检查多集是否为空。如果多集为空，则返回 true，否则返回 false。

**语法:**

```cpp
multiset_name.empty()

```

**参数:**函数不接受任何参数。

**返回值:**如果多集为空，函数返回真，否则返回假。

下面的程序说明了 multist::empty()函数:

**程序 1:**

## C++

```cpp
// C++ program to demonstrate the
// multiset::empty() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 15, 10, 15, 11, 10, 18, 18, 20, 20 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 9);

    if (!s.empty())
        cout << "The multiset is not empty";
    else
        cout << "The multiset is empty";
    return 0;
}
```

**Output:** 

```cpp
The multiset is not empty

```

**程序 2:**

## C++

```cpp
// C++ program to demonstrate the
// multiset::empty() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // declaration
    multiset<int> s;

    if (!s.empty())
        cout << "The multiset is not empty";
    else
        cout << "The multiset is empty";
    return 0;
}
```

**Output:** 

```cpp
The multiset is empty

```
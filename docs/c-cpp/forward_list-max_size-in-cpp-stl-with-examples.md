# c++ STL 中的 forward_list max_size()，示例

> 原文:[https://www . geesforgeks . org/forward _ list-max _ size-in-CPP-STL-with-examples/](https://www.geeksforgeeks.org/forward_list-max_size-in-cpp-stl-with-examples/)

**forward_list::max_size()** 是 C++ STL 中的内置函数，返回 forward_list 容器可以容纳的最大元素数

**语法:**

```cpp
forward_list_name.max_size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回容器可以容纳的最大元素数量。

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// forward_list::max_size() function
// when the list is not-empty
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // declaration of forward list
    forward_list<int> fl;

    // assign value
    fl.assign(5, 8);

    // prints the elements
    cout << "The forward_list elements: ";

    for (auto it = fl.begin(); it != fl.end(); it++)
        cout << *it << " ";

    cout << "\nThe max size: " << fl.max_size();
    return 0;
}
```

**Output:**

```cpp
The forward_list elements: 8 8 8 8 8 
The max size: 1152921504606846975

```

**程序 1:**

```cpp
// CPP program to demonstrate the
// forward_list::max_size() function
// when the list is empty
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // declaration of forward list
    forward_list<int> fl;

    cout << "\nThe max size: " << fl.max_size();
    return 0;
}
```

**Output:**

```cpp
The max size: 1152921504606846975

```
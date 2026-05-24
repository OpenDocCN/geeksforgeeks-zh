# c++ STL 中的多集 max_size()，示例

> 原文:[https://www . geesforgeks . org/multist-max _ size-in-CPP-STL-with-examples/](https://www.geeksforgeeks.org/multiset-max_size-in-cpp-stl-with-examples/)

**多集::max_size()** 是 C++ STL 中的内置函数，返回多集容器可以容纳的最大元素数量。

**语法:**

```cpp
multiset_name.max_size()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回多集容器可以容纳的最大元素数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::max_size() function
// when multiset is non-empty
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the multiset container
    s.insert(10);
    s.insert(13);
    s.insert(13);
    s.insert(25);
    s.insert(24);

    cout << "The multiset elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    cout << "\nThe max size of multiset: " << s.max_size();
    return 0;
}
```

**输出:**

```cpp
The multiset elements are: 10 13 13 24 25 
The max size of multiset: 461168601842738790

```

**程序二:**

```cpp
// CPP program to demonstrate the
// multiset::max_size() function
// when multiset is empty
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    cout << "\nThe max size of multiset: " << s.max_size();
    return 0;
}
```

**输出:**

```cpp
The max size of multiset: 461168601842738790

```

[多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)的所有功能
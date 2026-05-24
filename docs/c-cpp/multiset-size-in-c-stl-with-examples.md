# c++ STL 中的多集大小()，示例

> 原文:[https://www . geesforgeks . org/multist-size-in-c-STL-with-examples/](https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/)

**多集::size()** 是 C++ STL 中的内置函数，返回多集容器中的元素数量。

**语法:**

```cpp
multiset_name.size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回多集容器中的元素个数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::size() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the multiset container
    s.insert(10);
    s.insert(13);

    cout << "The size of multiset: " << s.size();
    s.insert(13);
    s.insert(25);

    cout << "\nThe size of multiset: " << s.size();
    s.insert(24);

    cout << "\nThe size of multiset: " << s.size();
    return 0;
}
```

**输出:**

```cpp
The size of multiset: 2
The size of multiset: 4
The size of multiset: 5

```

**程序二:**

```cpp
// CPP program to demonstrate the
// multiset::size() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    cout << "The size of multiset: " << s.size();
    s.insert(2);
    s.insert(3);

    cout << "\nThe size of multiset: " << s.size();
    s.insert(4);

    cout << "\nThe size of multiset: " << s.size();
    return 0;
}
```

**输出:**

```cpp
The size of multiset: 0
The size of multiset: 2
The size of multiset: 3

```

[标准:多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)的所有功能
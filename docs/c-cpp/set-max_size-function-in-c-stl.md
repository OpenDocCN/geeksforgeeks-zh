# 在 C++ STL 中设置 max_size()函数

> 原文:[https://www . geesforgeks . org/set-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/)

**set::max_size()** 是 C++ STL 中的一个内置函数，返回 set 容器可以容纳的最大元素数。

**语法:**

```cpp
set_name.max_size()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回集合容器可以容纳的最大元素数。

下面的程序说明了上面的功能:

T3】c++ T5

```cpp
// CPP program to demonstrate the
// set::max_size() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    set<int> s1, s2;

    s1.insert(1);

    // If set already contains elements
    cout << s1.max_size() << endl;

    // If set does not have elements
    cout << s2.max_size();

    return 0;
}
```

T6T8**输出:**T1

T12
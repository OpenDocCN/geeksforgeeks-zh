# c++ STL 中的 smatch max_size()函数

> 原文:[https://www . geesforgeks . org/smatch-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/smatch-max_size-function-in-c-stl/)

**smatch::max_size()** 是 C++ STL 中的内置函数，它返回 smatch 容器可以容纳的 match_results 对象中的最大元素数。

**语法:**

```cpp
smatch_name.max_size()
```

**参数:**此功能不接受任何参数。
**返回值:**这个函数返回 smatch 容器可以容纳的最大元素数量。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the 
// smatch::max_size() function in C++ STL
// when data-type is char 
#include <bits/stdc++.h>
using namespace std; 
int main()
{
    // match_results object(smatch)
    match_results<char*> match;

    cout << "max_size: " << 
    match.max_size() << endl;

    return 0;
}
```

**Output:**

```cpp
max_size: 768614336404564650

```

**程序 2:**

```cpp
// C++ program to illustrate the 
// smatch::max_size() function in C++ STL
// when data-type is int 
#include <bits/stdc++.h>
using namespace std; 
int main()
{
    // match_results object(smatch)
    match_results<int*> match;

    cout << "max_size: " << 
    match.max_size() << endl;

    return 0;
}
```

**Output:**

```cpp
max_size: 768614336404564650

```
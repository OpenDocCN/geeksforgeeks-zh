# c++ STL 中无序 _ 映射为空

> 原文:[https://www.geeksforgeeks.org/unordered_map-empty-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-empty-in-c-stl/)

**无序 _map::empty()** 功能用于检查容器大小是否为零。如果容器大小为零，则返回真，否则返回假。
**语法:**

```cpp
 unordered_map_name.empty()

```

**参数:**此函数不接受任何参数
**返回类型:**此函数返回布尔值 TRUE 或 FALSE。

**示例:**

> **输入:** ump = { {1，2}、{3，4}、{5，6}、{7，8 } }
> UMP . empty()；
> **输出:**假
> 
> **输入:**UMP = { }；
> UMP . empty()；
> **输出:**真

```cpp
// CPP program to illustrate
// Implementation of unordered_map empty() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two unordered_map
    unordered_map<int, int> ump1, ump2;

    // Inserting values
    ump1[1] = 2;
    ump1[3] = 4;
    ump1[5] = 6;
    ump1[7] = 8;

    // Print the size of container
    cout << "ump1 size = " << ump1.size() << endl;
    cout << "ump2 size = " << ump2.size() << endl;

    // Running the function for ump1
    if (ump1.empty())
        cout << "True\n";
    else
        cout << "False\n";

    // Running the function for ump2
    if (ump2.empty())
        cout << "True\n";
    else
        cout << "False\n";

    // Running the function for ump1 after
    // clearing it
    ump1.clear();
    if (ump1.empty())
        cout << "True\n";
    else
        cout << "False\n";

    return 0;
}
```

**Output:**

```cpp
ump1 size = 4
ump2 size = 0
False
True
True

```
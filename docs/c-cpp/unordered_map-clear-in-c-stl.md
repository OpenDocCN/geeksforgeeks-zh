# c++ STL 中无序 _ 映射清晰

> 原文:[https://www.geeksforgeeks.org/unordered_map-clear-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-clear-in-c-stl/)

**无序 _map::clear()** 函数用于从容器中移除所有元素。当此函数应用于无序映射时，其大小为零。
**语法:**

```cpp
 unordered_map_name.clear()

```

**参数:**此函数不接受任何参数
**返回类型:**此函数不返回任何内容。

**示例:**

> **输入:** ump = { {1，2}、{3，4}、{5，6}、{7，8 } }
> UMP . clear()；
> **输出:**UMP = { }；

```cpp
// CPP program to illustrate
// Implementation of unordered_map clear() function
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
    cout << "Unordered_map size before calling clear function: \n";
    cout << "ump1 size = " << ump1.size() << endl;
    cout << "ump2 size = " << ump2.size() << endl;

    // Deleting the  elements
    ump1.clear();
    ump2.clear();

    // Print the size of container
    cout << "Unordered_map size after calling clear function: \n";
    cout << "ump1 size = " << ump1.size() << endl;
    cout << "ump2 size = " << ump2.size() << endl;

    return 0;
}
```

**Output:**

```cpp
Unordered_map size before calling clear function: 
ump1 size = 4
ump2 size = 0
Unordered_map size after calling clear function: 
ump1 size = 0
ump2 size = 0

```

**是什么应用？**
clear 用于我们希望删除旧元素并从新开始时，尤其是在循环中。我们可以通过创建新的地图来实现相同的功能，但是清除相同的地图在性能上更好，因为我们不必创建新的对象。
# 在 C++ STL 中设置::size()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/setsize-c-STL/

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是按照特定顺序存储唯一元素的容器。在内部，集合中的元素总是*排序的*。集合通常被实现为*二分搜索法树*。

**set::size()**
**size()**函数用于返回 set 容器的大小或 set 容器中的元素数量。

**语法:**

```cpp
set_name.size()

```

**返回值:**返回集合容器中的元素个数。

**示例:**

```cpp
Input  : set1{'a', 'b', 'c', 'd'};
         set1.size();
Output : 4

Input  : set2{};
 set2.size();
Output : 0

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// C++ program to illustrate
// size() function on set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two sets
    set<char> set1, set2;
    for (int i = 0; i < 4; i++) {
        set1.insert('a' + i);
    }

    // Printing the size of sets
    cout << "set1 size: " << set1.size();
    cout << endl;
    cout << "set2 size: " << set2.size();
    return 0;
}
```

输出:

```cpp
set1 size: 4
set2 size: 0

```

**时间复杂度:**常数
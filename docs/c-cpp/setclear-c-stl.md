# 设置::在 C++ STL 中清除

> 哎哎哎:# t0]https://www . geeksforgeeks . org/setlear-c-STL/

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**set::clear()**

clear()函数用于移除 set 容器的所有元素，从而使其大小为 0。

**语法:**

```cpp
*setname*.clear()
Parameters :
No parameters are passed.
Result :
All the elements of the set are
removed ( or destroyed )
```

示例:

```cpp
Input  : set{1, 2, 3, 4, 5};
         set.clear();
Output : set{}

Input  : set{};
         set.clear();
Output : set{}

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// INTEGER SET
// CPP program to illustrate
// Implementation of clear() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    set<int> myset{ 1, 2, 3, 4, 5 };

    myset.clear();
    // Set becomes empty

    // Printing the Set
    for (auto it = myset.begin();
         it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
*No Output*

```

```cpp
// CHARACTER SET
// CPP program to illustrate
// Implementation of clear() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    set<char> myset{ 'A', 'b', 'd', 'e' };

    myset.clear();
    // Set becomes empty

    // Printing the Set
    for (auto it = myset.begin();
         it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
*No Output*

```

**时间复杂度:**线性即 O(n)
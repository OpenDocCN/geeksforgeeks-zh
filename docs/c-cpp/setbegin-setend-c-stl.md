# 在 C++ STL 中设置::begin()和设置::end()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/setbegin-setenv-c-STL/

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**set::begin()**

begin()函数用于返回指向 set 容器第一个元素的迭代器。begin()函数**返回一个双向迭代器**到容器的第一个元素。
**语法:**

```cpp
***setname***.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.
```

示例:

```cpp
Input  : myset{1, 2, 3, 4, 5};
         myset.begin();
Output : *returns an iterator to the element 1*

Input  : myset{8, 7};
         myset.end();
Output : *returns an iterator to past-the-end element.* 
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER SET EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // declaration of set container
    set<int> myset{ 1, 2, 3, 4, 5 };

    // using begin() to print set
    for (auto it = myset.begin(); it !=
                             myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CHARACTER SET EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // declaration of set container
    set<char> myset{ 'a', 'c', 'g', 'z' };

    // using begin() to print set
    for (auto it = myset.begin(); it !=
                           myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
a c g z 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// STRING SET EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <set>
#include <string>
using namespace std;

int main()
{
    // declaration of set container
    set<string> myset{ "This", "is",
                            "Geeksforgeeks" };

    // using begin() to print set
    for (auto it = myset.begin(); it !=
                               myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
Geeksforgeeks This is 
```

**时间复杂度:** O(1)

**set::end()**

它返回一个迭代器，指向集合容器的最后一个元素。因为它没有引用有效的元素，所以它不能取消引用 end()函数返回双向迭代器。
**语法:**

```cpp
***setname***.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to next of the last element.
```

示例:

```cpp
Input  : myset{1, 2, 3, 4, 5};
         myset.end();
Output : *returns an iterator to next of 5*
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER Example
// CPP program to illustrate
// Implementation of end() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // declaration of set container
    set<int> myset{ 1, 2, 3, 4, 5 };

    // using end() to print set
    for (auto it = myset.begin(); it !=
                          myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CHARACTER SET EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // declaration of set container
    set<char> myset{'a', 'c', 'g', 'z'};

    // using begin() to print set
    for (auto it=myset.begin(); it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
a c g z
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// STRING SET EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <set>
#include <string>
using namespace std;

int main()
{
    // declaration of set container
    set<string> myset{ "This", "is",
                             "Geeksforgeeks" };

    // using begin() to print set
    for (auto it = myset.begin(); it !=
                                myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
Geeksforgeeks This is 
```

**时间复杂度:** O(1)
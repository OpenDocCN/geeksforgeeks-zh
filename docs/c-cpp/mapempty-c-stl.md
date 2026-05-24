# 映射::空()在 C++ STL 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/mapmpty-c-STL/

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**map::empty()**

empty()函数用于检查地图容器是否为空。

**语法:**

```cpp
*mapname*.empty()
Parameters :
No parameters are passed.
Returns :
True, if map is empty
False, Otherwise

```

示例:

```cpp
Input  : map 
         mymap['a']=10;
         mymap['b']=20;
         mymap.empty();
Output : False

Input  : map 
         mymap.empty();
Output : True

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// Non Empty map example
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <map>
using namespace std;

int main()
{
    map<char, int> mymap;
    mymap['a'] = 1;
    mymap['b'] = 2;
    if (mymap.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
False
```

```cpp
// Empty map example
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <map>
using namespace std;

int main()
{
    map<char, int> mymap;
    if (mymap.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
True
```

**时间复杂度:** O(1)
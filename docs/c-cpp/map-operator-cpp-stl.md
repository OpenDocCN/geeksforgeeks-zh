# 映射::C++ STL 中的运算符[]

> 原文:[https://www.geeksforgeeks.org/map-operator-cpp-stl/](https://www.geeksforgeeks.org/map-operator-cpp-stl/)

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**map::operator[]**

该运算符用于引用位于运算符内部给定位置的元素。它类似于 at()函数，唯一的区别是 at()函数在位置不在地图大小的边界内时抛出一个超出范围的异常，而这个运算符会导致未定义的行为。
**语法:**

```cpp
***mapname[key]***
Parameters :
Key value mapped to the element to be fetched.
Returns :
Direct reference to the element at the given key value.
```

示例:

```cpp
Input  :  map mymap;
          mymap['a'] = 1;
          mymap['a'];
Output :  1

Input  :  map mymap;
          mymap["abcd"] = 7;
          mymap["abcd"];
Output :  7
```

**错误和异常**
1。如果该键不在地图中，它将显示未定义的行为。
2。否则它有一个无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of [] operator
#include <map>
#include <iostream>
#include<string>
using namespace std;

int main()
{
    // map declaration
    map<int,string> mymap;

    // mapping integers to strings
    mymap[1] = "Hi";
    mymap[2] = "This";
    mymap[3] = "is";
    mymap[4] = "GeeksForGeeks";

    // using operator[] to print string
    // mapped to integer 4
    cout << mymap[4];
    return 0;
}
```

输出:

```cpp
GeeksForGeeks
```

**时间复杂度:** O(logn)
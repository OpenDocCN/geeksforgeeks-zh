# 映射::at()在 C++ STL 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/mapat-c-STL/

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**map::at()**

at()函数用于引用映射到作为函数参数给出的键值的元素。例如，如果我们将字符串“hi”映射到整数 1，那么将整数 1 作为 at()函数的参数传递将返回字符串“hi”。

**at()函数与运算符[]**
at()函数检查容器的范围有何不同，当我们试图访问不在范围内的元素时，**抛出异常**，而运算符[]不检查容器的范围，当访问不在范围内的元素时，显示**未定义行为**。

**语法:**

```cpp
***mapname.at(key)***
Parameters :
Key value mapped to the element to be fetched.
Returns :
Direct reference to the element at the given key value.
```

示例:

```cpp
Input  :  map mymap;
          mymap['a'] = 1;
          mymap.at('a');
Output :  1

Input  :  map mymap;
          mymap["abcd"] = 7;
          mymap.at("abcd");
Output :  7
```

**错误和异常**
1。如果该键不在地图中，则抛出**超出范围。**
2。否则，它具有很强的无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of at() function
#include <iostream>
#include <map>
#include <string>
using namespace std;

int main()
{
    // map declaration
    map<string, int> mymap;

    // mapping strings to integers
    mymap["hi"] = 1;
    mymap["welcome"] = 2;
    mymap["thanks"] = 3;
    mymap["bye"] = 4;

    // printing the integer mapped
    // by string "thanks"
    cout << mymap.at("thanks");
    return 0;
}
```

输出:

```cpp
3
```

**时间复杂度:** O(logn)

**at()函数与运算符[]**
at()函数检查容器的范围有何不同，当我们试图访问不在范围内的元素时，**抛出异常**，而运算符[]不检查容器的范围，当访问不在范围内的元素时，显示**未定义行为**。
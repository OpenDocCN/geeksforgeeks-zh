# 映射::C++ STL 中的 begin()和 end()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/mapbegin-end-c-STL/

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**map::begin()**

begin()函数用于返回指向 map 容器第一个元素的迭代器。begin()函数向容器的第一个元素返回一个双向迭代器。

**语法:**

```cpp
*mapname*.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.

```

示例:

```cpp
Input  : mymap['a'] = 1;
         mymap['b'] = 2;
         mymap['c'] = 3;
         mymap.begin();
Output : *returns an iterator to the element 'a' = 1*

Input  : mymap['d'] = 1;
         mymap.begin();
Output : *returns an iterator to the element 'd' = 1*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// Demonstrates begin() and end()
#include <iostream>
#include <map>
using namespace std;

int main()
{
    // declaration of map container
    map<char, int> mymap;
    mymap['a'] = 1;
    mymap['b'] = 2;
    mymap['c'] = 3;

    // using begin() to print map
    for (auto it = mymap.begin();
         it != mymap.end(); ++ it)
        cout << it->first << " = "
             << it->second << '\n';
    return 0;
}
```

输出:

```cpp
a = 1
b = 2
c = 3
```

**map::end()**

end()函数用于返回一个迭代器，指向 map 容器的最后一个元素。因为它没有引用有效的元素，所以它不能取消引用 end()函数返回双向迭代器。

**语法:**

```cpp
*mapname*.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the next of last element.

```

示例:

```cpp
Input  : mymap['a'] = 1;
         mymap['b'] = 2;
         mymap['c'] = 3;
         mymap.end();
Output : *returns an iterator to next to c 
(after last element)*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Demonstrates begin() and end() 
#include <iostream>
#include <map>
using namespace std;

int main()
{
    // declaration of map container
    map<char, int> mymap;
    mymap['a'] = 1;
    mymap['b'] = 2;
    mymap['c'] = 3;

    // using begin() to print map
    for (auto it = mymap.begin();
         it != mymap.end(); ++ it)
        cout << it->first << " = "
             << it->second << '\n';
    return 0;
}
```

输出:

```cpp
a = 1
b = 2
c = 3
```
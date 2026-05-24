# multimap::operator=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/multimapoperator-c-stl/](https://www.geeksforgeeks.org/multimapoperator-c-stl/)

multimap::operator=用于通过替换现有内容向容器分配新内容。它还根据新内容修改大小。

语法:-

```cpp
multimap1 = (multimap2)

Parameters :
Another container of the same type.

Result :
Assign the contents of the container passed as 
parameter to the container written on left 
side of the operator.

```

示例:

```cpp
Input  :  multimap1 = { ('a', 1), ('b', 2), ('c', 3)}
          multimap2 = { ('d', 4), ('e', 5), ('f', 6)}
          multimap1 = multimap2;
Output :  multimap1 
d 4
e 5
f 6

Input  :  multimap1 = { ('abc', 1), ('bca', 2), ('cab', 3)}
          multimap2 = { ('def', 4), ('efd', 5), ('fde', 6)}
          multimap1 = multimap2;
Output :  multimap1 
def 4
efd 5
fde 6

```

错误和异常

1.如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP Program to illustrate working of
// multimap::operator= 
#include <iostream>
#include <map>
using namespace std;

int main()
{
    // initialise multimap
    multimap<char, int> m1;
    multimap<char, int> m2;

    // iterator for iterate all element of multimap
    multimap<char, int>::iterator iter;

    // multimap1 data
    m1.insert(make_pair('a', 1));
    m1.insert(make_pair('b', 2));
    m1.insert(make_pair('c', 3));

    // multimap2 data
    m2.insert(make_pair('d', 4));
    m2.insert(make_pair('e', 5));
    m2.insert(make_pair('f', 6));

    // operator=
    m1 = m2;

    // multimap1 data
    cout << "MultiMap 1 data" << "\n";
    for (iter = m1.begin(); iter != m1.end(); iter++)
        cout << (*iter).first << " " << (*iter).second << "\n";
}
```

**输出:-**

```cpp
MultiMap 1 data
d 4
e 5
f 6

```
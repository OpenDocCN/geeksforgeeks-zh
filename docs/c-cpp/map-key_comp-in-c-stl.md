# 在 C++ STL 中映射 key_comp()

> 原文:[https://www.geeksforgeeks.org/map-key_comp-in-c-stl/](https://www.geeksforgeeks.org/map-key_comp-in-c-stl/)

**std::map::key_comp()** 是 C++ STL 中的一个内置函数，它返回容器使用的比较对象的副本。默认情况下，这是一个 less 对象，返回与运算符“<”相同的值。它是一个函数指针或函数对象，接受两个与容器元素类型相同的参数，如果第一个参数被认为在它定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。如果 key_comp 反身返回 false(即，无论键作为参数传递的顺序如何)，则两个键被认为是等效的。

**语法:**

```cpp
key_compare map_name.key_comp();
```

**参数:**此功能不接受任何参数。

**返回值:**函数返回容器使用的比较对象的副本。

以下示例说明了 map::key_comp()方法:

**程序 1:**

```cpp
// C++ program to illustrate the
// map::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a map named m;
    map<char, int> m;

    map<char, int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into map
    m['a'] = 10;
    m['b'] = 20;
    m['c'] = 30;
    m['d'] = 40;

    cout << "Map has the elements\n";

    // Store key value of last element
    char l = m.rbegin()->first;

    // initializing the iterator
    map<char, int>::iterator it = m.begin();

    // printing elements of all map
    do {

        cout << it->first
             << " => "
             << it->second
             << '\n';
    } while (comp((*it++).first, l));

    return 0;
}
```

**Output:**

```cpp
Map has the elements
a => 10
b => 20
c => 30
d => 40

```

**程序 2:**

```cpp
// C++ program to illustrate the
// map::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a map named m;
    map<char, int> m;

    map<char, int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into map
    m['a'] = 1;
    m['b'] = 2;
    m['c'] = 3;
    m['d'] = 4;

    cout << "Map has the elements\n";

    // Store key value of last element
    char l = m.rbegin()->first;

    // initializing the iterator
    map<char, int>::iterator it = m.begin();

    // printing elements of all map
    do {

        cout << it->first
             << " => "
             << it->second
             << '\n';
    } while (comp((*it++).first, l));

    return 0;
}
```

**Output:**

```cpp
Map has the elements
a => 1
b => 2
c => 3
d => 4

```
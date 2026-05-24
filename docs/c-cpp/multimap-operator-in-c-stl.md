# 多映射运算符=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/multimap-operator-in-c-stl/](https://www.geeksforgeeks.org/multimap-operator-in-c-stl/)

**multimap::operator=** 是一个内置的 C++ STL，它为容器分配新的内容，替换其当前内容。

**语法:**

```cpp
multimap1_name = multimap2_name
```

**参数:**左边的多 map 是通过销毁多 map1 的元素来分配右边多 map 的容器。

**返回值:**这个函数不返回任何东西。

```cpp
// C++ program for illustration of
// multimap::operator= function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp, copymp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 2, 60 });
    mp.insert({ 2, 20 });
    mp.insert({ 1, 50 });
    mp.insert({ 4, 50 });

    // = operator is used to copy map
    copymp = mp;

    // prints the elements
    cout << "\nThe multimap mp1 is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << "\nThe multimap copymap is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = copymp.begin(); itr != copymp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:**

```cpp
The multimap mp1 is : 
KEY    ELEMENT
1    40
1    50
2    30
2    60
2    20
4    50

The multimap copymap is : 
KEY    ELEMENT
1    40
1    50
2    30
2    60
2    20
4    50

```
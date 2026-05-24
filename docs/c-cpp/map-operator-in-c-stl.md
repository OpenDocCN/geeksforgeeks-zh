# 映射运算符=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/map-operator-in-c-stl/](https://www.geeksforgeeks.org/map-operator-in-c-stl/)

**映射::operator=** 是 C++ STL 中的一个内置函数，它将容器的内容分配给不同的容器，替换其当前内容。

**语法:**

```cpp
map1_name = map2_name
```

**参数:**左边的地图是容器，右边的地图是通过破坏 map1 的元素来赋值的。

**返回值:**这个函数不返回任何东西。

```cpp
// C++ program for illustration of
// map::operator= function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp, copymp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 4, 50 });

    // = operator is used to copy map
    copymp = mp;

    // prints the elements
    cout << "\nThe map mp is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << "\nThe map copymap is : \n";
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
The map mp is : 
KEY    ELEMENT
1    40
2    30
4    50

The map copymap is : 
KEY    ELEMENT
1    40
2    30
4    50

```
# map::cbegin() 和 map::cend() 函数介绍

> 原文: [https://www.geeksforgeeks.org/map-cbegin-and-cend-function-in-c-stl/](https://www.geeksforgeeks.org/map-cbegin-and-cend-function-in-c-stl/)

## map::cbegin() 函数介绍

`map::cbegin()` 是 C++ STL 中的一个内置函数，它返回一个指向映射容器中第一个元素的常量迭代器。由于映射容器中的元素是有序存储的，`cbegin()` 将指向根据容器排序准则排在第一位的元素。

### 语法

```cpp
map_name.cbegin()
```

### 参数

该函数不接受任何参数。

### 返回值

该函数返回一个常量迭代器，引用映射容器中的第一个元素。

### 示例代码

```cpp
// C++ program to illustrate
// the map::cbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 4, 20 });
    mp.insert({ 5, 50 });

    auto ite = mp.cbegin();

    cout << "The first element is: ";
    cout << "{" << ite->first << ", "
         << ite->second << "}\n";

    // prints the elements
    cout << "\nThe map is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.cbegin(); itr != mp.cend(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

### 输出

```cpp
The first element is: {1, 40}

The map is : 
KEY    ELEMENT
1    40
2    30
3    60
4    20
5    50
```
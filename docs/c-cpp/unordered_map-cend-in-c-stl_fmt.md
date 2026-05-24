# C++ STL 中的 unordered_map::cend()

> 原文：[https://www.geeksforgeeks.org/unordered_map-cend-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-cend-in-c-stl/)

`unordered_map::cend()` 是 C++ STL 中的一个内置函数，它返回一个指向容器（或其某个桶）中“尾后”位置的迭代器。在 `unordered_map` 对象中，不能保证哪个特定元素被认为是它的第一个元素。但是容器中的所有元素都会被遍历，因为从它的开始到结束的范围是有效的。

这个函数有两种变体。

## 语法

```cpp
unordered_map.cend()
```

## 参数

此函数不接受任何参数。

## 返回类型

此函数返回一个指向容器末尾元素的迭代器。

## 示例

```cpp
// CPP program to illustrate
// unordered_map cend()
#include <bits/stdc++.h>
using namespace std;

int main()
{

unordered_map<int, int> ump;

// inserting data into unordered_map
    ump[1] = 2;
    ump[3] = 4;
    ump[5] = 6;

// here 'it' can not be modified
    for (auto it = ump.cbegin(); it != ump.cend(); ++ it)
        cout << it->first << " " << it->second << endl;
    return 0;
}
```

## 输出

```cpp
5 6
1 2
3 4
```
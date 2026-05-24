# 在 C++ STL 中设置 crbegin()和 crend()函数

> 原文:[https://www . geesforgeks . org/set-crbegin-and-crend-function-in-c-STL/](https://www.geeksforgeeks.org/set-crbegin-and-crend-function-in-c-stl/)

**set::crbegin()** 是 C++ STL 中的一个内置函数，它返回一个指向容器中最后一个元素的常量迭代器。迭代器不能用于修改集合容器中的元素。迭代器可以相应地增加或减少来遍历集合。
**语法:**

```cpp
constant_iterator set_name.crbegin()
```

**参数:**函数不取任何参数。
**返回值:**函数返回指向容器中最后一个元素的常量迭代器。
演示 set::crbegin()方法的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// set::crbegin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 12, 15, 11, 10 };

    // initializes the set from an array
    set<int> s(arr, arr + 5);

    // prints all elements in set
    for (auto it = s.crbegin(); it != s.crend(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
15 14 12 11 10
```
# c++ STL 中的无序 _ 多集 insert()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-insert-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-insert-in-c-stl/)

无序多集::insert()是 C++ STL 中的一个内置函数，它在无序多集中插入新元素。这增加了容器的尺寸。另请注意，具有相同值的元素也会随着插入次数的增加而存储。
**语法:**

```cpp
Unordered_multiset_name.insert(element)
```

**参数:**该功能接受单个参数*元素*。它指定要插入容器的元素。
**返回值:**该函数向新插入的元素返回一个迭代器。
以下程序说明上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// unordered_multiset::insert
#include <array>
#include <iostream>
#include <string>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_multiset<string> ums = { "apple", "orange", "banana" };
    array<string, 3> arr = { "cherry", "mango", "apple"};
    string str = "grapes";

    ums.insert(str); // copy insertion
    ums.insert(arr.begin(), arr.end()); // range insertion
    ums.insert({ "pineapple", "papaya" }); // initializer list insertion

    cout << "ums contains:";
    for (const string& x : ums)
        cout << " " << x;
    cout << endl;

    return 0;
}
```

**Output**

```cpp
ums contains: papaya pineapple mango cherry grapes banana apple apple orange

```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// unordered_multiset::insert
#include <array>
#include <iostream>
#include <string>
#include <unordered_set>
#include <vector>
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_multiset<int> ums = {2, 4, 6};
    vector<int> x;
    x.push_back(3);
    x.push_back(9);
      x.push_back(4);
    int val = 5;

    ums.insert(val); // copy insertion
    ums.insert(x.begin(), x.end()); // range insertion
    ums.insert({ 7, 8 }); // initializer list insertion

    cout << "ums contains:";
    for (const int& x : ums)
        cout << " " << x;
    cout << endl;

    return 0;
}
```

**Output**

```cpp
ums contains: 8 7 9 3 2 4 4 6 5

```
# 在 C++ 中使用 STL 删除字符串中所有连续的重复项

> 原文:[https://www . geesforgeks . org/从字符串中删除所有连续重复项-使用-stl-in-c/](https://www.geeksforgeeks.org/remove-all-consecutive-duplicates-from-the-string-using-stl-in-c/)

给定一个字符串 S，用 C++ 中的 STL 删除这个字符串中所有连续的重复项

**示例:**

```cpp
Input: Geeks for geeks
Output: Geks for geks

Input: aaaaabbbbbb
Output: ab

```

**方法:**
可以使用 STL 中提供的 [unique()](https://www.geeksforgeeks.org/stdunique-in-cpp/) 函数删除字符串的连续副本。

下面是上述方法的实现。

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "Geeksforgeeks is best";

    // Using unique() method
    auto res = unique(str.begin(), str.end());

    cout << string(str.begin(), res)
         << endl;
}
```

**Output:**

```cpp
Geksforgeks is best

```
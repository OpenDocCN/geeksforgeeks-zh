# 在 C++ 中使用 STL 删除字符串中的重复项

> 原文:[https://www . geesforgeks . org/remove-duplicates-from-a-string-use-STL-in-c/](https://www.geeksforgeeks.org/remove-duplicates-from-a-string-using-stl-in-c/)

给定一个字符串 S，用 C++ 中的 STL 删除这个字符串中的重复项

**示例:**

```cpp
Input: Geeks for geeks
Output: Gefgkors

Input: aaaaabbbbbb
Output: ab

```

**方法:**
可以使用 STL 中提供的 [unique()](https://www.geeksforgeeks.org/stdunique-in-cpp/) 功能删除字符串的连续副本。

下面是上述方法的实现。

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "aaaaabbbbbb";
    sort(str.begin(), str.end());

    // Using unique() method
    auto res = unique(str.begin(), str.end());

    cout << string(str.begin(), res)
         << endl;
}
```

**Output:**

```cpp
ab

```
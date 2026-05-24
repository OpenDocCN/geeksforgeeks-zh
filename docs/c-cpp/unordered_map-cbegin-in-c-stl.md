# c++ STL 中的无序 _ 映射 CBE gin

> 原文:[https://www . geesforgeks . org/unordered _ map-CBE gin-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-cbegin-in-c-stl/)

**c++ 中的 cbegin** 函数用于返回指向无序映射中第一个元素的常量迭代器。

**语法:**

```cpp
unordered_map.cbegin()
```

**参数**:取可选参数 *N* 。如果设置了，返回的迭代器将指向桶的第一个元素，否则将指向容器的第一个元素。

**返回值**:指向无序映射第一个元素的常量迭代器。

以下程序说明了 **cbegin** 功能的工作原理:

```cpp
// CPP program to demonstrate implementation of
// cbegin function in unordered_map
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_map<string, int> mp;

    // Adding some elements in the unordered_map
    mp["g"] = 1;
    mp["e"] = 2;
    mp["k"] = 4;
    mp["s"] = 5;

    cout << "Contents of the unordered_map :\n";
    for (auto it = mp.cbegin(); it != mp.cend(); it++)
        cout << it->first << "==>>"
             << it->second << "\n";
}
```

**Output:**

```cpp
Contents of the unordered_map :
s==>>5
k==>>4
g==>>1
e==>>2

```

函数的作用是:返回一个常量迭代器。如果我们试图改变值，我们会得到编译器错误。

```cpp
// CPP program to demonstrate implementation of
// cbegin function in unordered_map
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_map<string, int> mp;

    // Adding some elements in the unordered_map
    mp["g"] = 1;
    mp["e"] = 2;
    mp["k"] = 4;
    mp["s"] = 5;

    cout << "Contents of the unordered_map :\n";
    for (auto it = mp.cbegin(); it != mp.cend(); it++)
        it->second = 10; // This would cause compiler error
}
```

输出:

```cpp

prog.cpp: In function 'int main()':
prog.cpp:18:20: error: assignment of member 'std::pair, int>::second' in read-only object
         it->second = 10; // This would cause compiler error
                    ^ 
```

**时间复杂度:** O(1)平均。
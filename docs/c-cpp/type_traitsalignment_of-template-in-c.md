# c++ 中模板的类型 _ 特征::对齐 _ 方式

> 原文:[https://www . geeksforgeeks . org/type _ traitalignment _ of-template-in-c/](https://www.geeksforgeeks.org/type_traitsalignment_of-template-in-c/)

它用于查找等于类型 T 的对齐要求的成员常数值。如果 T 是引用类型，它将返回引用类型的对齐要求。如果 T 是数组类型，则返回元素类型的对齐要求。
**头文件:**

```cpp
#include<type_traits>
```

**语法:**

```cpp
template
  <class T>
  struct alignment_of;
```

**参数:**模板**标准::**的 alignment _ 接受单个参数 T(性状类)。
以下程序说明了 C++ STL 中模板的**标准::对齐方式:
**程序 1:**** 

## CPP14

```cpp
// C++ program to illustrate
// assignment_of template

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

class GFG {
};

// main method
int main()
{
    cout << alignment_of<GFG>::value << endl;
    cout << alignment_of<int>() << endl;
    cout << alignment_of<double>() << endl;

    return 0;
}
```

**Output:** 

```cpp
1
4
8
```
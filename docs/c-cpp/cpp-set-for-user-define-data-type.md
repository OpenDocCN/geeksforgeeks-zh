# 为用户定义的数据类型设置的 C++ 代码

> 原文:[https://www . geesforgeks . org/CPP-set-for-user-define-data-type/](https://www.geeksforgeeks.org/cpp-set-for-user-define-data-type/)

[C++ STL 集](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种用于以升序或降序存储不同值的数据结构。默认情况下，我们只能用它来存储系统定义的数据类型(例如 int、float、double、pair 等)。).

如果我们想将用户定义的数据类型存储在一个集合中(例如结构)，那么编译器会显示一条错误消息。这是因为集合的属性，集合中保存的值必须是升序或降序。这样做的时候，编译器不能比较两个结构(因为它们是用户定义的)，这就是为什么编译器向我们显示错误消息的原因。
所以，为了在集合中存储一个结构，需要设计一些比较函数 s。这方面的执行情况如下:

示例:

```cpp
Input  : 110 102 101 115
Output : 101 102 110 115

```

**解释:**
这里我们向集合中插入一个随机列表，当我们输出集合时，列表会根据我们所做的比较函数按升序排序。

```cpp
Input  : 3  2  34   0 76 
Output : 0  2   3  34 76

```

```cpp
// CPP implementation to use 
// user-defined data type in
// structures
#include<bits/stdc++.h>
using namespace std;

// Structure definition
struct Test {
    int id;

    // This function is used by set to order
    // elements of Test.
    bool operator<(const Test& t) const
    {
        return (this->id < t.id);
    }
};

// Driver method
int main()
{
    // put values in each 
    // structure define below.
    Test t1 = { 110 }, t2 = { 102 }, 
         t3 = { 101 }, t4 = { 115 };

    // define a set having 
    // structure as its elements.
    set<struct Test> s; 

    // insert structure in set
    s.insert(t1); 
    s.insert(t2);
    s.insert(t3);
    s.insert(t4);

    // define an iterator to iterate the whole set.
    set<struct Test>::iterator it; 

    for (it = s.begin(); it != s.end(); it++)
    {
        // print in ascending order as required.
        cout << (*it).id << endl; 
    }

    return 0;
}
```

**输出:**

```cpp
101
102
110
115

```

**应用:**
a)在按排序顺序打印所有不同结构时非常有用。
b)在已排序的结构列表中插入新结构。
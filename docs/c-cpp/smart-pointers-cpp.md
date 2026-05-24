# c++ 中的智能指针以及如何使用它们

> 原文:[https://www.geeksforgeeks.org/smart-pointers-cpp/](https://www.geeksforgeeks.org/smart-pointers-cpp/)

在本文中，我们将讨论 C++ 中的智能指针。什么是智能指针，为什么，以及如何正确使用它们？

指针用于访问程序外部的资源，比如堆内存。因此，为了访问堆内存(如果在堆内存中创建了任何东西)，使用指针。当访问任何外部资源时，我们只使用资源的副本。如果我们对它进行任何更改，我们只需在复制的版本中进行更改。但是，如果我们使用指向资源的指针，我们将能够更改原始资源。

## 普通指针的问题

看看下面的代码。

## C++

```cpp
#include <iostream>
using namespace std;

class Rectangle {
private:
    int length;
    int breadth;
};

void fun()
{
    // By taking a pointer p and
    // dynamically creating object
    // of class rectangle
    Rectangle* p = new Rectangle();
}

int main()
{
    // Infinite Loop
    while (1) {
        fun();
    }
}
```
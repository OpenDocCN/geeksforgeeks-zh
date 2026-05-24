# c++ 中左值引用和右值引用，示例

> 原文:[https://www . geesforgeks . org/lvalues-references-and-rvalues-references-in-c-with-examples/](https://www.geeksforgeeks.org/lvalues-references-and-rvalues-references-in-c-with-examples/)

**先决条件:**[c++ 中的左值和右值](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)、[c++ 中的引用](https://www.geeksforgeeks.org/references-in-c/)
**“l 值”**是指标识对象的内存位置。**“r 值”**是指存储在内存中某个地址的数据值。**c++ 中的引用**不过是已经存在的变量的替代。它们在变量名称前使用 **' & '** 来声明。

**示例:**

```cpp
int a = 10;

// Declaring lvalue reference
int& lref = a;

// Declaring rvalue reference
int&& rref = 20;
```

下面是左值和右值的实现:

## C++

```cpp
// C++ program to illustrate the
// lvalue and rvalue

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Declaring the variable
    int a{ 10 };

    // Declaring reference to
    // already created variable
    int& b = a;

    // Provision made to display
    // the boolean output in the
    // form of True and False
    // instead of 1 and
    cout << boolalpha;

    // Comparing the address of both the
    // variable and its reference and it
    // will turn out to be same
    cout << (&a == &b) << endl;
    return 0;
}
```

**Output:** 

```cpp
true
```
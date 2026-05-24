# c++ 增强库中的任何数据类型

> 原文:[https://www.geeksforgeeks.org/using-data-type/](https://www.geeksforgeeks.org/using-data-type/)

任何数据类型都用于在变量中存储任何类型的值。像 JavaScript、TypeScript 这样的脚本语言提供了任何数据类型的功能。
C++ 也提供了这个功能，但只是在 boost 库的帮助下。只要将变量的数据类型设为任意，就可以将任何类型的值赋给变量。以下是用任何数据类型声明变量所需的语法:
**语法:**

```cpp
boost::any variable_name;

```

**注意:**要使用 boost::any 数据类型，“boost/any.hpp”需要包含在程序中。

示例:

```cpp
boost::any x, y, z, a;
x = 12;
y = 'G';
z = string("GeeksForGeeks");
a = 12.75;

```

```cpp
// CPP Program to implement the boost/any library
#include "boost/any.hpp"
#include <bits/stdc++.h>
using namespace std;
int main()
{

    // declare any data type
    boost::any x, y, z, a;

    // give x is a integer value
    x = 12;

    // print the value of x
    cout << boost::any_cast<int>(x) << endl;

    // give y is a char
    y = 'G';

    // print the value of the y
    cout << boost::any_cast<char>(y) << endl;

    // give z a string
    z = string("GeeksForGeeks");

    // print the value of the z
    cout << boost::any_cast<string>(z) << endl;

    // give a  to double
    a = 12.75;

    // print the value of a
    cout << boost::any_cast<double>(a) << endl;

    // gives an error because it can't convert int to float
    try {
        boost::any b = 1;
        cout << boost::any_cast<float>(b) << endl;
    }
    catch (boost::bad_any_cast& e) {
        cout << "Exception Caught :  " << e.what() << endl;
        ;
    }

    return 0;
}
```

**Output:**

```cpp
12
G
GeeksForGeeks
12.75
Exception Caught :  boost::bad_any_cast: failed conversion using boost::any_cast

```

**参考:**T2】http://www.boost.org/doc/libs/1_66_0/doc/html/any.html
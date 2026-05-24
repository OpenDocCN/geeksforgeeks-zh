# type info::c++ 中的 bad_cast，带示例

> 原文:[https://www . geeksforgeeks . org/typeinfobad _ cast-in-c-with-examples/](https://www.geeksforgeeks.org/typeinfobad_cast-in-c-with-examples/)

标准 C++ 包含几个内置的异常类。 **typeinfo::bad_cast** 就是其中之一。这是动态转换失败时引发的异常。下面是相同的语法:

**头文件:**

```cpp
<typeinfo>

```

**语法:**

```cpp
class bad_cast;

```

**注意:**要使用 **std::bad_cast** ，应设置合适的试捕块。

**返回值:**不返回任何东西。

以下是以更好的方式理解 **std::bad_cast** 实现的例子:

**节目 1:**

```cpp
// C++ code for std::bad_cast
#include <bits/stdc++.h>
#include <typeinfo>

using namespace std;

// Base Class
class Base {
    virtual void member() {}
};

// Derived Class
class Derived : Base {
};

// main() method
int main()
{

    // try block
    try {
        Base gfg;
        Derived& rd
            = dynamic_cast<Derived&>(gfg);
    }

    // catch block to handle the errors
    catch (bad_cast& bc) {
        cerr << "bad_cast caught: "
             << bc.what() << endl;
    }

    return 0;
}
```

**输出:**

```cpp
bad_cast caught: std::bad_cast

```

**节目 2:**

```cpp
// C++ code for std::bad_cast
#include <bits/stdc++.h>
#include <typeinfo>

using namespace std;

// Base Class
class Base {
    virtual void member() {}
};

// Derived Class
class Derived : Base {
};

// main() method
int main()
{

    // try block
    try {
        Base geeksforgeeks;
        Derived& abc
            = dynamic_cast<Derived&>(
                geeksforgeeks);
    }

    // catch block to handle the errors
    catch (bad_cast& a) {
        cerr << "bad_cast caught: "
             << a.what() << endl;
    }

    return 0;
}
```

**输出:**

```cpp
bad_cast caught: std::bad_cast

```

**参考:**T2】http://www.cplusplus.com/reference/typeinfo/bad_cast/
# 异常::C++ 中的 bad_exception 附带示例

> 原文:[https://www . geesforgeks . org/exception bad _ exception-in-c-with-examples/](https://www.geeksforgeeks.org/exceptionbad_exception-in-c-with-examples/)

标准 C++ 包含几个内置的异常类，**异常::bad_exception** 就是其中之一。这是意外处理程序引发的异常。下面是相同的语法:

**头文件:**

```cpp
include<exception>

```

**语法:**

```cpp
class bad_exception;

```

**返回:****异常::bad_exception** 返回一个空终止字符，用于标识异常。

**注意:**要使用**异常::bad_exception** ，应该设置合适的试捕块。

以下是以更好的方式理解**异常的实现的例子::bad_exception** :

**程序 1 :**

```cpp
// C++ code for std::bad_exception
#include <bits/stdc++.h>

using namespace std;

void func()
{
    throw;
}

void geeksforgeeks() throw(bad_exception)
{
    throw runtime_error("test");
}

// main method
int main()
{
    set_unexpected(func);

    // try block
    try {
        geeksforgeeks();
    }

    // catch block to handle the errors
    catch (const bad_exception& gfg) {
        cout << "Caught exception "
             << gfg.what() << endl;
    }
    return 0;
}
```

**输出:**

```cpp
Caught exception std::bad_exception

```

**程序二:**

```cpp
// C++ code for std::bad_exception
#include <bits/stdc++.h>

using namespace std;

void gfg()
{
    throw;
}

void A_Computer_Science_Portal_For_Geeks()
     throw(bad_exception)
{
    throw runtime_error("test");
}

// main method
int main()
{
    set_unexpected(gfg);

    // try block
    try {
        A_Computer_Science_Portal_For_Geeks();
    }

    // catch block to handle the errors
    catch (const bad_exception& a) {
        cout << "Caught exception "
             << a.what() << endl;
    }
    return 0;
}
```

**输出:**

```cpp
Caught exception std::bad_exception

```

**参考:**T2】http://www.cplusplus.com/reference/exception/bad_exception/
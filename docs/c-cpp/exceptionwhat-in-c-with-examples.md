# 异常::C++ 中的 what()带示例

> 原文:[https://www . geesforgeks . org/exception what-in-c-with-examples/](https://www.geeksforgeeks.org/exceptionwhat-in-c-with-examples/)

**异常::what()** 用于获取标识异常的字符串。该函数返回一个空终止字符序列，可用于识别异常。下面是相同的语法:

**头文件:**

```cpp
#include<exception>

```

**语法:**

```cpp
virtual const char* what() const throw();

```

**返回:**函数 **std::what()** 返回一个空终止字符序列，用于识别异常。

**注意:**要利用 **std::what()** ，要设置合适的试捕块。

以下是以更好的方式理解 **std::what()** 实现的程序:

**程序 1:**

```cpp
// C++ code for exception::what()
#include <bits/stdc++.h>

using namespace std;

struct gfg : exception {
    const char* what() const noexcept
    {
        return "GeeksforGeeks!! "
               "A Computer Science"
               " Portal For Geeks";
    }
};

// main method
int main()
{

    // try block
    try {
        throw gfg();
    }

    // catch block to handle the errors
    catch (exception& gfg1) {
        cout << gfg1.what();
    }

    return 0;
}
```

**输出:**

```cpp
GeeksforGeeks!! A Computer Science Portal For Geeks

```

**程序二:**

```cpp
// C++ code for exception::what()

#include <bits/stdc++.h>

using namespace std;

struct geeksforgeeks : exception {
    const char* what() const noexcept
    {
        return "Hey!!";
    }
};

// main method
int main()
{

    // try block
    try {
        throw geeksforgeeks();
    }

    // catch block to handle the errors
    catch (exception& gfg) {
        cout << gfg.what();
    }

    return 0;
}
```

**输出:**

```cpp
Hey!!

```

**参考:**T2【http://www . cplusplus . com/Reference/exception/exception/what/
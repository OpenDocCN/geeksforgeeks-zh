# typeinfo::c++ 中的 bad_typeid，带示例

> 原文:[https://www . geesforgeks . org/typeinfobad _ type id-in-c-with-examples/](https://www.geeksforgeeks.org/typeinfobad_typeid-in-c-with-examples/)

标准 C++ 包含几个内置的异常类， **typeinfo::bad_typeid** 就是其中之一。这是对 null 指针的 typeid 引发的异常。下面是相同的语法:

**头文件:**

```cpp
<typeinfo>

```

**语法:**

```cpp
class bad_typeid;

```

**返回:****type info::bad _ typeid**返回一个空终止字符，用于标识异常。

**注意:**要使用 std::bad_typeid，应该设置适当的试捕块。

以下是以更好的方式理解 **typeinfo::bad_typeid** 实现的例子:

**程序 1:**

```cpp
// C++ code for std::bad_typeid
#include <bits/stdc++.h>

using namespace std;

struct gfg {
    virtual void func();
};

// main method
int main()
{
    gfg* g = nullptr;

    // try block
    try {
        cout << typeid(*g).name()
             << endl;
    }

    // catch block to handle the errors
    catch (const bad_typeid& fg) {
        cout << fg.what() << endl;
    }

    return 0;
}
```

**输出:**

```cpp
std::bad_typeid

```

**程序二:**

```cpp
// C++ code for std::bad_typeid
#include <bits/stdc++.h>

using namespace std;

struct geeksforgeeks {
    virtual void
    A_Computer_Science_Portal_For_Geeks();
};

// main method
int main()
{
    geeksforgeeks* gfg = nullptr;

    // try block
    try {
        cout << typeid(*gfg).name() << endl;
    }

    // catch block to handle the errors
    catch (const bad_typeid& fg) {
        cout << fg.what() << endl;
    }

    return 0;
}
```

**输出:**

```cpp
std::bad_typeid

```

**参考:**T2】http://www.cplusplus.com/reference/typeinfo/bad_typeid/
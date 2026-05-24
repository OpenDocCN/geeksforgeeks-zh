# 函数::C++ 中的 bad_function_call 附带示例

> 原文:[https://www . geesforgeks . org/function bad _ function _ call-in-c-with-examples/](https://www.geeksforgeeks.org/functionalbad_function_call-in-c-with-examples/)

标准 C++ 包含几个内置的异常类，**functional::bad _ function _ call**就是其中之一。这是在错误调用时引发的异常。下面是相同的语法:

**头文件:**

```cpp
include<functional>

```

**语法:**

```cpp
class bad_function_call;

```

**注意:**要使用**function::bad _ function _ call**，应该设置合适的试接球。

以下是以更好的方式理解**函数实现的程序::bad_function_call** :

**程序 1 :**

```cpp
// C++ code for functional::bad_function_call
#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    function<int()> gfg = nullptr;

    // try block
    try {
        gfg();
    }

    // catch block to handle the errors
    catch (const bad_function_call& geeksforgeeks) {
        cout << geeksforgeeks.what() << endl;
    }
    return 0;
}
```

**输出:**

```cpp
bad_function_call

```

**例 2 :**

```cpp
// C++ code for functional::bad_function_call
#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    function<int()> geeksforgeeks = nullptr;

    // try block
    try {
        geeksforgeeks();
    }

    // catch block to handle the errors
    catch (const bad_function_call& gfg) {
        cout << gfg.what() << endl;
    }
    return 0;
}
```

**输出:**

```cpp
bad_function_call

```

**参考:**T2【http://www . cplusplus . com/Reference/function/bad _ function _ call/
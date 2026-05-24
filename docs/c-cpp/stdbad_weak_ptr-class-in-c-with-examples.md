# std::bad_weak_ptr 类在 C++ 中有示例

> 原文:[https://www . geesforgeks . org/stdbad _ weak _ ptr-c-class-in-with-examples/](https://www.geeksforgeeks.org/stdbad_weak_ptr-class-in-c-with-examples/)

标准 C++ 包含几个内置的异常类， **std::bad_weak_ptr** 就是其中之一。 **std::bad_weak_ptr** 是 **shared_ptr** 的构造函数以 weak_ptr 为参数抛出异常的对象类型，此时 **weak_ptr** 引用的是已经删除的对象。下面是相同的语法:

**头文件:**

```cpp
<memory>

```

**语法:**

```cpp
class bad_weak_ptr: public exception;

```

**注意:**要使用 **std::bad_weak_ptr** ，应设置合适的试接球。

以下是以更好的方式理解 **std::bad_weak_ptr** 实现的程序:

**程序 1 :**

```cpp
// C++ code for std::bad_weak_ptr

#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    shared_ptr<int> gfg1(new int(75));

    weak_ptr<int> wp(gfg1);
    gfg1.reset();

    // try block
    try {
        shared_ptr<int> gfg2(wp);
    }

    // catch block to handle the errors
    catch (const bad_weak_ptr& gfg) {
        cout << gfg.what() << endl;
    }
    return 0;
}
```

**输出:**

```cpp
bad_weak_ptr

```

**程序二:**

```cpp
// C++ code for std::bad_weak_ptr

#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    shared_ptr<int> geeksforgeeks(new int(75));

    weak_ptr<int> wp(geeksforgeeks);
    geeksforgeeks.reset();

    // try block
    try {
        shared_ptr<int> 
        A_Computer_Science_portal_for_Geeks(wp);
    }

    // catch block to handle the errors
    catch (const bad_weak_ptr& gfg) {
        cout << gfg.what() << endl;
    }
}
```

**输出:**

```cpp
bad_weak_ptr

```

**参考:**T2】www.cplusplus.com/reference/memory/bad_weak_ptr/
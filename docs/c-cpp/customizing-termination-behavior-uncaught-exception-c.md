# 定制 C++ 中未捕获异常的终止行为

> 原文:[https://www . geesforgeks . org/customizing-termination-behavior-uncaped-exception-c/](https://www.geeksforgeeks.org/customizing-termination-behavior-uncaught-exception-c/)

每当 C++ 中出现异常时，都会按照使用 try-catch 块定义的行为来处理。但是，经常会出现这样的情况:异常被抛出，但没有被捕获，因为异常处理子系统无法为该特定异常找到匹配的捕获块。在这种情况下，会发生以下一组操作:

1.  异常处理子系统调用函数:**意外()**。该函数由默认的 C++ 库提供，定义了出现未捕获异常时的行为。默认情况下，意外呼叫**终止()**。
2.  终止功能定义了流程终止期间要执行的操作。默认情况下，这将调用**中止()**。
3.  进程被中止。

终止()和意外()只是调用其他函数来实际处理错误。如上所述，终止调用中止()，意外()调用终止()。因此，当出现异常处理错误时，这两个函数都会暂停程序执行。但是，您可以更改终止发生的方式。

要更改终止处理程序，使用的函数是 set _ terminate(terminate _ handler new handler)，在标题 **<异常>** 中定义。

以下程序演示了如何设置自定义终止处理程序:

```cpp
// CPP program to set a new termination handler
// for uncaught exceptions.
#include <exception>
#include <iostream>
using namespace std;

// definition of custom termination function
void myhandler()
{
    cout << "Inside new terminate handler\n";
    abort();
}

int main()
{
    // set new terminate handler
    set_terminate(myhandler); 
    try {
        cout << "Inside try block\n";
        throw 100;
    }
    catch (char a) // won't catch an int exception
    {
        cout << "Inside catch block\n";
    }
    return 0;
}
```

**输出:**

```cpp
Inside try block
Inside new terminate handler

```

 **运行时错误:**

```cpp
Abort signal from abort(3) (SIGABRT)
```

值得注意的是，您的自定义终止处理程序必须做的唯一一件事就是停止程序执行。它不得以任何方式返回程序或恢复程序。
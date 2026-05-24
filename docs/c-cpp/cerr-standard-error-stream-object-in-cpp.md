# cerr–c++ 中的标准错误流对象

> 原文:[https://www . geesforgeks . org/cerr-standard-error-stream-object-in-CPP/](https://www.geeksforgeeks.org/cerr-standard-error-stream-object-in-cpp/)

**标准输出流(cout):** [cout](https://www.geeksforgeeks.org/cincout-vs-scanfprintf/) 是 ostream 类的实例。 **cout** 用于在通常为显示屏的标准输出设备上产生输出。使用插入操作符( **< <** )将需要在屏幕上显示的数据插入标准输出流( **cout** )。

**标准误差流(cerr):** **cerr** 是用于输出误差的标准误差流。这是[牡蛎类](https://www.geeksforgeeks.org/c-stream-classes-structure/)的一个例子。由于 cerr 流是未缓冲的，所以当我们需要立即显示错误消息时使用它，并且不存储错误消息供以后显示。类 [ostream](https://www.geeksforgeeks.org/c-stream-classes-structure/) 的对象，表示面向窄字符(char 类型)的标准错误流。对应 C 流 [stderr](https://www.geeksforgeeks.org/error-handling-c-programs/) 。
**cerr**中的**“c”**是指“字符”，而“err”是指“错误”，因此 cerr 是指“字符错误”。使用 **cerr** 显示错误始终是一个很好的做法。

下面是说明 **cerr** 的程序:

```cpp
// C++ program to illustrate std::cerr

#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // This will print "Welcome to GfG"
    // in the error window
    cerr << "Welcome to GfG! :: cerr";

    // This will print "Welcome to GfG"
    // in the output window
    cout << "Welcome to GfG! :: cout";
    return 0;
}
```

在上面的程序中，第 11 行的输出将显示一个错误窗口:CPP 代码中的
**运行时错误:**

```cpp
Welcome to GfG! :: cerr

```
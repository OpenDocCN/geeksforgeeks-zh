# c++ 中的 cout

> 原文:[https://www.geeksforgeeks.org/cout-in-c/](https://www.geeksforgeeks.org/cout-in-c/)

C++ 中的 [cout 对象](https://www.geeksforgeeks.org/basic-input-output-c/)是类 [ostream](https://www.geeksforgeeks.org/c-stream-classes-structure/) 的对象。在[IOs stream 头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)中定义。它用于向标准输出设备(即监视器)显示输出。它与标准的 C 输出流 stdout 相关联。使用[插入操作符(< < )](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/) ，将需要在屏幕上显示的数据插入标准输出流(cout)。

**程序 1:**

下面是实现 cout 对象的 C++ 程序:

## c++

```cpp
// C++ program to illustrate the use
// of cout object
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Print standard output
    // on the screen
    cout << "Welcome to GFG";

    return 0;
}
```

**输出:**

```cpp
Welcome to GFG
```
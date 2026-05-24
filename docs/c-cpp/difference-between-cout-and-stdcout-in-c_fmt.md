# c++ 中 cout 和 std::cout 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-cout-and-stdcout-in-c/](https://www.geeksforgeeks.org/difference-between-cout-and-stdcout-in-c/)

`cout`是`ostream`类的预定义对象，用于在标准输出设备上打印数据。一般我们在 Linux 操作系统中为`g++`编译器编写程序时，需要程序中有`std`命名空间。我们通过使用命名空间`std`编写`using namespace std;`来使用它；然后我们可以访问任何对象，如`cin`的`cout`。

## 直接使用 std::cout

```cpp
// Program to show the use of cout
// without using namespace

#include <iostream>
int main()
{
    std::cout << "GeeksforGeeks";
    return 0;
}
```

**输出：**

```cpp
GeeksforGeeks
```

**std::cout：** 命名空间是一个声明性区域，其中定义了一些东西。因此，在这种情况下，`cout`在`std`命名空间中定义。因此，`std::cout`声明`cout`在`std`命名空间中定义，否则使用`cout`的定义，后者在`std`命名空间中定义。因此，`std::cout`用于从`std`命名空间定义`cout`。

## 使用 using namespace 简化

```cpp
// Program to show use of using namespace

#include <iostream>
using namespace std;
int main()
{
    cout << "GeeksforGeeks";
    return 0;
}
```

**输出：**

```cpp
GeeksforGeeks
```
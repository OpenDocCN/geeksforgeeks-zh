# 用 C/C++ 写操作系统无关代码

> 原文:[https://www . geesforgeks . org/writing-OS-independent-code-cc/](https://www.geeksforgeeks.org/writing-os-independent-code-cc/)

如何编写一个实用程序，列出目录的所有内容，而不考虑操作系统。

大多数 C/C++ 编译器都定义了可以用来检测操作系统的宏。例如，在 GCC 中，以下是常见的宏。

```cpp
_WIN32 : Defined for both 32 bit and 64 bit windows OS.
_WIN64 : Defined for 64 bit windows OS.

unix, __unix, __unix__ : Defined in UNIX OS

__APPLE__, __MACH__ : Defined in Mac OS

Source : StackOverflow

```

在视窗系统中，我们使用目录调用来列出所有目录，而在大多数其他操作系统中，则使用“ls”。下面是简单的 C++ 实现，列出了文件夹的目录，与操作系统无关。

```cpp
// C++ program to list all directories.
#include <bits/stdc++.h>
using namespace std;
int main()
{
#ifdef _WIN32
    system("dir");
#else
    system("ls");
#endif
    return 0;
}
```

以上与 OS 无关的代码与 Java 的平台无关性完全不同。在 Java 中，有中间字节代码是处理平台依赖关系的非常干净的方式。在这里，我们必须记住编译器特定的宏，并使用笨拙的#ifdef 和#else 编写代码，最重要的是，我们需要为每个操作系统重新编译代码。

本文由 **Shubham Agrawal** 控制。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
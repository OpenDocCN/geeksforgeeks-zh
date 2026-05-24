# 在 C++ 中命名 Mangling 和 extern“C”

> 原文:[https://www.geeksforgeeks.org/extern-c-in-c/](https://www.geeksforgeeks.org/extern-c-in-c/)

C++ 支持函数重载，即可以有多个同名但参数不同的函数。**c++ 编译器在生成目标代码时如何区分不同的函数**–它通过添加关于参数的信息来更改名称。这种为函数名添加附加信息的技术被称为**名称管理**。C++ 标准没有为名称管理指定任何特定的技术，因此不同的编译器可能会将不同的信息附加到函数名称中。

考虑以下名为 Mangling 的例子，它有函数 *f()的各种声明:*

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Function overloading in CPP to demonstrate
// Name Mangling

int f(void) { return 1; }

int f(int) { return 0; }

void g(void) { int i = f(), j = f(0); }
```

一些 C++ 编译器可能会将上面的名称改写为下面的名称，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Function overloading to demonstrate
// Name Mangling

int __f_v(void) { return 1; }

int __f_i(int) { return 0; }

void __g_v(void) { int i = __f_v(), j = __f_i(0); }
```

> **注意:** C 不支持函数重载，所以，当我们在 C++ 中链接一个 C 代码时，我们要确保一个符号的名称不变。

### **从 C++ 链接时如何处理 C 符号？**

在 C 语言中，名字可能不会被破坏，因为它不支持函数重载。那么当我们在 C++ 中链接一个 C 代码时，如何确保一个符号的名称不被改变呢？例如，参见下面使用 C.
的 printf()函数的 C++ 程序

## C++

```cpp
// C Program to demonstrate it
// doesn't support Name Mangling

#include <stdio.h>
int printf(const char* format, ...);

// Driver Code
int main()
{
    printf("GeeksforGeeks");
    return 0;
}
```

上述程序会产生一个错误。

**解释:**编译器出错的原因很简单， *printf()* 的名字被 C++ 编译器改了，没有找到新名字的函数定义。

**解决方案:**c++ 中的外部“C”

当一些代码被放入外部“C”块时，C++ 编译器确保函数名不被破坏——编译器发出一个名称不变的二进制文件，就像 C 编译器那样。
如果我们把上面的程序改成下面的，程序工作正常，在控制台上打印“GeeksforGeeks”(如下图)。

## C++ 14

```cpp
// CPP Program to demonstrate Extern "C"

#include <bits/stdc++.h>
using namespace std;

extern "C" {
int printf(const char* format, ...);
}

// Driver Code
int main()
{
    printf("GeeksforGeeks");
    return 0;
}
```

**Output**

```cpp
GeeksforGeeks
```

因此，所有的 C 风格头文件(stdio.h、string.h 等)在 extern“C”块中都有它们的声明。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#ifdef __cplusplus
extern "C" {
#endif
// Declarations of this file
#ifdef __cplusplus
}
#endif
```

**以上讨论的要点如下:**

**1。**由于 C++ 支持函数重载，因此必须在函数名(称为 Name mangling)中添加附加信息，以避免二进制代码中的冲突。
T3】2。函数名不能在 C 中更改，因为它不支持函数重载。为了避免链接问题，C++ 支持外部“C”块。C++ 编译器确保外部“C”块中的名称不被更改。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
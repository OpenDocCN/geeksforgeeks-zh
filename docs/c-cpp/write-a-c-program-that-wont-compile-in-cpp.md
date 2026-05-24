# 写一个不会用 C++ 编译的 C 程序

> 原文:[https://www . geeksforgeeks . org/write-a-c-program-the-not-compile-in-CPP/](https://www.geeksforgeeks.org/write-a-c-program-that-wont-compile-in-cpp/)

虽然 C++ 被设计成与 C 向后兼容，但是当用 C++ 编译器编译时，可能有许多 C 程序会产生编译器错误。以下是不会用 C++ 编译的 C 程序列表:

1.  在声明之前调用函数
2.  使用带有常量变量的普通指针
3.  使用类型化指针
4.  声明常数值而不初始化
5.  使用特定关键字作为变量名
6.  严格类型检查
7.  main()的返回类型

***下面详细讨论这些点:***

**1)** **在声明前调用函数:**在 C++ 中，在函数声明前调用函数是编译器错误。但是在 C 语言中，它可能会编译。(参见[当一个函数在 C 语言中声明之前被调用会发生什么？](https://www.geeksforgeeks.org/g-fact-95/))

## C

```cpp
// C Program to demonstrate calling
// a function before declaration
#include <stdio.h>

// Main starts
int main()
{
    // fun() is called before its
    // declaration/definition
    fun();
}

// Function Declaration
int fun()
{
    printf("Hello");
    return 0;
}
```

**2)使用带有 const 变量的普通指针:**在 C++ 中，当普通指针用于指向 const 变量时，会生成编译器错误，但在 C 中是允许的( ***必读–***[C 中的 Const 限定符](https://www.geeksforgeeks.org/const-qualifier-in-c/) )

## C

```cpp
// C Program to demonstrate using a
// normal pointer with const variable
#include <stdio.h>

// Main starts
int main()
{

    // A normal pointer points to const
    int const j = 20;

    int* ptr = &j;

    // The below assignment is invalid in C++,
    // results in error.In C, the compiler may
    // throw a warning, but casting is implicitly allowed
    printf("*ptr: %d\n", *ptr);

    return 0;
}
```

**3)使用类型化指针:**在 C 语言中，一个 void 指针可以直接分配给其他指针，比如 int *、char *。但是在 C++ 中，void 指针必须是显式类型转换的。

## C

```cpp
// C Program to demonstrate
// using typecasted pointers
#include <stdio.h>

// Main starts
int main()
{
    void* vptr;

    // In C++, it must be
    // replaced with int *iptr=(int *)vptr;
    int* iptr = vptr;

    return 0;
}
```

> **注意:**这是我们在使用 malloc()时注意到的。malloc()的返回类型为 void *。在 C++ 中，我们必须显式地将 malloc()的返回值类型转换为适当的类型，例如，“int *p = (int *)malloc(sizeof(int))”。在 C 语言中，类型转换是不必要的。

**4)声明常量值而不初始化:**在 C++ 中，常量变量必须初始化，但在 C 中则不需要。以下程序编译&在 C 中运行良好，但是在 C++ 中编译失败。

## C

```cpp
// C Program to demonstrate declaring
// constant values without initializing:
#include <stdio.h>

// Main starts
int main()
{
    const int a;   
    return 0;
}
```

**5)使用特定关键字作为变量名:**在 C 语言中，特定关键字可以作为变量名，但是在 C++ 中是不可能的。下面的程序不会用 C++ 编译，但会用 C 编译

## C

```cpp
// C Program to demonstrate using
// specific keywords as variable names
#include <stdio.h>

// Main starts
int main(void)
{

    // new is a keyword in C++
    // but not in C
    int new = 5;

    printf("%d", new);
}
```
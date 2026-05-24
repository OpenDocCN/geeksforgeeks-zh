# 为什么空结构的大小在 C++ 中是 1 字节，而在 C 中是 0 字节

> 原文:[https://www . geeksforgeeks . org/为什么-空结构-有-size-1 字节 in-c 但-0 字节 in-c/](https://www.geeksforgeeks.org/why-does-empty-structure-has-size-1-byte-in-c-but-0-byte-in-c/)

A [结构](https://www.geeksforgeeks.org/structures-in-cpp/)是 [C/C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的[自定义数据类型](https://www.geeksforgeeks.org/user-defined-data-types-in-c/)。一个结构创建一个[数据类型](https://www.geeksforgeeks.org/c-data-types/)，它可以用来将可能不同类型的项目组合成一个类型。“struct”关键字用于创建结构。创建结构的一般语法如下所示:

**语法-**

```cpp
struct structureName{
    member1;
    member2;
    member3;
    .
    .
    .
    memberN;
};
```

C++ 中的结构可以包含两种类型的成员:

1.  [**数据成员**](https://www.geeksforgeeks.org/c-classes-and-objects/)**–**这些成员是正常的 [C++ 变量](https://www.geeksforgeeks.org/variables-in-c/)。在 C++ 中，可以用不同数据类型的变量创建一个结构。
2.  [**成员函数**](https://www.geeksforgeeks.org/const-member-functions-c/)**–**这些成员是正常的 [C++ 函数](https://www.geeksforgeeks.org/functions-in-c/)。除了变量，函数也可以包含在结构声明中。

**问题陈述:**为什么空结构的大小在 C++ 中不是零，而在 [C](https://www.geeksforgeeks.org/c-language-set-1-introduction/) 中是零。

**解:**
下面是空结构的 C 程序:

## C

```cpp
// C program with an empty
// structure
#include <stdio.h>

// Driver code
int main()
{
    // Empty Structure
    struct empty {
    };

    // Initializing the Variable
    // of Struct type
    struct empty empty_struct;

    // Printing the Size of Struct
    printf("Size of Empty Struct in C programming = %ld",
           sizeof(empty_struct));
}
```

**Output**

```cpp
Size of Empty Struct in C programming = 0
```

下面是一个空结构的 C++ 程序:

## C++

```cpp
// C++ program to implement
// an empty structure
#include <iostream>
using namespace std;

// Driver code
int main()
{
    // Empty Struct
    struct empty {
    };

    // Initializing the Variable
    // of Struct type
    struct empty empty_struct;

    // Printing the Size of Struct
    cout << "Size of Empty Struct in C++ Programming = " << sizeof(empty_struct);
}
```

**Output**

```cpp
Size of Empty Struct in C++ Programming = 1
```

如果仔细观察，相同的代码在 C 和 C++ 中执行，但两种情况下的输出是不同的。我们来讨论一下背后的原因-

1.  C++ 标准不允许大小为 0 的[对象(或类)](https://www.geeksforgeeks.org/c-classes-and-objects/)。这是因为这将使得两个不同的对象具有相同的存储位置成为可能。这就是即使是空的类和结构也必须至少有 1 的大小的概念背后的原因。众所周知，空类的大小不是零。一般是 1 字节。C++ 结构也遵循与 C++ 类相同的原则，即 c++ 中的结构也不会是零字节的。最小大小必须是一个字节。
2.  在 C/C++ 中创建空结构违反了语法约束。然而， [GCC](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/) 允许 C 中的空结构作为扩展。此外，如果结构没有任何命名成员，则行为是未定义的，因为:

> **C99 表示-**
> 如果结构-声明-列表不包含命名成员，则行为是未定义的。

这意味着-

```cpp
// Constraint Violation
struct EmptyGeeksforGeeks {};

// Behavior undefined, 
// since there is no named member
struct EmptyGeeksforGeeks {int :0 ;}; 
```
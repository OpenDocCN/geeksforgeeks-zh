# C/c++ #包含带有示例的指令

> 原文:[https://www . geesforgeks . org/c-c-include-direction-with-examples/](https://www.geeksforgeeks.org/c-c-include-directive-with-examples/)

**#include** 是在程序中包含标准或用户定义文件的一种方式，大多写在任何 C/C++ 程序的开头。该指令由[预处理器](https://www.geeksforgeeks.org/cc-preprocessors/)读取，并命令其将用户定义或系统头文件的内容插入到以下程序中。这些文件主要从外部源导入到当前程序中。导入系统定义或用户定义的文件的过程称为**文件包含**。这种类型的预处理器指令告诉编译器在源代码程序中包含一个文件。以下是可以使用#include:
包含的两种文件类型

1.  **头文件或标准文件:**这是一个包含 C/C++ 函数声明和宏定义的文件，在几个源文件之间共享。像 printf()、scanf()、cout、cin 和各种其他输入输出或其他标准函数这样的函数包含在不同的头文件中。因此，为了利用这些功能，用户需要导入一些定义所需功能的头文件。
2.  **用户自定义文件:**这些文件类似于头文件，除了它们是由用户自己编写和定义的。这使得用户不必多次编写特定的函数。一旦编写了用户定义的文件，就可以使用#include 预处理器将其导入程序中的任何位置。

**语法:**

```cpp
#include "user-defined_file"
```

1.  **包括使用" ":**当使用双引号(" ")时，预处理器访问源“header_file”所在的当前目录。这种类型主要用于访问用户程序的任何头文件或用户自定义文件。

```cpp
#include <header_file>
```

1.  **包括使用< > :** 使用尖括号(< >)导入文件时，预处理器使用预定的目录路径访问文件。它主要用于访问位于标准系统目录中的系统头文件。

**示例 1:** 这显示了系统 I/O 头或标准文件的导入。

## C

```cpp
// C program showing the header file including
// standard input-output header file

#include <stdio.h>

int main()
{

    // "printf()" belongs to stdio.h
    printf("hello world");
    return 0;
}
```

## C++

```cpp
// C++ program showing the header file including
// standard input-output header file

#include <iostream>
using namespace std;

int main()
{

    // "cout" belongs to "iostream"
    cout << "hello world";
    return 0;
}
```

**Output:** 

```cpp
hello world
```
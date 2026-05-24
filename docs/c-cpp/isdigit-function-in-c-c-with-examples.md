# 是 C/C++ 中的 digit()函数，示例

> 原文:[https://www . geesforgeks . org/isdigit-function-in-c-c-with-examples/](https://www.geeksforgeeks.org/isdigit-function-in-c-c-with-examples/)

**是数字(c)** 是 [C](https://www.geeksforgeeks.org/c-programming-language/) 中的一个函数，可以用来检查传递的字符是否是数字。如果是数字，则返回非零值，否则返回 0。例如，它为**“0”**到**“9”**返回一个非零值，为其他值返回零。

*   **是在[ctype . h](https://www.geeksforgeeks.org/ctype-hcctype-library-in-c-c-with-examples/)**T5[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)中声明的。****
*   用于检查输入的字符是否为数字字符**【0–9】**。
*   它采用整数形式的单个参数，并返回类型为 **int** 的值。
*   即使**是整数()**作为参数，字符也会传递给函数。在内部，字符被转换为其用于检查的 **ASCII** 值。

**头文件:**

```cpp
#include <ctype.h>
```

**语法:**

```cpp
std::isdigit(int arg)
```

**参数:**模板 **std::isdigit()** 接受整数类型的单个参数。

**返回类型:**该函数根据传递给它的参数返回一个整数值，如果参数是一个数字字符，那么它返回一个**非零值**(真值)，否则它返回**零**(假值)。

下面是同样的程序来说明:

## C

```cpp
// C program to demonstrate isdigit()
#include <ctype.h>
#include <stdio.h>

// Driver Code
int main()
{
    // Taking input
    char ch = '6';

    // Check if the given input
    // is numeric or not
    if (isdigit(ch))
        printf("\nEntered character is"
               " numeric character");
    else
        printf("\nEntered character is not"
               " a numeric character");
    return 0;
}
```

// C++ 程序演示 is digit()
# include<ctype . h>
# include<iostream>
使用命名空间 std

//驱动代码
int main()
{
//取输入
char ch = ' 6 '；

//检查给定输入
//是否为数字
if(is digit(ch))
cout<<”\输入字符为“
< <”数字字符；
else
cout < <“输入字符”不是“
”数字字符；
返回 0；
}

**Output:**

```cpp
Entered character is numeric character

```
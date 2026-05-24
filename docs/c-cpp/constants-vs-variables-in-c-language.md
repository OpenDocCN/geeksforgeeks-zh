# C 语言中的常量与变量

> 原文:[https://www . geesforgeks . org/constants-vs-variables-in-c 语言/](https://www.geeksforgeeks.org/constants-vs-variables-in-c-language/)

### <u>[恒](https://www.geeksforgeeks.org/constants-in-c/)</u>

<u>T5】</u>

顾名思义，常量这个名称是用 C 编程语言给变量或值起的，一旦定义就不能修改。它们是程序中的固定值。可以有任何类型的常量，如整数、浮点、八进制、十六进制、字符常量等。每个常数都有一定的范围。太大而无法放入 int 的整数将被视为长整数。现在有各种不同的范围，从无符号位到有符号位。在有符号位下，int 的范围从-128 到+127 不等，在无符号位下，int 的范围从 0 到 255 不等。

**示例:**

```cpp
#include <stdio.h>

// Constants
#define val 10
#define floatVal 4.5
#define charVal 'G'

// Driver code
int main()
{
    printf("Integer Constant: %d\n", val);
    printf("Floating point Constant: %f\n", floatVal);
    printf("Character Constant: %c\n", charVal);

    return 0;
}
```

**Output:**

```cpp
Integer Constant: 10
Floating point Constant: 4.500000
Character Constant: G

```

### <u>[变量](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)</u>

一个**变量**简单来说就是一个存储空间，里面分配了一些内存。基本上，用来存储某种形式数据的变量。不同类型的变量需要不同的内存量，并且有一些特定的操作集可以应用于它们。

**变量声明:**
典型的变量声明形式如下:

```cpp
type variable_name;

or for multiple variables:
type variable1_name, variable2_name, variable3_name;

```

变量名可以由字母(大写和小写)、数字和下划线“_”字符组成。但是，名称不能以数字开头。

**示例:**

```cpp
#include <stdio.h>
int main()
{
    // declaration and definition of variable 'a123'
    char a123 = 'a';

    // This is also both declaration
    // and definition as 'b' is allocated
    // memory and assigned some garbage value.
    float b;

    // multiple declarations and definitions
    int _c, _d45, e;

    // Let us print a variable
    printf("%c \n", a123);

    return 0;
}
```

**Output:**

```cpp
a

```

### <u>变量和常量的区别</u>

| 常数 | 可变的 |
| --- | --- |
| 在整个程序中不能改变的值 | 与有值的相关符号名配对的存储位置 |
| 它类似于一个变量，但是一旦被定义就不能被程序修改 | 存储区保存数据 |
| 无法更改 | 可以根据程序员的需要进行更改 |
| 价值是固定的 | 价值是变化的 |
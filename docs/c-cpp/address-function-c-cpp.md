# 函数在 C 或 C++ 中的地址

> 原文:[https://www.geeksforgeeks.org/address-function-c-cpp/](https://www.geeksforgeeks.org/address-function-c-cpp/)

我们都知道每个函数的代码都驻留在内存中，所以每个函数都像程序中的所有其他变量一样有一个地址。我们只需在没有括号的情况下写出函数的名称，就可以得到函数的地址。详见 C 中的[功能指针。](https://www.geeksforgeeks.org/function-pointer-in-c/)

函数 main()的地址为 004113C0
函数 funct()的地址为 00411104

在 C/C++ 中，函数的名字可以用来查找函数的地址。

```cpp
// C program to addresses of a functions
// using its name
#include<stdio.h>

void funct()
{
    printf("GeeksforGeeks");
}

int main(void)
{
    printf("address of function main() is :%p\n", main);
    printf("address of function funct() is : %p\n", funct);
    return 0;
}
```

**Output:**

```cpp
address of function main() is :0x40053c
address of function funct() is : 0x400526

```
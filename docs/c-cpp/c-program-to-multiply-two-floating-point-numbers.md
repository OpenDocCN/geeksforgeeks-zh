# 两个浮点数相乘的 C 程序

> 原文:[https://www . geeksforgeeks . org/c-程序乘二浮点数/](https://www.geeksforgeeks.org/c-program-to-multiply-two-floating-point-numbers/)

给定两个浮点数 A 和 b，任务是编写一个程序来寻找这两个数的乘积。
![](img/6c0426b05d5156bb5b353a440c7dbefb.png)

**示例**:

> **输入** : A = 2.12，B = 3.88
> 输出 : 8.225600
> 
> **输入** : A = 3.78，B = 6.32
> 输出 : 23.889601

在下面的两个浮点数相乘的程序中，首先要求用户输入两个浮点数，使用 [scanf()](https://www.geeksforgeeks.org/scanf-fscanf-sscanf-scanf_s-fscanf_s-sscanf_s/) 功能扫描输入，并存储在变量![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")和![B](img/76d8ee369d9167cdfb7489cf2a197486.png "Rendered by QuickLaTeX.com")中。然后，使用算术运算符![*](img/c895ce0797f9585742ef4088814986f5.png "Rendered by QuickLaTeX.com")将变量![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")和![B](img/76d8ee369d9167cdfb7489cf2a197486.png "Rendered by QuickLaTeX.com")相乘，并将乘积存储在变量**乘积**中。

下面是两个浮点数相乘的 C 程序:

```cpp
// C program to multiply two floating point numbers
#include <stdio.h>

int main()
{
    float A, B, product = 0.0f;

    // Ask user to enter the two numbers
    printf("Enter two floating numbers A and B : \n");

    // Read two numbers from the user || A = 2.12, B = 3.88
    scanf("%f%f", &A, &B);

    // Calclulate the multiplication of A and B
    // using '*' operator
    product = A * B;

    // Print the product
    printf("Product of A and B is: %f", product);

    return 0;
}
```

**Output:**

```cpp
Enter two floating numbers A and B : 2.12 3.88
Product of A and B is: 8.225600

```
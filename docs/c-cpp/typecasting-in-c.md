# 在 C 中打字

> 原文:[https://www.geeksforgeeks.org/typecasting-in-c/](https://www.geeksforgeeks.org/typecasting-in-c/)

**类型转换:**它是一种 [数据类型](https://www.geeksforgeeks.org/data-types-in-c/) 由程序员在程序设计过程中使用转换运算符转换成另一种数据类型。在类型转换中，当将数据类型转换为另一种数据类型时，目标数据类型可能小于源数据类型，这就是为什么它也被称为收缩转换。

在某些情况下，如果[数据类型](https://www.geeksforgeeks.org/difference-between-type-casting-and-type-conversion/)保持不变，可能会给出不正确的输出。在这种情况下，类型转换有助于获得正确的输出并减少编译时间。

**程序 1:**

下面是 [C 程序](https://www.geeksforgeeks.org/c/)来说明打字的必要性:

## C

```cpp
// C program to illustrate the use of
// typecasting
#include <stdio.h>

// Function to divide a and b
void division(int a, int b)
{
    float div;

    // Division of a and b
    div = a / b;

    printf("The result is %f\n", div);
}

// Driver Code
int main()
{
    // Given a & b
    int a = 15, b = 2;

    // Function Call
    division(a, b);

    return 0;
}
```

**输出:**

```cpp
The result is 7.000000

```

**说明:**这里，实际需要的输出是**7.50000【T39 因此，要获得正确的输出，一种方法是改变给定变量的数据类型。但是正确的输出也可以通过**打字**来完成。这包括在数据类型的名称周围放一对圆括号，如**除法=(浮点)a/b** 。**

**程序二:**

下面是 C 程序来展示一下打字的使用:

## C

```cpp
// C program to showcase the use of
// typecasting
#include <stdio.h>

// Function to divide a and b
void division(int a, int b)
{
    float div;

    // Typecasting in float
    div = (float)a / b;

    printf("The result is %f\n", div);
}

// Driver Code
int main()
{
    // Given a & b
    int a = 15, b = 2;

    // Function Call
    division(a, b);

    return 0;
}
```

**输出:**

```cpp
The result is 7.500000

```

**说明:**在上面的 C 程序中，表达式 **(float)** 在运算之前将变量 a 从类型 **int** 转换为类型 **float** 。
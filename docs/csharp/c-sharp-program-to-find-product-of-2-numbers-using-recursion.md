# C# 程序用递归求 2 的乘积

> 原文:[https://www . geeksforgeeks . org/c-sharp-用递归程序查找 2 个数字的乘积/](https://www.geeksforgeeks.org/c-sharp-program-to-find-product-of-2-numbers-using-recursion/)

给定两个数字 x 和 y，用递归求乘积。递归是函数直接或间接调用自身的过程，相应的函数称为递归函数。它很容易用来解决问题，就像在这篇文章中使用递归，我们会找到两个数字的乘积。

**示例:**

```cs
Input  : x = 10, y = 3
Output : 30

Input  : x = 70, y = 4
Output : 280
```

**进场:**

> 要使用递归打印两个数的乘积，请执行以下步骤:
> 
> *   对于我们的任务，我们有两个数字，即 x，y。
> *   用零值初始化变量结果。
> *   递归地将 x 与结果相加 y 次。
> *   取基本条件为 y == 0。当 y 等于 0 时，从函数返回。
> *   迭代结束时，结果变量将包含 x，y 的乘积

**示例:**

## C#

```cs
// C# program to display the product of 
// two numbers using Recursion 
using System;

class GFG{

// Recursive function for calculating
// product of two numbers.
static int product(int x, int y)
{

    // If y is equal to zero then return 0
    if (y == 0)
        return 0;

    // Recursively calculate
    // y times sum of x
    else
        return (x + product(x, y - 1));
}

// Driver code
public static void Main ()
{
    int x = 10, y = 3;

    Console.Write(product(x, y));
}
}
```

**Output**

```cs
30
```

如果 y 大于 x，我们可以通过交换 x 和 y 来优化这个代码。让我们假设 x = 3 和 y = 150，如果我们遵循上面的程序，那么 x 被递归添加 150 次，但是通过交换 x，y(即 x = 150，y = 3)，我们只需要递归添加 x 3 次。

## C#

```cs
// C# program to display the product of 
// two numbers using Recursion 
using System;

class GFG{

// Recursive function for calculating
// product of two numbers.
static int product(int x, int y)
{

    // If y is equal to zero then return 0
    if (y == 0)
        return 0;

    // Recursively calculate
    // y times sum of x
    else
        return(x + product(x, y - 1));
}

// Driver code
public static void Main()
{
    int x = 3, y = 150;

    // Swapping the x and y if the y > x.
    if (x < y)
        Console.Write(product(y, x));
    else
        Console.Write(product(x, y));
}
}
```

**Output**

```cs
450
```
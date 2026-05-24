# 不使用预定义方法计算余弦(X)的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-不使用预定义方法计算余弦的程序/](https://www.geeksforgeeks.org/c-sharp-program-to-calculate-the-cosinex-without-using-a-predefined-method/)

余弦(x)也称为 Cos(x)。它是一个角度的三角函数。底边的长度与斜边的长度之比称为直角三角形中一个角的余弦。在本文中，我们将学习在不使用预定义方法的情况下计算余弦(X)。所以做这个任务我们用下面的公式:

> cos(x)= 1.0–p/2+q/24–p * q/720+q * q/40320–p * q * q/3628800

**例:**

```cs
Input  : cos(45)
Output : 0.7071

Input : cos(0)
Output : 1
```

**代码:**

## c#

```cs
// C# program to calculate the Cosine(X) 
// Without using a predefined method
using System;

class GFG{

// Function to calculate the Cosine(X)     
static double Cos(double theta)
{
    double R;
    double S;
    double ans;

    R = Math.Pow(theta, 2);
    S = Math.Pow(R, 2);

    // Substuting p,q in the below formula
    ans = 1.0 - R / 2 + S / 24 - R * S / 720 + 
            S * S / 40320 - R * S * S / 3628800;

    return ans;
}

// Driver code
static void Main(string[] args)
{
    Console.WriteLine("Cos(0):" + Cos(0));
    Console.WriteLine("Cos(3):" + Cos(1));
    Console.WriteLine("Cos(8):" + Cos(2));
}
}
```

**输出:**

```cs
Cos(0):1
Cos(3):0.540302303791887
Cos(8):-0.41615520282187
```
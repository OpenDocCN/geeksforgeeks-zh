# C# |数学。BigMul()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-bigmul-method/](https://www.geeksforgeeks.org/c-sharp-math-bigmul-method/)

在 C# 中 ***BigMul()*** 是一个方法类的方法。此方法用于计算两个 32 位数字的全积。
**语法:**

```cs
public static long BigMul(int a, int b)
```

**参数:**

> **a** :是第一个相乘的数字，这个参数的类型是*系统。Int32* 。
> **b** :是第二个要相乘的数字，这个参数的类型是*系统。Int32* 。

**返回类型:**该方法返回一个包含指定数字乘积的数字，该方法的返回类型为*系统。Int64* 。
**例:**

## C#

```cs
// C# program to demonstrate the 
// Math.BigMul() method
using System;
namespace ConsoleApplication1 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // defining two variable of type
        //  System.Int32
        Int32 x1 = 233232322;
        Int32 x2 = 189222338;

        // Using BigMul( ) method and storing 
        // result into a long(Int64) variable
        long product = Math.BigMul(x1, x2);

        // Getting the output
        Console.WriteLine("The product of the two numbers is " + product);
    }
}
}
```

**Output:** 

```cs
The product of the two numbers is 44132765266008836
```
# C# |数学。DivRem()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-divrem-method/](https://www.geeksforgeeks.org/c-sharp-math-divrem-method/)

在 C# 中 ***数学。*div rem()**是一个数学类方法，它将两个数字相除并返回余数。通过使用除法运算符，我们不能在单独的变量中得到余数，但是使用 *DivRem()* 方法，我们可以得到两者。
这个方法可以通过传递不同类型和数量的参数来重载。

1.  **数学。DivRem(Int32，Int32，Int32)**
2.  **数学。DivRem(Int64，Int64，Int64)**

#### 数学，数学。divem(Int32、Int32、int 32)

此方法用于计算两个 32 位有符号整数的商，并在输出参数中返回余数。

**语法:**

```cs
public static int DivRem(int dividend, int divisor, int result);

```

**参数:**

> **红利:**是类型为 *Int32* 的输入红利号。
> **除数:**是类型为 *Int32* 的输入除数。
> **结果:**是 *Int32* 类型的输出余数。

**返回类型:**该函数返回类型 *Int32* 的指定数字的*商*。

**异常:**如果*除数*的值为*零*，则该方法将给出**除数异常**。

**示例:**

```cs
// C# program to demonstrate working
// of Math.DivRem(Int32, Int32, Int32)
using System;

class DivRemGeeks {

    // Main method
    static void Main()
    {

        // Input +ve  dividend and divisor number
        int dividend_A = 9845324;
        int divisor_A = 7;

        // Input negative dividend and divisor number
        int dividend_B = -99999;
        int divisor_B = 2;

        int result_1;
        int result_2;

        // Using the MATH.DivRem() Method
        int quotient_ONE = Math.DivRem(dividend_A, divisor_A, out result_1);
        int quotient_TWO = Math.DivRem(dividend_B, divisor_B, out result_2);

        // Print Result
        Console.WriteLine(quotient_ONE);
        Console.WriteLine(result_1);
        Console.WriteLine(quotient_TWO);
        Console.WriteLine(result_2);
    }
}
```

**Output:**

```cs
1406474
6
-49999
-1

```

#### 数学，数学。DivRem(Int64、Int64、Int64)

此方法用于计算两个 64 位有符号整数(长)的商，并在输出参数中返回余数。

**语法:**

```cs
public static long DivRem(int dividend, int divisor, int result);

```

**参数:**

> **红利:**是类型为 *Int64* 的输入红利号。
> **除数:**是 *Int64* 类型的输入除数。
> **结果:**是 *Int64* 类型的输出余数。

**返回类型:**该函数返回类型 *Int64* 的指定数字的*商*。

**异常:**如果*除数*的值为*零*，则该方法将给出**除数异常**。

**示例:**

```cs
// C# program to demonstrate working
// of Math.DivRem(Int64, Int64, Int64) method
using System;

class DivRemGeeks {

    // Main method
    static void Main()
    {

        // Input +ve dividend and divisor number
        long dividend_A = 9223372036854775779;
        long divisor_A = 2000;

        // Input negative dividend and divisor number
        long dividend_B = -99999888844499233;
        long divisor_B = 768933;

        long result_1;
        long result_2;

        // Using the MATH.DivRem() Method
        long quotient_ONE = Math.DivRem(dividend_A, divisor_A, out result_1);
        long quotient_TWO = Math.DivRem(dividend_B, divisor_B, out result_2);

        // Print Result
        Console.WriteLine(quotient_ONE);
        Console.WriteLine(result_1);

        Console.WriteLine(quotient_TWO);
        Console.WriteLine(result_2);
    }
}
```

**Output:**

```cs
4611686018427387
1779
-130050197929
-359476

```

**参考文献:**[https://docs . Microsoft . com/en-us/dotnet/API/system . math . div rem？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.math.divrem?view=netframework-4.7.2)
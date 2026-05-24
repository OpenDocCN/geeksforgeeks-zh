# C# |数学。符号()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-sign-method/](https://www.geeksforgeeks.org/c-sharp-math-sign-method/)

在 C# 中， ***Sign()*** 是一个数学类方法，它返回一个指定数字符号的整数。通过更改传递的参数的数据类型，可以重载此方法，如下所示:

*   **数学。符号(十进制):**返回指定十进制数符号的整数。
*   **数学。符号(双精度):**返回指定双精度浮点数符号的整数。
*   **数学。符号(Int16):** 返回指定 16 位有符号整数符号的整数。这里 *Int16* 是*的简称*数据类型
*   **数学。符号(Int32):** 返回指定 32 位有符号整数符号的整数。这里 *Int32* 是 *int* 数据类型。
*   **数学。符号(Int64):** 返回指定 64 位有符号整数符号的整数。这里 *Int64* 是*长*的数据类型。
*   **数学。符号(字节):**返回指定 8 位有符号整数符号的整数。
*   **数学。符号(单):**返回指定单精度浮点数符号的整数。这里*单*是*浮动*数据类型。

**上述所有方法的通用语法:**

```cs
public static int Sign(data_type value)

```

**参数:**该方法采用单个参数的形式为**字节、int、double、sbyte 等。**

**返回类型:**该方法返回类型*系统的值。Int32* 符合下列条件:

| 返回值 | 条件: |
| Zero | 如果值等于零 |
| one | 如果值大于零 |
| -1 | 如果值小于零 |

**示例:**

```cs
// C# program to demonstrate the 
// Math.Sign() method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Decimal data type
        Decimal de = 150M;

        // Double data type
        Double d = 34.5432d;

        // Int16 data type
        short sh = 0;

        // Int32 data type
        int i = -5678;

        // Int64 data type
        long l = 598964564;

        // SByte data type
        sbyte sb = -34;

        // float data type
        float f = 56.89f;

        // displaying result
        Console.WriteLine("Decimal: " + de + " " + check(Math.Sign(de)));
        Console.WriteLine("Double: " + d + " " + check(Math.Sign(d)));
        Console.WriteLine("Int16: " + sh + " " + check(Math.Sign(sh)));
        Console.WriteLine("Int32: " + i + " " + check(Math.Sign(i)));
        Console.WriteLine("Int64: " + l + " " + check(Math.Sign(l)));
        Console.WriteLine("SByte: " + sb + " " + check(Math.Sign(sb)));
        Console.WriteLine("Single: " + f + " " + check(Math.Sign(f)));

    }

    // function to check whether the input 
    // number is greater than zero or not
    public static String check(int compare)
    {
        if (compare == 0)
            return "equal to zero";

        else if (compare < 0)
            return "less than zero";

        else
            return "greater than zero";
    }
}
```

**Output:**

```cs
Decimal: 150 greater than zero
Double: 34.5432 greater than zero
Int16: 0 equal to zero
Int32: -5678 less than zero
Int64: 598964564 greater than zero
SByte: -34 less than zero
Single: 56.89 greater than zero

```
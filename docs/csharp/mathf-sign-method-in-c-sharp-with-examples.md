# MathF。C# 中的 Sign()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-sign-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-sign-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。符号(单)*** 是一个 MathF 类方法，它返回一个指定数字符号的整数。

> **语法:**公共静态 int Sign(float x)；
> 这里， **x** 是需要计算符号的单精度浮点数。

**返回类型:**该方法返回类型*系统的值。Int32* 符合下列条件:

| 返回值 | 条件: |
| Zero | 如果值等于零 |
| one | 如果值大于零 |
| -1 | 如果值小于零 |

**示例:**

```cs
// C# program to demonstrate the
// MathF.Sign(Single) Method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // float data type
        float f1 = 746.89f;
        float f2 = -782.1247f;

        // displaying result
        Console.WriteLine(check(MathF.Sign(f1)));
        Console.WriteLine(check(MathF.Sign(f2)));
    }

    // function to check whether the input
    // number is greater than zero or not
    public static String check(int r)
    {
        if (r == 0)
            return "Equal to zero";

        else if (r < 0)
            return "Less than zero";

        else
            return "Greater than zero";
    }
}
```

**Output:**

```cs
Greater than zero
Less than zero

```
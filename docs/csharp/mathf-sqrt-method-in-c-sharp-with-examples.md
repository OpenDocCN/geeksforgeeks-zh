# MathF。C# 中的 Sqrt()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-sqrt-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-sqrt-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。Sqrt(Single)*** 是一个 MathF 类(存在于系统命名空间中)方法，用于计算指定的 **Single 或 float** 数据类型值的平方根。

> **语法:**公共静态 float Sqrt(float x)；
> 这里，x 是要计算平方根的数字，这个参数的类型是*系统。单身*。

**返回类型:**此方法返回 *x* 的平方根。如果 *x* 等于 NaN、*负有限性*或*正有限性*，则返回该值。该方法的返回类型为*系统。单*。

下面是举例说明上述方法的使用:
**例 1:**

```cs
// C# program to demonstrate the
// MathF.Sqrt(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // taking positive value
        float x = 78521F;

        // taking negative value
        float x1 = -7824F;

        // Input positive value
        // Output will be square
        // root of x
        Console.WriteLine(MathF.Sqrt(x));

        // Input negative value,
        // Output will be NaN
        Console.Write(MathF.Sqrt(x1));
    }
}
```

**Output:**

```cs
280.216
NaN

```

**例 2:**

```cs
// C# program to demonstrate the MathF.Sqrt()
// method when the argument is positive
// or negative Zero
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // taking positive zero 
        float x = 0f;
        Console.WriteLine(MathF.Sqrt(x));

        // taking negative zero
        float y = -0f;
        Console.Write(MathF.Sqrt(y));
    }
}
```

**Output:**

```cs
0
0

```
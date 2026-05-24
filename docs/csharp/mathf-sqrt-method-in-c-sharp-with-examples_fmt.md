# MathF.Sqrt() 方法在 C# 中的使用及示例

> 原文：[https://www.geeksforgeeks.org/mathf-sqrt-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-sqrt-method-in-c-sharp-with-examples/)

在 C# 中，`MathF.Sqrt(Single)` 是一个 `MathF` 类（存在于 `System` 命名空间中）的方法，用于计算指定的 `Single` 或 `float` 数据类型值的平方根。

## 语法

```cs
public static float Sqrt(float x);
```
这里，`x` 是要计算平方根的数字，这个参数的类型是 `System.Single`。

## 返回类型

此方法返回 `x` 的平方根。如果 `x` 等于 `NaN`、`NegativeInfinity` 或 `PositiveInfinity`，则返回该值。该方法的返回类型为 `System.Single`。

下面是举例说明上述方法的使用：

### 示例 1

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

**输出：**

```cs
280.216
NaN
```

### 示例 2

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

**输出：**

```cs
0
0
```
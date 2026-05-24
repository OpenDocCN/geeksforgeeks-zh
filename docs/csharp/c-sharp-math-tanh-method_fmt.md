# C# Math.Tanh() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-tanh-method/](https://www.geeksforgeeks.org/c-sharp-math-tanh-method/)

`Math.Tanh()` 是内置的数学类方法，它返回给定双精度值参数的双曲线正切值。如果给定的参数是 `NaN`，结果将是 `NaN`。

## 语法

```cs
public static double Tanh(double num)
```

## 参数

**num:** 是要返回双曲正切的数字，该参数的类型是 `System.Double`。

## 返回值

该方法返回 `num` 的双曲正切值，类型为 `System.Double`。如果 `num` 等于负无穷定义，则此方法返回 `-1`。如果 `num` 等于正无穷，则此方法返回 `1`。如果 `num` 等于 `NaN`，则此方法返回 `NaN`。

## 示例

```cs
Input  : num = 60.0
Output : 1.0
```

下面的程序说明了 `Math.Tanh()` 方法。

### 程序一

```cs
// C# program to illustrate the
// Math.Tanh()
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        double num1 = 60.0, num2 = 0.0, num3 = 1.0;

        // It returns the hyperbolic tan of
        // specified angle in radian
        double tanhvalue = Math.Tanh(num1);
        Console.WriteLine("The tanh of num1 = " + tanhvalue);

        tanhvalue = Math.Tanh(num2);
        Console.WriteLine("The tanh of num2 = " + tanhvalue);

        tanhvalue = Math.Tanh(num3);
        Console.WriteLine("The tanh of num3 = " + tanhvalue);
    }
}
```

**输出:**

```cs
The tanh of num1 = 1
The tanh of num2 = 0
The tanh of num3 = 0.761594155955765
```

### 程序二

```cs
// C# program to illustrate the
// Math.Tanh() Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        double num1 = (30 * (Math.PI)) / 180, num2 = 11.0, num3 = 45.0;

        // It returns the hyperbolic tan of
        // angle in radian
        double tanhvalue = Math.Tanh(num1);
        Console.WriteLine("The tanh of num1 = " + tanhvalue);

        tanhvalue = Math.Tanh(num2);
        Console.WriteLine("The tanh of num2 = " + tanhvalue);

        tanhvalue = Math.Tanh(num3);
        Console.WriteLine("The tanh of num3 = " + tanhvalue);
    }
}
```

**输出:**

```cs
The tanh of num1 = 0.480472778156452
The tanh of num2 = 0.999999999442106
The tanh of num3 = 1
```
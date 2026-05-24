# c# 中双精度转换为整数的不同方式

> 原文:[https://www . geesforgeks . org/different-way-to-convert-double-to-integer-in-c-sharp/](https://www.geeksforgeeks.org/different-ways-to-convert-double-to-integer-in-c-sharp/)

给定一个双实数，任务是在 [C# ](https://www.geeksforgeeks.org/c-sharp-tutorial/) 中将其转换为整数。将 Double 转换为 Integer 的方法主要有以下三种:

*   [使用型铸造](https://www.geeksforgeeks.org/c-sharp-type-casting/)
*   [使用 Math.round()](https://www.geeksforgeeks.org/c-sharp-math-round-method-set-1/)
*   [使用十进制。to t32()](https://www.geeksforgeeks.org/decimal-toint32-method-in-c-sharp/)

**示例:**

```cs
Input: double = 3452.234
Output: 3452 

Input: double = 98.23
Output: 98 
```

**1。使用类型转换:**这是一种非常简单和用户友好的技术。

**例:**

## C#

```cs
// C# program for type conversion from double to int
using System;
using System.IO;
using System.Text;
namespace GFG {
class Geeks {
  // Main Method
  static void Main(string[] args) {
    double a = 3452.345;
    int b = 0;

    // type conversion
    b = (int)a;

    Console.WriteLine(b);
  }
}
}
```

**输出:**

```cs
3452

```

**2。使用 Math.round():** 此方法返回最近的整数。

## C#

```cs
// C# program to demonstrate the
// Math.Round(Double) method
using System;

class Geeks {

  // Main method
  static void Main(string[] args) {
    Double dx1 = 3452.645;

    // Output value will be 12
    Console.WriteLine(Math.Round(dx1));
  }
}
```

**输出:**

```cs
3452

```

**3。使用十进制。ToInt32():** 此方法用于将指定 Decimal 的值转换为等效的 32 位有符号整数。

## C#

```cs
// C# program to convert Double to Integer
using System;
public
class Demo {
public
  static void Main() {
    double val = 3452.345;
    int res = Convert.ToInt32(val);
    Console.WriteLine(res);
  }
}
```

**输出:**

```cs
3452

```
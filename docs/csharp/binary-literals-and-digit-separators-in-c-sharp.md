# c# 中的二进制文字和数字分隔符

> 原文:[https://www . geesforgeks . org/二进制文字和数字分隔符-in-c-sharp/](https://www.geeksforgeeks.org/binary-literals-and-digit-separators-in-c-sharp/)

#### 二进制文字

固定值称为文字。文字是变量使用的值。在 **C# 7.0** **之前，有六种类型的文字**可用，它们是一个*整数*、*浮点*、*字符*、*字符串*、*空值*、*布尔文字*。在 C# 7.0 中，增加了一个名为**二进制文字**的文字。二进制文字用于将二进制值存储在变量中。二进制文字由 *0b* 表示。二进制文字主要用于位掩码。

**例:**

```cs
var num = 0b10001
```

这里，当编译器在变量值中看到 *0b* 时，它会自动将这个 *num* 视为二进制文字。如果您尝试在 C# 7.0 以下的编译器上运行此功能，那么编译器将会抛出一个错误，因为此功能是在 C# 7.0 中引入的，因此它将只在 C# 7.0 及以上的编译器上工作。

**例:**

```cs
// C# program to illustrate the 
// concept of binary literals.
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating binary literals 
        // by prefixing with 0b
        var num1 = 0b1001;
        var num2 = 0b01000011;

        Console.WriteLine("Value of Num1 is: " + num1);
        Console.WriteLine("Value of Num2 is: " + num2);
        Console.WriteLine("Char value of Num2 is: {0}",
                                 Convert.ToChar(num2));
    }
}
```

**输出:**

```cs
Value of Num1 is: 9
Value of Num2 is: 67
Char value of Num2 is: C

```
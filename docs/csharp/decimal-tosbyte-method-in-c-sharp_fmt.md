# Decimal.ToSByte() 方法（C#）

> 原文：[Decimal.ToSByte() Method in C#](https://www.geeksforgeeks.org/decimal-tosbyte-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 8 位有符号整数。用户还可以使用显式赋值运算符将十进制值转换为 8 位整数。

## 语法
```cs
public static SByte ToSByte(decimal value);
```
这里 `value` 是要转换的十进制数。

## 返回值
返回一个 8 位有符号整数，相当于指定的 `value`。

## 异常
如果指定值小于 `SByte.MinValue` 或大于 `SByte.MaxValue`，此方法将给出 `OverflowException`。

## 示例
以下程序说明了上述方法的使用：

### 例 1
```cs
// C# program to demonstrate the
// Decimal.ToSByte() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 127.5555M;
            Decimal dec2 = 04.2996m;

            // using Decimal.ToSByte(Decimal) Method
            sbyte val1 = Decimal.ToSByte(dec1);

            // using Decimal.ToSByte(Decimal) Method
            sbyte val2 = Decimal.ToSByte(dec2);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                              + "is : {0}", val1);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                              + "is : {0}",val2);

        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**
```cs
The SByte value is : 127
The SByte value is : 4
```

### 例 2
```cs
// C# program to demonstrate the
// Decimal.ToSByte() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // taking a decimal number
            // above the range of SByte
            Decimal dec1 = 129M;

            // Taking the maximum value
            // of Decimal
            Decimal dec2 = Decimal.MaxValue;

            // using Decimal.ToSByte(Decimal) Method
            // It will give error as decimal number
            // is above the range of SByte
            sbyte val1 = Decimal.ToSByte(dec1);

            // using Decimal.SByte(Decimal) Method
            // It will give error as Decimal.MaxValue
            // value is out of range from SByte
            int val2 = Decimal.ToSByte(dec2);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                              + "is : {0}",val1);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                              + "is : {0}",  val2);

        }

        catch (OverflowException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**
```cs
Exception Thrown: System.OverflowException
```

## 参考
*   [Decimal.ToSByte 方法（Microsoft Docs）](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tosbyte?view=netcore-2.2)
# UInt16。C# 中的最小值字段，示例

> 原文:[https://www . geesforgeks . org/uint 16-min value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-minvalue-field-in-c-sharp-with-examples/)

UInt16 Struct 的 **MinValue** 字段用于表示 16 位无符号整数的最小可能值，即 *ushort* 数据类型。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **0** 。如果整数值不在 *UInt16* 类型的范围内，它也从*overoveroverover exception*保存程序。UInt16 字段的主要用途是检查 *Int32* 值是否在 *UInt16* 类型的范围内，然后将其转换为 *UInt16* 值。

**语法:**

```cs
public const ushort MinValue = 0;
```

**返回值:**该字段始终返回 0。

**示例:**

```cs
// C# program to illustrate the
// UInt16.MinValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum value of UInt16 struct
        Console.WriteLine("Minimum Value is: " + UInt16.MinValue);

        // Taking an array of the 
        // unsigned long integer 
        // i.e UInt64 data type
        ulong[] num = {232146, 14343, 23122345, 4576863645437};

        // taking variable of UInt16 type
        ushort mynum;

        foreach(ulong n in num)
        {

            if (n >= UInt16.MinValue && n <= UInt16.MaxValue) {

                // using the method of Convert class
                // to convert Int64 to UInt16
                mynum = Convert.ToUInt16(n);

                Console.WriteLine("Conversion is Possible.");
            }

            else
            {
                Console.WriteLine("Not Possible");
            }
        }
    }
}
```

**输出:**

```cs
Minimum Value is: 0
Not Possible
Conversion is Possible.
Not Possible
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 16 . min value？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.minvalue?view=netstandard-2.1)
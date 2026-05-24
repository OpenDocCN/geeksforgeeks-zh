# UInt16。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/uint 16-maxvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-maxvalue-field-in-c-sharp-with-examples/)

UInt16 Struct 的 MaxValue 字段用于表示 16 位无符号整数的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 65535。其十六进制值为 *0xFFFF* 。如果整数值不在 *UInt16* 类型的范围内，用于避免*飞越异常*。

**语法:**

```cs
public const ushort MaxValue = 65535;
```

**返回值:**该字段始终返回 65535。

**示例:**

```cs
// C# program to illustrate the
// UInt16.MaxValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum value
        // of UInt16 struct
        Console.WriteLine("Maximum Value is: " + UInt16.MaxValue);

        // Taking an array of the 
        // unsigned long integer 
        // i.e UInt64 data type
        ulong[] num = {3422146, 7443, 43535776, 2342534654756123};

        // taking variable of UInt16 type
        ushort mynum;

        foreach(long n in num)
        {

            if (n >= UInt16.MinValue && n <= UInt16.MaxValue) 
                        {

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
Maximum Value is: 65535
Not Possible
Conversion is Possible.
Not Possible
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 16 . max value？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.maxvalue?view=netstandard-2.1)
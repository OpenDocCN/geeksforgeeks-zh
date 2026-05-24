# UInt32。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/uint 32-max value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-maxvalue-field-in-c-sharp-with-examples/)

UInt32 Struct 的 MaxValue 字段用于表示 32 位无符号整数的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 4294967295。其十六进制值为 *0xFFFFFFFF* 。通过在类型转换之前验证一个 *Int64* 值是否在 *UInt32* 类型的范围内，来避免运行时出现*溢出异常*。

**语法:**

```cs
public const uint MaxValue = 4294967295;
```

**返回值:**该字段始终返回 4294967295。

**示例:**

```cs
// C# program to illustrate the
// UInt32.MaxValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum value
        // of UInt32 struct
        Console.WriteLine("Maximum Value is: " + UInt32.MaxValue);

         // Taking an array of the 
        // unsigned long integer 
        // i.e UInt64 data type
        ulong[] num = {3422146, 732443, 42343535776, 2342534654756123};

        // taking variable of UInt32 type
        uint mynum;

        foreach(long n in num)
        {

            if (n >= UInt32.MinValue && n <= UInt32.MaxValue) 
            {

                // using the method of Convert class
                // to convert Int64 to UInt32
                mynum = Convert.ToUInt32(n);

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
Maximum Value is: 4294967295
Conversion is Possible.
Conversion is Possible.
Not Possible
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . max value？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.maxvalue?view=netstandard-2.1)
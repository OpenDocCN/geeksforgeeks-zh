# UInt32。C# 中的最小值字段，示例

> 原文:[https://www . geeksforgeeks . org/uint 32-min value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-minvalue-field-in-c-sharp-with-examples/)

UInt32 结构的**最小值**字段用于表示 32 位无符号整数的最小可能值，即 *uint* 数据类型。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **0** 。

**语法:**

```cs
public const uint MinValue = 0;
```

**返回值:**该字段始终返回 0。

**例:**

```cs
// C# program to illustrate the
// UInt32.MinValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum value of UInt32 struct
        Console.WriteLine("Minimum Value is: " + UInt32.MinValue);

        // Taking an array of the 
        // unsigned long integer 
        // i.e UInt64 data type
        ulong[] num = {34326, 32434, 12335546464565, 3434234786};

        // taking variable of UInt32 type
        uint mynum;

        foreach(ulong n in num)
        {

            if (n >= UInt32.MinValue && n <= UInt32.MaxValue) {

                // using the method of Convert class
                mynum = Convert.ToUInt32(n);

                Console.WriteLine("Conversion is Possible.");
            }

            else {
                Console.WriteLine("Not Possible");
            }
        }
    }
}
```

**输出:**

```cs
Minimum Value is: 0
Conversion is Possible.
Conversion is Possible.
Not Possible
Conversion is Possible.

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。uint 32。最小值？视图=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.minvalue?view=netstandard-2.1)
# Int32。C# 中的最小值字段，示例

> 原文:[https://www . geesforgeks . org/int 32-min value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-minvalue-field-in-c-sharp-with-examples/)

Int32 结构的**最小值**属性或字段用于表示 Int32 的最小可能值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **-2，147，483，648** 。其十六进制值为 *0x80000000* 。

**语法:**

```cs
public const int MinValue = -2147483648;
```

**返回值:**该字段始终返回-2147483648。

**示例:**

```cs
// C# program to illustrate the
// Int32.MinValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum value of Int32 struct
        Console.WriteLine("Minimum Value is: "+
                               Int32.MinValue);

        // Taking an array of long i.e Int64 data type
        long []num = {346, 434443, -33445, -442343263647};

        // taking variable of Int32 type
        int mynum;
        foreach(long n in num)
        {

            if(n >= Int32.MinValue && n <= Int32.MaxValue)
            {

                // using the method of Convert class
                mynum = Convert.ToInt32(n);
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
Minimum Value is: -2147483648
Conversion is Possible.
Conversion is Possible.
Conversion is Possible.
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . min value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.minvalue?view=netframework-4.7.2)
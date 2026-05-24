# Int32。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/int 32-maxvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-maxvalue-field-in-c-sharp-with-examples/)

Int32 Struct 的 MaxValue 字段或属性用于表示 Int32 的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 *2147483647* 。它的十六进制值是 *0x7FFFFFFF* 。用于在转换为 *Int32* 值时避免*飞越异常*。

**语法:**

```cs
public const int MaxValue = 2147483647;
```

**返回值:**该字段始终返回 2147483647。

**示例:**

```cs
// C# program to illustrate the
// Int32.MaxValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum value 
        // of Int32 struct
        Console.WriteLine("Maximum Value is: "+
                                Int32.MaxValue);

        // Taking an array of long i.e Int64 data type
        long[]num = {347, 49458, 345348534650436656};

        // taking variable of Int32 type
        int mynum;

        foreach(long n in num){

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
Maximum Value is: 2147483647
Conversion is Possible.
Conversion is Possible.
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . max value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.maxvalue?view=netframework-4.7.2)
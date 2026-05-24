# Int16。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/int 16-maxvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-maxvalue-field-in-c-sharp-with-examples/)

Int16 Struct 的 MaxValue 字段或属性用于表示 Int16 的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 32767。其十六进制值为 *0x7FFF* 。它用于在从具有较大范围上限的数字类型(如 *UInt16* 或 *Int32* 转换为 *Int16* 时避免出现*飞越异常*。

**语法:**

```cs
public const short MaxValue = 32767;
```

**返回值:**该字段始终返回 32767。

**示例:**

```cs
// C# program to illustrate the
// Int16.MaxValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum value 
        // of Int16 struct
        Console.WriteLine("Maximum Value is: "+
                                Int16.MaxValue);

        // Taking an array of long i.e Int64 data type
        long[]num = {345, -4677, -65245465445441, 44456564};

        // taking variable of Int16 type
        short mynum;
        foreach(long n in num){

            if(n >= Int16.MinValue && n <= Int16.MaxValue)
            {

                // using the method of Convert class
                // to convert Int64 to Int16 
                mynum = Convert.ToInt16(n);
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
Maximum Value is: 32767
Conversion is Possible.
Conversion is Possible.
Not Possible
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . max value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.maxvalue?view=netframework-4.7.2)
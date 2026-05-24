# Int16。C# 中的最小值字段，示例

> 原文:[https://www . geesforgeks . org/int 16-min value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-minvalue-field-in-c-sharp-with-examples/)

Int16 结构的**最小值**属性或字段用于表示 Int16 的最小可能值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **-32768** 。其十六进制值为 *0x8000* 。它还将程序从*overoverover over exception*保存下来，同时将具有更大更小范围的数字类型(如 Int64 和 Int32)转换为 *Int16* 。

**语法:**

```cs
public const short MinValue = -32768;
```

**返回值:**该字段始终返回-32768。

**示例:**

```cs
// C# program to illustrate the
// Int16.MinValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum value of Int16 struct
        Console.WriteLine("Minimum Value is: "+
                             Int16.MinValue);

        // Taking an array of long i.e Int64 data type
        long []num = {742346, 43443, -345, -7463647};

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
Minimum Value is: -32768
Not Possible
Not Possible
Conversion is Possible.
Not Possible

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . min value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.minvalue?view=netframework-4.7.2)
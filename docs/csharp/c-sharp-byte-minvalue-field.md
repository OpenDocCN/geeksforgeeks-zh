# C# | Byte。最小值字段

> 原文:[https://www.geeksforgeeks.org/c-sharp-byte-minvalue-field/](https://www.geeksforgeeks.org/c-sharp-byte-minvalue-field/)

字节结构的**最小值**字段用于表示字节数据类型的最小可能值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **0** 。

**语法:**

```cs
public const byte MinValue = 0;
```

**返回值:**该字段始终返回 0。

**例:**

```cs
// C# program to illustrate the
// Byte.MinValue field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum value of Byte struct
        Console.WriteLine("Minimum Value is: " + Byte.MinValue);

        // Taking an array of the
        // integers
        int[] num = {12, 45, 1235, 5342};

        // taking variable of Byte type
        byte mynum;

        foreach(int n in num)
        {

            if (n >= Byte.MinValue && n <= Byte.MaxValue)
            {

                // using the method of Convert class
                mynum = Convert.ToByte(n);

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
Conversion is Possible.
Conversion is Possible.
Not Possible
Not Possible

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。字节。最小值？视图=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.byte.minvalue?view=netstandard-2.1)
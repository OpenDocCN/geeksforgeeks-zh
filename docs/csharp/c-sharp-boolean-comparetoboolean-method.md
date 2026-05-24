# C# |布尔型。比较(布尔)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-boolean-compare tool-method/](https://www.geeksforgeeks.org/c-sharp-boolean-comparetoboolean-method/)

**布尔。比较(布尔)方法**用于将当前实例与指定的布尔对象进行比较，并返回它们相对值的指示。

**语法:**

```cs
public int CompareTo (bool value);
```

这里，*值*是一个布尔对象，用于与当前实例进行比较。

**返回值:**这个方法返回一个 32 位有符号整数，表示这个实例和*值*的相对顺序。

*   **is less than zero:** If this instance is *false* , the value is *true* .
*   **Zero:** If this instance and value are equal (either both are *true* or both are *false* ).
*   **is greater than zero:** If this instance is *true,* is *false* .

**例:**

```cs
// C# program to demonstrate
// Boolean.CompareTo(Boolean)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring val1 and val2
        bool val1, val2;

        // intializing the val1,
        // and val2
        val1 = true;
        val2 = false;

        // using CompareTo method
        int i = val2.CompareTo(val1);

        // checking the condition
        if (i > 0)
            Console.Write("val2 is greater than val1");

        else if (i < 0)
            Console.Write("val2 is less than val1");

        else
            Console.Write("val1 is equal to val1");
    }
}
```

**输出:**

```cs
val2 is less than val1

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。布尔型。相比于？view = net framework-4.8 # System _ Boolean _ compare to _ System _ Boolean _](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.compareto?view=netframework-4.8# System_Boolean_CompareTo_System_Boolean_)
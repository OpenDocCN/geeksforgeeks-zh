# C# | CharEnumerator。复位()方法

> 原文:[https://www . geesforgeks . org/c-sharp-charenumerator-reset-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-reset-method/)

**CharEnumerator。重置方法**用于将索引初始化到枚举字符串第一个字符之前的逻辑位置。

**语法:**

```cs
public void Reset ();
```

下面是说明使用**字符枚举器的程序。重置()**方法:

**例 1:**

```cs
// C# program to illustrate the
// use of CharEnumerator.Reset()
// Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "The Sun rises in the East and sets in the West.";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the string
        while (chEnum.MoveNext())
            Console.Write(chEnum.Current);

        // Reset the CharEnumerator object
        chEnum.Reset();
        Console.WriteLine();

        // Printing the string again
        while (chEnum.MoveNext())
            Console.Write(chEnum.Current);
    }
}
```

**输出:**

```cs
The Sun rises in the East and sets in the West.
The Sun rises in the East and sets in the West.

```
# 如何在 C# 中找到 StringBuilder 的最大容量

> 原文:[https://www . geesforgeks . org/how-to-find-a-max capacity-of-stringbuilder-in-c-sharp/](https://www.geeksforgeeks.org/how-to-find-the-maxcapacity-of-a-stringbuilder-in-c-sharp/)

**StringBuilder。最大容量属性**用于获取该实例的最大容量。

> **语法:**public int MaxCapacity { get；}
> 
> **属性值:**返回*系统类型的最大字符数。Int32* 这个实例可以成立。

**注:**本次实施最大容量为 *Int32。最大值*。但是，该值是特定于实现的，在其他或以后的实现中可能会有所不同。通过调用 StringBuilder(Int32，Int32)构造函数，可以显式设置 StringBuilder 对象的最大容量。

**例:**

```cs
// C# program to demonstrate
// the MaxCapacity Property
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // Create a StringBuilder object
        // with a String passed as parameter
        StringBuilder str1 = 
         new StringBuilder("GeeksforGeeks");

        // printing the MaxCapacity of str1
        Console.WriteLine("Maximum Capacity of str1 is: " 
                                     + str1.MaxCapacity);

        // Create a StringBuilder object
        StringBuilder str2 = new StringBuilder();

        // printing the MaxCapacity of str2
        Console.WriteLine("Maximum Capacity of str2 is: " 
                                     + str2.MaxCapacity);
    }
}
```

**输出:**

```cs
Maximum Capacity of str1 is: 2147483647
Maximum Capacity of str2 is: 2147483647

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。文字。stringbuilder。最大容量？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.maxcapacity?view=netframework-4.7.2)
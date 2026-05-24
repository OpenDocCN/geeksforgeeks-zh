# 如何在 C# 中移除 StringBuilder 中的所有字符

> 原文:[https://www . geeksforgeeks . org/如何从 c-sharp 中删除所有字符/](https://www.geeksforgeeks.org/how-to-remove-all-characters-from-stringbuilder-in-c-sharp/)

**StringBuilder。清除方法**用于从当前字符串生成器实例中移除所有字符。

**语法:**

```cs
public System.Text.StringBuilder Clear ();
```

它返回一个长度为零的 StringBuilder 对象。

**注意:**

*   Clear is a convenient method which is equivalent to setting the Length property of the current instance to 0 (zero).
*   Calling the Clear method does not modify the Capacity or MaxCapacity properties of the current instance.

**例:**

```cs
// C# program to demonstrate
// the Clear() Method
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating a StringBuilder object
        StringBuilder sb1 = new StringBuilder("GeeksforGeeks");

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                                             sb1.ToString(), sb1.Length);

        // using the method
        sb1.Clear();

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                                             sb1.ToString(), sb1.Length);

        sb1.Append("This  is C# Tutorials.");

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                                             sb1.ToString(), sb1.Length);
    }
}
```

**输出:**

```cs
The String is: GeeksforGeeks 
Total characters -- 13
The String is:  
Total characters -- 0
The String is: This  is C# Tutorials. 
Total characters -- 22

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。文字。stringbuilder。明白了吗？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.clear?view=netframework-4.7.2)
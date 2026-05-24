# StringBuilder。C# 中的 ToString 方法

> 原文:[https://www . geeksforgeeks . org/stringbuilder-tostring-method-in-c-sharp/](https://www.geeksforgeeks.org/stringbuilder-tostring-method-in-c-sharp/)

此方法用于将此实例的值转换为字符串。创建并初始化一个新的字符串对象，以从该字符串生成器对象中获取字符序列，然后由 ToString()返回字符串。对象包含的对该序列的后续更改不会影响字符串的内容。

> **语法:**公共覆盖字符串 ToString()；
> 
> **返回值:**该方法返回 StringBuilder 对象所包含的表示数据的字符串。

下面的程序说明了*字符串生成器。ToString()* 方法:

**例 1:**

```cs
// C# program to demonstrate
// the ToString() Method
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
          = new StringBuilder("GeeksForGeeks");

        // print string
        Console.WriteLine("String contains = "
                            + str.ToString());
    }
}
```

**Output:**

```cs
String contains = GeeksForGeeks

```

**例 2:**

```cs
// C# program to demonstrate
// the ToString() Method
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str = 
             new StringBuilder("GeeksforGeeks Contribute");

        // print string
        Console.WriteLine("String contains = "
                          + str.ToString());
    }
}
```

**Output:**

```cs
String contains = GeeksforGeeks Contribute

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . stringbuilder . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.tostring?view=netframework-4.7.2)
# 如何在 C# 中找到 StringBuilder 的长度

> 原文:[https://www . geeksforgeeks . org/如何找到 c-sharp 中 stringbuilder 的长度/](https://www.geeksforgeeks.org/how-to-find-the-length-of-the-stringbuilder-in-c-sharp/)

*StringBuilder。长度属性*用于获取或设置当前 StringBuilder 对象的长度。

> **语法:**public int Length { get；设置；}
> 返回当前实例的长度。
> 
> **异常:**如果为设置操作指定的值小于零或大于最大容量，该属性将给出*ArgumentOutOfRangeException*。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to demonstrate
// the Length() Property
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        // with a String passed as parameter
        StringBuilder str = new StringBuilder("WelcomeGeeks");

        // print string
        Console.WriteLine("String = "
                   + str.ToString());

        // get length of StringBuilder object
        int length = str.Length;

        // print length
        Console.WriteLine("length of String = "
                                     + length);
    }
}
```

**Output:**

```cs
String = WelcomeGeeks
length of String = 12

```

**例 2:**

```cs
// C# program to demonstrate
// the Length() Property
using System;
using System.Text;

class GFG {
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        // with a String passed as parameter
        StringBuilder str = new StringBuilder("India is Great");

        // print string
        Console.WriteLine("String = "
                   + str.ToString());

        // get length of StringBuilder object
        int length = str.Length;

        // print length
        Console.WriteLine("length of String = "
                                     + length);
    }
}
```

**Output:**

```cs
String = India is Great
length of String = 14

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . stringbuilder . length？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.length?view=netframework-4.7.2)
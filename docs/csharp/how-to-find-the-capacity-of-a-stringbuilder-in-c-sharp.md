# 如何在 C# 中找到字符串生成器的容量

> 原文:[https://www . geeksforgeeks . org/如何找到 c-sharp 中字符串构建器的容量/](https://www.geeksforgeeks.org/how-to-find-the-capacity-of-a-stringbuilder-in-c-sharp/)

**StringBuilder。容量属性**用于获取或设置当前实例分配的内存中可以包含的最大字符数。

> **语法:**公共 int Capacity { get 设置；}
> **返回值:**此属性将返回当前实例分配的内存中可以包含的最大字符数。其值的范围可以从*长度*到*最大容量*。
> **异常**:如果为设置操作指定的值小于此实例的当前长度，或者为设置操作指定的值大于最大容量，此属性将给出*ArgumentOutOfRangeException*。

下面的程序将说明上述属性的使用:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// the Capacity() Property
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object,
        // default capacity will be 16
        StringBuilder str = new StringBuilder();

        // get default capacity
        int cap = str.Capacity;

        Console.WriteLine("Default Capacity of StringBuilder = "
                                                         + cap);

        // add the String to StringBuilder Object
        str.Append("Geek");

        // get capacity
        cap = str.Capacity;

        // print the result
        Console.WriteLine("StringBuilder = " + str);
        Console.WriteLine("Current Capacity of StringBuilder = "
                                                         + cap);
    }
}
```

**Output:** 

```cs
 Capacity of StringBuilder = 16
StringBuilder = Geek
Current Capacity of StringBuilder = 16
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// the Capacity() Property
using System;
using System.Text;

class GFG {
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        // with a String passed as parameter
        StringBuilder str =
           new StringBuilder("WelcomeGeeks");

        // get capacity
        int capacity = str.Capacity;

        // print the result
        Console.WriteLine("StringBuilder = " + str);
        Console.WriteLine("Capacity of StringBuilder = "
                                            + capacity);
    }
}
```

**Output:** 

```cs
StringBuilder = WelcomeGeeks
Capacity of StringBuilder = 16
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . string builder . capacity？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.capacity?view=netframework-4.7.2)
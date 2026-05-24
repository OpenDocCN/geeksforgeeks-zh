# 乌利。带有示例的 C# 中的 DnsSafeHost 属性

> 原文:[https://www . geesforgeks . org/uri-dnssafehost-property-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-dnssafehost-property-in-c-sharp-with-examples/)

**乌利。DnsSafeHost 属性**是实例属性，用于获取一个可以安全用于 DNS 解析的未转义主机名。

**语法:**

```cs
public string DnsSafeHost { get; }

```

**返回值:**这个属性返回**字符串**，它以适合 DNS 解析的格式返回 URI 的主机部分，如果已经适合解析它就返回原始的主机字符串。

**异常:**如果实例是相对的 URI，并且该属性仅对绝对的 URI 有效，则该属性将给出 ***无效操作异常*** 。

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Uri.DnsSafeHost property
using System;
using System.Globalization;

class GFG {

  // Main Method
public static void Main() {
    // Declaring and initializing value1
    Uri v1 = new Uri("https://www.geeksforgeeks.org/greedy-algorithms/# standardGreedyAlgorithms");

    // using DnsSafeHost property
    Console.WriteLine("Uri DnsSafeHost: " + v1.DnsSafeHost);
  }
}
```

**输出:**

```cs
Hostname: www.geeksforgeeks.org

```

**例 2:**

## C#

```cs
// C# program to demonstrate the  
// Uri.DnsSafeHost property  
using System;  
using System.Globalization;  

class GFG {  

     // Main Method  
    public static void Main()  
    {  
        // Declaring and initializing value1  
        Uri  v1 = new Uri("https://docs.microsoft.com/en-us/dotnet/api/system.uri.isloopback?view=netcore-3.1");

        // using DnsSafeHost property  
        Console.WriteLine("Hostname: "+ v1.DnsSafeHost);  
    }  
}
```

**输出:**

```cs
Hostname: docs.microsoft.com`

```
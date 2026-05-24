# 乌利。用示例

在 C# 中返回属性

> 原文:[https://www . geesforgeks . org/uri-isloop back-property-in-c-sharp-with-example/](https://www.geeksforgeeks.org/uri-isloopback-property-in-c-sharp-with-example/)

**乌利。IsLoopback** 属性是 Uri 类的属性，用于检查指定的 Uri 是否引用了本地主机。

**语法:**

```cs
public bool IsLoopback { get; } 

```

**返回值:**这个属性的返回类型是布尔值，如果这个 Uri 引用了本地主机，则返回 true，否则返回 false。

**异常:**如果此实例表示相对 Uri，则此属性将给出无效操作异常，因为此属性仅适用于绝对 URI。

**例 1:**

## C#

```cs
// C# program to demonstrate the  
// Uri.IsLoopback property  
using System;  
using System.Globalization;  

class GFG {  

     // Main Method  
    public static void Main()  
    {  
        // Declaring and initializing value1  
        Uri  v1 = new Uri("https://www.geeksforgeeks.org/");  

        // using IsLoopback property  
        bool status = v1.IsLoopback;  

        // checking the status  
        if (status)  
            Console.WriteLine("Given Uri is a reference of localhost");  
        else
            Console.WriteLine("Given Uri is not reference of localhost");  
    }  
}
```

**输出:**

```cs
Given Uri is not reference of localhost

```

**例 2:**

## C#

```cs
// C# program to demonstrate the  
// Uri.IsLoopback property  
using System;  
using System.Globalization;  

class GFG {  

     // Main Method  
    public static void Main()  
    {  
        // Declaring and initializing value1  
        Uri  v1 = new Uri("http://localhost");  

        // using IsLoopback property  
        bool status = v1.IsLoopback;  

        // checking the status  
        if (status)  
            Console.WriteLine("Given Uri is a reference of localhost");  
        else
            Console.WriteLine("Given Uri is not reference of localhost");  
    }  
}
```

**输出:**

```cs
Given Uri is a reference of localhost

```
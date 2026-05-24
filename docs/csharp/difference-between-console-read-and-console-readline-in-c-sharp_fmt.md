# C# 中 Console.Read 与 Console.ReadLine 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-console-read-and-console-readline-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-console-read-and-console-readline-in-c-sharp/)

在 [`C#`](https://www.geeksforgeeks.org/csharp-programming-language/) 中，要从标准输入设备获取输入，使用以下方法：[`Console.Read()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.read) 和 [`Console.ReadLine()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.readline) 方法。[`Console`](https://learn.microsoft.com/en-us/dotnet/api/system.console) 是 [`System`](https://learn.microsoft.com/en-us/dotnet/api/system) 命名空间的预定义类。而 [`Read()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.read) 和 [`ReadLine()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.readline) 都是 [`Console`](https://learn.microsoft.com/en-us/dotnet/api/system.console) 类的方法。

[`Console.Read()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.read) 和 [`Console.ReadLine()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.readline) 唯一的区别是：[`Console.Read()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.read) 用于从标准输入设备只读单个字符，而 [`Console.ReadLine()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.readline) 用于从标准输入设备读取一行或一整串。

**程序 1：** [`Console.Read()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.read) 示例（C#）。

## C\#

```cs
// C# program to show the difference
// between Console.Read() and 
// Console.ReadLine() method

using System;

public class GFG{

    static void Main(string[] args)
    {
        // use of Read() method
        Console.Write(Convert.ToChar(Console.Read()));
        Console.Write(Convert.ToChar(Console.Read()));
        Console.Write(Convert.ToChar(Console.Read()));
    }
}
```

**输入：**

```cs
Geeks
```

**输出：**

```cs
Gee
```

**程序 2：** [`Console.ReadLine()`](https://learn.microsoft.com/en-us/dotnet/api/system.console.readline) 示例（C#）。

## C\#

```cs
// C# program to show the difference
// between Console.Read() and 
// Console.ReadLine() method

using System;

public class GFG{

    static void Main(string[] args)
    {
        // use of ReadLine() method
        Console.Write(Console.ReadLine());
        Console.Write(Console.ReadLine());
        Console.Write(Console.ReadLine());
    }
}
```

**输入：**

```cs
Geeks
For
Geeks
```

**输出：**

```cs
GeeksForGeeks
```

上述代码中，**程序 1** 显示只读单个字符，**程序 2** 显示读取字符串，直到找不到新的行字符。
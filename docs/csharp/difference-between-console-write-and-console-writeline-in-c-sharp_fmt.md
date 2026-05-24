# 控制台之间的区别：Write 和 WriteLine 在 C# 中的使用

> 原文：[https://www.geeksforgeeks.org/difference-between-console-write-and-console-writeline-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-console-write-and-console-writeline-in-c-sharp/)

在 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 中，要在控制台输出屏幕上打印数据，可以使用以下方法：`Console.Write()` 和 `Console.WriteLine()` 方法。`Console` 是 `System` 命名空间中的一个预定义类。而 `Write()` 和 `WriteLine()` 都是 `Console` 类的方法。

`Write()` 和 `WriteLine()` 唯一的区别在于：`Console.Write` 用于打印数据但不打印新行，而 `Console.WriteLine` 用于打印数据并同时打印一个新行。

**程序 1：** `Console.Write()` 的 C# 示例

## C#

```cs
// C# program to show the difference
// between Console.Write and 
// Console.WriteLine

using System;

public class GFG{

    static void Main(string[] args)
    {
        // use of Write() method
        Console.Write("Geeks");
        Console.Write("For");
        Console.Write("Geeks");
    }
}
```

**输出：**

```cs
GeeksForGeeks
```

**程序 2：** `Console.WriteLine()` 的 C# 示例

## C#

```cs
// C# program to show the difference
// between Console.Write and 
// Console.WriteLine

using System;

public class GFG{

    static void Main(string[] args)
    {
        // use of WriteLine() method
        Console.WriteLine("Geeks");
        Console.WriteLine("For");
        Console.WriteLine("Geeks");
    }
}
```

**输出：**

```cs
Geeks
For
Geeks
```

在上面的代码中，**程序 1** 显示的输出**不包含**每个控制台输出后的换行符，而**程序 2** 显示的输出**包含**每个控制台输出后的换行符。
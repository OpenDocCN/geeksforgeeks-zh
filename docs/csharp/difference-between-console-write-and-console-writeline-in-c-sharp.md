# 控制台之间的区别。写和控制台。C# 中的 WriteLine

> 原文:[https://www . geeksforgeeks . org/console-write-and-console-write line-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-console-write-and-console-writeline-in-c-sharp/)

在[**c#**](https://www.geeksforgeeks.org/csharp-programming-language/)中，要在控制台输出屏幕上打印数据，使用以下方法–**控制台。写()**和**控制台。WriteLine()** 方法。**控制台** 是**系统**命名空间的预定义类。而 **Write()** 和 **WriteLine()** 都是控制台类方法。

**Write()**和 **WriteLine()** 唯一的区别就是控制台。Write 用于打印数据不打印新行，而控制台。WriteLine 用于打印数据以及打印新行。

**程序 1:** 控制台示例。用 C# 写()

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

**输出:**

```cs
GeeksForGeeks

```

**程序 2:** 控制台示例。C# 中的 WriteLine()。

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

**输出:**

```cs
Geeks
For
Geeks

```

在上面的代码中，**程序 1** 显示输出**而不包括每个控制台输出中的换行符**，**程序 2** 显示输出**包括每个控制台输出中的换行符**。
# 控制台之间的区别。阅读并控制台。C# 中的 ReadLine

> 原文:[https://www . geeksforgeeks . org/console-read-and-console-read line-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-console-read-and-console-readline-in-c-sharp/)

在[**c#**](https://www.geeksforgeeks.org/csharp-programming-language/)中，要从标准输入设备获取输入，使用以下方法–**控制台。阅读()**和**控制台。ReadLine()** 方法。**控制台** 是**系统**命名空间的预定义类。而 **Read()** 和 **ReadLine()** 都是控制台类方法。

**Read()**和 **ReadLine()** 唯一的区别就是控制台。Read 用于从标准输出设备只读单个字符，而控制台。ReadLine 用于从标准输出设备读取一行或一串。

**程序 1:** 控制台示例。用 C# 阅读()。

## C#

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

**输入:**

```cs
Geeks

```

**输出:**

```cs
Gee

```

**程序 2:** 控制台示例。C# 中的 ReadLine()。

## C#

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

**输入:**

```cs
Geeks
For
Geeks

```

**输出:**

```cs
GeeksForGeeks

```

上述代码中，**程序 1** 显示只读单个字符，**程序 2** 显示读取字符串，直到找不到新的行字符。
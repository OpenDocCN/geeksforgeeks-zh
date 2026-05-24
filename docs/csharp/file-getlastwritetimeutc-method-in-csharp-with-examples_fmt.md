# File.GetLastWriteTimeUtc(String) 方法详解（C# 示例）

> 原文：[https://www.geeksforgeeks.org/file-getlastwritetimeutc-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-getlastwritetimeutc-method-in-csharp-with-examples/)

`File.GetLastWriteTimeUtc(String)` 是一个内置的 `File` 类方法，用于返回指定文件或目录上次写入的日期和时间，以协调世界时（UTC）表示。

**语法：**

```cs
public static DateTime GetLastWriteTimeUtc (string path);
```

**参数：** 该函数接受一个参数，如下所示：

*   `path`：指定的文件路径。

**异常：**

*   `UnauthorizedAccessException`：调用方没有所需的权限。
*   `ArgumentException`：`path` 是一个零长度字符串，只包含空格或一个或多个无效字符，如 `InvalidPathChars` 所定义。
*   `ArgumentNullException`：`path` 为空。
*   `PathTooLongException`：给定的路径、文件名或两者都超过了系统定义的最大长度。
*   `NotSupportedException`：`path` 的格式无效。

**返回值：** 以协调世界时（UTC）返回指定文件或目录上次写入的日期和时间。

以下是说明 `File.GetLastWriteTimeUtc()` 方法的程序。

**程序 1：** 在运行下面的代码之前，创建一个文件 `file.txt`，内容如下所示：

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

```cs
// C# program to illustrate the usage
// of File.GetLastWriteTimeUtc(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Calling GetLastWriteTimeUtc() function
        DateTime dt = File.GetLastWriteTimeUtc(myfile);

        // Getting the last write time in UTC
        Console.WriteLine("The last write time in "+
                  "UTC for this file was {0}.", dt);
    }
}
```

**执行：**

```cs
The last write time in UTC for this file was 4/3/2020 12:00:00 AM.
```

**程序 2：** 在运行下面的代码之前，创建一个文件，如下所示：

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

```cs
// C# program to illustrate the usage
// of File.GetLastWriteTimeUtc(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Setting the date
        File.SetLastWriteTime(myfile, new DateTime(2020, 4, 3));

        // Calling GetLastWriteTimeUtc() function
        DateTime dt = File.GetLastWriteTimeUtc(myfile);

        // Getting the last write time in UTC
        Console.WriteLine("The last write time in"+
                " UTC for this file was {0}.", dt);
    }
}
```

**执行：**

```cs
The last write time in UTC for this file was 4/3/2020 12:00:00 AM.
```
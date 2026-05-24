# 文件。C# 中的 `SetLastAccessTime()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/file-setlastaccesstime-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-setlastaccesstime-method-in-csharp-with-examples/)

`File.SetLastAccessTime(String, DateTime)` 是一个内置的 `File` 类方法，用于设置上次访问指定文件的日期和时间。

**语法：**

```cs
public static void SetLastAccessTime (string path, DateTime lastAccessTime);
```

**参数：** 该函数接受两个参数，如下所示：

*   `Path`：这是要设置访问日期和时间信息的文件。
*   `Last Access Time`：这是指定的上次本地访问的日期和时间。

**异常：**

*   `ArgumentException`：`path` 是一个零长度字符串，只包含空格或一个或多个无效字符，如 `InvalidPathChars` 所定义。
*   `ArgumentNullException`：`path` 为空。
*   `PathTooLongException`：指定的 `path`、文件名或两者都超过了系统定义的最大长度。
*   `FileNotFoundException`：未找到指定的 `path`。
*   `UnauthorizedAccessException`：调用方没有所需的权限。
*   `NotSupportedException`：`path` 的格式无效。
*   `ArgumentOutOfRangeException`：`lastAccessTime` 指定的值超出了此操作允许的日期或时间范围。

下面是说明 `File.SetLastAccessTime()` 方法的程序。

## 程序 1

在运行下面的代码之前，创建了一个文件 `file.txt`，内容如下所示：

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

```cs
// C# program to illustrate the usage
// of File.SetLastAccessTime() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Calling the SetLastAccessTime() function
        // to set last access date and time
        File.SetLastAccessTime(myfile, new DateTime(2020, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTime(myfile);
        Console.WriteLine("The last access date and"+
                 " time for this file was {0}.", dt);
    }
}
```

**输出：**

```cs
The last access date and time for this file was 5/4/2020 4:05:07 AM.
```

## 程序 2

最初没有创建文件。在代码下面，它自己创建了一个文件 `file.txt` 并打印了最后一次访问的日期和时间。

```cs
// C# program to illustrate the usage
// of File.SetLastAccessTime() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Checking the existence of the file
        if (!File.Exists(path)) {
            File.Create(path);
        }

        // Calling the SetLastAccessTime() function
        // to set last access date and time
        File.SetLastAccessTime(path, new DateTime(2019, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTime(path);
        Console.WriteLine("The last access date and "+
                  "time for this file was {0}.", dt);
    }
}
```

**输出：**

```cs
The last access date and time for this file was 5/4/2019 4:05:07 AM.
```
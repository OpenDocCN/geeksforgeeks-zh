# C# File.WriteAllText(String, String, Encoding) 方法及示例

> 原文：[https://www.geeksforgeeks.org/file-writealltextstring-string-encoding-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-writealltextstring-string-encoding-method-in-c-sharp-with-examples/)

`File.WriteAllText(String, String, Encoding)` 是一个内置的 `File` 类方法，用于创建新文件，使用指定的编码将指定的字符串写入文件，然后关闭文件。如果目标文件已经存在，它将被覆盖。

## 语法

```cs
public static void WriteAllText (string path, string contents, System.Text.Encoding encoding);
```

## 参数

该函数接受三个参数，如下所示：

*   `Path`：这是将要写入指定字符串的指定文件。
*   `Directory`：这是一个指定要写入文件的字符串。
*   `Encoding`：这是应用于字符串的指定编码。

## 异常

*   `ArgumentException`：`path` 是一个零长度字符串，只包含空格或一个或多个无效字符，如 `InvalidPathChars` 所定义。
*   `ArgumentNullException`：`path` 为空。
*   `PathTooLongException`：指定的 `path`、文件名或两者都超过了系统定义的最大长度。
*   `DirectoryNotFoundException`：指定的 `path` 无效。
*   `IOException`：打开文件时出现输入/输出错误。
*   `UnauthorizedAccessException`：`path` 指定了一个只读文件。或者 `path` 指定了一个隐藏的文件。或者当前平台不支持此操作。或者 `path` 指定了一个目录。或者调用者没有所需的权限。
*   `NotSupportedException`：`path` 的格式无效。
*   `SecurityException`：调用方没有所需的权限。

下面是说明 `File.WriteAllText` 方法的程序。

## 程序 1

最初，没有创建文件。下面代码自己创建一个文件 `file.txt` 并将指定的字符串数组写入文件。

```cs
// C# program to illustrate the usage
// of File.WriteAllText(String, String,
// Encoding) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Creating a string
        string createText = "GeeksforGeeks" + Environment.NewLine;

        // Writing the string to the file
        File.WriteAllText(path, createText, Encoding.UTF8);

        // Reading the contents of the file
        string readText = File.ReadAllText(path, Encoding.UTF8);
        Console.WriteLine(readText);
    }
}
```

## 输出

```cs
GeeksforGeeks
```

运行上述代码后，显示上述输出，并创建一个新文件 `file.txt`，如下所示：

![file.txt](img/d2a0cf46f82a72b41a2fdc5d7a3848b6.png)

## 程序 2

最初创建一个文件 `file.txt`，内容如下：

![file.txt](img/d2a0cf46f82a72b41a2fdc5d7a3848b6.png)

下面的代码用指定的字符串覆盖文件内容。

```cs
// C# program to illustrate the usage
// of File.WriteAllText(String, String,
// Encoding) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Creating a string
        string createText = "GFG is a cs portal." + Environment.NewLine;

        // Overwriting the string to the file
        File.WriteAllText(path, createText, Encoding.UTF8);

        // Reading the contents of the file
        string readText = File.ReadAllText(path, Encoding.UTF8);
        Console.WriteLine(readText);
    }
}
```

## 输出

```cs
GFG is a cs portal.
```

运行上述代码后，显示上述输出，文件 `file.txt` 内容如下图所示：

![file.txt](img/54353c657057c5a375c0427558af7455.png)
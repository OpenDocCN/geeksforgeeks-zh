# File.Open(String, FileMode, FileAccess, FileShare) 方法详解及示例

> 原文：[https://www.geeksforgeeks.org/file-openstring-filemode-fileaccess-fileshare-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-openstring-filemode-fileaccess-fileshare-method-in-c-sharp-with-examples/)

`File.Open(String, FileMode, FileAccess, FileShare)` 是一个内置的 `File` 类方法，用于在指定的路径上打开文件流，具有指定的读、写或读/写访问权限、模式以及共享选项。

## 语法

```csharp
public static FileStream Open(string path, FileMode mode, FileAccess access, FileShare share);
```

## 参数

该函数接受四个参数：

*   `path`：要打开的文件。
*   `mode`：此模式值指定如果文件不存在是否创建新文件，并确定是保留还是覆盖现有文件的内容。
*   `access`：此值指定可以在文件上执行的操作。
*   `share`：此值指定其他线程对文件的访问类型。

## 异常

*   `ArgumentException`：`path` 是零长度字符串、仅包含空格或包含一个或多个由 `InvalidPathChars` 定义的无效字符。或者 `access` 指定读取，而 `mode` 指定创建、新建、截断或追加。
*   `ArgumentNullException`：`path` 为空。
*   `PathTooLongException`：指定的 `path`、文件名或两者都超过了系统定义的最大长度。
*   `DirectoryNotFoundException`：指定的路径无效。
*   `IOException`：打开文件时出现输入/输出错误。
*   `UnauthorizedAccessException`：`path` 指定了一个只读文件，而 `access` 未指定读取。或者 `path` 指定了一个目录。或者调用者没有所需的权限。或者 `mode` 为 `Create`，而指定的文件是隐藏文件。
*   `ArgumentOutOfRangeException`：`mode`、`access` 或 `share` 指定了无效值。
*   `FileNotFoundException`：在 `path` 中指定的文件未找到。
*   `NotSupportedException`：`path` 的格式无效。

## 返回值

返回指定路径上的 `FileStream`，具有指定的读、写或读/写访问模式和指定的共享选项。

以下是说明 `File.Open(String, FileMode, FileAccess, FileShare)` 方法的程序。

### 程序 1

下面的代码创建一个临时文件，将一些指定的内容写入其中，打开该文件并打印其内容。这里不允许文件共享。

```csharp
// C# program to illustrate the usage
// of File.Open(String, FileMode,
// FileAccess, FileShare) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Creating a temporary file
        string path = Path.GetTempFileName();
        using(FileStream fs = File.Open(path, FileMode.Open))
        {
            // Putting some contents
            Byte[] info = new UTF8Encoding(true).GetBytes("GFG is a CS Portal.");
            fs.Write(info, 0, info.Length);
        }

        // Opening the stream and reading it back.
        using(FileStream fs = File.Open(path, FileMode.Open,
                           FileAccess.Read, FileShare.None))
        {
            byte[] b = new byte[1024];
            UTF8Encoding temp = new UTF8Encoding(true);

            while (fs.Read(b, 0, b.Length) > 0) {
                Console.WriteLine(temp.GetString(b));
            }
        }
    }
}
```

**执行：**

```
GFG is a CS Portal.
```

### 程序 2

最初创建一个文件 `file.txt`，内容如下所示：

![file.txt](img/355ab557f458f371c9801a73f6a6e8b5.png)

该代码将打开文件 `file.txt` 并打印其内容，不允许文件共享。

```csharp
// C# program to illustrate the usage
// of File.Open(String, FileMode,
// FileAccess, FileShare) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file path
        string path = @"file.txt";

        // Opening above file and reading it back.
        using(FileStream fs = File.Open(path, FileMode.Open,
                           FileAccess.Read, FileShare.None))
        {
            byte[] b = new byte[1024];
            UTF8Encoding temp = new UTF8Encoding(true);

            while (fs.Read(b, 0, b.Length) > 0) {
                // Printing the file contents
                Console.WriteLine(temp.GetString(b));
            }
        }
    }
}
```

**执行：**

```
GeeksforGeeks
```
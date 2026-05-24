# File.Open(String, FileMode) 方法详解

> 原文：[https://www.geeksforgeeks.org/file-openstring-filemode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-openstring-filemode-method-in-c-sharp-with-examples/)

`File.Open(String, FileMode)` 是一个内置的 `File` 类方法，用于在指定路径上打开具有读/写访问权限的 `FileStream`，不共享。

## 语法

```cs
public static System.IO.FileStream Open (string path, System.IO.FileMode mode);
```

## 参数

该函数接受两个参数，如下所示：

*   `Source file name`：这是要打开的指定文件。
*   `Mode`：此模式值指定如果文件不存在是否创建新文件，并决定是保留还是覆盖现有文件的内容。

## 异常

*   `ArgumentException`：`path` 是一个零长度字符串，只包含空格或一个或多个无效字符（如 `InvalidPathChars` 所定义）。
*   `ArgumentNullException`：`path` 为空。
*   `PathTooLongException`：给定的 `path`、`filename`，或者两者都超过了系统定义的最大长度。
*   `DirectoryNotFoundException`：指定的 `path` 无效。
*   `IOException`：打开文件时出现输入/输出错误。
*   `UnauthorizedAccessException`：`path` 指定了一个只读文件。或者当前平台不支持此操作。或者 `path` 指定了一个目录。或者调用者没有所需的权限。或者 `mode` 指定为 `Create`，而指定文件是隐藏文件。
*   `ArgumentOutOfRangeException`：`mode` 指定了无效值。
*   `FileNotFoundException`：在 `path` 中指定的文件未找到。
*   `NotSupportedException`：`path` 的格式无效。

## 返回值

返回以指定 `mode` 和 `path` 打开的文件流，具有读/写访问权限，不共享。

以下是说明 `File.Open(String, FileMode)` 方法的程序。

### 示例 1

下面的代码创建一个临时文件，将一些指定的内容写入其中，然后打开文件并打印出来。

```cs
// C# program to illustrate the usage
// of File.Open(String, FileMode) method

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
        using(FileStream fs = File.Open(path, FileMode.Open))
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
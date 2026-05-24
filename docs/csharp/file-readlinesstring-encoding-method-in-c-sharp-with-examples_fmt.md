# File.ReadLines(String, Encoding) 方法详解及示例

> 原文：[https://www.geeksforgeeks.org/file-readlinesstring-encoding-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-readlinesstring-encoding-method-in-c-sharp-with-examples/)

`File.ReadLines(String, Encoding)` 是一个内置的 `File` 类方法，用于读取具有指定编码的文件的行。

## 语法

> `public static System.Collections.Generic.IEnumerable<string> ReadLines(string path, System.Text.Encoding encoding);`

## 参数

该函数接受两个参数，如下所示：

> *   `Path`: This is the specified file to be read.
> *   `Code`: This code is applied to file content.

## 异常

*   `ArgumentException`: `path` 是一个零长度字符串，只包含空格，或者一个或多个由 `GetInvalidPathChars()` 方法定义的无效字符。
*   `ArgumentNullException`: `path` 为空。
*   `DirectoryNotFoundException`: `path` 无效。
*   `FileNotFoundException`: 未找到由 `path` 指定的文件。
*   `IOException`: 打开文件时出现输入/输出错误。
*   `PathTooLongException`: `path` 超过了系统定义的最大长度。
*   `SecurityException`: 调用方没有所需的权限。
*   `UnauthorizedAccessException`: `path` 指定了一个只读文件。或者当前平台不支持此操作。或者 `path` 是一个目录。或者调用者没有所需的权限。

## 返回值

返回指定文件的所有行。

下面是说明 `File.ReadLines(String, Encoding)` 方法的程序。

### 程序 1

最初创建一个文件 `file.txt`，内容如下：

![file.txt](img/0c0cc86bade8523d22345553100d911b.png)

```cs
// C# program to illustrate the usage
// of File.ReadLines(String, Encoding) method

// Using System, System.IO
// and System.Text namespaces
using System;
using System.IO;
using System.Text;

public class GFG {
    public static void Main(String[] argv)
    {
        // Calling the ReadLines(String, Encoding) function
        foreach(string line in File.ReadLines(@"file.txt", Encoding.UTF8))
        {
            // Printing the file contents
            Console.WriteLine(line);
        }
    }
}
```

**输出：**

```cs
GFG
gfg
Geeks
GeeksforGeeks
geeksforgeeks
```

### 程序 2

最初创建一个文件 `file.txt`，内容如下：

![file.txt](img/0c0cc86bade8523d22345553100d911b.png)

下面的代码从文件中过滤一些内容并打印出来。

```cs
// C# program to illustrate the usage
// of File.ReadLines(String, Encoding) method

// Using System, System.IO
// and System.Text namespaces
using System;
using System.IO;
using System.Text;

public class GFG {
    public static void Main(String[] argv)
    {
        // Calling the ReadLines(String, Encoding) function
        foreach(string line in File.ReadLines(@"file.txt", Encoding.UTF8))
        {
            // Filtering the file contents and printing
            if (line.Contains("GFG")) {
                Console.WriteLine(line);
            }
        }
    }
}
```

**输出：**

```cs
GFG
```
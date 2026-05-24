# File.WriteAllLines(String, String[]) 方法，示例

> 原文: [https://www.geeksforgeeks.org/file-writealllinesstring-string-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-writealllinesstring-string-method-in-c-sharp-with-examples/)

`File.WriteAllLines(String, String[])` 是一个内置的 `File` 类方法，用于创建新文件，将指定的字符串数组写入文件，然后关闭文件。

## 语法

```cs
public static void WriteAllLines (string path, string[] contents);
```

## 参数

该函数接受两个参数，如下所示：

*   `path`: 这是指定的文件，指定的字符串数组将被写入该文件。
*   `contents`: 这是要写入文件的字符串数组。

## 例外

*   `ArgumentException`: `path` 是一个零长度字符串，只包含空格或一个或多个无效字符，如 `InvalidPathChars` 所定义。
*   `ArgumentNullException`: 或者 `path` 或者 `contents` 为空。
*   `PathTooLongException`: 指定的 `path`、文件名或两者都超过了系统定义的最大长度。
*   `DirectoryNotFoundException`: 指定的 `path` 无效。
*   `IOException`: 打开文件时出现输入/输出错误。
*   `UnauthorizedAccessException`: `path` 指定了一个只读文件。或者 `path` 指定了一个隐藏的文件。或者当前平台不支持此操作。或者 `path` 指定了一个目录。或者调用者没有所需的权限。
*   `NotSupportedException`: `path` 的格式无效。
*   `SecurityException`: 调用方没有所需的权限。

下面是说明 `File.WriteAllLines(String, String[])` 方法的程序。

## 程序 1

最初，没有创建文件。下面代码自己创建一个文件 `file.txt` 并将指定的字符串数组写入文件。

```cs
// C# program to illustrate the usage
// of File.WriteAllLines(String,
// String[]) method

// Using System and System.IO,
// namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Creating some string array to
        // write into the file
        string[] createText = { "GFG", "is a", "CS portal." };

        // Calling WriteAllLines() function to write
        // the specified string array into the file
        File.WriteAllLines(path, createText);

        // Reading the file contents
        string[] readText = File.ReadAllLines(path);
        foreach(string s in readText)
        {
            Console.WriteLine(s);
        }
    }
}
```
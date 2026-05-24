# 文件。C# 中的 writellines(String，String[])方法，示例

> 原文:[https://www . geesforgeks . org/file-writellinestring-string-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-writealllinesstring-string-method-in-c-sharp-with-examples/)

**文件。writellines(String，String[])** 是一个内置的 File 类方法，用于创建新文件，将指定的字符串数组写入文件，然后关闭文件。
**语法:**

```cs
public static void WriteAllLines (string path, string[] contents);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the specified file to which the specified string array will be written.
> *   **Directory:** This is an array of strings to be written to the file.

**例外:**

*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **参数空异常:**或者*路径*或者*内容*为空。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **DirectoryNotFoundException:**指定的*路径*无效。
*   **IOException:** 打开文件时出现输入/输出错误。
*   **未授权访问异常:***路径*指定了一个只读文件。或者*路径*指定了一个隐藏的文件。或者当前平台不支持此操作。或者*路径*指定了一个目录。或者呼叫者没有所需的权限。
*   **notSupportDexception:***路径*的格式无效。
*   **安全性异常:**调用方没有所需的权限。

下面是说明文件的程序。writellines(String，String[])方法。
**程序 1:** 最初，没有创建文件。下面代码自己创建一个文件 *file.txt* 并将指定的字符串数组写入文件。

## C#

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
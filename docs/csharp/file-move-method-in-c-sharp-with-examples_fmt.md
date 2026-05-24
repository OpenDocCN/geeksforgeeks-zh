# File.Move() 方法及示例

> 原文：[https://www.geeksforgeeks.org/file-move-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-move-method-in-c-sharp-with-examples/)

`File.Move()` 是一个内置的 `File` 类方法，用于将指定的文件移动到新的位置。此方法还提供了指定新文件名的选项。

## 语法：
```cs
public static void Move (string sourceFileName, string destFileName);
```

## 参数：
该函数接受两个参数，如下图所示：
*   `sourceFileName`：这是要移动的指定源文件。它可以是绝对路径或相对路径。
*   `destFileName`：这是源文件将被移动到的指定目标文件。

## 异常：
*   `IOException`：`destFileName` 已经存在。
*   `FileNotFoundException`：`sourceFileName` 未找到。
*   `ArgumentNullException`：`sourceFileName` 或 `destFileName` 为空。
*   `ArgumentException`：`sourceFileName` 或 `destFileName` 是零长度字符串，仅包含空格或无效字符，如 `InvalidPathChars` 中所定义。
*   `UnauthorizedAccessException`：调用方没有所需的权限。
*   `PathTooLongException`：给定的路径、文件名或两者都超过了系统定义的最大长度。
*   `DirectoryNotFoundException`：在 `sourceFileName` 或 `destFileName` 中指定的路径无效。
*   `NotSupportedException`：`sourceFileName` 或 `destFileName` 的格式无效。

下面是说明 `File.Move()` 方法的程序。

## 程序 1：
在运行下面的代码之前，创建了一个文件 `file.txt`，内容如下：
![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)
```cs
// C# program to illustrate the usage
// of File.Move() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        try {
            // Moving the file file.txt to location C:\gfg.txt
            File.Move(@"file.txt", @"C:\gfg.txt");
            Console.WriteLine("Moved");
        }
        catch (IOException ex) {
            Console.WriteLine(ex);
        }
    }
}
```

## 输出：
```cs
Moved
```
运行上述代码后，显示上述输出，现有文件 `file.txt` 移动到新位置 `C:\gfg.txt`，如下图：
![C:\gfg.txt](img/8ac01f63ed78356ba485a343df62b82b.png)

## 程序 2：
最初没有创建文件。
```cs
// C# program to illustrate the usage
// of File.Move() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        try {
            // If file.txt is not found
            // then an exception will be shown
            File.Move(@"file.txt", @"C:\gfg.txt");
            Console.WriteLine("Moved");
        }
        catch (IOException ex) {
            Console.WriteLine(ex);
        }
    }
}
```

## 运行时错误：
> System.IO.FileNotFoundException: Could not find file '/home/runner/nutritioushavyrgression/file.txt'.
> File name: '/home/runner/nutritioushavyrgression/file.txt'
>    at System.IO.File.Move(String sourceFileName, String destFileName)
>    at GFG.Main()
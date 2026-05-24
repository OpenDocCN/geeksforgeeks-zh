# File.Replace(String, String, String, Boolean) 方法详解

> 原文：[https://www.geeksforgeeks.org/file-replacestring-string-string-boolean-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-replacestring-string-string-boolean-method-in-c-sharp-with-examples/)

`File.Replace(String, String, String, Boolean)` 是一个内置的 `File` 类方法，用于用源文件的内容替换指定目标文件的内容，然后删除源文件，创建被替换文件的备份，并可选地忽略合并错误。

## 语法

```csharp
public static void Replace(
    string sourceFileName,
    string destinationFileName,
    string destinationBackupFileName,
    bool ignoreMetadataErrors
);
```

## 参数

该函数接受四个参数，如下所示：

*   `SourceFileName`：指定的源文件。
*   `DestinationFileName`：指定的目标文件，其内容将被源文件的内容替换。
*   `DestinationBackupFileName`：此文件包含被替换的目标文件内容的备份。
*   `ignoreMetadataErrors`：此参数包含一个布尔值，`true` 表示忽略从替换文件到替换文件的合并错误（例如属性和访问控制列表 (ACLs)）；否则为 `false`。

## 异常

*   `ArgumentException`：由 `DestinationFileName` 参数描述的路径不是合法形式。或者 `DestinationBackupFileName` 参数描述的路径不是合法形式。
*   `ArgumentNullException`：`DestinationFileName` 参数为空。
*   `DriveNotFoundException`：指定了无效的驱动器。
*   `FileNotFoundException`：找不到当前文件信息对象描述的文件。或者找不到 `DestinationBackupFileName` 参数描述的文件。
*   `IOException`：打开文件时出现输入/输出错误。或者 `SourceFileName` 和 `DestinationFileName` 参数指定相同的文件。
*   `PathTooLongException`：指定的路径、文件名或两者都超过了系统定义的最大长度。
*   `PlatformNotSupportedException`：操作系统是 Windows 98 第二版或更早版本，文件系统不是 NTFS。
*   `UnauthorizedAccessException`：`SourceFileName` 或 `DestinationFileName` 参数指定了一个只读文件。或者当前平台不支持此操作。或源或目标参数指定目录而不是文件。或者调用者没有所需的权限。

## 示例

下面是说明 `File.Replace(String, String, String, Boolean)` 方法的程序。

**程序 1：** 在运行下面的代码之前，已经创建了三个文件，其中源文件为 `file1.txt`，目标文件为 `file2.txt`，备份文件为 `file3.txt`。这些文件的内容如下所示：

![file1.txt](img/cd9d14a55e03574b8bf71f4d702e7124.png)

![file2.txt](img/15e04d8943ff6da435c9d76945bab2b4.png)

![file3.txt](img/8f61cb310d5663c93eb820e79ef0f496.png)

```csharp
// C# program to illustrate the usage
// of File.Replace(String, String,
// String, Boolean) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying 3 files
        string sourceFileName = "file1.txt";
        string destinationFileName = "file2.txt";
        string destinationBackupFileName = "file3.txt";

        // Calling the Replace() function
        File.Replace(sourceFileName, destinationFileName, 
                        destinationBackupFileName, true);

        Console.WriteLine("Replacement process has been done.");
    }
}
```
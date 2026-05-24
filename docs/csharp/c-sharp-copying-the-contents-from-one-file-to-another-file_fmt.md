# C# – 将内容从一个文件复制到另一个文件

> 原文: [https://www.geeksforgeeks.org/c-sharp-copying-the-contents-from-one-file-to-another-file/](https://www.geeksforgeeks.org/c-sharp-copying-the-contents-from-one-file-to-another-file/)

给定一个文件，现在我们的任务是使用 C# 将数据从一个文件复制到另一个文件。因此，为了完成这个任务，我们使用了 `System.IO` 命名空间中 `File` 类的 `Copy()` 方法。此功能用于将内容从一个文件复制到一个新文件。它有两种不同类型的重载方法：

## 1. `Copy(String, String)`

此功能用于将内容从一个文件复制到新文件。它不支持覆盖同名文件。

**语法：**

```cs
File.Copy(file1, file2);
```

其中 `file1` 为第一个文件，`file2` 为第二个文件。

**异常：** 这个方法会抛出以下异常：

*   `UnauthorizedAccessException`：当调用方没有所需的权限时，将出现此异常。
*   `ArgumentException`：当 `file1` 或 `file2` 指定目录时，将出现此异常。
*   `ArgumentNullException`：当 `file1` 或 `file2` 为空时，将出现此异常。
*   `PathTooLongException`：当指定的路径、文件名或两者都超过系统定义的最大长度时，将出现此异常。
*   `DirectoryNotFoundException`：当 `file1` 或 `file2` 中指定的路径无效时，将出现此异常。
*   `FileNotFoundException`：当 `file1` 未找到时，将出现此异常。
*   `IOException`：当 `file2` 存在时，将出现此异常。
*   `NotSupportedException`：当 `file1` 或 `file2` 的格式无效时，将出现此异常。

## 2. `Copy(String, String, Boolean)`

此功能用于将内容从一个文件复制到新文件。它支持覆盖同名文件。

**语法：**

```cs
File.Copy(file1, file2, overwrite);
```

其中 `file1` 是第一个文件，`file2` 是第二个文件，`overwrite` 是一个布尔变量，如果目标文件可以被覆盖，则设置为 `true`，否则设置为 `false`。

**异常：** 这个方法会抛出以下异常：

*   `UnauthorizedAccessException`：当调用方没有所需的权限时，将出现此异常。或者 `file2` 是只读的，或者 `overwrite` 设置为 `true`，`file2` 隐藏，但 `file1` 不隐藏。
*   `ArgumentException`：当 `file1` 或 `file2` 指定目录时，将出现此异常。
*   `ArgumentNullException`：当 `file1` 或 `file2` 为空时，将出现此异常。
*   `PathTooLongException`：当指定的路径、文件名或两者都超过系统定义的最大长度时，将出现此异常。
*   `DirectoryNotFoundException`：当 `file1` 或 `file2` 中指定的路径无效时，将出现此异常。
*   `FileNotFoundException`：当 `file1` 未找到时，将出现此异常。
*   `IOException`：当 `file2` 存在且 `overwrite` 为 `false` 时，将出现此异常。
*   `NotSupportedException`：当 `file1` 或 `file2` 的格式无效时，将出现此异常。

## 示例

让我们考虑两个名为 `file1.txt` 和 `file2.txt` 的文件。现在，`file1.txt` 包含以下文本：

![](img/5f65b201677cdc4947d4a129d9ec5fe5.png)

现在 `file2.txt` 包含以下文本：

![](img/315c0573637cf32a2f5ef377b2147b90.png)

### 方法

1.  将两个文件放在系统的 C# 可执行文件夹中。
2.  在主方法中使用 `File.Copy()` 将内容从第一个文件复制到第二个文件。
3.  使用 `File.ReadAllText()` 方法显示 `file2.txt` 中的文本。

### C# 代码

```cs
// C# program to copy data from one file to another
using System;
using System.IO;

class GFG{

    static void Main()
    {

        // Copy contents from file1 to file2
        File.Copy("file1.txt", "file2.txt");

        // Display file2 contents
        Console.WriteLine(File.ReadAllText("file2.txt"));
    }
}
```

### 输出

现在，`file2.txt` 是：

![](img/72a8ab51187c0996c5b9f42dc850c87a.png)
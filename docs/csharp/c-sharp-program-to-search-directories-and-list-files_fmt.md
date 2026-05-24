# C# 程序搜索目录和列表文件

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-search-directories-and-list-files/](https://www.geeksforgeeks.org/c-sharp-program-to-search-directories-and-list-files/)

给定文件和目录，现在我们的任务是使用 C# 搜索这些文件和目录。为此，我们使用以下方法：

## 1. SearchOption

此方法用于指定是搜索当前目录还是包含所有子目录的当前目录。

**语法：**

```cs
public enum SearchOption
```

它将包含两个字段，即 `AllDirectories` 和 `TopDirectoryOnly`。`AllDirectories` 字段用于在搜索操作中执行包含当前目录及其所有子目录的搜索。而 `TopDirectoryOnly` 字段仅用于在主目录中搜索。

## 2. GetFiles

此方法用于返回特定目录或子目录中存在的文件的名称。或者我们可以说它返回给定目录中可用文件的名称和路径。

**语法：**

```cs
public static string[] GetFiles (string path);
```

其中 `path` 是要搜索的目录。该字符串不区分大小写。这里的路径可以是相对路径，也可以是绝对路径。

## 接近

1.  读取目录，使用搜索选项 `AllDirectories` 关键字。

    ```cs
    list = Directory.GetFiles("C:\\A\\","*.*", SearchOption.AllDirectories)
    ```

    在 C 盘 A 文件夹中搜索。

2.  使用 `foreach` 循环。

    ```cs
    foreach (string file in list)
    {
        Console.WriteLine(file);
    }
    ```

    遍历列表并显示。

## 示例

在本例中，我们通过在 C 盘目录中搜索来显示文件名列表及其路径。

### C#

```cs
// C# program to search directories and list files
using System;
using System.IO;

class GFG{

    static void Main()
    {

        // Here we search the file present in C drive
        // and A directory. Using SearchOption
        string[] list = Directory.GetFiles("C:\\A\\", "*.*",
                                           SearchOption.AllDirectories);

        // Display the file names
        // Present in the A directory
        foreach (string file in list)
        {
            Console.WriteLine(file);
        }
    }
}
```

**输出：**

```cs
C:\A\file.txt
```
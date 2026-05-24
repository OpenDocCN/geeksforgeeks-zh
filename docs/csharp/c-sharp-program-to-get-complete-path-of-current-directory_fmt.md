# C# 程序获取当前目录的完整路径

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-get-complete-path-of-current-directory/](https://www.geeksforgeeks.org/c-sharp-program-to-get-complete-path-of-current-directory/)

给定一个目录，现在我们的任务是找到给定目录或当前目录的路径。所以对于这个任务，我们使用`Directory`类的`GetCurrentDirectory()`方法。此方法将返回当前目录的完整路径。此方法给出的结果不会以反斜杠(`\`)结尾。

**语法：**

```cs
public static string GetCurrentDirectory();
```

**返回：** 将返回一个代表当前目录路径的字符串。

**异常：** 它将抛出以下异常：

*   `UnauthorizedAccessException`：当调用方没有所需的权限时，将发生此异常。
*   `NotSupportedException`：当操作系统是 Windows CE 时，将发生此异常。它不具备当前目录的功能。

## C\#

```cs
// C# program to find the path of 
// the currect directory
using System;
using System.IO;

class GFG{

    static void Main()
    {
        // Finding the complete path of the current directory
        // Using GetCurrentDirectory() method
        Console.WriteLine("Current directory path: " + 
                          Directory.GetCurrentDirectory());
    }
}
```

**输出：**

```cs
Current directory path: C:\Users\Sravan\ConsoleApplication12
```
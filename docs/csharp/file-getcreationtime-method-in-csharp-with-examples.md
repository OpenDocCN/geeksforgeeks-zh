# 文件。C# 中的 GetCreationTime()方法，带示例

> 原文:[https://www . geesforgeks . org/file-getcreationtime-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-getcreationtime-method-in-csharp-with-examples/)

**文件。GetCreationTime(String)** 是一个内置的 File 类方法，用于返回指定文件或目录的创建日期和时间。

**语法:**

```cs
public static DateTime GetCreationTime (string path);
```

**参数:**该函数接受如下所示的参数:

> *   **Path:** This is the path of the specified file that will return the creation date and time.

**异常:**

*   **未授权访问异常:**调用方没有所需的权限。
*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**给定的*路径*，文件名或两者都超过了系统定义的最大长度。
*   **notSupportDexception:***路径*的格式无效。

**返回值:**返回指定文件或目录的创建日期和时间。

下面是说明文件的程序。方法。

**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

```cs
// C# program to illustrate the usage
// of File.GetCreationTime(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main(string[] args)
    {
        // Calling the GetCreationTime() function
        DateTime fileCreatedDate = File.GetCreationTime(@"file.txt");

        // Printing the creation date and time of the
        // specified file
        Console.WriteLine("File created on: " + fileCreatedDate);
    }
}
```

**执行:**

```cs
File created on: 4/19/2020 4:02:54 AM

```

**程序 2:** 在运行下面的代码之前，创建了两个文件，如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

![gfg.txt](img/439537cf05f01bd02011003122e87175.png)

```cs
// C# program to illustrate the usage
// of File.GetCreationTime(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main(string[] args)
    {
        // Calling the GetCreationTime() function
        DateTime fileCreatedDate1 = File.GetCreationTime(@"file.txt");
        DateTime fileCreatedDate2 = File.GetCreationTime(@"gfg.txt");

        // Printing the creation date and time of the
        // specified file
        Console.WriteLine("File created on: " + fileCreatedDate1);
        Console.WriteLine("File created on: " + fileCreatedDate2);
    }
}
```

**执行:**

```cs
File created on: 4/19/2020 4:02:54 AM
File created on: 4/19/2020 4:07:02 AM

```
# 文件。C# 中的 GetLastAccessTime()方法，带示例

> 原文:[https://www . geesforgeks . org/file-getlasaccesstime-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-getlastaccesstime-method-in-csharp-with-examples/)

**文件。getlasaccesstime(String)**是一个内置的 File 类方法，用于返回指定文件或目录上次被访问的日期和时间。
**语法:**

```cs
public static DateTime GetLastAccessTime (string path);
```

**参数:**该函数接受一个参数，如下图所示:

> *   **Path:** This is the specified file path.

**例外:**

*   **未授权访问异常:**调用方没有所需的权限。
*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**给定的*路径*，文件名或两者都超过了系统定义的最大长度。
*   **notSupportDexception:***路径*的格式无效。

**返回值:**返回上次访问指定文件或目录的日期和时间。
以下是说明文件的程序。方法。
**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

## C#

```cs
// C# program to illustrate the usage
// of File.GetLastAccessTime(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Calling GetLastAccessTime() function
        DateTime dt = File.GetLastAccessTime(myfile);

        // Getting the last access time
        Console.WriteLine("The last access time for this file was {0}.", dt);
    }
}
```

**执行:**

```cs
The last access time for this file was 5/4/2020 12:00:00 AM.
```

**程序 2:** 在运行下面的代码之前，创建了一个文件，如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

## C#

```cs
// C# program to illustrate the usage
// of File.GetLastAccessTime(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Setting the date
        File.SetLastAccessTime(myfile, new DateTime(2020, 5, 4));

        // Calling GetLastAccessTime() function
        DateTime dt = File.GetLastAccessTime(myfile);

        // Getting the last access time
        Console.WriteLine("The last access time for this file was {0}.", dt);
    }
}
```

**执行:**

```cs
The last access time for this file was 5/4/2020 12:00:00 AM.
```
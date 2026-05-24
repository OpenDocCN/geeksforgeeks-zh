# 文件。C# 中的 SetLastAccessTime()方法，带示例

> 原文:[https://www . geesforgeks . org/file-setlastacesstime-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-setlastaccesstime-method-in-csharp-with-examples/)

**文件。setlasaccesstime(String，DateTime)** 是一个内置的 File 类方法，用于设置上次访问指定文件的日期和时间。

**语法:**

```cs
public static void SetLastAccessTime (string path, DateTime lastAccessTime);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the file for setting access date and time information.
> *   **Last Access Time:** This is the specified date and time of the last local visit.

**异常:**

*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **文件未找到异常:**未找到指定的*路径*。
*   **未授权访问异常:**调用方没有所需的权限。
*   **notSupportDexception:***路径*的格式无效。
*   **ArgumentOutOfRangeException:***最后访问时间*指定的值超出了此操作允许的日期或时间范围。

下面是说明文件的程序。方法。

**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

## C#

```cs
// C# program to illustrate the usage
// of File.SetLastAccessTime() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Calling the SetLastAccessTime() function
        // to set last access date and time
        File.SetLastAccessTime(myfile, new DateTime(2020, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTime(myfile);
        Console.WriteLine("The last access date and"+
                 " time for this file was {0}.", dt);
    }
}
```

**输出:**

```cs
The last access date and time for this file was 5/4/2020 4:05:07 AM.
```

**程序 2:** 最初没有创建文件。在代码下面，它自己创建了一个文件 *file.txt* 并打印了最后一次访问的日期和时间。

## C#

```cs
// C# program to illustrate the usage
// of File.SetLastAccessTime() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Checking the existence of the file
        if (!File.Exists(path)) {
            File.Create(path);
        }

        // Calling the SetLastAccessTime() function
        // to set last access date and time
        File.SetLastAccessTime(path, new DateTime(2019, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTime(path);
        Console.WriteLine("The last access date and "+
                  "time for this file was {0}.", dt);
    }
}
```

**输出:**

```cs
The last access date and time for this file was 5/4/2019 4:05:07 AM.
```
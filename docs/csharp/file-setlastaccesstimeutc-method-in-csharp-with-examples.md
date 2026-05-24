# 文件。C# 中的 SetLastAccessTimeUtc()方法及示例

> 原文:[https://www . geesforgeks . org/file-setlastacesstimeutc-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-setlastaccesstimeutc-method-in-csharp-with-examples/)

**文件。setlastacesstimeutc(String，DateTime)** 是一个内置的文件类方法，用于设置上次访问指定文件的日期和时间，以协调世界时(Utc)表示。
**语法:**

```cs
public static void SetLastAccessTimeUtc (string path, DateTime lastAccessTimeUtc);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the file for setting access date and time information.
> *   **Last visit time:** This is the specified last visit date and time, expressed in Universal Coordinated Time.

**例外:**

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
// of File.SetLastAccessTimeUtc() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string myfile = @"file.txt";

        // Calling the SetLastAccessTimeUtc() function
        // to set last access date and time
        File.SetLastAccessTimeUtc(myfile, new DateTime(2020, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTimeUtc(myfile);
        Console.WriteLine("The last access date and "+
             "time in UTC for this file was {0}.", dt);
    }
}
```

**输出:**

```cs
The last access date and time in UTC for this file was 5/4/2020 4:05:07 AM.
```

**程序 2:** 最初没有创建文件。下面代码自己装箱一个文件 *file.txt* 并打印最后一次访问的日期和时间。

## C#

```cs
// C# program to illustrate the usage
// of File.SetLastAccessTimeUtc() method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Checking the existance of the file
        if (!File.Exists(path)) {
            File.Create(path);
        }

        // Calling the SetLastAccessTimeUtc() function
        // to set last access date and time
        File.SetLastAccessTimeUtc(path, new DateTime(2019, 5, 4, 4, 5, 7));

        // Getting the last access date and time
        DateTime dt = File.GetLastAccessTimeUtc(path);
        Console.WriteLine("The last access date and time "+
                      "in UTC for this file was {0}.", dt);
    }
}
```

**执行:**

```cs
The last access date and time in UTC for this file was 5/4/2019 4:05:07 AM.
```
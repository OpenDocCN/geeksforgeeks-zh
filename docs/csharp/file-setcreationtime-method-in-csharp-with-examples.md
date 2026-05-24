# 文件。C# 中的 SetCreationTime()方法，带示例

> 原文:[https://www . geesforgeks . org/file-setcreationtime-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-setcreationtime-method-in-csharp-with-examples/)

**文件。SetCreationTime(String，DateTime)** 是一个内置的 File 类方法，用于设置文件创建的本地日期和时间。
**语法:**

```cs
public static void SetCreationTime (string path, DateTime creationTime);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** The specified file for which the creation date and time information is set.
> *   **Creation time:** The local date and time containing the value set for creating the path.

**例外:**

*   **文件未找到异常:**未找到指定的*路径*。
*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **io 异常:**执行操作时出现输入/输出错误。
*   **ArgumentOutOfRangeException:***创建时间*指定一个超出此操作允许的日期、时间或两者范围的值。
*   **未授权访问异常:**调用方没有所需的权限。
*   **notSupportDexception:***路径*的格式无效。

下面是说明文件的程序。方法。
**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示-

![file.txt](img/78c9ba1435dec5c78e0a796cc6c788f5.png)

## C#

```cs
// C# program to illustrate the usage
// of File.SetCreationTime(String, DateTime) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        // Specifying a new date and time
        DateTime D1 = new DateTime(2017, 12, 25, 2, 6, 8);

        // Calling SetCreationTime() function
        // to set the new date and time
        File.SetCreationTime("file.txt", D1);

        // Calling the GetCreationTime() function
        // to get the creation date and time
        DateTime D2 = File.GetCreationTime("file.txt");
        Console.WriteLine("The File Creation Time is : " + D2.ToString());
    }
}
```

**输出:**

```cs
The File Creation Time is : 25/12/2017 02:06:08 AM
```

**程序 2:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/78c9ba1435dec5c78e0a796cc6c788f5.png)

## C#

```cs
// C# program to illustrate the usage
// of File.SetCreationTime(String, DateTime) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        // Calling the GetCreationTime() function to
        // get the original file creation date and time
        DateTime D1 = File.GetCreationTime("file.txt");
        Console.WriteLine("File Creation Old Time is: " + D1.ToString());

        // Specifying a new date and time
        DateTime D2 = new DateTime(2017, 12, 25, 2, 6, 8);

        // Calling SetCreationTime() function
        // to set the new date and time
        File.SetCreationTime("file.txt", D2);

        // Calling the GetCreationTime() function
        // to get the new creation date and time
        DateTime D3 = File.GetCreationTime("file.txt");
        Console.WriteLine("File Creation new Time is : " + D3.ToString());
    }
}
```

**输出:**

```cs
File Creation Old Time is: 4/25/2020 11:26:14 AM
File Creation new Time is : 25/12/2017 02:06:08 AM
```
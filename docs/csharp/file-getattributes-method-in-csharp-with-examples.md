# 文件。C# 中的 GetAttributes()方法及示例

> 原文:[https://www . geesforgeks . org/file-getattributes-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-getattributes-method-in-csharp-with-examples/)

**文件。GetAttributes(String)** 是一个内置的 File 类方法，用于获取路径上文件的文件属性。文件属性是那些被授予或拒绝的特定权限。这些权限属于用户或访问文件的操作系统。这些属性包括只读、存档、系统、隐藏等。

**语法:**

```cs
public static System.IO.FileAttributes GetAttributes (string path);
```

**参数:**该函数接受如下所示的参数:

```cs
path: This is the specified file path.
```

**例外:**

*   **参数异常:***路径*为空，仅包含空格或无效字符。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **notSupportDexception:***路径*的格式无效。
*   **文件未找到异常:***路径*表示文件无效，例如位于未映射的驱动器上，或者找不到文件。
*   **directory ynotfoundexception:***路径*代表一个目录，无效，例如位于未映射的驱动器上或找不到该目录。
*   **IOException:** 此文件正被另一个进程使用。
*   **未授权访问异常:**调用方没有所需的权限。

**返回:**返回路径上文件的文件属性。
以下是说明文件的程序。GetAttributes(字符串)方法。
**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示-

![file.txt](img/78c9ba1435dec5c78e0a796cc6c788f5.png)

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.GetAttributes(String) method

// Using System, System.IO
// and System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"file.txt";

        // Getting the file attributes
        FileAttributes attributes = File.GetAttributes(path);

        // Checking if the file is having whether hidden attributes

        // If the file is having hidden attribute then
        // that attribute will be removed
        if ((attributes & FileAttributes.Hidden) == FileAttributes.Hidden) {
            // Removing the file's hidden attribute
            attributes = RemoveAttribute(attributes, FileAttributes.Hidden);

            // Calling the SetAttributes() function
            File.SetAttributes(path, attributes);
            Console.WriteLine("The {0} file is no longer hidden.", path);
        }
        else {
            // Calling the SetAttributes() function to
            // set hidden attribute
            File.SetAttributes(path, File.GetAttributes(path) | FileAttributes.Hidden);
            Console.WriteLine("The {0} file is now hidden.", path);
        }
    }

    private static FileAttributes RemoveAttribute(FileAttributes attributes,
                                          FileAttributes attributesToRemove)
    {
        return attributes & ~attributesToRemove;
    }
}
```

**输出:**

```cs
The file.txt file is now hidden.
```

**程序 2:** 最初没有创建文件。下面的代码，本身创建了一个文件 *gfg.txt* 。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.GetAttributes(String) method

// Using System, System.IO
// and System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file
        string path = @"gfg.txt";

        // Create the file if it does not exist.
        if (!File.Exists(path)) {
            File.Create(path);
        }

        // Getting the file attributes
        FileAttributes attributes = File.GetAttributes(path);

        // Checking if the file is having whether hidden attributes

        // If the file is having hidden attribute then
        // that attribute will be removed
        if ((attributes & FileAttributes.Hidden) == FileAttributes.Hidden) {
            // Removing the file's hidden attribute
            attributes = RemoveAttribute(attributes, FileAttributes.Hidden);

            // Calling the SetAttributes() function
            File.SetAttributes(path, attributes);
            Console.WriteLine("The {0} file is no longer hidden.", path);
        }
        else {
            // Calling the SetAttributes() function to
            // set hidden attribute
            File.SetAttributes(path, File.GetAttributes(path) | FileAttributes.Hidden);
            Console.WriteLine("The {0} file is now hidden.", path);
        }
    }

    private static FileAttributes RemoveAttribute(FileAttributes attributes,
                                          FileAttributes attributesToRemove)
    {
        return attributes & ~attributesToRemove;
    }
}
```

**输出:**

```cs
The gfg.txt file is now hidden.
```
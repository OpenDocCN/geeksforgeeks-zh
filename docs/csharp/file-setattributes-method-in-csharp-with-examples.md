# 文件。C# 中的 SetAttributes()方法，示例

> 原文:[https://www . geesforgeks . org/file-set attributes-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-setattributes-method-in-csharp-with-examples/)

**文件。SetAttributes(String，FileAttributes)** 是一个内置的 File 类方法，用于在指定路径上设置文件的指定文件属性。文件属性是那些被授予或拒绝的特定权限。这些权限属于用户或访问文件的操作系统。这些属性包括只读、存档、系统、隐藏等。

**语法:**

```cs
public static void SetAttributes (string path, System.IO.FileAttributes fileAttributes);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the specified file path.
> *   **File attribute:** This is the bitwise combination of enumerated values.

**例外:**

*   **参数异常:***路径*为空，仅包含空格、无效字符或文件属性无效。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **notSupportDexception:***路径*的格式无效。
*   **DirectoryNotFoundException:**指定的*路径*无效。
*   **文件未找到异常:**找不到文件。
*   **未授权访问异常:***路径*指定了一个只读文件。或者当前平台不支持此操作。或者*路径*指定了一个目录。或者呼叫者没有所需的权限。

下面是说明文件的程序。方法。
**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/78c9ba1435dec5c78e0a796cc6c788f5.png)

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.SetAttributes(String) method

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
// of File.SetAttributes(String) method

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
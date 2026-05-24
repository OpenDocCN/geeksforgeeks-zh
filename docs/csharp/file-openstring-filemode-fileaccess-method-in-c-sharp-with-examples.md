# 文件。C# 中的 Open(字符串、文件模式、文件访问)方法，示例

> 原文:[https://www . geesforgeks . org/file-open string-file mode-file access-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-openstring-filemode-fileaccess-method-in-c-sharp-with-examples/)

**文件。Open(String，FileMode，FileAccess)** 是一个内置的 File 类方法，用于以指定的模式在指定的路径上打开一个 FileStream，并且在不共享的情况下进行访问。
**语法:**

> 公共静态系统。打开文件流(字符串路径，系统。文件模式模式，系统。IO.FileAccess 访问)；

**参数:**该函数接受三个参数，如下图所示:

> *   **Path:** This is the file to be opened.
> *   **Mode:** This mode value specifies whether to create a new file if there is no new file, and determines whether to keep or overwrite the contents of the existing file.
> *   **Access:** This value specifies the operations that can be performed on the file. ..

**例外:**

*   **参数异常:**指定的*路径*是零长度字符串，只包含空格，或者一个或多个无效字符，如 InvalidPathChars 所定义。或*访问*指定的读取和*模式*指定的创建、新建、截断或追加。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**指定的*路径*、文件名或两者都超过了系统定义的最大长度。
*   **DirectoryNotFoundException:**指定的*路径*无效。
*   **IOException:** 打开文件时出现输入/输出错误。
*   **未授权访问异常:***路径*指定了一个只读文件，*访问*未被读取。或者*路径*指定了一个目录。或者呼叫者没有所需的权限。或者*模式*为创建，指定文件为隐藏文件。
*   **ArgumentOutOfRangeException:***模式*或*访问*指定了无效值。
*   **文件未找到异常:**在*路径*中指定的文件未找到。
*   **notSupportDexception:***路径*的格式无效。

**返回值:**返回一个非共享的 FileStream，提供对指定文件的访问，具有指定的模式和访问权限。
以下是说明文件的程序。Open(字符串、文件模式、文件访问)方法。
**程序 1:** 下面的代码创建一个临时文件，将一些指定的内容写入其中，打开该文件并打印其内容。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.Open(String, FileMode,
// FileAccess) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Creating a temporary file
        string path = Path.GetTempFileName();
        using(FileStream fs = File.Open(path, FileMode.Open))
        {
            // Putting some contents
            Byte[] info = new UTF8Encoding(true).GetBytes("GFG is a CS Portal.");
            fs.Write(info, 0, info.Length);
        }

        // Opening the stream and reading it back.
        using(FileStream fs = File.Open(path, FileMode.Open, FileAccess.Read))
        {
            byte[] b = new byte[1024];
            UTF8Encoding temp = new UTF8Encoding(true);

            while (fs.Read(b, 0, b.Length) > 0) {
                Console.WriteLine(temp.GetString(b));
            }
        }
    }
}
```

**输出:**

```cs
GFG is a CS Portal.
```

**程序 2:** 最初创建一个文件 *file.txt* ，内容如下所示-

![file.txt](img/355ab557f458f371c9801a73f6a6e8b5.png)

下面这段代码将打开文件 *file.txt* 并打印其内容。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.Open(String, FileMode,
// FileAccess) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file path
        string path = @"file.txt";

        // Opening above file and reading it back.
        using(FileStream fs = File.Open(path, FileMode.Open, FileAccess.Read))
        {
            byte[] b = new byte[1024];
            UTF8Encoding temp = new UTF8Encoding(true);

            while (fs.Read(b, 0, b.Length) > 0) {
                // Printing the file contents
                Console.WriteLine(temp.GetString(b));
            }
        }
    }
}
```

**输出:**

```cs
GeeksforGeeks
```
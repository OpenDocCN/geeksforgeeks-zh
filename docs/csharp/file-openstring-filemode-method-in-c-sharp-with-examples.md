# 文件。C# 中的 Open(字符串，文件模式)方法，示例

> 原文:[https://www . geesforgeks . org/file-open string-file mode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-openstring-filemode-method-in-c-sharp-with-examples/)

**文件。Open(String，FileMode)** 是一个内置的 File 类方法，用于在指定路径上打开具有读/写访问权限的 FileStream，不共享。
**语法:**

```cs
public static System.IO.FileStream Open (string path, System.IO.FileMode mode);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Source file name:** This is the specified file to be opened.
> *   **Mode:** This mode value specifies whether to create a new file if there is no new file, and determines whether to keep or overwrite the contents of the existing file.

**例外:**

*   **参数异常:***路径*是一个零长度字符串，只包含空格或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**给定的*路径*、*文件名*，或者两者都超过了系统定义的最大长度。
*   **DirectoryNotFoundException:**指定的*路径*无效。
*   **IOException:** 打开文件时出现输入/输出错误。
*   **未授权访问异常:***路径*指定了一个只读文件。或者当前平台不支持此操作。或者*路径*指定了一个目录。或者呼叫者没有所需的权限。或者*模式*被创建，指定文件是隐藏文件。
*   **argumentoutofrangerexception:***模式*指定了无效值。
*   **文件未找到异常:**在*路径*中指定的文件未找到。
*   **notSupportDexception:***路径*的格式无效。

**返回值:**返回以指定模式和路径打开的文件流，具有读/写访问权限，不共享。
以下是说明文件的程序。Open(字符串，文件模式)方法。
**程序 1:** 下面的代码创建一个临时文件，将一些指定的内容写入其中，然后打开文件并打印出来。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.Open(String, FileMode) method

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
        using(FileStream fs = File.Open(path, FileMode.Open))
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
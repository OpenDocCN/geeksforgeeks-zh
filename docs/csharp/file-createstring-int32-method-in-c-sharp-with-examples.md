# 文件。C# 中的 Create(String，Int32)方法，示例

> 原文:[https://www . geesforgeks . org/file-createstring-int 32-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-createstring-int32-method-in-c-sharp-with-examples/)

**文件。Create(String，Int32)** 是一个内置的 File 类方法，用于覆盖现有文件，指定缓冲区大小，否则如果指定的文件不存在，则创建一个新文件。
**语法:**

```cs
public static System.IO.FileStream Create (string path, int bufferSize);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the specified file path.
> *   **Buffer size:** This is the specified buffer size.

**例外:**

*   **未授权访问异常:**调用方没有所需的权限。或者*路径*指定了一个只读文件。或者路径指定了一个隐藏的文件。
*   **ArgumentException:** 路径是零长度字符串，仅包含空格，或一个或多个无效字符，如 InvalidPathChars 所定义。
*   **ArgumentNullException:***路径*为空。
*   **路径工具异常:**给定的*路径*，文件名或两者都超过了系统定义的最大长度。
*   **DirectoryNotFoundException:**指定的*路径*无效(例如，它位于未映射的驱动器上)。
*   **IOException:** 创建文件时出现输入/输出错误。
*   **notSupportDexception:***路径*的格式无效。

下面是说明文件的程序。Create(String，Int32)方法。
**程序 1:** 最初，没有创建文件。下面代码自己创建一个新文件 *file.txt* 带有指定的内容。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.Create(String, Int32) method

// Using System, System.IO and
// System.Text namespaces
using System;
using System.IO;
using System.Text;

class GFG {
    public static void Main()
    {
        // Specifying a file path
        string file_path = @"file.txt";

        try {
            // Creating a new file with below
            // specified contents
            using(FileStream fs = File.Create(file_path, 1024))
            {
                // Adding some info into the file
                byte[] info = new UTF8Encoding(true).GetBytes("GeeksforGeeks");
                fs.Write(info, 0, info.Length);
            }

            // Reading the file contents
            using(StreamReader sr = File.OpenText(file_path))
            {
                string s = "";
                while ((s = sr.ReadLine()) != null) {
                    Console.WriteLine(s);
                }
            }
        }
        catch (Exception ex) {
            Console.WriteLine(ex.ToString());
        }
    }
}
```
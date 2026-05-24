# 文件。C# 中的 AppendAllText(字符串、字符串、编码)方法，示例

> 原文:[https://www . geesforgeks . org/file-appendalltextstring-string-encoding-method-in-csharp-with-examples/](https://www.geeksforgeeks.org/file-appendalltextstring-string-encoding-method-in-csharp-with-examples/)

**文件。AppendAllText(String，String，Encoding)** 是一个内置的 File 类方法，用于使用指定的编码将指定的字符串追加到给定的文件中，如果该文件存在，则创建一个新文件，然后追加完成。

**语法:**

```cs
public static void AppendAllText (string path, string contents, System.Text.Encoding encoding);
```

**参数:**该函数接受两个参数，如下图所示:

> *   **Path:** This is the file to be appended with the given content.
> *   **Directory:** This is the specified content to be added to the file.
> *   **Code:** This is the specified character code.

**例外:**

*   **ArgumentException:** 路径是零长度字符串，只包含空格，或者包含一个或多个由 InvalidPathChars 定义的无效字符。
*   **ArgumentNullException:** 路径为空。
*   **路径工具异常:**给定的路径、文件名或两者都超过了系统定义的最大长度。
*   **directory ynotfoundexception:**指定的路径无效(例如，目录不存在或位于未映射的驱动器上)。
*   **IOException:** 打开文件时出现输入/输出错误。
*   **未授权访问异常:**路径指定了一个只读文件。或者当前平台不支持此操作。或者路径指定了一个目录。或者呼叫者没有所需的权限。
*   **notSupportDexception:**路径的格式无效。
*   **安全性异常:**调用方没有所需的权限。

下面是说明文件的程序。方法。
**程序 1:** 在运行下面的代码之前，创建了一个文件，其内容如下所示:

![file.txt](img/843c9341473936a9e0b0994a5d801fdb.png)

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.AppendAllText() method

// Using System, System.IO,
// System.Text and System.Linq namespaces
using System;
using System.IO;
using System.Text;
using System.Linq;

class GFG {
    // Main() method
    public static void Main()
    {
        // Creating a file
        string myfile = @"file.txt";

        // Adding extra texts
        string appendText = " is a CS portal." + Environment.NewLine;
        File.AppendAllText(myfile, appendText, Encoding.UTF8);

        // Opening the file to read from.
        string readText = File.ReadAllText(myfile);
        Console.WriteLine(readText);
    }
}
```

**执行:**

```cs
mcs -out:main.exe main.cs
mono main.exe
GeeksforGeeks is a CS portal.
```

运行上述代码后，显示上述输出，文件内容如下所示:

![file.txt](img/e64434e43b911c9145cd3ff3e5347d66.png)

**程序 2:** 最初没有创建文件，但是下面的代码本身创建了一个新文件并附加了指定的内容。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the usage
// of File.AppendAllText() method

// Using System, System.IO,
// System.Text and System.Linq namespaces
using System;
using System.IO;
using System.Text;
using System.Linq;

class GFG {
    // Main() method
    public static void Main()
    {
        // Creating a file
        string myfile = @"file.txt";

        // Checking the existence of file
        if (!File.Exists(myfile)) {
            // Creating a file with below content
            string createText = "GFG" + Environment.NewLine;
            File.WriteAllText(myfile, createText);
        }

        // Adding extra texts
        string appendText = " is a CS portal." + Environment.NewLine;
        File.AppendAllText(myfile, appendText, Encoding.UTF8);

        // Opening the file to read from.
        string readText = File.ReadAllText(myfile);
        Console.WriteLine(readText);
    }
}
```

**执行:**

```cs
mcs -out:main.exe main.cs
mono main.exe
GFG
 is a CS portal.
```

运行上述代码后，显示了上述输出，并创建了一个新文件，如下所示:

![file.txt](img/7330c4bae0c77e20a05b65c0b973a7be.png)
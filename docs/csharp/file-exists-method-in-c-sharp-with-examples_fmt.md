# File.Exists(String) 方法在 C# 中的示例

> 原文: [https://www.geeksforgeeks.org/file-exists-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-exists-method-in-c-sharp-with-examples/)

`File.Exists(String)` 是一个内置的 `File` 类方法，用于确定指定文件是否存在。如果调用方具有所需的权限，并且路径包含现有文件的名称，则此方法返回 `true`；否则，返回 `false`。此外，如果路径为空，则此方法返回 `false`。

> **语法:**
> ```cs
> public static bool Exists (string path);
> ```
> 这里，`path` 是要检查的指定路径。

## 示例 1

在运行下面的代码之前，创建一个文件 `file.txt`，内容如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

```cs
// C# program to illustrate the usage
// of File.Exists(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        // Checking the existence of the specified
        if (File.Exists("file.txt")) {
            Console.WriteLine("Specified file exists.");
        }
        else {
            Console.WriteLine("Specified file does not "+
                      "exist in the current directory.");
        }
    }
}
```

**输出:**
```cs
Specified file exists.
```

## 示例 2

在运行下面的代码之前，不创建任何文件。

```cs
// C# program to illustrate the usage
// of File.Exists(String) method

// Using System and System.IO namespaces
using System;
using System.IO;

class GFG {
    static void Main()
    {
        // Checking the existence of the specified
        if (File.Exists("file.txt")) {
            Console.WriteLine("Specified file exists.");
        }
        else {
            Console.WriteLine("Specified file does not"+
                    " exist in the current directory.");
        }
    }
}
```

**输出:**
```cs
Specified file does not exist in the current directory.
```
# 文件。C# 中存在()方法，示例

> 原文:[https://www . geesforgeks . org/file-exists-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/file-exists-method-in-c-sharp-with-examples/)

**文件。Exists(String)** 是一个内置的 File 类方法，用于确定指定文件是否存在。如果调用方具有所需的权限，并且路径包含现有文件的名称，则此方法返回 true 否则，为假。此外，如果路径为空，则此方法返回 false。

> **语法:**
> 
> ```cs
> public static bool Exists (string path);
> ```
> 
> 这里，路径是要检查的指定路径。

**程序 1:** 在运行下面的代码之前，创建了一个文件 *file.txt* ，内容如下所示:

![file.txt](img/e30364ee2029737d20ae9f2d8b5c234a.png)

## c sharp . c sharp . c sharp . c sharp

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

**程序 2:** 在运行下面的代码之前，不创建任何文件。

## c sharp . c sharp . c sharp . c sharp

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
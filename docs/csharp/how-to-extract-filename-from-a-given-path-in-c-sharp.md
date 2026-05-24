# 如何在 C# 中从给定路径提取文件名

> 原文:[https://www . geeksforgeeks . org/如何从给定的 c-sharp 路径中提取文件名/](https://www.geeksforgeeks.org/how-to-extract-filename-from-a-given-path-in-c-sharp/)

在用 C# 开发桌面或网络应用程序时，可能会出现从给定路径提取文件名的要求(在使用“文件打开”对话框或任何其他来源选择文件时可以使用该路径)。路径可能包含驱动器名、目录名和文件名。要从文件中提取文件名，我们使用“**”类的“ **GetFileName()** ”方法。此方法用于获取指定路径字符串的文件名和扩展名。如果文件*路径*为空，返回值为*空*。**

> ****语法:**公共静态字符串 GetFileName(字符串路径)；
> 这里，*路径*就是我们要从中获取文件名和扩展名的字符串。**
> 
> ****返回值:**此方法将返回路径中最后一个目录分隔符后的字符。如果*路径*的最后一个字符是目录或卷分隔符，该方法返回空。如果*路径*为空，该方法返回空。**

****异常:**如果*路径*包含一个或多个在*getinvalipathchars()*中定义的无效字符，此方法将给出 ***参数异常*** 。**

****示例:****

```cs
**Input :** 

string strPath = "c://myfiles//ref//file1.txt";

//function call to get the filename
filename = Path.GetFileName(strPath);

**Output :**

file1.txt 
```

```cs
// C# program to extract the 
// filename from a given path
using System;
using System.IO;
using System.Text;

namespace Geeks {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // taking full path of a file
        string strPath = "C:// myfiles//ref//file1.txt";

        // initialize the value of filename
        string filename = null;

        // using the method
        filename = Path.GetFileName(strPath);
        Console.WriteLine("Filename = " + filename);

        Console.ReadLine();
    }
}
}
```

****Output:**

```cs
Filename = file1.txt

```** 

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . io . path . getfilename？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.io.path.getfilename?view=netframework-4.7.2)**
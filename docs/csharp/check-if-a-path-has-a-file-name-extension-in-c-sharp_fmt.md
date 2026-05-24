# 检查路径在C#中是否有文件扩展名

> 原文：[https://www.geeksforgeeks.org/check-if-a-path-has-a-file-name-extension-in-c-sharp/](https://www.geeksforgeeks.org/check-if-a-path-has-a-file-name-extension-in-c-sharp/)

`Path.HasExtension`方法用于检查指定路径是否有文件扩展名。
此方法将开始搜索一个句点（`.`）后跟至少一个来自*路径末端的字符*。如果在遇到*目录分隔符*、*替代目录分隔符*或*卷分隔符*字符之前发现此模式，此方法返回`true`。

## 语法

```cs
public static bool HasExtension (string path);
```

这里，`path`是搜索扩展名的指定路径。

## 返回值

如果路径中最后一个目录分隔符（`\` 或 `/`）或卷分隔符（`:`）后面的字符包含句点（`.`）后跟一个或多个字符，则该方法将返回`true`；否则，为`false`。

## 异常

如果`path`包含一个或多个在`GetInvalidPathChars()`中定义的无效字符，此方法将给出`ArgumentNullException`。

## 示例

```cs
Input : 
string strPath1 = "C:// myfiles//ref//file1.txt";
string strPath2 = "C:// myfiles//ref//file2";

// checking for the extension
Path.HasExtension(strPath1);
Path.HasExtension(strPath2);

Output :

true
false
```

```cs
// C# program to check whether
// a file have an extension or not
using System;
using System.IO;

namespace Geeks {

class GFG {

// Main Method
    static void Main(string[] args)
    {

// taking two paths
        string strPath1 = "C:// myfiles// ref// file1.txt";
        string strPath2 = "C:// myfiles// ref// file2";

// checking whether the file 
        // has an extension or not
        if (Path.HasExtension(strPath1))
            Console.WriteLine("{0} have an extension...", strPath1);
        else
            Console.WriteLine("{0} don't have an extension...", strPath1);

// checking whether the file 
        // has an extension or not
        if (Path.HasExtension(strPath2))
            Console.WriteLine("{0} have an extension...", strPath2);
        else
            Console.WriteLine("{0} don't have an extension...", strPath2);

Console.ReadLine();
    }
}
}
```

## 输出

```cs
C:// myfiles// ref// file1.txt have an extension...
C:// myfiles// ref// file2 don't have an extension...
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.io.path.hasextension?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.io.path.hasextension?view=netframework-4.7.2)
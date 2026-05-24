# C# 程序检查文件信息

> 原文:[https://www . geesforgeks . org/c-sharp-程序检查文件信息/](https://www.geeksforgeeks.org/c-sharp-program-to-check-the-information-of-the-file/)

给定一个文件，现在我们的任务是通过 C# 查看这个文件的信息。所以为了完成这个任务，我们使用了 FileInfo 类。这个类为创建、复制、删除、打开和移动文件提供了不同类型的属性和方法。它也用于创建 FileStream 对象。因此，这里我们创建了一个包含文件名的文件信息类的对象。

**语法** :

```cs
FileInfo info = new FileInfo("C:\\sravan\\data.txt"); 
```

**例**:

在本例中，我们考虑一个名为“data.txt”的文件，该文件存在于 C 驱动器的“sravan”文件夹或“C:\ Sr avan \ \ data . txt”中。现在借助这个路径，我们将使用 Attributes 属性找到“data.txt”文件的信息。此属性返回一个被编码为枚举标志的枚举常量。

## c#

```cs
// C# program to display the information of file
using System;
using System.IO;

class GFG{

static void Main()
{

    // Get the file 
    FileInfo information = new FileInfo("C:\\sravan\\data.txt");

    // Get the file information
    FileAttributes attributes = information.Attributes;

    // Display file information
    Console.WriteLine("Attribute of the File is {0}", attributes);
}
}
```

**输出:**

```cs
Attribute of the File is Archive
```
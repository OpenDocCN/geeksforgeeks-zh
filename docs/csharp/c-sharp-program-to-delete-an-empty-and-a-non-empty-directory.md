# C# 程序删除一个空的和一个非空的目录

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-delete-一个空的和一个非空的目录/](https://www.geeksforgeeks.org/c-sharp-program-to-delete-an-empty-and-a-non-empty-directory/)

给定一个目录(空或非空)，现在我们必须删除给定的目录。这里，空目录意味着该目录不存在任何文件或子目录。我们可以将一个目录定义为文件和子目录的集合，一个目录可能有数据，也可能不包含数据。非空目录是指包含文件或子目录的目录。我们可以使用目录类的 delete()方法删除目录。该方法以两种不同的方式重载:

*   **删除(字符串)**
*   **删除(字符串，布尔型)**

我们一个一个来讨论。

### 删除(字符串)

此方法用于从给定的路径或位置删除空目录。

**语法:**

> 公共静态 void Delete(字符串 Mypath)；

其中 Mypath 是我们要移除的给定目录的位置，该参数的类型是字符串。

**异常:**

它可以有以下例外

*   IOException:当存在与 Mypath 给定的名称和位置相同的文件时，会出现此异常。或者该目录是只读的。
*   UnauthorizedAccessException:当调用方没有指定的权限时，将出现此异常。
*   ArgumentNullException:当 Mypath 为空时，将出现此异常。
*   PathTooLongException:当给定的 Mypath、文件名或两者都超过系统定义的最大长度时，将出现此异常。
*   DirectoryNotFoundException:当“我的路径”不存在或找不到时，将出现此异常。或者给定的路径无效。

**例 1:**

让我们考虑一下 D 驱动器中一个名为“sravan”的空目录。现在使用删除(字符串)方法，我们删除“sravan”目录。

## C#

```cs
// C# program to delete the empty directory
// Using Delete(string) method
using System;
using System.IO;

class GFG{

static void Main()
{

    // Delete empty directory
    // Using Delete() method
    Directory.Delete("D:/sravan");
    Console.WriteLine("Deleted");
}
}
```

**输出:**

```cs
Deleted
```

**例 2:**

让我们考虑一个名为“vignan”的非空目录，在 D 驱动器中有一个名为“test”的文件。现在使用删除(字符串)方法，我们将删除“vignan”目录。

## C#

```cs
// C# program to delete the empty directory
// Using Delete(string) method
using System;
using System.IO;

class GFG{

static void Main()
{

    // Delete empty directory
    // Using Delete() method
    Directory.Delete("D:/vignan");
    Console.WriteLine("Deleted");
}
}
```

**输出:**

```cs
Deleted
```

### 删除(字符串、布尔值)

此方法用于删除给定的目录以及目录中的任何子目录和文件。

**语法:**

> 公共静态 void Delete(字符串 Mypath，bool 递归)；

其中 Mypath 是目录路径，如果为真，递归用于删除文件、目录等。否则为假。

**异常:**

它可以有以下例外

*   IOException:当存在与 Mypath 指定的名称和位置相同的文件时，会出现此异常。或者该目录是只读的。
*   UnauthorizedAccessException:当调用方没有所需的权限时，将出现此异常。
*   ArgumentNullException:当 Mypath 为空时，将出现此异常。
*   PathTooLongException:当指定的 Mypath、文件名或两者都超过系统定义的最大长度时，将出现此异常。
*   DirectoryNotFoundException:当“我的路径”不存在或找不到时，将出现此异常。

**例 1:**

让我们考虑 D 驱动器中一个名为“vignan”的空目录。现在使用删除(字符串，布尔)方法，我们将删除“vignan”目录。

## C#

```cs
// C# program to delete the empty directory
// Using Delete(String, Boolean) method
using System;
using System.IO;

class GFG{

static void Main()
{

    // Delete empty directory
    // Using Delete(String, Boolean) method
    Directory.Delete("D:/vignan", true);
    Console.WriteLine("Deleted");
}
}
```

**输出:**

```cs
Deleted
```

**例 2:**

让我们考虑一个名为“sravan”的非空目录，在 D 驱动器中有一个名为“test”的文件。现在使用删除(字符串，布尔)方法，我们将删除“sravan”目录。

## C#

```cs
// C# program to delete the non-empty directory
// Using Delete(String, Boolean) method
using System;
using System.IO;

class GFG{

static void Main()
{

    // Delete non-empty directory
    // Using Delete(String, Boolean) method
    Directory.Delete("D:/sravan", true);
    Console.WriteLine("Deleted");
}
}
```

**输出:**

```cs
Deleted
```
# 检查给定目录存在与否的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-要检查的程序-给定目录-存在与否/](https://www.geeksforgeeks.org/c-sharp-program-to-check-given-directory-exists-or-not/)

给定一个目录，现在我们的任务是检查给定目录是否存在。所以对于这个任务，我们使用目录类的 Exists()方法。如果给定目录存在，此方法将返回 true，否则返回 false。

**语法**:

> 公共静态 bool Exists(字符串？my path)；

其中，Mypath 是字符串类型的 Exists()方法的参数。它表示指定目录的位置或路径。现在，如果给定路径引用现有目录，Exists 方法将返回 true，否则将返回 false。

**返回类型:**这个方法的返回类型是一个布尔值，可以是真，也可以是假。如果给定的 Mypath 引用现有目录，此方法将返回 true，否则将返回 false。

**例 1:**

## C#

```cs
// C# program to check wether the given
// directory exits or not
using System;
using System.IO;

class GFG{

static void Main()
{

    // Check whether the directory named
    // vignan exists or not 
    // Using Exists() method
    if (Directory.Exists("D:/vignan"))
        Console.WriteLine("The Specified directory Exists");
    else
        Console.WriteLine("The specified directory does not Exist");
}
}
```

**输出:**

```cs
The Specified directory Exists
```

**例 2:**

## C#

```cs
// C# program to check wether the given
// directory exits or not
using System;
using System.IO;

class GFG{

static void Main()
{

    // Check whether the directory named
    // geeks exists or not 
    // Using Exists() method
    if (Directory.Exists("D:/geeks"))
        Console.WriteLine("Exists");
    else
        Console.WriteLine("Not Exist");
}
}
```

**输出:**

```cs
Not Exist
```
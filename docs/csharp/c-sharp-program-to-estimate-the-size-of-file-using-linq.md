# 使用 LINQ 估算文件大小的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-预估文件大小-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-estimate-the-size-of-file-using-linq/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将估计文件的大小。为此，我们使用以下方法和类:

**1。GetFiles:** 它将返回特定目录或子目录中存在的文件的名称。

**语法:**

```cs
public static string[] GetFiles (string path);
```

其中路径是要搜索的目录。该字符串不区分大小写。

**2。** [**选择方法**](https://www.geeksforgeeks.org/linq-projection-operator-select/) **:** 该方法用于将序列的每个元素投影到一个新的形式中。或者换句话说，当我们想要从指定的集合或序列中获取单个值时，使用这个方法。

**语法:**

```cs
Select<TSource,TResult>(IEnumerable<TSource>, Func<TSource,TResult>)
```

这用于使用文件信息类选择新文件

**3。文件信息类:**该类提供了不同类型的属性和实例方法，用于文件的复制、创建、删除、移动和打开，并有助于文件流对象的创建。

**语法:**

```cs
public sealed class FileInfo : System.IO.FileSystemInfo
```

**4。** [**数学。舍入方法**](https://www.geeksforgeeks.org/c-sharp-math-round-method-set-1/) **:** 此方法用于将一个值舍入到最接近的整数或指定的小数位数。

**语法:**

```cs
Math.Round(Decimal, Int32)
```

### **进场:**

**1。**使用 GetFiles()方法从路径中获取文件

```cs
string[] list = Directory.GetFiles("c:\\A\\");
```

**2。**使用文件类选择文件，使用 average()函数计算平均值

```cs
average = list.Select(file =>new FileInfo(file).Length).Average();
```

**3。**使用数学将尺寸四舍五入到小数点后 1 位。舍入函数

```cs
Math.Round(average / 10, 1)
```

**4。**显示文件的大小

**示例:**在本例中，我们将找到给定文件的大小

![](img/8bb4dba089960a7d66ca89537cfeefb2.png)

## C#

```cs
// C# program to estimate the file size 
// Using LINQ
using System;
using System.Linq;
using System.IO;

class GFG{

static void Main(string[] args)
{

    // Get the file from the path
    string[] list = Directory.GetFiles("c:\\A\\");

    // Get the average size
    var average = list.Select(file => new FileInfo(file).Length).Average();

    // Round off the average size to 1 decimal point
    average = Math.Round(average / 10, 1);

    // Display average file size
    Console.WriteLine("The Average size of the file is {0} MB", average);
}
}
```

**输出:**

```cs
The Average size of the file is 1.3 MB
```
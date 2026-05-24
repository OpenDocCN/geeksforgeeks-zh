# 使用 LINQ

基于扩展名计数文件的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-count-files-on-extension-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-count-the-files-based-on-extension-using-linq/)

给定文件，现在我们使用 LINQ 基于扩展名对文件进行计数。我们正在考虑所有类型的文件格式，如 pdf、txt、xml，并将根据扩展名对这些文件进行计数。为此，我们必须知道以下方法:

*   **路径。GetExtension():** 此方法用于获取给定路径的扩展。
*   **TrimStart():** 此方法用于切割路径，从给定的字符串开始。
*   **ToLower():** 此方法用于将字符串转换为 Lower。
*   [**GroupBy():**](https://www.geeksforgeeks.org/linq-grouping-operator-groupby/) 该函数用于对指定序列或列表中共享公共属性的数据进行分组。
*   **count():** 此方法用于从给定序列中获取元素总数。

**示例:**

```cs
Input: {myfile1.txt, myfile2.txt, myfile3.xml}
Output: 3 file ---> txt
        1 file ---> xml

Input: {file12.txt, file23.xml, file45.pdf}
Output: 1 file ---> txt
        1 file ---> xml
        1 file ---> pdf
```

**进场:**

> *   Create a list of files with different extensions.
> *   Use to read files. GetExtension () method. Then convert the file extension to lowercase to eliminate case sensitivity. Then before that, apply the trim function, put the same file extensions into a groupby using the group by method, and then use the count function to count the file extensions already in the group.
> 
> ```cs
> var result = files.Select(f => Path.GetExtension(f)
>                              .TrimStart('.').ToLower())
>                              .GroupBy(y => y, (ex, excnt) => new
>                              {
>                                 Extension = ex,
>                                 Count = excnt.Count()
>                              });
>                              
> ```
> 
> *   Use file count
> 
> ```cs
> foreach (var i in result)
> {
>     Console.WriteLine(i.Count + " File --> " + 
>                       i.Extension + " format ");
> }
> ```
> 
> 显示文件计数和扩展名

**示例:**

## C#

```cs
// C# program to count the files according 
// to their extension
using System;
using System.IO;
using System.Linq;

class GFG{

public static void Main()
{

    // Declare files with different extensions
    string[] files = { "171fa07058.txt", "171fa07058.pdf",
                       "171fa07058.xml", "171fa07058.txt", 
                       "171fa07058.txt", "171fa07058.xml" };

    // Group by files with an extension
    var result = files.Select(f => Path.GetExtension(f)
                             .TrimStart('.').ToLower())
                             .GroupBy(y => y, (ex, excnt) => new
                             {
                                Extension = ex,
                                Count = excnt.Count()
                             });

    // Display the final result
    foreach (var i in result)
    {
        Console.WriteLine(i.Count + " File --> " + 
                      i.Extension + " format ");
    }
}
}
```

**输出:**

```cs
3 File --> txt format 
1 File --> pdf format 
2 File --> xml format
```
# 如何在 C# 中从数组中获取逗号分隔的字符串？

> 原文:[https://www . geesforgeks . org/如何从 c-sharp 数组中获取逗号分隔字符串/](https://www.geeksforgeeks.org/how-to-get-a-comma-separated-string-from-an-array-in-c-sharp/)

给定一个数组，现在我们的任务是从给定的数组中获取一个逗号分隔的字符串。所以我们可以使用[字符串来完成这个任务。Join()](https://www.geeksforgeeks.org/c-sharp-join-method-set-1/) 方法。此方法借助数组中每个项目之间的逗号分隔符来连接数组中的项目。

**语法:**

```cs
String.Join(",", array_name)
```

其中 array_name 是输入数组。

**示例:**

```cs
Input: {"sireesha", "priyank", "ojaswi", "gnanesh"}
Output: sireesha,priyank,ojaswi,gnanesh

Input: {"sireesha", "priyank"}
Output: sireesha,priyank
```

**方法 1:**

*   声明字符串数组。
*   使用 string join()函数获取逗号分隔的字符串。

```cs
String.Join(",", names)
```

*   显示最终结果。

**示例:**

## C#

```cs
// C# program to display the comma separated
// string from an array 
using System;

class GFG{

public static void Main()
{

    // Creating an array of string elements
    String[] names = { "sireesha", "priyank", 
                       "ojaswi", "gnanesh" };

    // Join the elements separated by comma
    // Using Join() method
    var str1 = String.Join(",", names);

    // Display the final string
    Console.WriteLine(str1);
}
}
```

**输出:**

```cs
sireesha,priyank,ojaswi,gnanesh
```

**方法 2:**

我们还可以从对象数组中找到命令分隔的字符串。

*   使用名字和姓氏方法创建一个名为 MyEmployee 的类。
*   在主方法中声明 MyEmployee 的对象数组。
*   使用 string join()函数获取逗号分隔的字符串。

```cs
String.Join(",", e.Select(m => m.First_Name));
```

这里，我们只加入名字，所以我们使用 select 方法来选择员工的名字。

*   显示最终结果。

**例 2:**

## C#

```cs
// C# program to display the comma separated
// string from an array 
using System;
using System.Linq;

// MyEmployee class
class MyEmployee
{
    public string First_Name { get; set; }
    public string Last_Name { get; set; }
}

class GFG{

public static void Main()
{

    // Creating object array of MyEmployee
    MyEmployee[] e = {
        new MyEmployee(){ First_Name = "Sumi", Last_Name = "Goyal" },
        new MyEmployee(){ First_Name = "Mohan", Last_Name = "Priya" },
        new MyEmployee(){ First_Name = "Sumit", Last_Name = "Singh" }
    };

    // Join the elements separated by comma
    // Using Join() method
    var res = String.Join(",", e.Select(m => m.First_Name));

    // Display teh final result
    Console.WriteLine("Final String:" + res);
}
}
```

**输出:**

```cs
Final String:Sumi,Mohan,Sumit
```
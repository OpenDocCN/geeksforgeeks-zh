# 使用环境类获取系统目录路径的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-path-system-directory-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-path-of-system-directory-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将讨论如何获取系统目录的路径。所以我们使用环境类的**系统目录**属性。此属性返回系统目录的完整路径

**语法** :

> 环境。
> 
> 系统目录

**返回类型:**该属性的返回类型为字符串，该字符串代表系统目录的路径。

**例:**

## c#

```cs
// C# program to find the path of system directory
using System;

class GFG{

static public void Main()
{

    // Declaring a variable
    string resultDir = "";

    // Now finding the path of system directory
    // Using the SystemDirectory property of
    // the Environment class
    resultDir = Environment.SystemDirectory;

    // Displaying the result
    Console.WriteLine("System Directory:" + resultDir);
}
}
```

**输出:**

```cs
System Directory:
C:\Windows\system32
```
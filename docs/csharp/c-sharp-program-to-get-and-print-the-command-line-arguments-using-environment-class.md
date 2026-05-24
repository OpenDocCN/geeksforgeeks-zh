# 使用环境类获取和打印命令行参数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取并打印命令行参数-使用环境-类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-and-print-the-command-line-arguments-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将讨论如何使用环境类获取和显示命令行参数。因此，为了完成这个任务，我们使用环境类的**命令行**属性。此属性用于查找当前进程的命令行。

**语法:**

> 环境。
> 
> 命令线

**返回类型:**该属性的返回类型为字符串。该字符串表示命令行参数。

**例:**

```cs
Input  : Hello Geeks
Output : Hello Geeks

Input  : Hello 123
Output : Hello 123
```

## c#

```cs
// C# program to display the command line arguments
// using Environment Class
using System;

class GFG{

static public void Main()
{

    // Declaring a string variable
    string commandlineResult = "";

    // Getting the command line argument
    // Using the CommandLine property of 
    // Environment class
    commandlineResult = Environment.CommandLine;

    // Display the data
    Console.WriteLine("Command Line Data: \n" + 
                      commandlineResult);
}
}
```

**输出** :

```cs
E:\> example.exe Hello Geeks
Command Line Data:
example.exe Hello Geeks
```
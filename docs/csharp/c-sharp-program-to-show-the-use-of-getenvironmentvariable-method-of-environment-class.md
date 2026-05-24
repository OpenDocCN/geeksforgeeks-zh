# C# 程序演示环境类的 GetEnvironmentVariable()方法的使用

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-show-of-getenvironmentvariable-of-environment-method-class/](https://www.geeksforgeeks.org/c-sharp-program-to-show-the-use-of-getenvironmentvariable-method-of-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息，GetEnvironmentVariable()方法就是其中之一。此方法用于从当前进程中获取环境变量的值。

**语法:**

> 环境。

环境变量

其中目录名是目录

**Return:** 该方法将返回表示环境变量的字符串，如果找不到环境变量，则返回 null。

**异常:**此方法将抛出以下异常:

*   ArgumentNullException is thrown when the variable is empty.
*   SecurityException will be thrown when the caller does not have the required permission to perform this operation.

**例:**

## c#

```cs
// C# program to illustrate the GetEnvironmentVariable()
// method of Environment Class
using System;
using System.IO;

class GFG{

static public void Main()
{

    // Get the windows directory
    // environment details
    Environment.CurrentDirectory = Environment.GetEnvironmentVariable("windir");
    DirectoryInfo info = new DirectoryInfo(".");

    // Display the information
    Console.WriteLine("Information:\n" + info.FullName);
}
}
```

**输出:**

```cs
Information:
D:\Windows
```
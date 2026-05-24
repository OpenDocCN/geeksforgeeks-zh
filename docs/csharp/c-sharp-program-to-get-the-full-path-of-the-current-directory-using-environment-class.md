# 使用环境类获取当前目录完整路径的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-当前目录的完整路径-使用环境-类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-full-path-of-the-current-directory-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。在本文中，我们将讨论如何获取当前目录的完整路径。所以为了解决这个问题，我们使用环境类的 **CurrentDirectory** 属性。此属性返回计算机当前工作目录的完整路径。此属性还引发以下异常:

*   **Parameter exception:** This exception will be thrown when the CurrentDirectory property tries to be set to an empty string.
*   [T0】 argumentNullException: 【T1] This exception will be thrown when the CurrentDirectory property tries to be set to null.
*   **ioexception:** This exception is thrown when an input-output error occurs.
*   **Directory synchronization exception:** This exception will be thrown when the CurrentDirectory property tries to set the local path/address that cannot be found.
*   **Securityexception:** This exception is thrown when the caller does not have proper permission.

**语法:**

> 环境。当前目录

**返回类型:**该属性的返回类型为字符串。返回的字符串表示当前目录路径。

**例:**

## c#

```cs
// C# program to find the current directory path
// Using Environment Class
using System;

class GFG{

static public void Main()
{

    // Declaring a string
    string resultPath = "";

    // Get the complete path of the current
    // working directory. Using 
    // CurrentDirectory property of 
    // Environment class
    resultPath = Environment.CurrentDirectory;

    Console.WriteLine("System Directory:\n" + resultPath);
}
}
```

**输出:**

```cs
System Directory:
/Users/Projects/newprogram/
```
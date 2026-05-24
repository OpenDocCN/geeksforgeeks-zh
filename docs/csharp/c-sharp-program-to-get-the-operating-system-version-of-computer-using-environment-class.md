# 使用环境类获取计算机操作系统版本的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取操作系统版本-计算机使用环境-类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-operating-system-version-of-computer-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。在本文中，我们将讨论如何获取计算机的操作系统版本。所以我们使用环境类的 **OSVersion** 属性。此属性返回系统或平台标识符的当前操作系统版本。如果此属性未获取系统的当前版本或不是 PlatformID 一部分的平台标识符，它还将返回 InvalidOperationException。

**语法:**

> 环境。OSVersion
> 
> spa

**返回:**返回平台标识或系统版本。

**示例:**

在下面的例子中，使用环境类的操作系统版本属性，我们可以找到我们计算机系统的当前操作系统版本。

## C#

```cs
// C# program to get the current operating
// system version of the computer 
// Using Environment Class
using System;
using System.Collections;

class GFG
{

    static public void Main()
    {

        // Display the current OS version of the system 
        // Using OSVersion property of the Environment class
        Console.WriteLine("The current operating System version is " +
                          Environment.OSVersion);
    }
}
```

**输出:**

```cs
The current operating System version is Unix 20.3.0.0
```
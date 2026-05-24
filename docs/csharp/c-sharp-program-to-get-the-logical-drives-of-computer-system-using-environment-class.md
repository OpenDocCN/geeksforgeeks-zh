# 使用环境类获取计算机系统逻辑驱动器的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取计算机系统逻辑驱动器-使用环境-类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-logical-drives-of-computer-system-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。在这篇文章中，我们将得到计算机系统的逻辑驱动器。所以为了解决这个问题，我们使用了环境类的 **GetLogicalDrives()** 方法。此方法用于获取计算机中的逻辑驱动器。它将以字符串格式返回驱动器阵列。

**语法** :

> 字符串[]环境。getlogicaldrivers()

**Return:** 这个方法的返回类型是字符串数组**。**这个字符串数组保存了计算机系统中逻辑驱动器的名称。

**异常:**该方法还抛出以下异常:

*   **ioexception:** The getlogicaldrivers () method throws this exception when an input/output error occurs.
*   **SecurityException:** The getlogicaldrivers () method throws this exception when the caller does not have the appropriate permission.

**例:**

## c#

```cs
// C# program to find the logical drives of 
// current computer system. Using the
// Environment class
using System;

class GFG{

static public void Main()
{

    // Declare the string array to 
    // store the logical drives
    string[] drives = Environment.GetLogicalDrives();

    Console.WriteLine("Logical Drives of this computer:");

    // Display all drives present in the computer system
    foreach (string d in drives)
    {
        Console.WriteLine("\t" + d);
    }
}
}
```

**输出:**

```cs
Logical Drives of this computer:
C:\
D:\
E:\
F:\
```
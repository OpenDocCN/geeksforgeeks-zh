# 使用环境类获取机器名或主机名的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-machine-name-or-host-name-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-machine-name-or-host-name-using-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用预定义的机器名属性，我们可以使用环境类获得机器名或主机名。此属性用于查找计算机的 NetBIOS 名称。当此属性未获取计算机名称时，它还会引发 InvalidOperationException。

**语法:**

> 环境。机器名称
> 
> T5

**返回:**这个方法返回一个包含机器名称的字符串。

**例:**

## c#

```cs
// C# program to find the name of the machine
// Using Environment class
using System;

class GFG{

static public void Main()
{

    // Here we get the machine name
    // Using the MachineName property
    // of the Environment class
    Console.WriteLine("Machine Name is" + Environment.MachineName);
}
}
```

**输出:**

```cs
Machine Name is Check
```
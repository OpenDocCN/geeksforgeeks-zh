# 使用环境类获取当前堆栈跟踪信息的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-current-stack-trace-information-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-get-current-stack-trace-information-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们使用 **StackTrace** 属性来获取当前堆栈跟踪信息。此属性用于获取当前堆栈跟踪信息

**语法**:

> 字符串环境。StackTrace

**返回:**字符串并给出类名和 id

**例 1:**

## C#

```cs
// C# program to find the current stack trace information
using System;

class GFG{

static public void Main()
{

    // Define the variable with string
    string my_variable = "Hello Geeks";

    // Get the current stack trace details
    // Using StackTrace property
    my_variable = Environment.StackTrace;
    Console.WriteLine("Information of current stack trace: \n" +
                      my_variable);
}
}
```

**输出:**

```cs
Current Stack Trace Details: 
  at System.Environment.get_StackTrace () [0x00000] in <a1ae6166591d4020b810288d19af38d4>:0 
  at GFG.Main () [0x00000] in <ec0c23afce674aedba9f00d218402cf6>:0
```

**例 2:**

## C#

```cs
// C# program to find the current stack trace information
using System;

class GFG{

static public void Main()
{

    // Define the variable with integer
    string my_variable = "58";

    // Get the current stack trace details
    // Using StackTrace property
    my_variable = Environment.StackTrace;
    Console.WriteLine("Information of current stack trace: \n" +
                      my_variable);
}
}
```

**输出:**

```cs
Current Stack Trace Details: 
  at System.Environment.get_StackTrace () [0x00000] in <a1ae6166591d4020b810288d19af38d4>:0 
  at GFG.Main () [0x00000] in <092e5ea1577d4af6be34040e9472afab>:0 
```
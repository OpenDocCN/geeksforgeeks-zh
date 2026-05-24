# 使用环境类检查运行进程是否为 64 位进程的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-check-running-process-is-64 位-process-or-not-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-check-whether-running-process-is-64-bit-process-or-not-using-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们可以使用环境类的**is 64 位进程**属性来检查系统中运行的是哪个进程。此方法用于检查当前进程是否为 64 位进程。如果当前进程是 64 位进程，那么它将返回真，否则它将返回假。

**语法:**

> 环境。is 64 位流程

**返回类型:**该属性的返回类型为布尔值。如果进程是 64 位进程，它将返回 true。否则，返回 false。

**例 1:**

在这个例子中，我们在 64 位机器上运行代码。

## C#

```cs
// C# program to determine whether the given 
// process is 64-bit process or not. Using 
// Is64BitProcess process of Environment Class
using System;

class GFG{

static public void Main()
{

    // Declare a boolean variable and set to false
    bool process = false;

    // Set the method to the initialized variable
    process = Environment.Is64BitProcess;

    // Check whether the current process 
    // is 64-bit process or not
    if (process == true)
        Console.WriteLine("The current process is 64-bit process");
    else
        Console.WriteLine("The current process is not 64-bit process");
}
}
```

**输出:**

```cs
The current process is 64-bit process
```

**例 2:**

在这个例子中，我们在 32 位机器上运行相同的代码，得到不同的输出，因为现在进程是 32 位的。

## C#

```cs
// C# program to determine whether the given 
// process is 64-bit process or not. Using 
// Is64BitProcess process of Environment Class
using System;

class GFG{

static public void Main()
{

    // Declare a boolean variable and set to false
    bool process = false;

    // Set the method to the initialized variable
    process = Environment.Is64BitProcess;

    // Check whether the current process 
    // is 64-bit process or not
    if (process == true)
        Console.WriteLine("The current process is 64-bit process");
    else
        Console.WriteLine("The current process is not 64-bit process");
}
}
```

**输出:**

```cs
The current process is not 64-bit process
```
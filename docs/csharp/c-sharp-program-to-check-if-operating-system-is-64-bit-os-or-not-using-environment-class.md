# 检查操作系统是 64 位操作系统还是不使用环境类的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序检查操作系统是否为 64 位操作系统或不使用环境类/](https://www.geeksforgeeks.org/c-sharp-program-to-check-if-operating-system-is-64-bit-os-or-not-using-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们将讨论如何检查运行的操作系统是否是 64 位操作系统，以及是否使用环境类。所以我们需要使用环境类的 **Is64BitOperatingSystem** 属性。此属性用于检查运行的操作系统是否基于 64 位体系结构，如果是 64 位操作系统，则返回 true，否则返回 false。

**语法:**

```cs
Environment.Is64BitOperatingSystem
```

**返回类型:**该属性的返回类型为布尔值。如果操作系统是 64 位操作系统，则返回真。否则，它将返回 false。

**例:**

## c#

```cs
// C# program to check whether the given
// OS is 64-bit Os or not. Using the
// Environment class
using System;

class GFG{

static public void Main()
{

    // Declaring a variable of bool type
    // to store the result
    bool outresult;

    // Now we determine the current operating system 
    // is 64-bit OS or not. Using the Is64BitOperatingSystem
    // property of Environment class
    outresult = Environment.Is64BitOperatingSystem;

    // Display the result
    if (outresult == true)
        Console.WriteLine("Yes! the current operating " +
                          "system is 64-bit OS");
    else
        Console.WriteLine("No! the current operating " + 
                          "system is not 64-bit OS");
}
}
```

**输出:**

```cs
Operating System is based 64-bit architecture
```

当我们在 32 位系统中运行相同的代码时，输出将是:

```cs
Operating System is not based 64-bit architecture
```
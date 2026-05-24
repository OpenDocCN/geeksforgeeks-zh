# 使用环境类

获取当前机器处理器数量的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-程序获取当前机器使用环境类的处理器数量/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-number-of-processors-of-the-current-machine-using-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们将讨论如何获取当前机器的处理器数量。因此，我们使用环境类的 **ProcessorCount** 属性。此属性返回当前进程中存在的处理器计数。

**语法:**

> 环境。
> 
> 处理器计数

**返回类型:**该属性的返回类型为 32 位有符号整数。

**例:**

## c#

```cs
// C# program to find the number of processors of 
// the current machine using Environment class
using System;

class GFG{

static public void Main()
{

    // Declare a variable
    int result;

    // Now find the number of processors 
    // of the current machine
    // Using ProcessorCount property 
    result = Environment.ProcessorCount;

    // Display the result
    Console.WriteLine("Total number of processors " + 
                      "in current process is " + result);
}
}
```

**输出:**

```cs
Total number of processors in current process is 4
```
# 使用环境类获取操作系统页面文件内存大小的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取操作系统页面文件大小使用环境类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-memory-size-for-os-page-file-using-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们将讨论如何找到操作系统页面文件的内存大小。所以我们可以通过 **SystemPageSize** 属性找到 OS 页面文件的内存大小。此属性返回操作系统内存页中存在的字节数。

**语法:**

> 环境。系统页面大小

**返回类型:**该属性的返回类型为整数。

**示例:**

## C#

```cs
// C# program to find the size of operating 
// system's memory page. Using Environment Class
using System;

class GFG{

static public void Main()
{
    // Declare a variable
    int result;

    // Now we find the memory size for OS Page file 
    // Using SystemPageSize property of Environment class
    result = Environment.SystemPageSize;

    // Display the result
    Console.WriteLine("The memory size for OS page file is " + result);
}
}
```

**输出:**

```cs
The memory size for OS page file is 4096
```

**例 2:**

## C#

```cs
// C# program to find the size of operating 
// system's memory page. Using Environment Class
using System;

class GFG{

static public void Main()
{

    // Arithmetic operation
    int Sum = 1 + 3;
    Console.WriteLine("Sum:" + Sum);

    // Declare a variable
    int res;

    // Now we find the memory size for OS Page file 
    // Using SystemPageSize property of Environment class
    res = Environment.SystemPageSize;

    // Display the result
    Console.WriteLine("The memory size for OS page file is " + res);
}
}
```

**输出:**

```cs
Sum:4
The memory size for OS page file is 4096
```
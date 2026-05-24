# 演示环境类 GetCommandLineArgs()方法使用的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-演示-使用-getcommandlineargs-method-of-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-use-of-getcommandlineargs-method-of-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们将演示环境类的 **GetCommandLineArgs()** 方法的使用。此方法用于获取当前进程的命令行参数，并返回一个字符串数组，该数组包含命令行上传递的参数。命令行参数通常由空格分隔，我们可以使用双引号(")在参数中包含空格。而单引号(')不提供相同的功能。当双引号跟在偶数个反斜杠后面时，开始的反斜杠对被替换为一个反斜杠，双引号也被删除。例如:输入:MyData \\\\"app1 \\\\"app2，输出:MyData \\\app1，\app2。当双引号跟在奇数个反斜杠后面时，开始的反斜杠对被替换为一个反斜杠，其余的反斜杠被删除。在这种情况下，双引号不会被删除。例如:输入:MyData \\\\\"app1 \"app2，输出:MyData \\"app1 "，app2

**语法:**

> 公共静态字符串[] GetCommandLineArgs ()

**Return:** 它返回一个字符串数组，其中保存了当前正在运行的进程的命令行参数。在这个数组中，第一项是可执行文件名，其余项是命令行参数。

例外:

**notSupportDexception:**当不支持调用的方法时，或者当试图读取、查找或写入不支持调用功能的流时，会引发此异常。

**例** :

```cs
Input  : c/cpp java python
Output :
c/cpp
java
python

Input  : 11 java python
Output :
11
java
python
```

**例:**

## c#

```cs
// C# program to illustrate the use of
// GetCommandLineArgs() Method of Environment Class
using System;

class GFG{

static public void Main()
{

    // Declare an array of string that holds the
    // command-line arguments for the running process
    // Using GetCommandLineArgs() method of
    // Environment class
    string[] commandline = Environment.GetCommandLineArgs();

    Console.WriteLine("Command Line Arguments are:");

    // Display the command-line arguments for
    // the current process
    foreach(string arguments in commandline)
    {
        Console.WriteLine("\t" + arguments);
    }
}
}
```

**输出:**

```cs
Command Line Arguments are:
/Users/Projects/newprogram/newprogram/bin/Debug/netcoreapp3.0/newprogram.dll
```
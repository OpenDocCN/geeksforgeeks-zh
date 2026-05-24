# C# |命令行参数

> 原文:[https://www . geesforgeks . org/c-sharp-命令行-参数/](https://www.geeksforgeeks.org/c-sharp-command-line-arguments/)

用户或程序员传递给 **Main()** 方法的参数称为命令行参数。Main()方法是程序执行的入口点。Main()方法接受字符串数组。但是它从不接受程序中任何其他方法的参数。在 **[C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/)** 中，命令行参数通过如下方式传递给 Main()方法:

```cs
static void Main(string[] args)
or 
static int Main(string[] args)

```

**注意:**要在**窗口窗体应用程序**中启用 Main 方法中的命令行参数，必须在**程序中手动修改 Main 的签名。Windows 窗体设计器生成代码并创建不带输入参数的 Main。也可以使用 **[环境。命令行](https://docs.microsoft.com/en-us/dotnet/api/system.environment.commandline?view=netframework-4.7.2)** 或 **[环境。GetCommandLineArgs](https://docs.microsoft.com/en-us/dotnet/api/system.environment.getcommandlineargs?view=netframework-4.7.2)** 从控制台或 Windows 应用程序中的任意点访问命令行参数。**

**例:**

```cs
// C# program to illustrate the 
// Command Line Arguments
using System;  
namespace ComLineArg  
{  
    class Geeks {  

        // Main Method which accepts the
        // command line arguments as 
        // string type parameters  
        static void Main(string[] args) 
        {  

            // To check the length of 
            // Command line arguments  
            if(args.Length > 0)
            {
                Console.WriteLine("Arguments Passed by the Programmer:");  

                // To print the command line 
                // arguments using foreach loop
                foreach(Object obj in args)  
                {  
                    Console.WriteLine(obj);       
                }  
            }  

            else
            {
                Console.WriteLine("No command line arguments found.");
            }
    }   }
}
```

**要编译并执行上述程序，请遵循以下命令:**

```cs
Compile: csc Geeks.cs  
Execute: Geeks.exe Welcome To GeeksforGeeks!

```

**输出:**

```cs
Arguments Passed by the Programmer:
Welcome
To
GeeksforGeeks!

```

在上面的程序中，Length 用于查找命令行参数的数量，命令行参数将存储在 args[]数组中。借助 Convert 类和 parse 方法，还可以将字符串参数转换为数字类型。例如:

```cs
long num = Int64.Parse(args[0]);
or
long num = long.Parse(args[0]);

```

这将通过使用 Parse 方法将字符串更改为长类型。也可以使用 C# 类型 long，它别名 Int64。类似地，可以使用 C# 中预定义的解析方法进行解析。

**参考:**[https://docs . Microsoft . com/en-us/dotnet/csharp/编程指南/main-and-command-args/命令行参数](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/main-and-command-args/command-line-arguments)
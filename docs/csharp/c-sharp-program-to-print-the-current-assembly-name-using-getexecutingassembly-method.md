# 使用 GetExecutingAssembly()方法打印当前程序集名称的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-current-assembly-name-use-getexecutingassembly-method/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-current-assembly-name-using-getexecutingassembly-method/)

在 C# 中，GetExecutingAssembly()方法是 Assembly 类的方法。此方法返回包含当前正在执行的代码的程序集。要使用这种方法，我们必须使用系统。我们计划中的反思。

**语法**:

```cs
public static System.Reflection.Assembly GetExecutingAssembly ();
```

它将返回当前程序程序集、版本、区域性和公钥标记。

**例 1** :

## C#

```cs
// C# program to display the current assembly name 
using System;
using System.Reflection;

class GFG{

static void Main(string[] args)
{
    Console.WriteLine("Current assembly contains:");

    // Get the executing assembly
    // Using GetExecutingAssembly() method
    Console.WriteLine(Assembly.GetExecutingAssembly());
}
}
```

**输出:**

```cs
Current assembly contains:
main, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null
```

**例 2:**

## C#

```cs
// C# program to display the current assembly name 
using System;
using System.Reflection;

class GFG{

static void Main(string[] args)
{

    // Get the executing assembly 
    // with FullName property
    // FullName property is use 
    // to print the name of the assembly
    Console.WriteLine(Assembly.GetExecutingAssembly().FullName);
}
}
```

**输出:**

```cs
main, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null
```
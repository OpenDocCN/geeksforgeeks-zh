# 使用环境类检查 CLR 是否关闭的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-clr-正在关闭或未使用环境类/](https://www.geeksforgeeks.org/c-sharp-program-to-check-whether-the-clr-is-shutting-down-or-not-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将检查 CLR(公共语言运行库)是否正在关闭。所以我们使用环境类的 HasShutdownStarted 属性。此属性用于检查 CLR 是否正在关闭或应用程序域是否正在卸载。如果 CLR 关闭，那么它将返回真。否则，如果关闭了非 CLR，它将返回 false。

在 dot net 框架中，当应用程序域被 CLR 卸载时，它会对该应用程序域中包含终结器函数的所有对象执行终结器。因此，当 CLR 关闭时，它将在所有具有终结器功能的对象上执行终结器线程。因此，当终结器线程启动时，此属性返回 true，否则返回 false。

**语法** :

```cs
bool Environment.HasShutdownStarted
```

**返回类型**:该属性的返回类型为布尔值。如果 CLR 正在关闭，则返回真，否则返回假。

**例:**

## c#

```cs
// C# program to check whether the CLR is shutdown or not
// Using Environment class
using System;

class GFG
{

    static public void Main()
    {

        // Declare a variable
        bool result;

        // Determining whether the CLR is shutting down or not
        // Using HasShutdownStarted property of Environment class
        result = Environment.HasShutdownStarted;

        // Displaying result
        if (result == true)
            Console.WriteLine("Yes! CLR is shutting down");
        else
            Console.WriteLine("No! CLR is not shutting down");
    }
}
```

**输出:**

```cs
No! CLR is not shutting down
```
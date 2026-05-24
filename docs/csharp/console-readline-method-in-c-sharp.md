# 控制台。C# 中的 ReadLine()方法

> 原文:[https://www . geesforgeks . org/console-readline-method-in-c-sharp/](https://www.geeksforgeeks.org/console-readline-method-in-c-sharp/)

此方法用于从标准输入流中读取下一行字符。它属于[控制台类](https://www.geeksforgeeks.org/console-class-in-c-sharp/)(系统命名空间)。如果标准输入设备是键盘，则 ReadLine 方法会一直阻塞，直到用户按下回车键。如果标准输入被重定向到一个文件，那么这个方法从一个文件中读取一行文本。

> **语法:**公共静态字符串 ReadLine()；
> **返回值:**从输入流中返回下一行字符串类型的字符，如果没有可用的行，则返回 null。

**异常:**

*   **io 异常**:如果出现输入输出错误。
*   **OutOfMemoryException** :如果内存不足，无法为返回的字符串分配缓冲区。
*   **argumentoutofrangerexception**:如果下一行字符的字符数大于 MaxValue。

下面的程序说明了上述方法的使用:
**例 1:** 这里，从用户那里获取输入。因为年龄是一个整数，所以我们用 Convert 对它进行了类型化。ToInt32()方法。它从输入流中读取下一行。它会一直阻塞，直到按下回车键。因此，它通常用于暂停控制台，以便用户可以检查输出。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// the use of Console.ReadLine()
using System;
using System.IO;

class GFG {

    // Main Method
    public static void Main()
    {
        int age;
        string name;

        Console.WriteLine("Enter your name: ");

        // using the method
        // typecasting not needed
        // as ReadLine returns string
        name = Console.ReadLine();

        Console.WriteLine("Enter your age: ");

        // Converted string to int
        age = Convert.ToInt32(Console.ReadLine());

        if (age >= 18)
        {
            Console.WriteLine("Hello " + name + "!"
                        + " You can vote");
        }
        else {
            Console.WriteLine("Hello " + name + "!"
                + " Sorry you can't vote");
        }
    }
}
```

**输出:**

![](img/d1707f4212f26a760bd73f3ddf1bb3fa.png)

**示例 2:** 暂停控制台

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// the use of Console.ReadLine()
// to pause the console
using System;
using System.IO;

class Geeks {

    // Main Method
    public static void Main()
    {
        string name;
        int n;

        Console.WriteLine("Enter your name: ");

        // typecasting not needed as
        // ReadLine returns string
        name = Console.ReadLine();

        Console.WriteLine("Hello " + name +
             " Welcome to GeeksforGeeks!");

        // Pauses the console until
        // the user presses enter key
        Console.ReadLine();
    }
}
```

**输出:**

![](img/f8693ed42697981d9ac44044e1b7265c.png)

**说明:**在上面的输出中可以看到控制台暂停。光标将持续闪烁，直到您按下回车键。
T3【参考:

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . console . readline？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.console.readline?view=netframework-4.7.2)
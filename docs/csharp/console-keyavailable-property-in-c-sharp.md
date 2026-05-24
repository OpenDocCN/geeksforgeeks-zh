# 控制台。C# 中的 KeyAvailable()属性

> 原文:[https://www . geesforgeks . org/console-keyavailable-property-in-c-sharp/](https://www.geeksforgeeks.org/console-keyavailable-property-in-c-sharp/)

**控制台。KeyAvailable 属性**用于获取一个值，该值显示输入流中是否有按键可用。在按键可用之前，此属性不会阻止输入。

> **语法:**公共静态 bool KeyAvailable { get}
> **属性值:**返回*真*如果可以按键，否则返回假。

**异常:**

*   **无效操作异常:**如果标准输入被重定向到文件而不是键盘。
*   **io 异常:**如果出现输入/输出错误。

**示例:**

## C#

```cs
// C# Program to demonstrate
// KeyAvailable property
using System;
using System.Threading;

namespace GFG {

class GFG {

    public static void Main()
    {
        // declare a new ConsoleKeyInfo object
        ConsoleKeyInfo c = new ConsoleKeyInfo();

        // outer loop to work until 'z' is pressed
        do {
            Console.WriteLine("\nPress a key to display; "+
                              "press the 'z' key to quit.");

            // inner loop to check whether a key
            // is pressed using KeyAvailable
            while (Console.KeyAvailable == false)

                // Loop until input is entered.
                Thread.Sleep(50);
            c = Console.ReadKey(true);
            Console.WriteLine("You pressed the '{0}' key.", c.Key);

        } while (c.Key != ConsoleKey.Z);
    }
}
}
```
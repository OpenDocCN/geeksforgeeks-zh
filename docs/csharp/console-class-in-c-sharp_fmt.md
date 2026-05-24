# c# 中的控制台类

> 原文:[https://www.geeksforgeeks.org/console-class-in-c-sharp/](https://www.geeksforgeeks.org/console-class-in-c-sharp/)

控制台是一个操作系统窗口，用户可以通过它与操作系统进行通信，或者我们可以说控制台是一个应用程序，在其中我们可以从键盘给出文本作为输入，并从计算机端获得文本作为输出。命令提示符是窗口中控制台的一个示例，它接受 MS-DOS 命令。控制台包含两个名为屏幕缓冲区和控制台窗口的属性。

在 C# 中，`Console` 类用于表示控制台应用程序的标准输入、输出和错误流。不允许您继承控制台类。该类在 `System` 命名空间下定义。此类不包含任何构造函数。此类提供不同类型的属性和方法来执行操作，而不是构造函数。

## 属性

| 属性 | 描述 |
| --- | --- |
| `BackgroundColor` | 获取或设置控制台的背景色。 |
| `BufferHeight` | 获取或设置缓冲区的高度。 |
| `BufferWidth` | 获取或设置缓冲区的宽度。 |
| `CapsLock` | 获取一个值，该值指示大写锁定键盘开关是打开还是关闭。 |
| `CursorLeft` | 获取或设置光标在缓冲区内的列位置。 |
| `CursorSize` | 获取或设置字符单元格内光标的高度。 |
| `CursorTop` | 获取或设置光标在缓冲区内的行位置。 |
| `CursorVisible` | 获取或设置一个值，该值指示光标是否可见。 |
| `Error` | 获取标准错误输出流。 |
| `ForegroundColor` | 获取或设置控制台的前景色。 |
| `In` | 获取标准输入流。 |
| `InputEncoding` | 获取或设置控制台用于读取输入的编码。 |
| `IsError` | 获取一个值，该值指示错误输出流是否已从标准错误流重定向。 |
| `IsInputRedirected` | 获取一个值，该值指示输入是否已从标准输入流重定向。 |
| `IsOutputRedirected` | 获取一个值，该值指示输出是否已从标准输出流重定向。 |
| `KeyAvailable` | 获取一个值，该值指示按键在输入流中是否可用。 |
| `LargestWindowHeight` | 根据当前字体和屏幕分辨率，获取控制台窗口的最大可能行数。 |
| `LargestWindowWidth` | 根据当前字体和屏幕分辨率，获取最大可能数量的控制台窗口列。 |
| `NumberLock` | 获取一个值，该值指示数字锁定键盘开关是打开还是关闭。 |
| `Out` | 获取标准输出流。 |
| `OutputEncoding` | 获取或设置控制台用于写入输出的编码。 |
| `Title` | 获取或设置要在控制台标题栏中显示的标题。 |
| `TreatControlCAsInput` | 获取或设置一个值，该值指示控制修饰键和 C 控制台键(Ctrl+C)的组合是被视为普通输入还是被视为由操作系统处理的中断。 |
| `WindowHeight` | 获取或设置控制台窗口区域的高度。 |
| `WindowLeft` | 获取或设置控制台窗口区域相对于屏幕缓冲区的最左侧位置。 |
| `WindowTop` | 获取或设置控制台窗口区域相对于屏幕缓冲区的顶部位置。 |
| `WindowWidth` | 获取或设置控制台窗口的宽度。 |

**示例:**

```cs
// C# program to illustrate how to get
// Background and Foreground color
// of the console
using System;

public class GFG {

    static public void Main()
    {

        // Get the Background and foreground 
        // color of Console Using BackgroundColor
        // and ForegroundColor property of Console
        Console.WriteLine("Background color  :{0}",
                        Console.BackgroundColor);

        Console.WriteLine("Foreground color : {0}", 
                        Console.ForegroundColor);
    }
}
```

**Output:**

```cs
Background color : Black
Foreground color : Black
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Beep()` | 通过控制台扬声器播放蜂鸣声。 |
| `Clear()` | 清除控制台缓冲区和相应的控制台窗口的显示信息。 |
| `MoveBufferArea(Int32, Int32, Int32, Int32, Int32, Int32)` | 将屏幕缓冲区的指定源区域复制到指定的目标区域。 |
| `OpenStandardError()` | 获取标准错误流。 |
| `OpenStandardInput()` | 获取标准输入流。 |
| `OpenStandardOutput()` | 获取标准输出流。 |
| `Read()` | 从标准输入流中读取下一个字符。 |
| `ReadKey()` | 获取用户按下的下一个字符或功能键。按下的键显示在控制台窗口中。 |
| `ReadLine()` | 从标准输入流中读取下一行字符。 |
| `ResetColor()` | 将前台和后台控制台颜色设置为默认值。 |
| `SetBufferSize(Int32, Int32)` | 将屏幕缓冲区的高度和宽度设置为指定值。 |
| `SetCursorPosition(Int32, Int32)` | 设置光标的位置。 |
| `SetError(TextWriter)` | 将 `Error` 属性设置为指定的 `TextWriter` 对象。 |
| `SetIn(TextReader)` | 将 `In` 属性设置为指定的 `TextReader` 对象。 |
| `SetOut(TextWriter)` | 将 `Out` 属性设置为指定的 `TextWriter` 对象。 |
| `SetWindowPosition(Int32, Int32)` | 设置控制台窗口相对于屏幕缓冲区的位置。 |
| `SetWindowSize(Int32, Int32)` | 将控制台窗口的高度和宽度设置为指定值。 |
| `Write()` | 将指定值的文本表示形式写入标准输出流。 |
| `WriteLine()` | 将指定的数据(后跟当前行结束符)写入标准输出流。 |

**示例:**

```cs
// C# program to illustrate the concept
// of WriteLine(String) method in console
using System;

public class GFG {

    static public void Main()
    {

        // WriteLine(String) method is used 
        // to display the string
        Console.WriteLine("Welcome to GeeksforGeeks");
        Console.WriteLine("This is a tutorial of Console Class");
    }
}
```

**Output:**

```cs
Welcome to GeeksforGeeks
This is a tutorial of Console Class
```

## 事件

| 事件 | 描述 |
| --- | --- |
| `CancelKeyPress` | 当同时按下控制修饰键(Ctrl)和 C 控制台键(C)或中断键(Ctrl+C 或 Ctrl+Break)时发生。 |

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.console?view=netframework-4.7.2#definition](https://docs.microsoft.com/en-us/dotnet/api/system.console?view=netframework-4.7.2#definition)
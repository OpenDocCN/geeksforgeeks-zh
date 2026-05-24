# c# 中的控制台类

> 原文:[https://www.geeksforgeeks.org/console-class-in-c-sharp/](https://www.geeksforgeeks.org/console-class-in-c-sharp/)

控制台是一个操作系统窗口，用户可以通过它与操作系统进行通信，或者我们可以说控制台是一个应用程序，在其中我们可以从键盘给出文本作为输入，并从计算机端获得文本作为输出。命令提示符是窗口中控制台的一个示例，它接受 MS-DOS 命令。控制台包含两个名为屏幕缓冲区和控制台窗口的属性。
在 C# 中，Console 类用于表示控制台应用程序的标准输入、输出和错误流。不允许您继承控制台类。该类在*系统*命名空间下定义。此类不包含任何构造函数。此类提供不同类型的属性和方法来执行操作，而不是构造函数。

#### 性能

| 财产 | 描述 |
| **[【背景色】](https://www.geeksforgeeks.org/c-sharp-how-to-change-background-color-of-text-in-console/)** | 获取或设置控制台的背景色。 |
| **[【缓冲高度】](https://www.geeksforgeeks.org/c-sharp-how-to-change-bufferheight-of-the-console/)** | 获取或设置缓冲区的高度。 |
| **[【缓冲宽度】](https://www.geeksforgeeks.org/c-sharp-how-to-change-bufferwidth-of-the-console/)** | 获取或设置缓冲区的宽度。 |
| **[【caps lock】](https://www.geeksforgeeks.org/c-sharp-check-if-caps-lock-is-on-or-off-through-console/)** | 获取一个值，该值指示大写锁定键盘开关是打开还是关闭。 |
| **[【游标左】](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-cursorleft-of-the-console/)** | 获取或设置光标在缓冲区内的列位置。 |
| **[游标大小](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-cursorsize-of-the-console/)** | 获取或设置字符单元格内光标的高度。 |
| **[【游标顶部】](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-cursortop-of-the-console/)** | 获取或设置光标在缓冲区内的行位置。 |
| [游标可见](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-visibility-of-the-cursor-of-console/) | 获取或设置一个值，该值指示光标是否可见。 |
| **[错误](https://www.geeksforgeeks.org/c-sharp-getting-the-standard-error-output-stream-through-console/)** | 获取标准错误输出流。 |
| **[【foregroundcolor】](https://www.geeksforgeeks.org/c-sharp-how-to-change-foreground-color-of-text-in-console/)** | 获取或设置控制台的前景色。 |
| **[在](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-standard-input-stream-through-console/)** | 获取标准输入流。 |
| **[输入编码](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-input-encoding-scheme-of-the-console/)** | 获取或设置控制台用于读取输入的编码。 |
| **[是错误的](https://www.geeksforgeeks.org/c-sharp-check-if-error-is-redirected-on-the-console-or-not/)** | 获取一个值，该值指示错误输出流是否已从标准错误流重定向。 |
| **[是指](https://www.geeksforgeeks.org/c-sharp-check-if-input-is-redirected-on-the-console-or-not/)** | 获取一个值，该值指示输入是否已从标准输入流重定向。 |
| **[同向](https://www.geeksforgeeks.org/c-sharp-check-if-output-is-redirected-on-the-console-or-not/)** | 获取一个值，该值指示输出是否已从标准输出流重定向。 |
| **[【可用钥匙】](https://www.geeksforgeeks.org/console-keyavailable-property-in-c-sharp/)** | 获取一个值，该值指示按键在输入流中是否可用。 |
| **[【宽风洞高度】](https://www.geeksforgeeks.org/c-sharp-getting-the-largest-window-height-of-the-console/)** | 根据当前字体和屏幕分辨率，获取控制台窗口的最大可能行数。 |
| **[【宽风洞宽度】](https://www.geeksforgeeks.org/c-sharp-getting-the-largest-window-width-of-the-console/)** | 根据当前字体和屏幕分辨率，获取最大可能数量的控制台窗口列。 |
| **[号块](https://www.geeksforgeeks.org/c-sharp-check-if-num-lock-is-on-or-off-through-console/)** 号块 | 获取一个值，该值指示数字锁定键盘开关是打开还是关闭。 |
| **[出](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-standard-output-stream-through-console/)** | 获取标准输出流。 |
| **[输出编码](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-output-encoding-scheme-of-the-console/)** | 获取或设置控制台用于写入输出的编码。 |
| **[标题](https://www.geeksforgeeks.org/c-sharp-how-to-change-title-of-the-console/)** | 获取或设置要在控制台标题栏中显示的标题。 |
| **[治疗控制输入](https://www.geeksforgeeks.org/console-treatcontrolcasinput-property-in-c-sharp-with-examples/)** | 获取或设置一个值，该值指示控制修饰键和 C 控制台键(Ctrl+C)的组合是被视为普通输入还是被视为由操作系统处理的中断。 |
| 窗高 | 获取或设置控制台窗口区域的高度。 |
| **[【windowleft】](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-windowleft-of-the-console/)** | 获取或设置控制台窗口区域相对于屏幕缓冲区的最左侧位置。 |
| **[【windowtop】](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-windowtop-of-the-console/)** | 获取或设置控制台窗口区域相对于屏幕缓冲区的顶部位置。 |
| **[窗口宽度](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-windowwidth-of-the-console/)** | 获取或设置控制台窗口的宽度。 |

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
        Console.WriteLine("Background color  :{0}",
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

#### 方法

| 方法 | 描述 |
| **[【哔()](https://www.geeksforgeeks.org/c-sharp-how-to-play-beep-sound-through-console/)** | 通过控制台扬声器播放蜂鸣声。 |
| **[晴()](https://www.geeksforgeeks.org/console-clear-method-in-c-sharp/)** | 清除控制台缓冲区和相应的控制台窗口的显示信息。 |
| **[【移动缓冲区()](https://www.geeksforgeeks.org/console-movebufferarea-method-in-c-sharp/)** | 将屏幕缓冲区的指定源区域复制到指定的目标区域。 |
| **open standards error()** | 获取标准错误流。 |
| **开放式标准输入()T3** | 获取标准输入流。 |
| **OpenStandardOutput()** | 获取标准输出流。 |
| **[读作()](https://www.geeksforgeeks.org/console-read-method-in-c-sharp/)** | 从标准输入流中读取下一个字符。 |
| **[【read key()](https://www.geeksforgeeks.org/console-readkey-method-in-c-sharp/)** | 获取用户按下的下一个字符或功能键。按下的键显示在控制台窗口中。 |
| **阅读线()** | 从标准输入流中读取下一行字符。 |
| **[【重置颜色()](https://www.geeksforgeeks.org/console-resetcolor-method-in-c-sharp/)** | 将前台和后台控制台颜色设置为默认值。 |
| **T1】SetBufferSize(Int32，Int32)T3】** | 将屏幕缓冲区的高度和宽度设置为指定值。 |
| **[SetCursorPosition(Int32，Int32)](https://www.geeksforgeeks.org/console-setcursorposition-method-in-c-sharp/)** | 设置光标的位置。 |
| **设置错误(文本书写器)T3** | 将错误属性设置为指定的文本编写器对象。 |
| **设置(文本阅读器)T3** | 将“输入”属性设置为指定的文本阅读器对象。 |
| **[设定](https://www.geeksforgeeks.org/console-setout-method-in-c-sharp/)** | 将输出属性设置为指定的文本编写器对象。 |
| **[SetWindowPosition(Int32，Int32)](https://www.geeksforgeeks.org/console-setwindowposition-method-in-c-sharp/)** | 设置控制台窗口相对于屏幕缓冲区的位置。 |
| **[SetWindowSize(Int32，Int32)](https://www.geeksforgeeks.org/console-setwindowsize-method-in-c-sharp/)** | 将控制台窗口的高度和宽度设置为指定值。 |
| **Write()** | 将指定值的文本表示形式写入标准输出流。 |
| **WriteLine()** | 将指定的数据(后跟当前行结束符)写入标准输出流。 |

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

#### 事件

| 事件 | 描述 |
| 取消按键 | 当同时按下控制修饰键(Ctrl)和 C 控制台键(C)或中断键(Ctrl+C 或 Ctrl+中断)时发生。 |

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.console?视图= net framework-4 . 7 . 2 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.console?view=netframework-4.7.2# definition)
# C# 程序不使用写线打印 Hello World】

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-hello-world-无需使用-writeline/](https://www.geeksforgeeks.org/c-sharp-program-to-print-hello-world-without-using-writeline/)

Hello World 程序是任何编程语言中最基础的程序。它在屏幕上打印“你好世界”。在本文中，我们将显示“你好世界”，而不使用写线方法。所以做这个任务我们用以下方法:

*   [**Console. Open standard output (**](https://www.geeksforgeeks.org/console-openstandardoutput-method-in-c-sharp-with-examples/) **):** This method is used to obtain the standard output stream.
*   [**Console. Read key ()**](https://www.geeksforgeeks.org/console-readkey-method-in-c-sharp/) **:** This method is used to get the next character pressed by the user, which will be displayed in the console window.
*   **BeginWrite ():** This method is used to start an asynchronous write operation.

**异步等待处理。WaitOne():** 

为了编写 Hello World，我们以 ASCII 格式获取每个单独的字符，然后将这些字符一起显示。

<figure class="table">

| **弦** | H | e | l | l | o |   | W | o | r | l | d |
| ascii 码 | seventy-two | One hundred and one | One hundred and eight | One hundred and eight | One hundred and eleven | Thirty-two | Eighty-seven | One hundred and eleven | One hundred and fourteen | One hundred and eight | One hundred |

</figure>

### 方法

**1。**内部 if 条件，写 OpenStandardOutput()显示 Hello World。

**2。**这个方法后面跟一个 BeginWrite()方法，取整数 Bytes。

```cs
BeginWrite(new byte[] { 072, 101, 108, 108, 111, 032, 087, 111, 
                        114, 108, 100, 0 }, 0, 12, null, null)
```

**3。**最后我们用的是 AsyncWaitHandle。WaitOne()方法后跟 BeginWrite()方法。

```cs
BeginWrite(new byte[] { 072, 101, 108, 108, 111, 032, 087, 111, 
                        114, 108, 100, 0 }, 0, 12, null, 
                        null).AsyncWaitHandle.WaitOne()) 
```

**例:**

## c#

```cs
// C# program to display Hello World without
// using WriteLine() method
using System;

class GFG{

static void Main(string[] args)
{

    // ASCII values for Hello World
    if (System.Console.OpenStandardOutput().BeginWrite(new byte[] { 
        072, 101, 108, 108, 111, 032, 087, 111, 114, 108, 100, 0 }, 
        0, 12, null, null).AsyncWaitHandle.WaitOne()) 
    { 
    }
}
}
```

**输出** :

```cs
Hello World
```
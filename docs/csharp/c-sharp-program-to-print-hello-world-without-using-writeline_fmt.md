# C# 程序：不使用 WriteLine 打印 Hello World

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-print-hello-world-without-using-writeline/](https://www.geeksforgeeks.org/c-sharp-program-to-print-hello-world-without-using-writeline/)

Hello World 程序是任何编程语言中最基础的程序。它在屏幕上打印“Hello World”。在本文中，我们将显示“Hello World”，而不使用 `WriteLine` 方法。所以做这个任务我们用以下方法：

*   [`Console.OpenStandardOutput()`](https://www.geeksforgeeks.org/console-openstandardoutput-method-in-c-sharp-with-examples/)：此方法用于获取标准输出流。
*   [`Console.ReadKey()`](https://www.geeksforgeeks.org/console-readkey-method-in-c-sharp/)：此方法用于获取用户按下的下一个字符，该字符将显示在控制台窗口中。
*   `BeginWrite()`：此方法用于启动异步写操作。
*   `AsyncWaitHandle.WaitOne()`：

为了编写 Hello World，我们以 ASCII 格式获取每个单独的字符，然后将这些字符一起显示。

| 字符 | H | e | l | l | o |   | W | o | r | l | d |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ASCII 码 | 72 | 101 | 108 | 108 | 111 | 32 | 87 | 111 | 114 | 108 | 100 |

### 方法

1.  内部 `if` 条件，调用 `OpenStandardOutput()` 显示 Hello World。
2.  这个方法后面跟一个 `BeginWrite()` 方法，取整数 `Bytes`。
    ```cs
    BeginWrite(new byte[] { 072, 101, 108, 108, 111, 032, 087, 111, 
                            114, 108, 100, 0 }, 0, 12, null, null)
    ```
3.  最后我们用的是 `AsyncWaitHandle.WaitOne()` 方法，它跟在 `BeginWrite()` 方法之后。
    ```cs
    BeginWrite(new byte[] { 072, 101, 108, 108, 111, 032, 087, 111, 
                            114, 108, 100, 0 }, 0, 12, null, 
                            null).AsyncWaitHandle.WaitOne())
    ```

**示例：**

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

**输出：**

```cs
Hello World
```
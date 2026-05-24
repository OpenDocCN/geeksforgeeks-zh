# 螺纹。C# 中的重置端口方法

> 原文:[https://www . geesforgeks . org/thread-resetabort-method-in-c-sharp/](https://www.geeksforgeeks.org/thread-resetabort-method-in-c-sharp/)

一个[线程类](https://www.geeksforgeeks.org/thread-class-in-c/)负责在多线程编程中创建和管理一个线程。它提供了一种称为**重置端口**的方法，负责取消当前线程的中止请求。它防止*线程异常*终止线程。

**语法:**

```cs
public static void ResetAbort ();
```

**异常:**

*   *线程状态异常*:如果当前线程没有调用中止。
*   *安全异常*:如果调用者没有当前线程所需的安全权限。

以下程序说明了 *ResetAbort()* 方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// use of ResetAbort method
using System;
using System.Threading;
using System.Security.Permissions;

class MyThread {

    // Method Job
    public void Job()
    {
        try {

            for (int I = 0; I < 10; I++) 
            {
                Console.WriteLine(" My Thread is working..!");
                Thread.Sleep(100);
            }
        }

        catch (ThreadAbortException e) 
        {
            Console.WriteLine("Caught ThreadAbortException and reset");
            Console.WriteLine("Ex message: {0}", e.Message);
            Thread.ResetAbort();
        }

        Console.WriteLine("Thread is alive and working..!");
        Thread.Sleep(2000);
        Console.WriteLine("Thread is finished its working..!");
    }
}

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {
        MyThread obj = new MyThread();
        Thread T = new Thread(obj.Job);
        T.Start();
        Thread.Sleep(100);
        Console.WriteLine("Aborting thread");
        T.Abort();
        T.Join();
        Console.WriteLine("Main thread ends");
    }
}
```

**输出:**

```cs
My Thread is working..!
Aborting thread
Caught ThreadAbortException and reset
Ex message: Thread was being aborted.
Thread is alive and working..!
Thread is finished its working..!
Main thread ends

```

**例 2:**

```cs
// C# program to illustrate the
// use of ResetAbort method
using System;
using System.Threading;

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing  threads
        Thread thr = new Thread(Job);

        // Start the execution of Thread
        thr.Start();

        // Reset abort request
        // Using ResetAbort method
        Thread.ResetAbort();
    }

    public static void Job()
    {
        Console.WriteLine("Hello");
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。线程。线程状态异常:无法重置中止，因为没有请求中止。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . reseta port？视图=网络框架-4 . 7 . 2 # 系统 _ 线程 _ 线程 _ 重置端口](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.resetabort?view=netframework-4.7.2# System_Threading_Thread_ResetAbort)
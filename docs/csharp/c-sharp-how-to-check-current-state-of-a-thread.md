# C# |如何检查线程的当前状态

> 原文:[https://www . geesforgeks . org/c-sharp-如何检查当前线程状态/](https://www.geeksforgeeks.org/c-sharp-how-to-check-current-state-of-a-thread/)

线程类负责在多线程编程中创建和管理线程。它提供了一个名为**线程状态**的*属性*来检查线程的当前状态。线程的初始状态是*未启动*状态。

**语法:**

```cs
public ThreadState ThreadState{ get; }
```

**返回值:**该属性返回指示当前线程状态的值。

以下程序说明了*线程状态*属性的使用:

**例 1:**

```cs
// C# program to illustrate the 
// use of ThreadState property
using System;
using System.Threading;

public class GFG {

    // Main Method
    static public void Main()
    {
        Thread thr;

        // Get the reference of main Thread
        // Using CurrentThread property
        thr = Thread.CurrentThread;

        // Display the current state
        // of the main thread
        Console.WriteLine("The name of the current state of the Main " 
                                 + "thread is: {0}", thr.ThreadState);
    }
}
```

**输出:**

```cs
The name of the current state of the main thread is: Running

```

**例 2:**

```cs
// C# program to illustrate the 
// use of ThreadState property
using System;
using System.Threading;

public class GFG {

    // Main method
    public static void Main()
    {
        // Creating and initializing threads
        Thread TR1 = new Thread(new ThreadStart(job));
        Thread TR2 = new Thread(new ThreadStart(job));

        Console.WriteLine("ThreadState of TR1 thread"+
                         " is: {0}", TR1.ThreadState);

        Console.WriteLine("ThreadState of TR2 thread"+
                         " is: {0}", TR2.ThreadState);

        // Running state
        TR1.Start();
        Console.WriteLine("ThreadState of TR1 thread "+
                           "is: {0}", TR1.ThreadState);

        TR2.Start();
        Console.WriteLine("ThreadState of TR2 thread"+
                         " is: {0}", TR2.ThreadState);
    }

    // Static method
    public static void job()
    {
        Thread.Sleep(2000);
    }
}
```

**输出:**

```cs
ThreadState of TR1 thread is: Unstarted
ThreadState of TR2 thread is: Unstarted
ThreadState of TR1 thread is: Running
ThreadState of TR2 thread is: WaitSleepJoin

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . thread state？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.threadstate?view=netframework-4.7.2)
# 螺纹。C# 中的 CurrentThread 属性

> 原文:[https://www . geesforgeks . org/thread-currentthread-property-in-c-sharp/](https://www.geeksforgeeks.org/thread-currentthread-property-in-c-sharp/)

线程类负责在多线程编程中创建和管理线程。它提供了一个名为 **CurrentThread** 的属性来检查当前运行的线程。或者换句话说，该属性的值指示当前正在运行的线程。

> **语法:**公共静态 Thread CurrentThread { get}
> 
> **返回值:**该属性返回一个代表当前运行线程的线程。

下面的程序说明了 CurrentThread 属性的使用:
。
**例 1:**

```cs
// C# program to illustrate the 
// use of CurrentThread property
using System;
using System.Threading;

class GFG {

    // Main Method
    static public void Main()
    {
        Thread thr;

        // Get the reference of main Thread
        // Using CurrentThread property
        thr = Thread.CurrentThread;
        thr.Name = "Main thread";
        Console.WriteLine("Name of current running "+
                            "thread: {0}", thr.Name);
    }
}
```

**输出:**

```cs
Name of current running thread: Main thread
```

**例 2:**

```cs
// C# program to illustrate the
// use of CurrentThread property
using System;
using System.Threading;

class GFG {

    // Display the id of each thread
    // Using CurrentThread and 
    // ManagedThreadId properties
    public static void Myjob()
    {
        Console.WriteLine("Thread Id: {0}", 
           Thread.CurrentThread.ManagedThreadId);
    }

    // Main method
    static public void Main()
    {

        // Creating multiple threads
        ThreadStart value = new ThreadStart(Myjob);
        for (int q = 1; q <= 7; ++q) 
        {
            Thread mythread = new Thread(value);
            mythread.Start();
        }
    }
}
```

**输出:**

```cs
Thread Id: 3
Thread Id: 8
Thread Id: 9
Thread Id: 6
Thread Id: 5
Thread Id: 7
Thread Id: 4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . current thread？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.currentthread?view=netframework-4.7.2)
# C# |多线程中的线程优先级

> 原文:[https://www . geeksforgeeks . org/c-sharp-thread-priority-in-多线程/](https://www.geeksforgeeks.org/c-sharp-thread-priority-in-multithreading/)

在多线程环境中，每个线程都有自己的优先级。一个线程的优先级显示了一个线程访问 CPU 资源的频率。每当我们在 C# 中创建一个线程时，它总是被赋予一些优先级。

**要点:**

*   程序员可以显式地为线程分配优先级。
*   线程的默认优先级是*正常*。
*   操作系统不分配线程的优先级。
*   如果线程已经到达最终状态，例如*中止*，那么这将给出`ThreadStateException`。
*   如果为设置操作指定的值不是有效的*线程优先级*值，那么这将给出`ArgumentException`
*   不能保证优先级高的线程先执行，优先级低的线程后执行。由于上下文切换，最高优先级线程可能在最低优先级线程之后执行。
*   当你给一个线程分配优先级时，你需要小心，如果你做得不小心，你可能会让线程*饥饿*。
*   线程优先级将始终取决于进程优先级或父容器，因此将线程优先级设置为最高不会对应于实时执行。

#### 如何设置和获取线程的优先级？

**螺纹。优先级属性**用于获取或设置一个指示线程调度优先级的值。

**语法:**

```cs
public ThreadPriority Priority{ get; set; }
```

这里，`System.Threading`命名空间下的*线程优先级*枚举负责指定线程的调度优先级，优先级为:

*   **最高:**该优先级的值为 4。
*   **高于正常值:**该优先级的值为 3。
*   **正常:**该优先级的值为 2。
*   **低于正常值:**该优先级的值为 1。
*   **最低:**该优先级的值为 0。

**属性值:**线程优先级值之一。默认值为正常。

**异常:**

*   **线程状态异常:**如果线程已经达到最终状态，如中止。
*   **参数异常:**如果为设置操作指定的值不是有效的线程优先级值。

**例 1:**

```cs
// C# program to illustrate how to
// set and get the priority of threads
using System;
using System.Threading;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating and initializing threads
        Thread T1 = new Thread(work);
        Thread T2 = new Thread(work);
        Thread T3 = new Thread(work);

        // Set the priority of threads
        T2.Priority = ThreadPriority.Highest;
        T3.Priority = ThreadPriority.BelowNormal;
        T1.Start();
        T2.Start();
        T3.Start();

        // Display the priority of threads
        Console.WriteLine("The priority of T1 is: {0}",
                                          T1.Priority);

        Console.WriteLine("The priority of T2 is: {0}",
                                          T2.Priority);

        Console.WriteLine("The priority of T3 is: {0}",
                                          T3.Priority);
    }

    public static void work()
    {

        // Sleep for 1 second
        Thread.Sleep(1000);
    }
}
```

**输出:**

```cs
The priority of T1 is: Normal
The priority of T2 is: Highest
The priority of T3 is: BelowNormal

```

**例 2:**

```cs
// C# program to illustrate the
// Priority property of Thread class
using System;
using System.Threading;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating and initializing threads
        Thread T1 = new Thread(work1);
        Thread T2 = new Thread(work2);

        // Set the priority of threads
        // Here T2 thread executes first 
        // because the Priority of T2 is
        // highest as compare to T1 thread
        T1.Priority = ThreadPriority.Lowest;
        T2.Priority = ThreadPriority.Highest;
        T1.Start();
        T2.Start();
    }
    public static void work1()
    {

        Console.WriteLine("T1 thread is working..");
    }
    public static void work2()
    {

        Console.WriteLine("T2 thread is working..");
    }
}
```

**输出:**

```cs
T2 thread is working..
T1 thread is working..

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . priority？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.priority?view=netframework-4.7.2)
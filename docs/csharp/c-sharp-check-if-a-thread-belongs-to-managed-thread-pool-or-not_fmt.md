# C# | 检查线程是否属于托管线程池

> 原文: [https://www.geeksforgeeks.org/c-sharp-check-if-a-thread-belongs-to-managed-thread-pool-or-not/](https://www.geeksforgeeks.org/c-sharp-check-if-a-thread-belongs-to-managed-thread-pool-or-not/)

线程类负责在多线程编程中创建和管理线程。它提供了一个名为 `IsThreadPoolThread` 的属性来检查该线程是否属于托管线程池。

## 语法

```cs
public bool IsThreadPoolThread { get; }
```

## 返回值

如果给定线程属于托管线程池，则该属性返回 `true`。否则，返回 `false`。该属性的返回类型为 `System.Boolean`。

下面的程序说明了 `IsThreadPoolThread` 属性的使用：

## 例 1

```cs
// C# program to illustrate the use 
// of IsThreadPoolThread  property
using System;
using System.Threading;

class GFG {

// Main Method
    static public void Main()
    {
        Thread T;

// Get the reference of main Thread
        // Using CurrentThread property
        T = Thread.CurrentThread;

// Check if the main thread belongs to
        // the managed thread pool or not
        // Using IsThreadPoolThread  property
        Console.WriteLine("Is main thread belongs to Thread"+
                      " pool? : {0} ", T.IsThreadPoolThread);
    }
}
```

**输出:**

```cs
Is main thread belongs to Thread pool? : False 
```

## 例 2

```cs
// C# program to illustrate the use
//  of IsThreadPoolThread  property
using System;
using System.Threading;

class GFG {

// Main method
    public static void Main()
    {

// Creating and initializing threads
        Thread TR1 = new Thread(new ThreadStart(job));
        ThreadPool.QueueUserWorkItem(new WaitCallback(job1));
        TR1.Start();
    }

// Static methods
    public static void job()
    {
        Console.WriteLine("Is thread 1 belongs to thread pool: {0}",
                           Thread.CurrentThread.IsThreadPoolThread);
    }

public static void job1(object stateInfo)
    {
        Console.WriteLine("Is thread 2 belongs to thread pool: {0}",
                           Thread.CurrentThread.IsThreadPoolThread);
    }
}
```

**输出:**

```cs
Is thread 1 belongs to thread pool: False
Is thread 2 belongs to thread pool: True
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.isthreadpoolthread?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.isthreadpoolthread?view=netframework-4.7.2)
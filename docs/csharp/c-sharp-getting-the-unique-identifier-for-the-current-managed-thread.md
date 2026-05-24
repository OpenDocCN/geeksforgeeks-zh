# C# |获取当前托管线程的唯一标识符

> 原文:[https://www . geesforgeks . org/c-sharp-获取当前托管线程的唯一标识符/](https://www.geeksforgeeks.org/c-sharp-getting-the-unique-identifier-for-the-current-managed-thread/)

线程类负责在多线程编程中创建和管理线程。它提供了一个名为**managed readid**的属性来检查当前托管线程的唯一标识符。或者换句话说，线程的 ManagedThreadId 属性的值在其进程中唯一地定义了该线程。ManagedThreadId 属性的值不会随时间变化。

**语法:**

```cs
public int ManagedThreadId { get; }
```

**返回值:**此属性返回一个值，该值指示此托管线程的唯一标识符。该属性的返回类型为*系统。Int32* 。

**例 1:**

```cs
// C# program to illustrate the 
// use of ManagedThreadId property
using System;
using System.Threading;

public class GFG {

    // Main Method
    static public void Main()
    {
        Thread T;

        // Get the reference of main Thread
        // Using CurrentThread property
        T = Thread.CurrentThread;

        // Display the unique id of the main 
        // thread Using ManagedThreadId property
        Console.WriteLine("The unique id of the main "+
                 "thread is: {0} ", T.ManagedThreadId);
    }
}
```

**输出:**

```cs
The unique id of the main thread is: 1 

```

**例 2:**

```cs
// C# program to illustrate the 
// use of ManagedThreadId property
using System;
using System.Threading;

public class GFG {

    // Main method
    public static void Main()
    {
        // Creating and initializing threads
        Thread thr1 = new Thread(new ThreadStart(job));
        Thread thr2 = new Thread(new ThreadStart(job));
        Thread thr3 = new Thread(new ThreadStart(job));

        Console.WriteLine("ManagedThreadId of thread 1 "+
                        "is: {0}", thr1.ManagedThreadId);

        Console.WriteLine("ManagedThreadId of thread 2 "+
                        "is: {0}", thr2.ManagedThreadId);

        Console.WriteLine("ManagedThreadId of thread 3 "+
                        "is: {0}", thr3.ManagedThreadId);

        // Running state
        thr1.Start();
        thr2.Start();
        thr3.Start();
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
ManagedThreadId of thread 1 is: 3
ManagedThreadId of thread 2 is: 4
ManagedThreadId of thread 3 is: 5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . managed readid？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.managedthreadid?view=netframework-4.7.2)
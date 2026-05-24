# 如何在 C# 中检查线程是否存活

> 原文：[https://www.geeksforgeeks.org/how-to-check-whether-a-thread-is-alive-or-not-in-c/](https://www.geeksforgeeks.org/how-to-check-whether-a-thread-is-alive-or-not-in-c/)

`Thread`类负责在多线程编程中创建和管理线程。它提供了一个名为 `IsAlive` 的属性来检查线程是否活动。或者换句话说，该属性的值指示线程的当前执行。

## 语法

```cs
public bool IsAlive { get; }
```

## 返回值

如果线程正常启动而没有终止或中止，该属性返回 `true`。否则，返回 `false`。该属性的返回类型为 `System.Boolean`。

以下程序说明了 `IsAlive` 属性的使用：

## 例 1

```cs
// C# program to illustrate the 
// use of IsAlive property
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

// Display the current state of 
        // the main thread Using IsAlive
        // property
        Console.WriteLine("Is main thread is alive"+
                            " ? : {0}", thr.IsAlive);
    }
}
```

**输出：**

```cs
Is main thread is alive ? : True
```

## 例 2

```cs
// C# program to illustrate the 
// use of IsAlive property
using System;
using System.Threading;

public class GFG {

// Main method
    public static void Main()
    {
        // Creating and initializing threads
        Thread Thr1 = new Thread(new ThreadStart(job));
        Thread Thr2 = new Thread(new ThreadStart(job));

// Display the current state of 
        // the threads Using IsAlive 
        // property
        Console.WriteLine("Is thread 1 is alive : {0}",
                                 Thr1.IsAlive);

        Console.WriteLine("Is thread 2 is alive : {0}",
                                 Thr2.IsAlive);
        Thr1.Start();
        Thr2.Start();

// Display the current state of 
        // the threads Using IsAlive
        // property
        Console.WriteLine("Is thread 1 is alive : {0}",
                                 Thr1.IsAlive);

        Console.WriteLine("Is thread 2 is alive : {0}",
                                 Thr2.IsAlive);
    }

// Static method
    public static void job()
    {
        Thread.Sleep(2000);
    }
}
```

**输出：**

```cs
Is thread 1 is alive : False
Is thread 2 is alive : False
Is thread 1 is alive : True
Is thread 2 is alive : True
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.isalive?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.isalive?view=netframework-4.7.2)
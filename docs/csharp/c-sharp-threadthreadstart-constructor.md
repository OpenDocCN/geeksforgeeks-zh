# C# |线程(ThreadStart)构造器

> 原文:[https://www . geeksforgeeks . org/c-sharp-thread start-constructor/](https://www.geeksforgeeks.org/c-sharp-threadthreadstart-constructor/)

**线程(ThreadStart)构造器**用于初始化一个线程类的新实例。如果参数值为空，该构造函数将给出 *ArgumentNullException* 。

**语法:**

```cs
public Thread(ThreadStart start);
```

这里， *ThreadStart* 是一个[委托](https://www.geeksforgeeks.org/c-delegates/)，它表示当这个线程开始执行时要调用的一个方法。

以下程序说明了*线程(ThreadStart)* 构造函数的使用:

**例 1:**

```cs
// C# program to illustrate the
// use of Thread(ThreadStart) 
// constructor with static method
using System;
using System.Threading;

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing a thread
        // with Thread(ThreadStart) constructor
        Thread thr = new Thread(new ThreadStart(Job));
        thr.Start();
    }

    // Static method
    public static void Job()
    {
        Console.WriteLine("Number is :");
        for (int z = 0; z < 4; z++) {
            Console.WriteLine(z);
        }
    }
}
```

**输出:**

```cs
Number is :
0
1
2
3

```

**例 2:**

```cs
// C# program to illustrate the
// use of Thread(ThreadStart) 
// constructor with Non-static method
using System;
using System.Threading;

class GThread {

    // Non-static method
    public void Job()
    {
        for (int z = 0; z < 3; z++) {
            Console.WriteLine("HELLO...!!");
        }
    }
}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of GThread class
        GThread obj = new GThread();

        // Creating and initializing a thread
        // with Thread(ThreadStart) constructor
        Thread thr = new Thread(new ThreadStart(obj.Job));
        thr.Start();
    }
}
```

**输出:**

```cs
HELLO...!!
HELLO...!!
HELLO...!!

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread-ctor？view = net framework-4 . 7 . 2 # System _ Threading _ Thread _ ctor _ System _ Threading _ Thread start _](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=netframework-4.7.2# System_Threading_Thread__ctor_System_Threading_ThreadStart_)
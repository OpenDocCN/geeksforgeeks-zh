# 如何在 C# 中检查一个线程是否是后台线程

> 原文:[https://www . geesforgeks . org/how-to-check-thread-thread-in-c-sharp/](https://www.geeksforgeeks.org/how-to-check-whether-a-thread-is-a-background-thread-or-not-in-c-sharp/)

我们知道线程是由线程类创建和管理的。因此，Thread 类提供了一个名为**的属性 IsBackground 属性**来检查给定的线程是在后台运行还是在前台运行。如果*是背景*的值设置为*真*，则表示该线程是背景线程。或者如果*的值是 Background* 设置为 *false* ，则表示该线程是前台线程。

**语法:**

```cs
public bool IsBackground { get; set; }
```

**返回值:**如果该线程是或将成为后台线程，则该属性返回 *true* ，否则返回 *false* 。

**异常:**线程死了这个属性会给出`ThreadStateException`。

**例 1:**

```cs
// C# program to illustrate the
// concept of Background thread
using System;
using System.Threading;

class GFG {

    // Main method
    static void Main(string[] args)
    {
        // Creating and initializing thread
        Thread mythr = new Thread(mythread);

        // Name of the thread is Geek thread
        mythr.Name = "Geek thread";
        mythr.Start();

        // IsBackground is the property
        // of Thread which allows thread
        // to run in the background
        mythr.IsBackground = true;

        Console.WriteLine("Main Thread Ends!!");
    }

    // Static method
    static void mythread()
    {

        // Display the name of the
        // current working thread
        Console.WriteLine("In progress thread is: {0}",
                          Thread.CurrentThread.Name);

        Thread.Sleep(1000);

        Console.WriteLine("Completed thread is: {0}",
                          Thread.CurrentThread.Name);
    }
}
```

**输出:**

```cs
In progress thread is: Geek thread
Main Thread Ends!!

```

**例 2:**

```cs
// C# program to illustrate the
// concept of IsBackground property
using System;
using System.Threading;

class Geeks {

    int J;

    public Geeks(int J)
    {
        this.J = J;
    }

    // This method will display
    // the counting of background
    // and foreground threads
    public void display()
    {
        for (int i = 0; i < J; i++) {

            Console.WriteLine("{0} count: {1}", 
             Thread.CurrentThread.IsBackground ? 
                           "Background Thread" : 
                        "Foreground Thread", i);

            Thread.Sleep(250);
        }

        Console.WriteLine("{0} finished its counting.",
                    Thread.CurrentThread.IsBackground ?
            "Background Thread" : "Foreground Thread");
    }
}

// Driver Class
class GFG {

    // Main method
    static void Main()
    {
        // Creating and initializing
        // objects of Geeks class
        // Creating and initializing 
        // objects of Thread class
        Geeks obj1 = new Geeks(5);
        Thread fthr = new Thread(new ThreadStart(obj1.display));

        Geeks obj2 = new Geeks(10);
        Thread bthr = new Thread(new ThreadStart(obj2.display));

        // bthr thread is a background
        // thread because the value of
        // IsBackground property is true
        bthr.IsBackground = true;

        fthr.Start();
        bthr.Start();
    }
}
```

**输出:**

```cs
Foreground Thread count: 0
Background Thread count: 0
Background Thread count: 1
Foreground Thread count: 1
Background Thread count: 2
Foreground Thread count: 2
Background Thread count: 3
Foreground Thread count: 3
Background Thread count: 4
Foreground Thread count: 4
Background Thread count: 5
Foreground Thread finished its counting.

```

**注:**

*   线程可以是后台线程，也可以是前台线程。后台线程类似于前台线程，只是后台线程不会阻止进程终止。
*   一旦属于某个进程的所有前台线程都已终止，公共语言运行库就会结束该进程。任何剩余的后台线程都将停止，并且不会完成。
*   主线程或主应用程序线程以及线程类构造函数创建的所有线程都在前台执行(即它们的 IsBackground 属性返回 false)。
*   线程池线程和从非托管代码进入托管执行环境的所有线程都在后台执行(即它们的 IsBackground 属性返回 true)。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . is background？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.isbackground?view=netframework-4.7.2)
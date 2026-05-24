# c# 中线程的类型

> 原文:[https://www.geeksforgeeks.org/types-of-threads-in-c-sharp/](https://www.geeksforgeeks.org/types-of-threads-in-c-sharp/)

多线程是 C# 最有用的特性，它允许对程序的两个或多个部分进行并发编程，以最大限度地提高 CPU 的利用率。程序的每个部分都称为线程。换句话说，线程是进程中的轻量级进程。C# 支持如下两种类型的线程:

#### 前台线程

即使*主*线程离开进程，仍继续运行以完成其工作的线程，这种类型的线程称为前台线程。前台线程不关心主线程是否活动，它只在完成分配的工作时才完成。或者换句话说，前台线程的寿命不依赖于主线程。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// concept of foreground thread
using System;
using System.Threading;

class GFG {

    // Main method
    static void Main(string[] args)
    {

        // Creating and initializing thread
        Thread thr = new Thread(mythread);
        thr.Start();
        Console.WriteLine("Main Thread Ends!!");
    }

    // Static method
    static void mythread()
    {
        for (int c = 0; c <= 3; c++) {

            Console.WriteLine("mythread is in progress!!");
            Thread.Sleep(1000);
        }
        Console.WriteLine("mythread ends!!");
    }
}
```

**输出:**

```cs
Main Thread Ends!!
mythread is in progress!!
mythread is in progress!!
mythread is in progress!!
mythread is in progress!!
mythread ends!!
```

**说明:**在上例中， *thr* 线程在主线程结束后运行。所以，*螺纹的寿命不取决于主螺纹的寿命。*或*线程只有在完成其分配的任务时才结束其进程。* 

#### 背景线程

当 Main 方法离开其进程时离开其进程的线程，这些类型的线程被称为后台线程。或者换句话说，背景线程的寿命取决于主线程的寿命。如果主线程完成了它的进程，那么后台线程也结束了它的进程。
**注意:**如果你想在你的程序中使用一个后台线程，那么将线程的 IsBackground 属性的值设置为 *true* 。
**例:**

## c sharp . c sharp . c sharp . c sharp

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
        Thread thr = new Thread(mythread);

        // Name of the thread is Mythread
        thr.Name = "Mythread";
        thr.Start();

        // IsBackground is the property of Thread
        // which allows thread to run in the background
        thr.IsBackground = true;

        Console.WriteLine("Main Thread Ends!!");
    }

    // Static method
    static void mythread()
    {

        // Display the name of the
        // current working thread
        Console.WriteLine("In progress thread is: {0}",
                            Thread.CurrentThread.Name);

        Thread.Sleep(2000);

        Console.WriteLine("Completed thread is: {0}",
                          Thread.CurrentThread.Name);
    }
}
```

**输出:**

```cs
In progress thread is: Mythread
Main Thread Ends!!
```

**说明:**在上例中，Thread 类的 *IsBackground 属性*通过使 *IsBackground* 的值为真，将 *thr* 线程设置为背景线程。如果将*的值设置为“后台”*为“假”，那么给定的线程将表现为前台线程。现在*螺纹的加工在主螺纹的加工结束时结束。*
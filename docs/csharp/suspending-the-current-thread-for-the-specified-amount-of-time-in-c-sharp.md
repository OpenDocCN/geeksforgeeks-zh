# 在 C# 中暂停当前线程指定的时间量

> 原文:[https://www . geeksforgeeks . org/暂停当前线程指定的 c-sharp 时间量/](https://www.geeksforgeeks.org/suspending-the-current-thread-for-the-specified-amount-of-time-in-c-sharp/)

在 C# 中，一个 **Sleep()** 方法将线程的当前执行暂时挂起指定的毫秒数，这样其他线程就可以得到开始执行的机会，或者可能得到 CPU 执行。`Thread.Sleep`方法重载列表中有两种方法，如下:

*   **睡眠(Int32)**
*   **睡眠(时间跨度)**

#### 睡眠(Int32)

此方法将当前线程挂起描述符毫秒数。如果超时值为负且不等于无穷大，此方法将抛出*argumentout of range exception*。

**语法:**

```cs
public static void Sleep (int millisecondsTimeout);
```

这里，*毫秒时间输出*是线程被挂起的毫秒数。如果*毫秒时间输出*参数的值为零，则线程放弃其时间片的剩余部分给任何准备运行的同等优先级的线程。如果没有其他具有相同优先级的线程准备运行，则当前线程的执行不会暂停。

**示例:**

```cs
// C# program to illustrate the
// concept of Sleep(Int32) method
using System;
using System.Threading;

class ExampleofThread {

    // Non-Static method
    public void thread1()
    {
        for (int x = 0; x < 2; x++) {

            Console.WriteLine("Thread1 is working");

            // Sleep for 4 seconds
            // Using Sleep() method
            Thread.Sleep(4000);
        }
    }

    // Non-Static method
    public void thread2()
    {
        for (int x = 0; x < 2; x++) {

            Console.WriteLine("Thread2 is working");
        }
    }
}

// Driver Class
public class ThreadExample {

    // Main method
    public static void Main()
    {

        // Creating instance for mythread() method
        ExampleofThread obj = new ExampleofThread();

        // Creating and initializing threads
        Thread thr1 = new Thread(new ThreadStart(obj.thread1));
        Thread thr2 = new Thread(new ThreadStart(obj.thread2));

        thr1.Start();
        thr2.Start();
    }
}
```

**输出:**

```cs
Thread1 is working
Thread2 is working
Thread2 is working
Thread1 is working

```

**说明:**通过使用 *thread1* 方法中的`Thread.Sleep(4000);`，我们使 *thr1* 线程休眠 **4** 秒，因此在 4 秒之间 *thr2* 线程有机会在 4 秒后执行 *thr1* 线程恢复工作。

#### 睡眠(时间跨度)

此方法将当前线程挂起所描述的时间。如果超时值为负且不等于无限毫秒，或大于*最大值*毫秒，此方法将抛出*argumentout of range exception*。

**语法:**

```cs
public static void Sleep (TimeSpan timeout);
```

这里*超时*是线程暂停的时间量。如果*毫秒时间输出*参数的值为零，则线程放弃其时间片的剩余部分给任何准备运行的同等优先级的线程。如果没有其他具有相同优先级的线程准备运行，则当前线程的执行不会暂停。

**示例:**

```cs
// C# program to illustrate the
// concept of Sleep(TimeSpan)
using System;
using System.Threading;

class GFG {

    // Main method
    static void Main()
    {

        // Set the timeout value, i.e. 3 seconds
        TimeSpan timeout = new TimeSpan(0, 0, 3);

        for (int k = 0; k < 3; k++) {

            Console.WriteLine("Thread is" + 
                 " sleeping for 3 seconds.");

            // Using Sleep(TimeSpan) method
            Thread.Sleep(timeout);
        }

        Console.WriteLine("Main thread exits");
    }
}
```

**输出:**

```cs
Thread is sleeping for 3 seconds.
Thread is sleeping for 3 seconds.
Thread is sleeping for 3 seconds.
Main thread exits

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . sleep？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.sleep?view=netframework-4.7.2)
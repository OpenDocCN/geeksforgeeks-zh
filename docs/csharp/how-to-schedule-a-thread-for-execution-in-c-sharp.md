# 如何在 C# 中调度线程执行

> 原文:[https://www . geeksforgeeks . org/如何调度 c-sharp 中的线程执行/](https://www.geeksforgeeks.org/how-to-schedule-a-thread-for-execution-in-c-sharp/)

**螺纹。启动方法**负责调度一个线程执行。这个方法可以通过传递不同的参数来重载。

*   **Start()**
*   **开始(对象)**

#### 开始()

此方法告诉操作系统将当前实例的状态更改为“正在运行”。或者换句话说，由于这个方法，线程开始执行。

**语法:**

```cs
public void Start ();
```

**异常:**

*   **线程状态异常:**如果线程已经启动。
*   **OutOfMemoryException :** 如果内存不足，无法启动线程。

**示例:**

```cs
// C# program to illustrate the
// use of Start() method
using System;
using System.Threading;

class GThread {

    // Non-static method
    public void Job()
    {
        for (int X = 0; X < 4; X++) {
            Console.WriteLine(X);
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
        Thread thr = new Thread(new ThreadStart(obj.Job));

        // Start the execution of Thread
        // Using Start() method
        thr.Start();
    }
}
```

**输出:**

```cs
0
1
2
3

```

#### 开始(对象)

此方法告诉操作系统将当前实例的状态更改为“正在运行”。它传递一个对象，该对象包含线程执行的方法要使用的数据。此参数是可选的。

**语法:**

```cs
public void Start (object parameter);
```

这里，*参数*是一个包含线程执行的方法要使用的数据的对象。

**异常:**

*   **线程状态异常:**如果线程已经启动。
*   **OutOfMemoryException :** 如果内存不足，无法启动线程。
*   **无效操作异常:**如果线程是使用线程启动委托而不是参数化线程启动委托创建的。

**示例:**

```cs
// C# program to illustrate the
// use of Start(Object) method
using System;
using System.Threading;

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of GFG class
        GFG obj = new GFG();

        // Creating and initializing threads
        Thread thr1 = new Thread(obj.Job1);
        Thread thr2 = new Thread(Job2);

        // Start the execution of Thread
        // Using Start(Object) method
        thr1.Start(01);
        thr2.Start("Hello")
    }

    // Non-static method
    public void Job1(object value)
    {
        Console.WriteLine("Data of Thread 1 is: {0}", value);
    }

    // Static method
    public static void Job2(object value)
    {
        Console.WriteLine("Data of Thread 2 is: {0}", value);
    }
}
```

**输出:**

```cs
Data of Thread 1 is: 1
Data of Thread 2 is: Hello

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . start？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.start?view=netframework-4.7.2)
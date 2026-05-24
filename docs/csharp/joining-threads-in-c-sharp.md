# 在 C# 中连接线程

> 原文:[https://www.geeksforgeeks.org/joining-threads-in-c-sharp/](https://www.geeksforgeeks.org/joining-threads-in-c-sharp/)

在 C# 中，Thread 类提供了 **Join()** 方法，该方法允许一个线程等待另一个线程完成其执行。如果 *t* 是其线程当前正在执行的线程对象，则 *t.Join()* 会导致当前线程暂停其执行，直到其加入的线程完成其执行。
如果有多个线程调用 join()方法，这意味着 Join 上的重载允许程序员指定等待时间。但是，与睡眠一样，join 依赖于操作系统的计时，因此您不应该假设 Join 会等待您指定的时间。

`Thread.Join()`方法重载列表中有 ***三个*** 方法如下:

*   **Join() Method:** This method blocks the calling thread until the thread represented by this instance terminates while continuing to perform standard COM and SendMessage pumping.

    **语法:**

    ```cs
    public void Join ();
    ```

*   **Join(Int32) Method:** This method blocks the calling thread until the thread represented by this instance terminates or the specified time elapses while continuing to perform standard COM and SendMessage pumping.

    **语法:**

    ```cs
    public bool Join (int millisecondsTimeout);
    ```

*   **Join(TimeSpan) Method:** This method blocks the calling thread until the thread represented by this instance terminates or the specified time elapses while continuing to perform standard COM and SendMessage pumping.

    **语法:**

    ```cs
    public bool Join (TimeSpan timeout);
    ```

**例 1:**

```cs
// C# program to illustrate the 
// concept of Join() method
using System; 
using System.Threading; 

public class ExThread 
{ 

    // Non-Static method
    public void mythread() 
    { 
        for (int x = 0; x < 4; x++) 
        { 
            Console.WriteLine(x); 
            Thread.Sleep(100); 
        } 
    } 

    // Non-Static method
    public void mythread1()
    {
        Console.WriteLine("2nd thread is Working..");
    }
} 

// Driver Class
public class ThreadExample 
{ 
    // Main method
    public static void Main() 
    { 
        // Creating instance for
        // mythread() method
        ExThread obj = new ExThread(); 

        // Creating and initializing threads 
        Thread thr1 = new Thread(new ThreadStart(obj.mythread)); 
        Thread thr2 = new Thread(new ThreadStart(obj.mythread1)); 
        thr1.Start(); 

        // Join thread
        thr1.Join(); 
        thr2.Start(); 

    } 
} 
```

**输出:**

```cs
0
1
2
3
2nd thread is Working..

```

**说明:**在上面的例子中，我们有一个名为 *ExThread* 的类，这个类包含一个非静态的方法，即`mythread()`和`mythread1()`。所以我们创建一个实例，即 *ExThread* 类的 *obj* ，并在 *ThreadStart* 类的构造函数中引用它。使用`Thread thr1 = new Thread(new ThreadStart(obj.mythread));`语句，我们创建一个名为 *thr1* 的线程，并初始化该线程的工作，类似于线程 *thr2* 。使用`thr1.Join();`语句，我们将 *thr2* 的调用发送到等待中，直到 *thr1* 线程的工作完成。之后*线程执行。*

**例 2:**

```cs
// C# program to illustrate the
// concept of Join() method
using System;
using System.Threading;

class GFG {

    // Creating TimeSpan for thread
    static TimeSpan mytime = new TimeSpan(0, 0, 1);

    // Main method
    public static void Main()
    {
        // Creating and initializing new thread
        Thread thr = new Thread(mywork);
        thr.Start();

        if (thr.Join(mytime + mytime)) {            
            Console.WriteLine("New thread is terminated");
        }
        else {
            Console.WriteLine("Join timed out");
        }
    }

    static void mywork()
    {
        Thread.Sleep(mytime);
    }
}
```

**输出:**

```cs
New thread is terminated
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . join？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.join?view=netframework-4.7.2)
# 在 C# 中命名一个线程并获取当前线程的名称

> 原文:[https://www . geeksforgeeks . org/命名线程并获取当前 c-sharp 中线程的名称/](https://www.geeksforgeeks.org/naming-a-thread-and-fetching-name-of-current-thread-in-c-sharp/)

线程是进程中的轻量级进程。在 C# 中，允许用户给线程分配一个名称，也可以使用**线程找到当前工作线程的名称。线程类的名称属性**。

**语法:**

```cs
public string Name { get; set; }
```

这里，*字符串*包含线程的名称，如果没有指定或设置名称，则为*空值*。

**要点:**

*   “名称”属性的默认值为空。
*   赋予 name 属性的字符串可以包括任何 Unicode 字符。
*   线程类的名称属性是一次写入。
*   如果请求了设置操作，但名称属性已经设置，则给出`InvalidOperationException`。

**例 1:**

```cs
// C# program to illustrate the 
// concept of assigning names 
// to the thread and fetching
// name of the current working thread
using System;
using System.Threading;

class Geek {

    // Method of Geek class
    public void value()
    {
        // Fetching the name of 
        // the current thread
        // Using Name property
        Thread thr = Thread.CurrentThread;
        Console.WriteLine("The name of the current "+
                           "thread is: " + thr.Name);
    }
}

// Driver class
public class GFG {

    // Main Method
    static public void Main()
    {

        // Creating object of Geek class
        Geek obj = new Geek();

        // Creating and initializing threads
        Thread thr1 = new Thread(obj.value);
        Thread thr2 = new Thread(obj.value);
        Thread thr3 = new Thread(obj.value);
        Thread thr4 = new Thread(obj.value);

        // Assigning the names of the threads
        // Using Name property
        thr1.Name = "Geeks1";
        thr2.Name = "Geeks2";
        thr3.Name = "Geeks3";
        thr4.Name = "Geeks4";

        thr1.Start();
        thr2.Start();
        thr3.Start();
        thr4.Start();
    }
}
```

**输出:**

```cs
The name of the current thread is: Geeks2
The name of the current thread is: Geeks3
The name of the current thread is: Geeks4
The name of the current thread is: Geeks1

```

**例 2:**

```cs
// C# program to illustrate the 
// concept of giving a name to thread
using System;
using System.Threading;

class Name {
    static void Main()
    {

        // Check whether the thread
        // has already been named
        // to avoid InvalidOperationException
        if (Thread.CurrentThread.Name == null) {

            Thread.CurrentThread.Name = "MyThread";
            Console.WriteLine("The name of the thread is MyThread");
        }
        else {
            Console.WriteLine("Unable to name the given thread");
        }
    }
}
```

**输出:**

```cs
The name of the thread is MyThread

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . name？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.name?view=netframework-4.7.2)
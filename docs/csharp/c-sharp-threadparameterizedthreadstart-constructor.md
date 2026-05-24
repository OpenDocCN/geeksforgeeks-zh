# C# |线程(ParameterizedThreadStart)构造器

> 原文:[https://www . geeksforgeeks . org/c-sharp-threadparametersedthreadstart-constructor/](https://www.geeksforgeeks.org/c-sharp-threadparameterizedthreadstart-constructor/)

**Thread(parameterzedsthreadstart)构造函数**用于初始化 Thread 类的一个新实例。它定义了一个委托，该委托允许对象在线程启动时传递给线程。如果该构造函数的参数为空，则该构造函数给出 *ArgumentNullException* 。

**语法:**

```cs
public Thread(ParameterizedThreadStart start);
```

这里， *start* 是一个代表当这个线程开始执行时要调用的方法的委托。
下面的程序说明了*线程的使用(参数化线程启动)*构造函数:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of Thread(ParameterizedThreadStart)
// constructor with non-static method
using System;
using System.Threading;

public class MYTHREAD {

    // Non-static method
    public void Job()
    {
        for (int z = 0; z < 3; z++) {

            Console.WriteLine("My thread is "+
                          "in progress...!!");
        }
    }
}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of MYTHREAD class
        MYTHREAD obj = new MYTHREAD();

        // Creating a thread which
        // calls a parameterized instance method
        Thread thr = new Thread(obj.Job);
        thr.Start();
    }
}
```

**输出:**

```cs
My thread is in progress...!!
My thread is in progress...!!
My thread is in progress...!!
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use of
// Thread(ParameterizedThreadStart)
// constructor with static method
using System;
using System.Threading;

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // Creating a thread which calls
        // a parameterized static-method
        Thread thr = new Thread(Job);
        thr.Start();
    }

    // Static method
    public static void Job()
    {
        Console.WriteLine("My thread is"+
                    " in progress...!!");

        for (int z = 0; z < 3; z++) {
            Console.WriteLine(z);
        }
    }
}
```

**输出:**

```cs
My thread is in progress...!!
0
1
2
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread-ctor？view = net framework-4 . 7 . 2 # System _ Threading _ Thread _ ctor _ System _ Threading _ parameterizedsthreadstart _](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=netframework-4.7.2# System_Threading_Thread__ctor_System_Threading_ParameterizedThreadStart_)
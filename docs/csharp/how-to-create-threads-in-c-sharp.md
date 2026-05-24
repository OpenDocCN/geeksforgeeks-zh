# 如何在 C# 中创建线程

> 原文:[https://www . geesforgeks . org/how-create-threads-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-threads-in-c-sharp/)

在 C# 中，多线程系统建立在线程类之上，它封装了线程的执行。这个类包含几个有助于管理和创建线程的方法和属性，这个类是在`System.Threading`命名空间下定义的。`System.Threading`命名空间提供了多线程编程中使用的类和接口。

*这个命名空间中一些常用的类有:*

| 类别名 | 描述 |
| **互斥** | 它是一个同步原语，也可以用于 IPS(进程间同步)。 |
| **监控** | 这个类提供了一种以同步方式访问对象的机制。 |
| **信号量** | 此类用于限制可以并发访问资源或资源池的线程数量。 |
| **螺纹** | 此类用于创建和控制线程，设置其优先级，并获取其状态。 |
| 线程池 | 这个类提供了一个线程池，可以用来执行任务、发布工作项、处理异步输入/输出、代表其他线程等待以及处理计时器。 |
| **线程本地** | 这个类提供数据的线程本地存储。 |
| **小时** | 此类提供了一种机制，用于以指定的时间间隔在线程池线程上执行方法。不允许您继承此类。 |
| **挥发性** | 此类包含执行易失性内存操作的方法。 |

**在 C# 程序中创建线程的步骤:**

1.  首先导入`System.Threading`命名空间，它在你的程序中创建一个线程中起着重要的作用，因为你不需要每次都写类的完全限定名。

    ```cs
    Using System;
    Using System.Threading

    ```

2.  Now, create and initialize the thread object in your main method.

    ```cs
    public static void main()
    {
        Thread thr = new Thread(job1);
    }

    ```

    **或**

    您也可以使用 ThreadStart 构造函数来初始化新实例。

    ```cs
    public static void main()
    {
         Thread thr = new Thread(new ThreadStart(job1));
    }

    ```

3.  现在可以调用线程对象了。

    ```cs
    public static void main()
    {
        Thread thr = new Thread(job1);
        thr.Start();
    }

    ```

下面的程序说明了上述步骤的实际实现:

**例 1:**

```cs
// C# program to illustrate the
// creation of thread using
// non-static method
using System;
using System.Threading;

public class ExThread {

    // Non-static method
    public void mythread1()
    {
        for (int z = 0; z < 3; z++) {
            Console.WriteLine("First Thread");
        }
    }
}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of ExThread class
        ExThread obj = new ExThread();

        // Creating thread
        // Using thread class
        Thread thr = new Thread(new ThreadStart(obj.mythread1));
        thr.Start();
    }
}
```

**输出:**

```cs
First Thread
First Thread
First Thread

```

**解释:**在上面的例子中，我们有一个名为 *ExThread* 的类，它包含一个名为 *mythread1()* 的非静态方法。所以我们创建一个实例，即 ExThread 类的 *obj* ，并在 *ThreadStart* 类的构造函数中引用它，如本语句`Thread a = new Thread(new ThreadStart(obj.mythread1));`中所给出的。使用 T `hread a = new Thread(new ThreadStart(obj.mythread1));`语句，我们将创建一个名为*的线程，并初始化该线程的工作。通过使用`thr.Start();`语句。*

**例 2:**

```cs
// C# program to illustrate the creation
// of thread using static method
using System;
using System.Threading;

public class ExThread {

    // Static method for thread a
    public static void thread1()
    {
        for (int z = 0; z < 5; z++) {
            Console.WriteLine(z);
        }
    }

    // static method for thread b
    public static void thread2()
    {
        for (int z = 0; z < 5; z++) {
            Console.WriteLine(z);
        }
    }
}

// Driver Class
public class GFG {

    // Main method
    public static void Main()
    {
        // Creating and initializing threads
        Thread a = new Thread(ExThread.thread1);
        Thread b = new Thread(ExThread.thread2);
        a.Start();
        b.Start();
    }
}
```

**输出:**

```cs
0
1
2
3
4
0
1
2
3
4

```

**说明:**在上例中，我们有一个名为 *ExThread* 的类，包含两个名为 *thread1()* 和 *thread2()* 的静态方法。所以我们不需要创建 *ExThread* 类的实例。这里我们使用类名来调用这些方法，比如`ExThread.thread1`、`ExThread.thread2`。通过使用`Thread a = new Thread(ExThread.thread1);` 语句，我们创建并初始化线程 *a* 的工作，类似于线程 *b* 。通过使用`a.Start();`和`b.Start();`语句， *a* 和 *b* 线程被调度执行。

**注意:**由于上下文切换，这些程序的输出可能会有所不同。
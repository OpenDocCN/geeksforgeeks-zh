# c# 中的线程类

> 原文:[https://www.geeksforgeeks.org/thread-class-in-c-sharp/](https://www.geeksforgeeks.org/thread-class-in-c-sharp/)

在 C# 中，多线程系统建立在线程类之上，它封装了线程的执行。这个类包含几个有助于管理和创建线程的方法和属性，这个类是在`System.Threading`命名空间下定义的。

**螺纹类特性:**

*   线程类用于创建线程。
*   在线程类的帮助下，你可以创建[前台和后台线程](https://www.geeksforgeeks.org/types-of-threads-in-c/)。
*   线程类允许您[设置线程的优先级](https://www.geeksforgeeks.org/c-thread-priority-in-multithreading/)。
*   它还为您提供线程的当前状态。
*   它提供当前执行线程的引用。
*   它是一个密封类，因此不能被继承。

#### 构造器

| 构造器 | 描述 |
| **[线程(parameterzedsthreadstart)](https://www.geeksforgeeks.org/c-sharp-threadparameterizedthreadstart-constructor/)** | 初始化线程类的新实例，指定一个委托，该委托允许在线程启动时将对象传递给线程。 |
| **线程(ParameterizedThreadStart，Int32)** | 初始化线程类的新实例，指定一个委托，该委托允许在线程启动时将对象传递给线程，并指定线程的最大堆栈大小。 |
| **[【线程启动】](https://www.geeksforgeeks.org/c-sharp-threadthreadstart-constructor/)** | 初始化线程类的新实例。 |
| **螺纹(螺纹起点，Int32)** | 初始化线程类的新实例，指定线程的最大堆栈大小。 |

**示例:**

```cs
// C# program to illustrate
// ThreadStart constructor
using System;
using System.Threading;

public class MXThread {

    // Non-static method
    public void mythr()
    {
        for (int J = 0; J < 2; J++) {

            Console.WriteLine("My Thread is"+
                         " in progress...!!");
        }
    }
}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of ExThread class
        MXThread obj = new MXThread();

        // Creating and initializing thread
        // Using thread class and 
        // ThreadStart constructor
        Thread t = new Thread(new ThreadStart(obj.mythr));
        t.Start();
    }
}
```

**输出:**

```cs
My Thread is in progress...!!
My Thread is in progress...!!

```

#### 性能

| 财产 | 描述 |
| 公寓状态 | 获取或设置此线程的单元状态。 |
| **电流上下文** | 获取线程正在其中执行的当前上下文。 |
| 电流文化 | 获取或设置当前线程的区域性。 |
| 主电流 | 获取或设置线程的当前主体(对于基于角色的安全性)。 |
| **[【电流线程】](https://www.geeksforgeeks.org/thread-currentthread-property-in-c-sharp/)** | 获取当前正在运行的线程。 |
| **电流驱动文化** | 获取或设置资源管理器在运行时查找区域性特定资源时使用的当前区域性。 |
| 执行上下文 | 获取一个 ExecutionContext 对象，该对象包含有关当前线程的各种上下文的信息。 |
| **[【isalive】](https://www.geeksforgeeks.org/how-to-check-whether-a-thread-is-alive-or-not-in-c/)** | 获取一个值，该值指示当前线程的执行状态。 |
| **[【isackground】](https://www.geeksforgeeks.org/how-to-check-whether-a-thread-is-a-background-thread-or-not-in-c-sharp/)** | 获取或设置一个值，该值指示线程是否为后台线程。 |
| **[【ist thread pool thread】](https://www.geeksforgeeks.org/c-sharp-check-if-a-thread-belongs-to-managed-thread-pool-or-not/)** | 获取一个值，该值指示线程是否属于托管线程池。 |
| **[【managedthread】](https://www.geeksforgeeks.org/c-sharp-getting-the-unique-identifier-for-the-current-managed-thread/)** | 获取当前托管线程的唯一标识符。 |
| **[名称](https://www.geeksforgeeks.org/naming-a-thread-and-fetching-name-of-current-thread-in-c-sharp/)** | 获取或设置线程的名称。 |
| **[优先](https://www.geeksforgeeks.org/c-sharp-thread-priority-in-multithreading/)** | 获取或设置一个值，该值指示线程的调度优先级。 |
| **[线程状态](https://www.geeksforgeeks.org/c-sharp-how-to-check-current-state-of-a-thread/)** | 获取包含当前线程状态的值。 |

**示例:**

```cs
// C# program to illustrate how to
// set and get the priority of threads
using System;
using System.Threading;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating and initializing threads
        Thread THR1 = new Thread(work);
        Thread THR2 = new Thread(work);
        Thread THR3 = new Thread(work);

        // Set the priority of threads
        THR2.Priority = ThreadPriority.Lowest;
        THR3.Priority = ThreadPriority.AboveNormal;
        THR1.Start();
        THR2.Start();
        THR3.Start();

        // Display the priority of threads
        Console.WriteLine("The priority of Thread 1 is: {0}",
                                              THR1.Priority);

        Console.WriteLine("The priority of Thread 2 is: {0}",
                                              THR2.Priority);

        Console.WriteLine("The priority of Thread 3 is: {0}",
                                              THR3.Priority);
    }

    public static void work()
    {

        // Sleep for 1 second
        Thread.Sleep(1000);
    }
}
```

**输出:**

```cs
The priority of Thread 1 is: Normal
The priority of Thread 2 is: Lowest
The priority of Thread 3 is: AboveNormal

```

#### 方法

| 方法 | 描述 |
| **[打掉()](https://www.geeksforgeeks.org/how-to-terminate-a-thread-in-c-sharp/)** | 在调用线程的线程中引发线程异常，以开始终止线程的过程。调用此方法通常会终止线程。 |
| **AllocateDataSlot()** | 在所有线程上分配一个未命名的数据槽。为了获得更好的性能，请改用用 ThreadStaticAttribute 属性标记的字段。 |
| **AllocateNamedDataSlot(字符串)** | 在所有线程上分配一个命名数据槽。为了获得更好的性能，请改用用 ThreadStaticAttribute 属性标记的字段。 |
| 开始临界区域() | 通知宿主执行即将进入一个代码区域，在该区域中，线程中止或未处理异常的影响可能会危及应用程序域中的其他任务。 |
| **BeginThreadAffinity()** | 通知宿主托管代码即将执行依赖于当前物理操作系统线程标识的指令。 |
| **disablecomobjecteagerclean()** | 关闭当前线程的运行时可调用包装(RCW)的自动清理。 |
| **end critical 区域()** | 通知宿主执行即将进入代码区域，在该区域中，线程中止或未处理异常的影响仅限于当前任务。 |
| **EndThreadAffinity()** | 通知宿主托管代码已完成执行依赖于当前物理操作系统线程标识的指令。 |
| **等于(对象)** | 确定指定的对象是否等于当前对象。 |
| **最终确定()** | 确保在垃圾收集器回收线程对象时释放资源并执行其他清理操作。 |
| **自由名称数据批次(字符串)** | 为进程中的所有线程消除名称和插槽之间的关联。为了获得更好的性能，请改用用 ThreadStaticAttribute 属性标记的字段。 |
| **get partstate()** | 返回一个表示单元状态的单元状态值。 |
| **get comprendedstack()** | 返回一个 CompressedStack 对象，该对象可用于捕获当前线程的堆栈。 |
| **GetData(本地数据存储区)T1** | 在当前线程的当前域内，从当前线程的指定槽中检索值。为了获得更好的性能，请改用用 ThreadStaticAttribute 属性标记的字段。 |
| **GetDomain()** | 返回当前线程正在其中运行的当前域。 |
| get omainid() | 返回唯一的应用程序域标识符。 |
| **GetHashCode（）** | 返回当前线程的哈希代码。 |
| **获取命名数据插槽（字符串）** | 查找命名的数据槽。为了获得更好的性能，请改用用 ThreadStaticAttribute 属性标记的字段。 |
| gettype() | 获取当前实例的类型。 |
| **中断()** | 中断处于等待睡眠连接线程状态的线程。 |
| **[加入()](https://www.geeksforgeeks.org/joining-threads-in-c-sharp/)** | 阻塞调用线程，直到该实例表示的线程终止，同时继续执行标准的组件和发送消息泵送。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **记忆屏障()** | 按如下方式同步内存访问:执行当前线程的处理器不能以这样一种方式对指令重新排序，即在调用 MemoryBarrier()之前的内存访问在调用 MemoryBarrier()之后的内存访问之后执行。 |
| **[复位()](https://www.geeksforgeeks.org/thread-resetabort-method-in-c-sharp/)** | 取消为当前线程请求的中止(对象)。 |
| **恢复()** | 恢复已挂起的线程。 |
| **setpartstate(公寓状态)** | 设置线程启动前的单元状态。 |
| **set comprendedstack(压缩叠叠)** | 将捕获的压缩跟踪应用于当前线程。 |
| **SetData(局部数据存储槽，对象)** | 为当前正在运行的线程的当前域设置该线程的指定槽中的数据。为了获得更好的性能，请改用标记有 ThreadStaticAttribute 属性的字段。 |
| **[睡眠()](https://www.geeksforgeeks.org/suspending-the-current-thread-for-the-specified-amount-of-time-in-c-sharp/)** | 将当前线程挂起指定的时间。 |
| **自旋等待(Int32)** | 使线程等待迭代参数定义的次数。 |
| **[Start()](https://www.geeksforgeeks.org/how-to-schedule-a-thread-for-execution-in-c-sharp/)** | 导致线程被调度执行。 |
| **暂停()** | 挂起线程，或者如果线程已经挂起，则不起作用。 |
| **ToString()** | 返回表示当前对象的字符串。 |
| **trsetpartstate(公寓状态)** | 设置线程启动前的单元状态。 |
| 挥发性() | 读取字段的值。该值是计算机中任何处理器最近写入的值，与处理器数量或处理器缓存状态无关。 |
| **挥发分()** | 立即将值写入字段，以便计算机中的所有处理器都能看到该值。 |
| **产量()** | 导致调用线程将执行交给另一个准备在当前处理器上运行的线程。操作系统选择要屈服的线程。 |

**示例:**

```cs
// C# program to illustrate the
// concept of Join() method
using System;
using System.Threading;

public class MYThread {

    // Non-Static method
    public void mythr1()
    {
        Console.WriteLine("1nd thread is Working..!!");
        Thread.Sleep(100);
    }

    // Non-Static method
    public void mythr2()
    {
        Console.WriteLine("2nd thread is Working..!!");
    }
}

// Driver Class
public class ThreadExample {

    // Main method
    public static void Main()
    {
        // Creating instance of MYThread class
        MYThread obj = new MYThread();

        // Creating and initializing threads
        Thread T1 = new Thread(new ThreadStart(obj.mythr1));
        Thread T2 = new Thread(new ThreadStart(obj.mythr2));
        T1.Start();

        // Join thread
        T1.Join();
        T2.Start();
    }
}
```

**输出:**

```cs
1nd thread is Working..!!
2nd thread is Working..!!

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread？视图= net framework-4 . 7 . 2 # 线程安全](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread?view=netframework-4.7.2# thread-safety)
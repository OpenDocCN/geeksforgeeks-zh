# 如何在 C# 中终止一个线程

> 原文:[https://www . geeksforgeeks . org/如何终止 c-sharp 中的线程/](https://www.geeksforgeeks.org/how-to-terminate-a-thread-in-c-sharp/)

在 C# 中，可以使用**中止()方法**终止一个线程。Abort()将`ThreadAbortException` 抛出到调用它的线程中。由于这个异常，线程被终止。`Thread.Abort Method`的过载列表中有两种方法，如下:

*   ****中止()*****   ****Abort(Object)**

    #### 中止()

    该方法在调用它的线程中引发`ThreadAbortException` ，开始终止线程的过程。通常，此方法用于终止线程。

    **语法:**

    ```cs
    public void Abort();
    ```

    **异常:**

    *   **安全异常**:如果调用者没有所需的权限。
    *   **线程状态异常**:如果正在中止的线程当前处于挂起状态。

    **示例:**

    ```cs
    // C# program to illustrate the
    // concept of Abort() method
    // on a single thread
    using System;
    using System.Threading;

    class ExampleofThread {

        // Non-Static method
        public void thread()
        {
            for (int x = 0; x < 3; x++) {
                Console.WriteLine(x);
            }
        }
    }

    // Driver Class
    class ThreadExample {

        // Main method
        public static void Main()
        {

            // Creating instance for mythread() method
            ExampleofThread obj = new ExampleofThread();

            // Creating and initializing threads
            Thread thr = new Thread(new ThreadStart(obj.thread));
            thr.Start();

            Console.WriteLine("Thread is abort");

            // Abort thr thread
            // Using Abort() method
            thr.Abort();
        }
    }
    ```

    **输出:**

    ```cs
    Thread is abort

    ```

    **解释:**上面的例子展示了 Thread 类提供的 Abort()方法的使用。通过使用`thr.Abort();`语句，我们可以终止线程的*执行。*

    #### 中止(对象)

    此方法在调用它的线程中引发`ThreadAbortException` ，开始终止线程的过程，同时还提供关于线程终止的异常信息。通常，此方法用于终止线程。

    **语法:**

    ```cs
    public void Abort(object information);
    ```

    在这里，*信息*包含线程停止时您想要传递的任何信息。只有使用*线程异常*的*异常状态*属性才能访问此信息。

    **异常:**

    *   **安全异常**:如果调用者没有所需的权限。
    *   **线程状态异常**:如果正在中止的线程当前处于挂起状态。

    **示例:**

    ```cs
    // C# program to illustrate the
    // concept of Abort(object)
    using System;
    using System.Threading;

    class ExThread {

        public Thread thr;

        public ExThread(string name)
        {
            thr = new Thread(this.RunThread);
            thr.Name = name;
            thr.Start();
        }

        // Enetring point for thread
        void RunThread()
        {
            try {
                Console.WriteLine(thr.Name +
                            " is starting.");

                for (int j = 1; j <= 100; j++) 
                {
                    Console.Write(j + " ");
                    if ((j % 10) == 0) 
                    {
                        Console.WriteLine();
                        Thread.Sleep(200);
                    }
                }
                Console.WriteLine(thr.Name + 
                      " exiting normally.");
            }
            catch (ThreadAbortException ex) {
                Console.WriteLine("Thread is aborted and the code is "
                                                 + ex.ExceptionState);
            }
        }
    }

    // Driver Class
    class GFG {

        // Main method
        static void Main()
        {

            // Creating object of ExThread
            ExThread obj = new ExThread("Thread ");
            Thread.Sleep(1000);
            Console.WriteLine("Stop thread");
            obj.thr.Abort(100);

            // Waiting for a thread to terminate.
            obj.thr.Join();
            Console.WriteLine("Main thread is terminating");
        }
    }
    ```

    **输出:**

    ```cs
    Thread  is starting.
    1 2 3 4 5 6 7 8 9 10 
    11 12 13 14 15 16 17 18 19 20 
    21 22 23 24 25 26 27 28 29 30 
    31 32 33 34 35 36 37 38 39 40 
    41 42 43 44 45 46 47 48 49 50 
    Stop thread
    Thread is aborted and the code is 100
    Main thread is terminating

    ```

    **要点:**

    *   如果调用异常终止方法的线程持有异常终止线程所需的锁，就会出现**死锁**。
    *   如果在尚未启动的线程上调用 *Abort* 方法，那么当调用 Start 时，该线程将中止。
    *   如果在被阻塞或正在休眠的线程上调用*中止*方法，那么该线程将被中断，然后中止。
    *   如果在挂起的线程上调用 *Abort* 方法，则在调用 Abort 的线程中抛出`ThreadStateException` ，并且 *AbortRequested* 被添加到被中止线程的 *ThreadState* 属性中。
    *   在调用*恢复*之前，暂停线程中不会抛出*线程异常。*
    *   如果在当前正在执行非托管代码的托管线程上调用*中止*方法，则在线程返回托管代码之前，不会引发`ThreadAbortException` 。
    *   如果对*中止*的两个调用同时出现，那么一个调用可以设置状态信息，另一个调用可以执行中止。但是，应用程序无法检测到这种情况。
    *   在线程上调用*中止*后，线程的状态包括*中止请求*。在线程由于成功调用中止的结果而终止后，线程的状态将更改为停止。如果有足够的权限，作为*中止*目标的线程可以使用*重置中止*方法取消中止。

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . threading . thread . abort？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.threading.thread.abort?view=netframework-4.7.2)**
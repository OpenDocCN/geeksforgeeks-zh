# Java 中锁框架 vs 线程同步

> 原文：[https://www.geeksforgeeks.org/lock-framework-vs-thread-synchronization-in-java/](https://www.geeksforgeeks.org/lock-framework-vs-thread-synchronization-in-java/)

使用 `java.util.concurrent` 包中存在的 `Lock` 框架可以实现线程同步机制。锁框架像同步块一样工作，只是锁可能比 Java 的同步块更复杂。锁允许更灵活地构造同步代码。Java 5 引入了这种新方法来解决下面提到的同步问题。

让我们看看一个 `Vector` 类，它有很多同步的方法。当一个类中有 100 个同步方法时，在任何给定的时间点，这 100 个方法中只能有一个线程被执行。在使用同步块的任何给定时间点，只允许一个线程访问一个方法。这是一个非常昂贵的手术。锁通过允许为不同目的配置不同的锁来避免这种情况。一个锁下可以有几个同步的方法，另一个锁下可以有几个同步的方法。这允许更多的并发性，也提高了整体性能。

**示例：**

```java
Lock lock = new ReentrantLock();
lock.lock();

// Critical section
lock.unlock();
```

锁通过 `lock()` 方法获取，通过 `unlock()` 方法释放。调用不带 `lock()` 的 `unlock()` 将引发异常。如前所述，`Lock` 接口存在于 `java.util.concurrent.locks` 包中，`ReentrantLock` 实现 `Lock` 接口。

*注意：* `lock()` 调用的次数应始终等于 `unlock()` 调用的次数。

在下面的代码中，用户创建了一个名为 `TestResource` 的资源，它有两个方法和两个不同的锁。有两个名为 `DisplayJob` 和 `ReadJob` 的作业。`LockTest` 类创建 5 个线程来完成 `DisplayJob`，创建 5 个线程来完成 `ReadJob`。所有 10 个线程共享一个资源 `TestResource`。

```java
import java.util.Date;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

// Test class to test the lock example
// 5 threads are created with DisplayJob
// and 5 thread are created with ReadJob.
// Both these jobs use single TestResource named "test".
public class LockTest
{
    public static void main(String[] args)
    {
        TestResource test = new TestResource();
        Thread thread[] = new Thread[10];
          for (int i = 0; i < 5; i++)
          {
              thread[i] = new Thread(new DisplayJob(test),
              "Thread " + i);
          }
          for (int i = 5; i < 10; i++)
          {
              thread[i] = new Thread(new ReadJob(test),
              "Thread " + i);
          }
          for (int i = 0; i < 10; i++)
          {
              thread[i].start();
          }
    }

}
// DisplayJob class implementing Runnable interface.
// This uses TestResource object passed in the constructor.
// run method invokes displayRecord method on TestResource.
class DisplayJob implements Runnable
{

    private TestResource test;
    DisplayJob(TestResource tr)
    {
        test = tr;
    }
    @Override
    public void run()
    {
        System.out.println("display job");
        test.displayRecord(new Object());
    }
}
// ReadJob class implementing Runnable interface.
// which uses TestResource object passed in the constructor.
// run method invokes readRecord method on TestResource.
class ReadJob implements Runnable
{

    private TestResource test;

    ReadJob(TestResource tr)
    {
        test = tr;
    }
    @Override
    public void run()
    {
        System.out.println("read job");
        test.readRecord(new Object());
    }
}
// Class which has two locks and two methods.

class TestResource
{

    // displayQueueLock is created to make
    // displayQueueLock thread safe.
    // When T1 acquires lock on testresource(o1)
    // object displayRecord method
    // T2 has to wait for lock to be released
    // by T1 on testresource(o1) object
    // displayRecord method.  But T3, can execute
    // readRecord method with out waiting for lock
    // to be released by t1 as
    // readRecord method uses readQueueLock not
    // displayQueueLock.
    private final Lock
    displayQueueLock = new ReentrantLock();
    private final Lock
    readQueueLock = new ReentrantLock();

    // displayRecord uses displayQueueLock to
    // achieve thread safety.
    public void displayRecord(Object document)
    {
        final Lock displayLock = this.displayQueueLock;
        displayLock.lock();
        try
          {
              Long duration =
                          (long) (Math.random() * 10000);
              System.out.println(Thread.currentThread().
              getName() + ": TestResource: display a Job"+
              " during " + (duration / 1000) + " seconds ::"+
              " Time - " + new Date());
              Thread.sleep(duration);
          }
          catch (InterruptedException e)
          {
              e.printStackTrace();
          }
          finally
          {
              System.out.printf("%s: The document has been"+
              " dispalyed\n", Thread.currentThread().getName());
              displayLock.unlock();
          }
    }

    // readRecord uses readQueueLock to achieve thread safety.
    public void readRecord(Object document)
    {
        final Lock readQueueLock = this.readQueueLock;
        readQueueLock.lock();
        try
          {
              Long duration =
                        (long) (Math.random() * 10000);
              System.out.println
              (Thread.currentThread().getName()
              + ": TestResource: reading a Job during " +
              (duration / 1000) + " seconds :: Time - " +
              new Date());
              Thread.sleep(duration);
          }
          catch (InterruptedException e)
          {
              e.printStackTrace();
          }
          finally
          {
              System.out.printf("%s: The document has"+
              " been read\n", Thread.currentThread().getName());
              readQueueLock.unlock();
          }
    }
}
```

**输出：**

> display job
> display job
> display job
> display job
> display job
> read job
> read job
> read job
> read job
> read job
> Thread 5: TestResource: reading a Job during 4 seconds :: Time - Wed Feb 27 15:49:53 GMT 2019
> Thread 0: TestResource: display a Job during 6 seconds :: Time - Wed Feb 27 15:49:53 GMT 2019

在上面的例子中，`DisplayJob` 不需要等待 `ReadJob` 线程完成任务，因为 `ReadJob` 和 `DisplayJob` 使用两种不同的锁。这不可能用 `synchronized` 来实现。

区别如下：

| parameter | Lock framework | synchronized |
| --- | --- | --- |
| Cross-method | Yes, Locks can be implemented across methods. You can call `lock()` in method1 and `unlock()` in method2. | impossible |
| Attempt to acquire lock | Yes, the `tryLock(timeout)` method is supported by the lock framework. If the resource is available, it will acquire the lock of the resource; otherwise, it will return `false` and the Thread will not be blocked. | Impossible synchronization |
| Fair lock management | Yes, in the case of lock framework, fair lock management is available. It gives the lock to the long-awaited thread. Even in the fair mode set to `true`, if `tryLock` is encoded, it will be served first. | Impossible to synchronize with |
| Waiting thread list | Yes, you can use the `getQueuedThreads()` method of the Lock framework to see the list of waiting threads. | Impossible to synchronize with |
| Release the lock in an exception | ```java Lock.lock(); myMethod(); Lock.unlock();``` If any exception is thrown from `myMethod()`, then `unlock()` cannot be executed in this code. | `synchronized` works very clearly in this situation. It releases the lock. |
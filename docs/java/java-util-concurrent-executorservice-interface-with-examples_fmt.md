# Java并发包ExecutorService接口详解

> 原文：[https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/)

`ExecutorService`接口通过添加帮助管理和控制线程执行的方法来扩展`Executor`。它在[`java.util.concurrent`](https://www.geeksforgeeks.org/tag/java-concurrent-package/)包中定义。它定义了执行返回结果的线程、一组线程和确定关闭状态的方法。

`ExecutorService`接口在一个名为`Executors`的实用程序类中实现。它定义了提供`ExecutorService`接口和许多其他接口的实现的方法，并带有一些默认设置。

## 继承层次

```java
java.util.concurrent
  ↳ Interface ExecutorService
```

## 实现子接口

```java
ScheduledExecutorService
```

## 实现类

```java
AbstractExecutorService
ForkJoinPool
ScheduledThreadPoolExecutor
ThreadPoolExecutor
```

## ExecutorService接口的方法

**1. `shutdown()`** – 当被调用时，该函数会导致所有当前正在执行的任务在完成后按照开始的顺序终止，并拒绝任何新的传入任务。

**语法：**

```java
void shutdown()
```

**2. `shutdownNow()`** – 在调用时，函数强制终止所有任务，而不管它们的当前状态，即运行、等待或就绪。返回中处于就绪状态的任务列表。

**语法：**

```java
List<Runnable> shutdownNow()
```

**3. `isShutdown()`** – 函数告诉调用的执行器是否关闭。如果关闭，则返回`true`，否则返回`false`。

**语法：**

```java
boolean isShutdown()
```

**4. `isTerminated()`** – 该功能检查关机后是否所有任务都已完成。如果完成则返回真，否则返回假。

**语法：**

```java
boolean isTerminated()
```

**5. `awaitTermination()`** – 该函数在发现关机请求后等待所有任务完成执行。它等待`timeLimit`参数指定的时间。

**语法：**

```java
boolean awaitTermination(long timeout, TimeUnit unit) throws InterruptedException
```

**6. `submit()`** – 该函数将一个返回结果的任务添加到正在执行的任务列表中以供执行。它返回一个`Future`对象，该对象返回任务完成后的结果。

**语法：**

```java
1. <T> Future<T> submit(Callable<T> task)
2. <T> Future<T> submit(Runnable task, T result)
3. Future<?> submit(Runnable task)
```

**7. `invokeAll()`** – 函数执行集合中包含的所有任务。将返回`Future`对象列表，其中包含各种任务的状态和返回值。

**语法：**

```java
1. <T> List<Future<T>> invokeAll(Collection<? extends Callable<T>> tasks, long timeout, TimeUnit unit) throws InterruptedException
2. <T> List<Future<T>> invokeAll(Collection<? extends Callable<T>> tasks) throws InterruptedException
```

**8. `invokeAny()`** – 函数执行集合中包含的所有任务。任何一项任务完成后，它都会返回结果，所有其他任务都会被取消。

**语法：**

```java
1. <T> T invokeAny(Collection<? extends Callable<T>> tasks, long timeout, TimeUnit unit) throws InterruptedException, ExecutionException, TimeoutException
2. <T> T invokeAny(Collection<? extends Callable<T>> tasks) throws InterruptedException, ExecutionException
```

## 示例代码

```java
// Java program to demonstrate ExecutorService interface

import java.util.concurrent.*;

public class SimpleExecutor {

    public static void main(String[] args)
    {
        CountDownLatch cd1 = new CountDownLatch(5);
        CountDownLatch cd2 = new CountDownLatch(5);
        CountDownLatch cd3 = new CountDownLatch(5);
        CountDownLatch cd4 = new CountDownLatch(5);

        ExecutorService es = Executors.newFixedThreadPool(2);

        System.out.println("Starting");

        es.execute(new MyThread(cd1, "A"));
        es.execute(new MyThread(cd2, "B"));
        es.execute(new MyThread(cd3, "C"));
        es.execute(new MyThread(cd4, "D"));

        try {
            cd1.await();
            cd2.await();
            cd3.await();
            cd4.await();
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }

        es.shutdown();
        System.out.println("Done");
    }
}

class MyThread implements Runnable {
    String name;
    CountDownLatch latch;

    MyThread(CountDownLatch latch, String name)
    {
        this.name = name;
        this.latch = latch;

        new Thread(this);
    }

    public void run()
    {
        for (int i = 0; i < 5; i++) {
            System.out.println(name + ":  " + i);
            latch.countDown();
        }
    }
}
```

## 输出

```java
Starting
A:  0
A:  1
A:  2
A:  3
A:  4
C:  0
C:  1
C:  2
C:  3
C:  4
D:  0
D:  1
D:  2
D:  3
D:  4
B:  0
B:  1
B:  2
B:  3
B:  4
Done
```

**参考：** [https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/)
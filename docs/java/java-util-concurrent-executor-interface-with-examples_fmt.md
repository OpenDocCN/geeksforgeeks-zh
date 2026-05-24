# Java.util.concurrent.Executor 接口示例

> 原文：[https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/)

Java 中的并发应用编程接口提供了一个名为`Executor`的特性，即**启动并控制线程**的执行。因此，`Executor`提供了一种使用`Thread`类管理线程的替代方法。`Executor`的核心是`Executor`接口。它指的是执行提交的`Runnable`任务的对象。

**类层次结构：**
```java
java.util.concurrent
  ↳ Interface Executor
```

**实现的子接口：**
```java
ExecutorService
ScheduledExecutorService
```

**已知实现类：**
```java
AbstractExecutorService
ForkJoinPool
ScheduledThreadPoolExecutor
ThreadPoolExecutor
```

**Executor 接口的方法：**
1.  `execute()`：该函数在未来某个时间执行给定的命令。根据`Executor`实现的判断，该命令可以在新线程、池线程或调用线程中执行。
    **语法：**
    ```java
    void execute(Runnable task)
    ```

## 示例代码

```java
import java.util.concurrent.Executor;
import java.util.concurrent.RejectedExecutionException;

public class ExecutorDemo {
    public static void main(String[] args)
    {
        ExecutorImp obj = new ExecutorImp();
        try {
            obj.execute(new NewThread());
        }
        catch (RejectedExecutionException
               | NullPointerException exception) {
            System.out.println(exception);
        }
    }
}

class ExecutorImp implements Executor {
    @Override
    public void execute(Runnable command)
    {
        new Thread(command).start();
    }
}

class NewThread implements Runnable {
    @Override
    public void run()
    {
        System.out.println("Thread executed under an executor");
    }
}
```

**输出：**
```java
Thread executed under an executor
```

**参考：** [T2T4]
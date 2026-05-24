# Java 中的 `java.lang.management.ThreadInfo` 类

> 原文：[https://www.geeksforgeeks.org/java-lang-management-threadinfo-class-in-java/](https://www.geeksforgeeks.org/java-lang-management-threadinfo-class-in-java/)

`java.lang.management.ThreadInfo` 类包含获取线程信息的方法。这些信息包括：

*   线程标识
*   线程名称
*   线程的状态
*   线程的堆栈跟踪
*   线程被阻止的对象
*   线程阻止的对象监视器列表
*   被线程阻止的可拥有的同步器列表
*   线程被阻止的次数
*   线程被阻塞的时间

**语法：** 类声明

```java
public class ThreadInfo
extends Object
```

此类的方法如下：

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| `ThreadInfo from(CompositeData)` | 此方法用于将此复合数据表示为 `ThreadInfo` 对象。 |
| `getBlockedCount()` | 此方法用于了解与此 `ThreadInfo` 对象关联的线程被阻止进入监视器或重新进入监视器的次数。 |
| `getBlockedTime()` | 此方法用于了解与此 `ThreadInfo` 对象关联的线程被阻止进入或重新进入监视器的毫秒数。 |
| `getLockedMonitors()` | 此方法用于获取与此 `ThreadInfo` 对象关联的线程当前锁定的 `MonitorInfo` 对象列表。 |
| `getLockedSynchronizers()` | 此方法用于获取与此 `ThreadInfo` 对象关联的线程当前锁定的可拥有的同步器列表。 |
| `getLockInfo()` | 此方法用于获取与此 `ThreadInfo` 对象关联的线程因等待而被阻止的对象的信息。它返回一个表示信息的 `LockInfo` 对象。 |
| `getLockName()` | 此方法用于获取与此 `ThreadInfo` 对象关联的线程因等待而被阻止的对象的名称。 |
| `getLockOwnerId()` | 此方法用于获取阻止此线程的对象的所有者的线程 ID。 |
| `getLockOwnerName()` | 此方法用于获取阻止此线程的对象的所有者的线程名称。 |
| `getStackTrace()` | 此方法用于获取线程的堆栈跟踪。 |
| `getThreadId()` | 此方法用于获取线程的 ID。 |
| `getThreadName()` | 此方法用于获取线程的名称。 |
| `getThreadState()` | 此方法用于获取线程的状态。 |
| `getWaitedCount()` | 此方法用于了解与此 `ThreadInfo` 对象关联的线程等待通知的次数。 |
| `getWaitedTime()` | 此方法用于了解与此 `ThreadInfo` 对象关联的线程等待通知的毫秒数。 |
| `isInNative()` | 此方法用于确定此 `ThreadInfo` 对象是否正在通过 Java 原生接口执行原生代码。 |
| `isSuspended()` | 此方法用于确定与此 `ThreadInfo` 对象关联的线程是否被挂起。 |
| `toString()` | 此方法用于获取给定 `ThreadInfo` 对象的字符串表示形式。 |

</figure>

**实现：**

## 示例 1：创建新的 ThreadInfo 对象

```java
// Java Program to demonstrate ThreadInfo Class

// Importing required libraries
import java.lang.management.ManagementFactory;
import java.lang.management.ThreadInfo;

// Main class
public class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating a new thread by
            // creating an object of Thread class
            Thread thread = new Thread();

            // running the thread using run() method
            thread.run();

            // Getting thread id using getId() method
            long id = thread.getId();

            // Creating a new ThreadInfo object
            // using that id
            ThreadInfo info
                = ManagementFactory.getThreadMXBean()
                      .getThreadInfo(id);

            // Print and display message on the console
            System.out.println(
                "ThreadInfo object created successfully");
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // print the line number where exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出：**

```java
ThreadInfo object created successfully
```

## 示例 2：使用 ThreadInfo 类获取通用清理器线程信息

```java
// Java Program to demonstrate ThreadInfo Class

// Importing required libraries
import java.lang.management.ManagementFactory;
import java.lang.management.ThreadInfo;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // try block to check for exceptions
        try {

            long id = 10;

            // Creating a new ThreadInfo object
            // using this id
            ThreadInfo info
                = ManagementFactory.getThreadMXBean()
                      .getThreadInfo(id);
            // Printing information about the thread

            // 1. Printing thread id
            System.out.println("Thread ID: "
                               + info.getThreadId());
            // 2. Printing Thread Name
            System.out.println("Thread Name: "
                               + info.getThreadName());
            // 3. Printing thread State
            System.out.println("Thread State: "
                               + info.getThreadState());
            // 4. Printing thread waited count
            System.out.println("Waited count: "
                               + info.getWaitedCount());
            // 5. Printing thread waited time
            System.out.println("Waited time: "
                               + info.getWaitedTime());
            // 6. Printing how many times this thread had
            // been blocked
            System.out.println("Times blocked: "
                               + info.getBlockedCount());
            // 7. Printing Blocked duration
            System.out.println("Blocked duration: "
                               + info.getBlockedTime());
            // 8. Printing Locked Monitors
            System.out.println("Locked Monitors: "
                               + info.getLockedMonitors());
            // 9. Printing Locked Owner's ID
            System.out.println("Locked Owner's ID: "
                               + info.getLockOwnerId());
            // 10. Printing Locked Owner's Name
            System.out.println("Locked Owner's Name: "
                               + info.getLockOwnerName());
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the line number where exception occured
            e.printStackTrace();
        }
    }
}
```

**输出：**

```java
Thread ID: 10
Thread Name: Common-Cleaner
Thread State: TIMED_WAITING
Waited count: 1
Waited time: -1
Times blocked: 0
Blocked duration: -1
Locked Monitors: [Ljava.lang.management.MonitorInfo;@15aeb7ab
Locked Owner's ID: -1
Locked Owner's Name: null
```
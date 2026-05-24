# Java 中的 `ThreadGroup` 类

> 原文：[https://www.geeksforgeeks.org/java-lang-threadgroup-class-java/](https://www.geeksforgeeks.org/java-lang-threadgroup-class-java/)

线程组创建一组线程。它提供了一种方便的方法来将线程组作为一个单元进行管理。这在您想要挂起和恢复大量相关线程的情况下尤其有价值。

*   线程组形成一个树，其中除了初始线程组之外的每个线程组都有一个父线程组。
*   一个线程被允许访问关于它自己的线程组的信息，但不能访问关于它的线程组的父线程组或任何其他线程组的信息。

## 构造方法

1.  **`ThreadGroup(String name)`**：构建一个新的线程组。这个新组的父组是当前正在运行的线程的线程组。

    ```java
    Throws: SecurityException - if the current thread cannot
     create a thread in the specified thread group.
    ```

2.  **`ThreadGroup(ThreadGroup parent, String name)`**：创建新的线程组。这个新组的父组是指定的线程组。

    ```java
    Throws:
    NullPointerException - if the thread group argument is null.
    SecurityException - if the current thread cannot create a thread in the
    specified thread group.
    ```

## 方法

1.  **`int activeCount()`**：此方法返回该组中的线程数加上此线程作为父线程的任何组。

    ```java
    Syntax: public int activeCount()
    Returns: This method returns an estimate of the number of
    active threads in this thread group and in any other thread group
    that has this thread group as an ancestor.
    Exception: NA
    ```

    ```java
    // Java code illustrating activeCount() method
    import java.lang.*;
    class NewThread extends Thread
    {
        NewThread(String threadname, ThreadGroup tgob)
        {
            super(tgob, threadname);
            start();
        }
        public void run()
        {
            for (int i = 0; i < 1000; i++)
            {
                try
                {
                    Thread.sleep(10);
                }
                catch (InterruptedException ex)
                {
                    System.out.println("Exception encounterted");
                }
            }
        }
    }
    public class ThreadGroupDemo
    {
        public static void main(String arg[])
        {
            // creating the thread group
            ThreadGroup gfg = new ThreadGroup("parent thread group");

            NewThread t1 = new NewThread("one", gfg);
            System.out.println("Starting one");
            NewThread t2 = new NewThread("two", gfg);
            System.out.println("Starting two");

            // checking the number of active thread
            System.out.println("number of active thread: "
                               + gfg.activeCount());
        }
    }
    ```

    输出：

    ```java
    Starting one
    Starting two
    number of active thread: 2
    ```

2.  **`int activeGroupCount()`**：此方法返回此线程组中活动组的估计数。

    ```java
    Syntax: public int activeGroupCount().
    Returns: Returns the number of groups for which the invoking thread is parent.
    Exception: NA.
    ```

    ```java
    // Java code illustrating activeGroupCount() method
    import java.lang.*;
    class NewThread extends Thread
    {
        NewThread(String threadname, ThreadGroup tgob)
        {
            super(tgob, threadname);
            start();
        }
        public void run()
        {
            for (int i = 0; i < 1000; i++)
            {
                try
                {
                    Thread.sleep(10);
                }
                catch (InterruptedException ex)
                {
                    System.out.println("Exception encounterted");
                }
            }
            System.out.println(Thread.currentThread().getName() +
                " finished executing");
        }
    }
    public class ThreadGroupDemo
    {
        public static void main(String arg[]) throws InterruptedException
        {
            // creating the thread group
            ThreadGroup gfg = new ThreadGroup("gfg");

            ThreadGroup gfg_child = new ThreadGroup(gfg, "child");

            NewThread t1 = new NewThread("one", gfg);
            System.out.println("Starting one");
            NewThread t2 = new NewThread("two", gfg);
            System.out.println("Starting two");

            // checking the number of active thread
            System.out.println("number of active thread group: "
                               + gfg.activeGroupCount());
        }
    }
    ```

    输出：

    ```java
    Starting one
    Starting two
    number of active thread group: 2
    one finished executing
    two finished executing
    ```

3.  **`void checkAccess()`**：导致安全管理器验证调用线程是否可以访问和/或更改调用 `checkAccess()` 的组。

    ```java
    Syntax: final void checkAccess().
    Returns: NA.
    Exception: NA.
    ```

    ```java
    // Java code illustrating checkAccess() method
    import java.lang.*;
    class NewThread extends Thread
    {
        NewThread(String threadname, ThreadGroup tgob)
        {
            super(tgob, threadname);
            start();
        }
        public void run()
        {
            for (int i = 0; i < 1000; i++)
            {
                try
                {
                    Thread.sleep(10);
                }
                catch (InterruptedException ex)
                {
                    System.out.println("Exception encounterted");
                }
            }
            System.out.println(Thread.currentThread().getName() +
                  " finished executing");
        }
    }
    public class ThreadGroupDemo
    {
        public static void main(String arg[]) throws InterruptedException,
            SecurityException
        {
            // creating the thread group
            ThreadGroup gfg = new ThreadGroup("Parent thread");

            ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");

            NewThread t1 = new NewThread("one", gfg);
            System.out.println("Starting one");
            NewThread t2 = new NewThread("two", gfg);
            System.out.println("Starting two");
            gfg.checkAccess();
            System.out.println(gfg.getName() + " has access");
            gfg_child.checkAccess();
            System.out.println(gfg_child.getName() + " has access");
        }
    }
    ```

    输出：

    ```java
    Starting one
    Starting two
    Parent thread has access
    child thread has access
    one finished executing
    two finished executing
    ```

4.  **`void destroy()`**：销毁线程组及其被调用的任何子组。

    ```java
    Syntax: public void destroy().
    Returns: NA.
    Exception:
    IllegalThreadStateException - if the thread group is not
    empty or if the thread group has already been destroyed.
    SecurityException - if the current thread cannot modify this thread group.
    ```

    ```java
    // Java code illustrating destroy() method
    import java.lang.*;
    class NewThread extends Thread
    {
        NewThread(String threadname, ThreadGroup tgob)
        {
            super(tgob, threadname);
            start();
        }
        public void run()
        {
            for (int i = 0; i < 10; i++)
            {
                try
                {
                    Thread.sleep(10);
                }
                catch (InterruptedException ex)
                {
                    System.out.println("Exception encounterted");
                }
            }
        }
    }
    public class ThreadGroupDemo
    {
        public static void main(String arg[]) throws InterruptedException,
            SecurityException
        {
            // creating the thread group
            ThreadGroup gfg = new ThreadGroup("Parent thread");

            ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");

            NewThread t1 = new NewThread("one", gfg);
            System.out.println("Starting one");
            NewThread t2 = new NewThread("two", gfg);
            System.out.println("Starting two");

            // block until other thread is finished
            t1.join();
            t2.join();

            // destroying child thread
            gfg_child.destroy();
            System.out.println(gfg_child.getName() + " destroyed");

            // destroying parent thread
            gfg.destroy();
            System.out.println(gfg.getName() + " destroyed");
        }
    }
    ```

    输出：

    ```java
    Starting one
    Starting two
    child thread destroyed
    Parent thread destroyed
    ```

5.  **`int enumerate(Thread[] group)`**：将调用线程组中的线程放入 `group` 数组中。

## `enumerate(Thread[] group)` 方法

```java
Syntax: public int enumerate(Thread group[]).
Returns: the number of threads put into the array.
Exception: SecurityException - if the current thread 
does not have permission to enumerate this thread group.
```

```java
// Java code illustrating enumerate() method.
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() +
             " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting one");
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting two");
        // returns the number of threads put into the array
        Thread[] group = new Thread[gfg.activeCount()];
        int count = gfg.enumerate(group);
        for (int i = 0; i < count; i++) 
        {
            System.out.println("Thread " + group[i].getName() + " found");
        }
    }
}
```

输出:

```java
Starting one
Starting two
Thread one found
Thread two found
one finished executing
two finished executing
```

## `enumerate(Thread[] group, boolean recurse)` 方法

**int enumerate(Thread[] group, boolean recurse):** The threads that comprise the invoking thread group are put into the `group` array. If `all` is **true**, then threads in all subgroups of the thread are also put into `group`.

```java
Syntax: public int enumerate(Thread[] list, boolean recurse).
Returns: the number of threads placed into the array.
Exception: SecurityException - if the current thread does 
not have permission to enumerate this thread group.
```

```java
// Java code illustrating enumerate(Thread[] group, boolean recurse)
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() +
              " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting one");
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting two");
        // returns the number of threads put into the array
        Thread[] group = new Thread[gfg.activeCount()];
        int count = gfg.enumerate(group, true);
        for (int i = 0; i < count; i++) 
        {
            System.out.println("Thread " + group[i].getName() + " found");
        }
    }
}
```

输出:

```java
Starting one
Starting two
Thread one found
Thread two found
one finished executing
two finished executing
```

## 13. `int enumerate(ThreadGroup[] group)`
调用线程组的子组被放入 `group` 数组中。

**语法：** `public int enumerate(ThreadGroup[] group)`
**返回值：** 放入数组中的线程组数量。
**异常：** `SecurityException` - 如果当前线程没有权限枚举此线程组。

```java
// Java code illustrating enumerate(ThreadGroup[] group) method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
               " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting one");
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting two");
        // returns the number of threads put into the array
        ThreadGroup[] group = new ThreadGroup[gfg.activeCount()];
        int count = gfg.enumerate(group);
        for (int i = 0; i < count; i++) 
        {
            System.out.println("ThreadGroup " + group[i].getName() +
                " found");
        }
    }
}
```

**输出：**
```java
Starting one
Starting two
ThreadGroup child thread found
two finished executing
one finished executing
```

## 14. `int enumerate(ThreadGroup[] group, boolean all)`
调用线程组的子组被放入 `group` 数组中。如果 `all` 为 `true`，则所有子组的子组（依此类推）也会被放入 `group` 中。

**语法：** `public int enumerate(ThreadGroup[] group, boolean all)`
**返回值：** 放入数组中的线程组数量。
**异常：** `SecurityException` - 如果当前线程没有权限枚举此线程组。

```java
// Java code illustrating enumerate(ThreadGroup[] group, boolean all)
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() +
               " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting one");
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting two");
        // returns the number of threads put into the array
        ThreadGroup[] group = new ThreadGroup[gfg.activeCount()];
        int count = gfg.enumerate(group, true);
        for (int i = 0; i < count; i++) 
        {
            System.out.println("ThreadGroup " + group[i].getName() + 
                " found");
        }
    }
}
```

**输出：**
```java
Starting one
Starting two
ThreadGroup child thread found
two finished executing
one finished executing
```

## 15. `int getMaxPriority()`
返回组的最大优先级设置。

**语法：** `final int getMaxPriority()`
**返回值：** 此线程组中线程可以拥有的最大优先级。
**异常：** NA。

```java
// Java code illustrating getMaxPriority() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() +
               " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        // checking the maximum priority of parent thread
        System.out.println("Maximum priority of ParentThreadGroup = "
                           + gfg.getMaxPriority());
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting one");
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting two");
    }
}
```

**输出：**
```java
Maximum priority of ParentThreadGroup = 10
Starting one
Starting two
two finished executing
one finished executing
```

## 22. `String getName()`
此方法返回组的名称。

**语法：** `final String getName()`
**返回值：** 此线程组的名称。
**异常：** NA。

```java
// Java code illustrating getName() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Exception encounterted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
              " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());
    }
}
```

**输出：**
```java
Starting one
Starting two
two finished executing
one finished executing
```

## 23. `ThreadGroup getParent()`
如果调用的 `ThreadGroup` 对象没有父级，则返回 `null`。否则，返回调用对象的父级。

## 24. void interrupt():
调用线程组中所有线程的 `interrupt()` 方法。

```java
Syntax: public final void interrupt().
Returns: NA.
Exception: SecurityException - if the current thread is not allowed to access this thread group or any of the threads in the thread group.
```

```java
// Java code illustrating interrupt() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
              System.out.println("Thread " + Thread.currentThread().getName()
                                   + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
             " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());
        // interrupting thread group
        gfg.interrupt();
    }
}
```

输出:
```java
Starting one
Starting two
Thread two interrupted
Thread one interrupted
one finished executing
two finished executing
```

## 25. boolean isDaemon():
测试此线程组是否为守护线程组。守护线程组在其最后一个线程停止或其最后一个线程组被销毁时会自动销毁。

```java
Syntax: public final boolean isDaemon().
Returns: true if the group is daemon group. Otherwise it returns false.
Exception: NA.
```

```java
// Java code illustrating isDaemon() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
              System.out.println("Thread " + Thread.currentThread().getName()
                                   + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
                " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());
        if (gfg.isDaemon() == true)
            System.out.println("Group is Daemon group");
        else
            System.out.println("Group is not Daemon group");
    }
}
```

输出:
```java
Starting one
Starting two
Group is not Daemon group
two finished executing
one finished executing
```

## 26. boolean isDestroyed():
此方法测试该线程组是否已被销毁。

```java
Syntax: public boolean isDestroyed().
Returns: true if this object is destroyed.
Exception: NA.
```

```java
// Java code illustrating isDestroyed() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
              System.out.println("Thread " + Thread.currentThread().getName()
                                   + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
                " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException, Exception
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());
        if (gfg.isDestroyed() == true)
            System.out.println("Group is destroyed");
        else
            System.out.println("Group is not destroyed");
    }
}
```

输出:
```java
Starting one
Starting two
Group is not destroyed
one finished executing
two finished executing
```

## 33. void list():
显示有关线程组的信息。

```java
Syntax: public void list().
Returns: NA.
Exception: NA.
```

## `boolean parentOf(ThreadGroup group)`
此方法测试此线程组是否是指定的线程组或其祖先线程组之一。

```java
Syntax: final boolean parentOf(ThreadGroup group).
Returns: true if the invoking thread is the parent 
of group(or group itself). Otherwise, it returns false.
Exception: NA.
```

```java
// Java code illustrating parentOf() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Thread " + Thread.currentThread().getName()
                                   + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
                " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException, Exception
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");

        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());

        // checking who is parent thread
        if (gfg.parentOf(gfg_child))
            System.out.println(gfg.getName() + " is parent of " +
               gfg_child.getName());
    }
}
```

输出:

```java
Starting one
Starting two
Parent thread is parent of child thread
two finished executing
one finished executing
```

## `void setDaemon(boolean isDaemon)`
此方法更改此线程组的守护程序状态。守护程序线程组在其最后一个线程停止或其最后一个线程组被销毁时自动销毁。

```java
Syntax: final void setDaemon(boolean isDaemon).
Returns: If isDaemon is true, then the invoking group is 
flagged as a daemon group.
Exception: SecurityException - if the current 
thread cannot modify this thread group.
```

```java
// Java code illustrating setDaemon() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
        start();
    }
    public void run()
    {
        for (int i = 0; i < 10; i++) 
        {
            try 
            {
                Thread.sleep(10);
            }
            catch (InterruptedException ex) 
            {
                System.out.println("Thread " + Thread.currentThread().getName()
                                   + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + 
               " finished executing");
    }
} 
public class ThreadGroupDemo 
{
    public static void main(String arg[]) throws InterruptedException,
        SecurityException, Exception
    {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");

        // daemon status is set to true
        gfg.setDaemon(true);

        // daemon status is set to true
        gfg_child.setDaemon(true);
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());

        if (gfg.isDaemon() && gfg_child.isDaemon())
            System.out.println("Parent Thread group and "
                               + "child thread group"
                               + " is daemon");
    }
}
```

输出:

```java
Starting one
Starting two
Parent Thread group and child thread group is daemon
one finished executing
two finished executing
```

## `void setMaxPriority(int priority)`
将调用组的最大优先级设置为 `priority`。

```java
Syntax: final void setMaxPriority(int priority).
Returns: NA.
Exception: SecurityException - if the current thread 
cannot 
modify this thread group.
```

```java
// Java code illustrating setMaxPriority() method
import java.lang.*;
class NewThread extends Thread 
{
    NewThread(String threadname, ThreadGroup tgob)
    {
        super(tgob, threadname);
    }
    public void run()
    {
```

# Java ThreadGroup 示例与 `toString()` 方法

## 代码示例

```java
for (int i = 0; i < 10; i++) {
    try {
        Thread.sleep(10);
    } catch (InterruptedException ex) {
        System.out.println("Thread " + Thread.currentThread().getName() + " interrupted");
    }
}
System.out.println(Thread.currentThread().getName() + " [priority = " + Thread.currentThread().getPriority() + "] finished executing.");
}
}
public class ThreadGroupDemo {
    public static void main(String arg[]) throws InterruptedException, SecurityException, Exception {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");
        gfg.setMaxPriority(Thread.MAX_PRIORITY - 2);
        gfg_child.setMaxPriority(Thread.NORM_PRIORITY);

        NewThread t1 = new NewThread("one", gfg);
        t1.setPriority(Thread.MAX_PRIORITY);
        System.out.println("Starting " + t1.getName());
        t1.start();
        NewThread t2 = new NewThread("two", gfg_child);
        t2.setPriority(Thread.MAX_PRIORITY);
        System.out.println("Starting " + t2.getName());
        t2.start();
    }
}
```

输出：

```java
Starting one
Starting two
two [priority = 5] finished executing.
one [priority = 8] finished executing.
```

## 37. `String toString()`

此方法返回此线程组的字符串表示形式。

```java
Syntax: public String toString().
Returns: String equivalent of the group.
Exception: SecurityException - if the current thread cannot modify this thread group.
```

```java
// Java code illustrating toString() method
import java.lang.*;
class NewThread extends Thread {
    NewThread(String threadname, ThreadGroup tgob) {
        super(tgob, threadname);
        start();
    }
    public void run() {
        for (int i = 0; i < 10; i++) {
            try {
                Thread.sleep(10);
            } catch (InterruptedException ex) {
                System.out.println("Thread " + Thread.currentThread().getName() + " interrupted");
            }
        }
        System.out.println(Thread.currentThread().getName() + " finished executing");
    }
}
public class ThreadGroupDemo {
    public static void main(String arg[]) throws InterruptedException, SecurityException, Exception {
        // creating the thread group
        ThreadGroup gfg = new ThreadGroup("Parent thread");
        ThreadGroup gfg_child = new ThreadGroup(gfg, "child thread");

        // daemon status is set to true
        gfg.setDaemon(true);

        // daemon status is set to true
        gfg_child.setDaemon(true);
        NewThread t1 = new NewThread("one", gfg);
        System.out.println("Starting " + t1.getName());
        NewThread t2 = new NewThread("two", gfg);
        System.out.println("Starting " + t2.getName());

        // string equivalent of the parent group
        System.out.println("String equivalent: " + gfg.toString());
    }
}
```

输出：

```java
Starting one
Starting two
String equivalent: java.lang.ThreadGroup[name=Parent thread, maxpri=10]
one finished executing
two finished executing
```

---
本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
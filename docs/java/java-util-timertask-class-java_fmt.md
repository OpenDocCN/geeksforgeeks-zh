# Java 中的 TimerTask 类

> 原文：[https://www.geeksforgeeks.org/java-util-timertask-class-java/](https://www.geeksforgeeks.org/java-util-timertask-class-java/)

`TimerTask` 是 `java.util` 包中定义的抽象类。`TimerTask` 类定义了一个任务，该任务可以被安排为只运行一次，也可以重复运行多次。为了定义 `TimerTask` 对象，需要实现这个类，并且需要重写 `run` 方法。当定时器对象调度 `run` 方法时，`run` 方法被隐式调用。

**注意：**`TimerTask` 类的一个实例用于定义需要定期运行的任务。

## 构造函数

*   `TimerTask()`：创建一个新的定时器任务。

## 声明

```java
public abstract class TimerTask
        extends Object
        implements Runnable
```

## 方法

1.  `cancel()`：`java.util.TimerTask.cancel()` 取消此计时器任务。

**语法：**

```java
public boolean cancel()
```

**返回：**
如果此任务被安排为一次性执行且尚未运行，或者此任务被安排为重复执行，则返回 `true`。如果任务被安排为一次性执行但已经运行，或者任务从未被安排，或者任务已被取消，则返回 `false`。

2.  `run()`：`java.util.TimerTask.run()` 此计时器任务要执行的操作。

**语法：**

```java
public abstract void run()
```

**描述：**
此定时器任务要执行的操作。

3.  `scheduledExecutionTime()`：`java.util.TimerTask.scheduledExecutionTime()` 返回此任务最近一次实际执行的计划执行时间。

## 方法继承自 java.lang.Object 类

*   `clone()`
*   `equals(Object obj)`
*   `finalize()`
*   `getClass()`
*   `hashCode()`
*   `notifyAll()`
*   `toString()`
*   `wait()`

## 演示 TimerTask 类用法的 Java 程序

```java
// Java program to demonstrate
// working of TimerTask class
import java.util.Timer;
import java.util.TimerTask;

class Helper extends TimerTask
{
    public static int i = 0;
    public void run()
    {
        System.out.println("Timer ran" + ++i);
        if(i == 4)
        {
            synchronized(Test.obj)
            {
                Test.obj.notify();
            }
        }
    }

}

public class Test
{
    public static Test obj;
    public static void main(String[] args) throws InterruptedException
    {
        obj = new Test();

        // creating an instance of timer class
        Timer timer = new Timer();

        // creating an instance of task to be scheduled
        TimerTask task = new Helper();

        // scheduling the timer instance
        timer.schedule(task, 1000, 3000);

        // fetching the scheduled execution time of
        // the most recent actual execution of the task
        System.out.println(task.scheduledExecutionTime());

        synchronized(obj)
        {
            //this thread waits until i reaches 4
            obj.wait();
        }

        //canceling the task assigned
        System.out.println("Cancel the timer task: " + task.cancel());

        // at this point timer is still running
        // without any task assigned to it

        // canceling the timer instance created
        timer.cancel();
    }
}
```

## 输出

```java
Timer ran 1
Timer ran 2
Timer ran 3
Timer ran 4
Cancel the timer task: true
```

## 参考资料

*   [Oracle 文档](https://docs.oracle.com/javase/8/docs/api/java/util/TimerTask.html)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
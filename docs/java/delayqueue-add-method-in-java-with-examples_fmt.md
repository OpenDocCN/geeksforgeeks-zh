# Java 中的 `DelayQueue` `add()` 方法示例

> 原文：`https://www.geeksforgeeks.org/delayqueue-add-method-in-java-with-examples/`

Java 中 `DelayQueue` 类的 `add(E ele)` 方法用于将给定元素插入延迟队列，如果元素已经成功插入，则返回 `true`。这里，`E` 指的是这个延迟队列集合维护的元素类型。

**语法：**

```java
public boolean add(E ele)
```

**参数：** 该方法只取一个参数 `ele`。它指的是将被插入延迟队列的元素。
**返回值：** 如果元素添加成功，则返回值为 `true`，否则返回 `false`。
**异常：**

*   **`NullPointerException`**：如果试图在这个延迟队列中插入一个 `null` 值，这个方法会抛出一个 `NullPointerException`。

下面的程序说明了 `DelayQueue` 类的 `add()` 方法：

## 示例程序 1

```java
// Java program to illustrate the add()
// method in Java

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create a DelayQueue instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Create an instance of Delayed
        Delayed obj = new Delayed() {
            public long getDelay(TimeUnit unit)
            {
                return 24; // some value is returned
            }

            public int compareTo(Delayed o)
            {
                if (o.getDelay(TimeUnit.DAYS) > this.getDelay(TimeUnit.DAYS))
                    return 1;
                else if (o.getDelay(TimeUnit.DAYS) == this.getDelay(TimeUnit.DAYS))
                    return 0;
                return -1;
            }
        };

        // Use the add() method to add obj to
        // the empty DelayQueue instance
        queue.add(obj);

        System.out.println("Size of the queue : " + queue.size());
    }
}
```

**输出：**

```java
Size of the queue : 1
```

## 示例程序 2

演示 `NullPointerException` 的程序。

```java
// Java program to illustrate the Exception
// thrown by add() method of
// DelayQueue class

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create an instance of DelayQueue
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Try to add NULL to the queue
        try {
            queue.add(null);
        }

        // Catch Exception
        catch (Exception e) {

            // Print Exception raised
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.lang.NullPointerException
```
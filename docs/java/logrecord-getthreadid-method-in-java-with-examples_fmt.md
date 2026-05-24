# Java 中的 `LogRecord getThreadID()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/logrecord-getthreadid-method-in-java-with-examples/](https://www.geeksforgeeks.org/logrecord-getthreadid-method-in-java-with-examples/)

`java.util.logging.LogRecord` 的 `getThreadID()` 方法用于获取消息来源线程的标识符。这个方法有助于识别生成日志消息的线程。

## 语法

```java
public int getThreadID()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回线程号。

## 示例

以下程序说明 `getThreadID()` 方法：

### 程序 1

```java
// Java program to illustrate
// getThreadID() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // get Thread ID
        int id = logRecord.getThreadID();

        // print
        System.out.println(
            "Thread ID = "
            + id);
    }
}
```

**输出：**

```java
Thread ID = 1
```

### 程序 2

```java
// Java program to illustrate
// getThreadID() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {
        // start the Thread
        Thread thread1 = new Thread1();
        thread1.start();

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");
        logRecord.setThreadID((int)thread1
                                  .getId());

        // get Thread ID
        int id = logRecord.getThreadID();

        // print
        System.out.println(
            "Thread ID = "
            + id);
    }
}

class Thread1 extends Thread {
    public void run()
    {
        System.out.println("Thread is running...");
    }
}
```

**输出：**

```java
Thread is running...
Thread ID = 11
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getThreadID()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getThreadID())
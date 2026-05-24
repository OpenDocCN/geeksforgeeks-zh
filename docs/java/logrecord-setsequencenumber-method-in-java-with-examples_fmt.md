# Java 中的 `LogRecord setSequenceNumber()` 方法，带示例

> 原文：`https://www.geeksforgeeks.org/logrecord-setsequencenumber-method-in-java-with-examples/`

`java.util.LogRecord` 的 `setSequenceNumber()` 方法用于将序列号设置为日志记录，以便进行日志记录。

## 语法

```java
public void setSequenceNumber(long seq)
```

## 参数

该方法接受 `seq` 作为 `long` 型参数，这是我们要设置的序列号。

## 返回值

此方法不返回任何内容。

## 示例

下面的程序说明了 `setSequenceNumber()` 方法：

### 程序 1

```java
// Java program to illustrate
// setSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set sequence number
        logRecord.setSequenceNumber(41545412);

        // print the sequence number
        System.out.println(
            "Sequence Number = "
            + logRecord.getSequenceNumber());
    }
}
```

**输出：**

```java
Sequence Number = 41545412
```

### 程序 2

```java
// Java program to illustrate
// setSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class Main {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.INFO,
                            "GFG Logger");

        // set sequence number
        logRecord.setSequenceNumber(96236641);

        // print the sequence number
        System.out.println(
            "Sequence Number = "
            + logRecord.getSequenceNumber());
    }
}
```

**输出：**

```java
Sequence Number = 96236641
```

## 参考文献

`https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setSequenceNumber(long)`
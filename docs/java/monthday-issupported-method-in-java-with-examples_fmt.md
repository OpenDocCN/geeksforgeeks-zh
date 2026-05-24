# MonthDay.isSupported() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/monthday-issupported-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-issupported-method-in-java-with-examples/)

`MonthDay` 类的 `isSupported()` 方法用于检查指定字段是否被该类支持。这意味着使用该方法可以检查是否可以为指定字段查询该 `MonthDay`。

计时场支持的字段有：
*   `MONTH_OF_YEAR`
*   `YEAR`

所有其他时间域实例都将返回 `false`。

**语法：**
```java
public boolean isSupported(TemporalField field)
```

**参数：** 该方法接受一个参数 `field`，该字段是要检查的字段。
**返回值：** 如果该 `MonthDay` 支持该字段，则该方法返回布尔值 `true`，否则返回 `false`。

下面的程序说明了 `isSupported()` 方法：

### 示例程序 1
```java
// Java program to demonstrate
// MonthDay.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // apply isSupported() method
        boolean value
            = month.isSupported(
                ChronoField.MONTH_OF_YEAR);

        // print result
        System.out.println("MONTH_OF_YEAR Field is supported: "
                           + value);
    }
}
```
**输出：**
```java
MONTH_OF_YEAR Field is supported: true
```

### 示例程序 2
```java
// Java program to demonstrate
// MonthDay.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // apply isSupported() method
        boolean value
            = month.isSupported(
                ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field is supported: "
                           + value);
    }
}
```
**输出：**
```java
MilliSecond Field is supported: false
```

**参考文献：** [https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isSupported(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isSupported(java.time.temporal.TemporalField))
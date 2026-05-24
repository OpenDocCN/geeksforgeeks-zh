# Java 中的 ChronoLocalDateTime 接口 getChronology() 方法，带示例

> 原文：[ChronoLocalDateTime getChronology() method in Java with Examples](https://www.geeksforgeeks.org/chronolocaldatetime-getchronology-method-in-java-with-examples/)

Java 中 `ChronoLocalDateTime` 接口的 `getChronology()` 方法获取此日期时间使用的日历系统。

## 语法

```java
default Chronology getChronology()
```

## 参数

此方法不接受任何参数。

## 返回值

返回 `Chronology`（年表），不为空。

下面的程序举例说明了 Java 中的 `getChronology()` 方法：

## 程序 1

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDateTime date
            = LocalDateTime
                  .from(ZonedDateTime.now());

        System.out.println(date.getChronology());
    }
}
```

## 输出

```java
ISO
```

## 参考

[ChronoLocalDateTime getChronology() method](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#getChronology--)
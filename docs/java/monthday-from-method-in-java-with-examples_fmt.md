# Java 中的 MonthDay from()方法，带示例

> 原文：[https://www.geeksforgeeks.org/monthday-from-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-from-method-in-java-with-examples/)

Java 中 `MonthDay` 类的 `from()` 方法从时态对象中获取 `MonthDay` 的一个实例。

## 语法

```java
public static MonthDay from(TemporalAccessor temporal)
```

## 参数

该方法接受一个参数 `temporal`，指定要转换的时态对象，该参数不为 `null`。

## 返回值

函数返回 `LocalDate`，不为 `null`。

## 异常

如果无法转换为 `MonthDay`，函数抛出 `DateTimeException`。

## 示例

以下程序说明了 `MonthDay.from()` 方法：

### 程序 1

```java
// Program to illustrate the from() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        MonthDay date = MonthDay.from(ZonedDateTime.now());
        System.out.println(date);
    }
}
```

**输出：**

```java
--12-06
```

### 程序 2

```java
// Program to illustrate the from() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        MonthDay date = MonthDay.from(ZonedDateTime.now());
        System.out.println(date);
    }
}
```

**输出：**

```java
--12-06
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#from-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#from-java.time.temporal.TemporalAccessor-)
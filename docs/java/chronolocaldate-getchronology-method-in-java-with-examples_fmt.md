# Java 中的 ChronoLocalDate.getChronology() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-getchronology-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-getchronology-method-in-java-with-examples/)

Java 中 `ChronoLocalDate` 接口的 `getChronology()` 方法获取这个日期的年表，就是 ISO 日历系统。

## 语法

```java
public IsoChronology getChronology()
```

## 参数

此方法不接受任何参数。

## 返回值

返回 ISO 年表，不为空。

下面的程序举例说明了 Java 中的 `getChronology()` 方法：

## 程序 1

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.chrono.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");
        System.out.println(dt.getChronology());
    }
}
```

**输出：**

```java
ISO
```

## 程序 2

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDate dt
            = LocalDate.parse("2018-02-21");
        System.out.println(dt.getChronology());
    }
}
```

**输出：**

```java
ISO
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#getChronology--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#getChronology--)
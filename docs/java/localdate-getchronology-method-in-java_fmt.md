# Java 中的 LocalDate `getChronology()` 方法

> 原文：[https://www.geeksforgeeks.org/localdate-getchronology-method-in-java/](https://www.geeksforgeeks.org/localdate-getchronology-method-in-java/)

Java 中 `LocalDate` 类的 `getChronology()` 方法获取这个日期的年表，也就是 ISO 日历系统。

语法：

```java
public IsoChronology getChronology()
```

参数：此方法不接受任何参数。

返回值：返回 ISO 年表，不为空。

下面的程序举例说明了 Java 中 `LocalDate` 的 `getChronology()` 方法：

程序 1：

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDate dt = LocalDate.parse("2018-11-27");
        System.out.println(dt.getChronology());
    }
}
```

输出：

```java
ISO
```

程序 2：

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDate dt = LocalDate.parse("2018-02-21");
        System.out.println(dt.getChronology());
    }
}
```

输出：

```java
ISO
```

参考：[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getChronology()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getChronology())
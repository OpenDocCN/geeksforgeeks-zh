# Java 中的 ChronoLocalDate 接口的 isLeapYear() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-isleapyear-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isleapyear-method-in-java-with-examples/)

Java 中 `ChronoLocalDate` 接口的 `isLeapYear()` 方法用于检查年份是否为闰年。

## 语法

```java
public boolean isLeapYear()
```

## 参数

此方法不接受参数。

## 返回值

如果年份是闰年，函数返回 `true`，否则返回 `false`。

## 示例

下面的程序说明了 Java 中的 `isLeapYear()` 方法：

### 程序 1

```java
// Program to illustrate the isLeapYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Checks
        System.out.println(dt1.isLeapYear());
    }
}
```

**输出：**

```java
false
```

### 程序 2

```java
// Program to illustrate the isLeapYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2012-11-27");

        // Checks
        System.out.println(dt1.isLeapYear());
    }
}
```

**输出：**

```java
true
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isLeapYear--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isLeapYear--)
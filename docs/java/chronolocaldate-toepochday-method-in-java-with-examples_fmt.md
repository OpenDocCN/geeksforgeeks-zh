# ChronoLocalDate toEpochDay() 方法详解与示例

> 原文：[ChronoLocalDate toEpochDay() method in Java with Examples](https://www.geeksforgeeks.org/chronolocaldate-toepochday-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `toEpochDay()` 方法用于将此日期表示为 EpochDay。EpochDay 是从 1970-01-01 (ISO) 的第 0 天开始计算的天数。输出将采用 ISO 8601 格式。

## 语法

```java
default long toEpochDay()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个 `long` 值，即该日期的 EpochDay 计数，不为 `null`。

## 示例

下面的程序说明了 `toEpochDay()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoLocalDate.toEpochDay() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate as EpochDay: "
                           + localD.toEpochDay());
    }
}
```

**输出：**

```java
ChronoLocalDate as EpochDay: 17871
```

### 程序 2

```java
// Java program to demonstrate
// ChronoLocalDate.toEpochDay() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2021-06-30");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate as EpochDay: "
                           + localD.toEpochDay());
    }
}
```

**输出：**

```java
ChronoLocalDate as EpochDay: 18808
```

## 参考

[ChronoLocalDate Java 文档](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#toEpochDay--)
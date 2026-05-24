# Java 中的即时截断 To()方法，示例

> 原文：[https://www.geeksforgeeks.org/instant-truncatedto-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-truncatedto-method-in-java-with-examples/)

一个`Instant`类的`truncatedTo()`方法用来获取这个瞬间在指定单位的值。此方法采用一个参数`unit`，即本瞬间被截断到的单位。它返回一个截断的不可变瞬间，其值以指定的单位表示。

## 语法

```java
public Instant truncatedTo(TemporalUnit unit)
```

## 参数

该方法取一个参数`unit`，该单位是本瞬间被截断到的单位。它不应为`null`。

## 返回

该方法返回一个不可变的截断瞬间，其值以指定的单位表示。

## 异常

此方法抛出以下异常：

*   `DateTimeException`：如果单位对截断无效。
*   `UnsupportedTemporalTypeException`：如果单位不被支持。

下面的程序说明了`Instant.truncatedTo()`方法：

### 程序 1

```java
// Java program to demonstrate
// Instant.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T09:24:54.63Z");

        // print instance
        System.out.println("Instant before"
                           + " truncate: "
                           + instant);

        // truncate to ChronoUnit.HOURS
        // means unit smaller than Hour
        // will be Zero
        Instant returnvalue
            = instant.truncatedTo(ChronoUnit.HOURS);

        // print result
        System.out.println("Instant after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出：**

```java
Instant before truncate: 2018-12-30T09:24:54.630Z
Instant after  truncate: 2018-12-30T09:00:00Z
```

### 程序 2

```java
// Java program to demonstrate
// Instant.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T09:24:54.63Z");

        // print instance
        System.out.println("Instant before"
                           + " truncate: "
                           + instant);

        // truncate to ChronoUnit.DAYS
        // means unit smaller than DAY
        // will be Zero
        Instant returnvalue
            = instant.truncatedTo(ChronoUnit.DAYS);

        // print result
        System.out.println("Instant after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出：**

```java
Instant before truncate: 2018-12-30T09:24:54.630Z
Instant after  truncate: 2018-12-30T00:00:00Z
```

### 程序 3：显示异常

```java
// Java program to demonstrate
// Instant.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T09:24:54.63Z");

        try {
            instant.truncatedTo(ChronoUnit.ERAS);
        }
        catch (Exception e) {

            // print result
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception:
 java.time.temporal.UnsupportedTemporalTypeException:
 Unit is too large to be used for truncation
```

参考：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#truncatedTo(java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#truncatedTo(java.time.temporal.TemporalUnit))
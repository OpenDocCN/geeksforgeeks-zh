# Java 中 LocalTime 的 of() 方法示例

> 原文：[https://www.geeksforgeeks.org/localtime-of-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-of-method-in-java-with-examples/)

## 1. `of(int hour, int minute)` 方法

`of(int hour, int minute)` 方法属于 `LocalTime` 类，用于根据传入的小时和分钟值创建 `LocalTime` 实例。此方法中，小时和分钟以整数格式传入，并基于这些值返回时间。秒和纳秒的值在此方法中默认设置为零。

**语法：**
```java
public static LocalTime of(int hour,
                           int minute)
```

**参数：** 该方法接受两个参数：
*   `hour` – 整数类型，代表一天中的小时。取值范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。取值范围从 0 到 59。

**返回值：** 该方法返回 `LocalTime`。

**异常：** 如果小时或分钟的任何参数值超出范围，该方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中 `LocalTime` 的 `of(hour, minute)` 方法：

**程序：**
```java
// Java program to demonstrate
// LocalTime of(int hour,
// int minute) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalTime object
        LocalTime localtime
            = LocalTime.of(6, 5);

        // Print time
        System.out.println("TIME: "
                           + localtime);
    }
}
```

**输出：**
```java
TIME: 06:05
```

## 2. `of(int hour, int minute, int second)` 方法

`of(int hour, int minute, int second)` 方法属于 `LocalTime` 类，用于根据传入的小时、分钟和秒值创建 `LocalTime` 实例。此方法中，小时、分钟和秒的值以整数格式传入，并基于这些值返回时间。纳秒的值在此方法中默认设置为零。

**语法：**
```java
public static LocalTime of(int hour,
                           int minute,
                           int second)
```

**参数：** 该方法接受三个参数：
*   `hour` – 整数类型，代表一天中的小时。取值范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。取值范围从 0 到 59。
*   `second` – 整数类型，表示分钟中的秒。取值范围从 0 到 59。

**返回值：** 该方法返回 `LocalTime`。

**异常：** 如果有任何参数超出范围，该方法抛出 `DateTimeException`。

下面的程序说明了 Java 中 `LocalTime` 的 `of(hour, minute, second)` 方法：

**程序：**
```java
// Java program to demonstrate
// LocalTime of(int hour, int minute, int second) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalTime object
        LocalTime localtime
            = LocalTime.of(6, 5, 40);

        // Print time
        System.out.println("TIME: "
                           + localtime);
    }
}
```

**输出：**
```java
TIME: 06:05:40
```

## 3. `of(int hour, int minute, int second, int nanosecond)` 方法

`of(int hour, int minute, int second, int nanosecond)` 方法属于 `LocalTime` 类，用于根据给定的（传入的）小时、分钟、秒和纳秒值创建 `LocalTime` 实例。此方法中，小时、分钟、秒和纳秒的值以整数形式传入，并基于这些值返回时间。此方法中没有参数值被设置为零。

**语法：**
```java
public static LocalTime of(int hour,
                           int minute,
                           int second,
                           int nanosecond)
```

**参数：** 该方法接受四个参数：
*   `hour` – 整数类型，代表一天中的小时。取值范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。取值范围从 0 到 59。
*   `second` – 整数类型，表示分钟中的秒。取值范围从 0 到 59。
*   `nanosecond` – 整数型，代表秒的纳秒部分。取值范围从 0 到 999999999。

**返回值：** 该方法返回 `LocalTime`。

**异常：** 如果小时、分钟、秒或纳秒的任何参数值超出范围，该方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中 `LocalTime` 的 `of(hour, minute, second, nanosecond)` 方法：

**程序：**
```java
// Java program to demonstrate
// LocalTime of(int hour, int minute,
// int second, int nanosecond) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalTime object
        LocalTime localtime
            = LocalTime.of(
                6, 5, 40, 50);

        // Print time
        System.out.println("TIME: "
                           + localtime);
    }
}
```

**输出：**
```java
TIME: 06:05:40.000000050
```

### 参考文献
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int, int))
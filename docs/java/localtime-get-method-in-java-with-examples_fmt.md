# Java 中的 LocalTime get()方法，示例

> 原文：[https://www.geeksforgeeks.org/localtime-get-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-get-method-in-java-with-examples/)

`LocalTime`类的`get()`方法有助于从该`LocalTime`中获取作为参数传递的指定字段的值作为整数值。此方法这次查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回`int`值时，将引发异常。

**语法：**

```java
public int get(TemporalField field)
```

**参数：** 此方法接受单个参数`TemporalField`，即要获取的字段。它不应为`null`。
**返回值：** 该方法返回字段的`int`值。
**异常：** 该方法抛出以下异常：

*   `DateTimeException`：如果无法获得该字段的值或该值超出了该字段的有效值范围。
*   `UnsupportedTemporalTypeException`：如果该字段不支持或值的范围超过一个整数。
*   `ArithmeticException`：如果出现数值溢出。

下面的程序说明了`get()`方法：

## 示例 1

```java
// Java program to demonstrate
// LocalTime.get() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Mili of Second value from LocalTime
        // using get method
        int secondvalue
            = time.get(ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field: "
                           + secondvalue);
    }
}
```

**输出**

```java
MilliSecond Field: 630
```

## 示例 2：获取不支持的`TemporalType`异常

```java
// Java program to demonstrate
// LocalTime.get() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // try to find era using ChronoField
        try {
            int secondvalue
                = time.get(ChronoField.YEAR);
        }
        catch (Exception e) {
            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.time.temporal.UnsupportedTemporalTypeException: Unsupported field: Year
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#get(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#get(java.time.temporal.TemporalField))
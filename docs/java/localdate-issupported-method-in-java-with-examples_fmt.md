# Java 中的 LocalDate isSupported()方法，示例

> 原文: [https://www.geeksforgeeks.org/localdate-issupported-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-issupported-method-in-java-with-examples/)

在 `LocalDate` 类中，根据传递给它的参数，有两种类型的 `isSupported()` 方法。

## 支持检查（TemporalField）

`isSupported()` 是 `LocalDate` 类的一个方法，用来检查指定的字段是否被 `LocalDate` 类支持。也就是说，使用这个方法我们可以检查这个 `LocalDate` 是否可以查询到指定的字段。

计时字段支持的字段有：

*   `YEAR_OF_ERA`

所有其他时间域实例都将返回 `false`。

**语法：**

```java
public boolean isSupported(TemporalField field)
```

**参数：** 此方法接受一个单参数 `field`，即要检查的字段。

**返回值：** 如果该区域日期支持该字段，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `isSupported()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDate.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate lt
            = LocalDate.parse("2018-11-03");

        // check YEAR_OF_ERA is supported in LocalDate
        boolean value
            = lt.isSupported(ChronoField.YEAR_OF_ERA);

        // print result
        System.out.println("YEAR_OF_ERA Field is supported: "
                           + value);
    }
}
```

**输出：**

```java
YEAR_OF_ERA Field is supported: true
```

## 支持检查（TemporalUnit）

`isSupported()` 是 `LocalDate` 类的一个方法，用来检查指定的单位是否被 `LocalDate` 类支持。这意味着使用这个方法我们可以检查这个 `LocalDate` 是否可以查询到指定的单位。

计时单位支持的字段有：

*   `DAYS`
*   `WEEKS`
*   `MONTHS`
*   `YEARS`
*   `DECADES`
*   `CENTURIES`
*   `MILLENNIA`
*   `ERAS`

所有其他计时单位实例将返回 `false`。

**语法：**

```java
public boolean isSupported(TemporalUnit unit)
```

**参数：** 该方法只接受一个参数 `unit`，即要检查的单位。

**返回值：** 如果该区域日期支持该字段，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `isSupported()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDate.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate lt
            = LocalDate.parse("2018-12-29");

        // check CENTURIES ChronoUnit supported in LocalDate
        boolean value
            = lt.isSupported(ChronoUnit.CENTURIES);

        // print result
        System.out.println("ChronoUnit CENTURIES is  supported: "
                           + value);
    }
}
```

**输出：**

```java
ChronoUnit CENTURIES is  supported: true
```

**参考：**
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalField))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalUnit))
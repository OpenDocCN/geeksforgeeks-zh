# 将时间戳转换为日期的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-convert-timestamp-to-date/](https://www.geeksforgeeks.org/java-program-to-convert-timestamp-to-date/)

[`Date`](https://www.geeksforgeeks.org/date-class-java-examples/) 类用于在 Java 中显示日期和时间并操纵日期和时间。除此之外，它还用于在 Java 中格式化日期。`Date` 类和 `Time` 类跨时区关联数据。所以为了使用这个类，需要从 [`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中导入它。

`Timestamp` 类可以用 Java 中的 `Date` 类转换成日期。`Date` 类的构造函数接收一个 `long` 值作为参数。由于 `Date` 类的构造函数需要一个 `long` 值，我们需要使用 `Timestamp` 类的 [`getTime()`](https://www.geeksforgeeks.org/java-sql-timestamp-gettime-function-with-examples/) 方法（存在于 `SQL` 包中）将 `Timestamp` 对象转换成一个 `long` 值。

> 导入 `Date` 类的语法如下：`import java.util.Date;`

导入该类后，可以创建 `Date` 类的对象，以便打印当前日期和时间。现在为了打印默认的日期和时间，只需调用打印命令并使用 [`toString()`](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法获取当前的日期和时间。

**注意：** 为了打印到现在为止的毫秒数，只需使用 `getTime()` 而不是 `toString()` 来获取程序执行之前的毫秒数。另外，请记住 `01-01-1970` 是基准时间，也称为纪元时间。

**方法：** 有以下 3 种方法：
1.  使用构造函数
2.  使用日期引用
3.  使用日历类

**实现：** 借助 Java 程序单独描述方法：

## 方法 1：使用日期构造函数将时间戳更新为日期

```java
// Java program to convert timestamp to Date

// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        // Using currentTimeMillis
        Timestamp ts
            = new Timestamp(System.currentTimeMillis());

        // Passing the long value in the Date class constructor
        Date date = new Date(ts.getTime());

        // Printing the date
        System.out.println(date);
    }
}
```

**Output**

```java
Tue Nov 24 00:28:31 UTC 2020
```

## 方法 2：使用日期引用从时间戳到日期

`Timestamp` 类扩展了 `Date` 类。因此，您可以直接将 `Timestamp` 类的一个实例分配给 `Date`。在这种情况下，`Date` 对象的输出将像 `Timestamp` 一样，即它的格式像日期后跟时间（以毫秒为单位）。

```java
// Java program to convert timestamp to Date
// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        Timestamp ts
            = new Timestamp(System.currentTimeMillis());

        /* Date class is super class of TimeStamp class*/

        // Directly assigning the object of
        // timestamp class to date class
        Date date = ts;

        // Printing the date
        System.out.println(date);
    }
}
```

**Output**

```java
2020-11-24 00:28:30.646
```

## 方法 3：使用日历类从时间戳到日期

我们还可以使用 `Calendar` 类来获取使用 `Timestamp` 的 `Date`，下面是将 `Timestamp` 转换为 `Date` 的方法的实现。

```java
// Java program to convert timestamp to Date

// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;
import java.util.Calendar;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        Timestamp timestamp
            = new Timestamp(System.currentTimeMillis());

        // Getting the calendar class instance
        Calendar calendar = Calendar.getInstance();

        // Passing the long value to calendar class function
        calendar.setTimeInMillis(timestamp.getTime());

        // Getting the time using getTime() function
        System.out.println(calendar.getTime());
    }
}
```

**Output**

```java
Tue Nov 24 00:28:31 UTC 2020
```
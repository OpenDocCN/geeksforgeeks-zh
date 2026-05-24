# 将日期转换为时间戳的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-convert-date-to-timestamp/](https://www.geeksforgeeks.org/java-program-to-convert-date-to-timestamp/)

我们可以使用 `SQL` 包中的 `Timestamp` 类将日期转换为时间戳。

- `Timestamp` 类的构造函数需要一个长值。
- 因此，需要使用 `Date` 类的 `getTime()` 方法（存在于 `util` 包中）将数据转换为长值。

**示例:**

```java
Input: Date is 19 October 2021 
Output: 2021-10-19 18:11:24
Explanation: Date would be printed along with the current time to milliseconds.
```

## 时间戳类

`Timestamp` 类提供格式化和解析方法来支持 JDBC 转义语法。它还结合了保存 SQL 时间戳分数秒值的能力。

### 如何使用时间戳类？

- 导入 `java.sql.Timestamp` 包。
- 导入 `java.util.Date` 包。
- 创建 `Date` 类的对象。
- 将其转换为长使用 `getTime()` 的方法。

**语法:**

```java
public long getTime()
```

**参数:** 函数不接受任何参数。

**返回值:** 返回 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数。

- 创建一个 `Timestamp` 类的对象，并传递 `getTime()` 方法返回的值。
- 最后，打印这个 `Timestamp` 对象值。

**示例:**

### Java 代码示例

```java
// Java Program to convert date to time stamp

import java.sql.Timestamp;
import java.util.Date;
public class GFG_Article {
    public static void main(String args[])
    {

        // getting the system date
        Date date = new Date();

        // getting the object of the Timestamp class
        Timestamp ts = new Timestamp(date.getTime());

        // printing the timestamp of the current date
        System.out.println(ts);
    }
}
```

**输出:**

```java
2021-10-19 20:18:08.813
```

## 格式化时间戳值

- 我们可以使用 `SimpleDateFormat` 类来格式化时间戳值。
- 最初，通过使用 `Timestamp` 类，时间以标准格式显示，但是我们可以使用 `SimpleDateFormat` 类将其格式化为我们自己选择的格式。

**示例:**

### Java 代码示例

```java
// Java program to convert date to time-stamp using
// SimpleDataFormat class and TimeStamp class

import java.sql.Timestamp;
import java.util.Date;
import java.text.SimpleDateFormat;

public class GFG {

    public static void main(String args[])
    {

        // getting the system date
        Date date = new Date();

        // getting the timestamp object
        Timestamp ts = new Timestamp(date.getTime());

        // using SimpleDateFormat class,we can format the
        // time-stamp according to ourselves
        // getting the timestamp upto sec
        SimpleDateFormat formatter
            = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");

       System.out.println(formatter.format(ts));

       // getting the timestamp to seconds
       SimpleDateFormat formatter1
            = new SimpleDateFormat("yyyy-MM-dd HH:mm");

      // printing the timestamp
      System.out.println(formatter1.format(ts));

    }
}
```

**输出:**

```java
2021-10-19 20:21:34
2021-10-19 20:21
```
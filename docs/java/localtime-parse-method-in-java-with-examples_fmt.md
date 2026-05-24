# Java 中的 LocalTime.parse() 方法示例

> 原文：[https://www.geeksforgeeks.org/localtime-parse-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-parse-method-in-java-with-examples/)

在 `LocalTime` 类中，根据传递给它的参数，有两种类型的 `parse()` 方法。

## parse(CharSequence text)

`parse()` 是 `LocalTime` 类的一个方法，用于从作为参数传递的字符串（如 "10:15:45"）中获取 `LocalTime` 的实例。该字符串必须具有有效的日期时间，并使用日期时间格式化程序 `ISO_LOCAL_TIME` 进行分析。

### 语法

```java
public static LocalTime parse(CharSequence text)
```

### 参数

该方法只接受一个参数 `text`，即 `LocalTime` 中要解析的文本。它不应为空。

### 返回值

该方法返回 `LocalTime`，即解析后的本地日期时间。

### 异常

如果文本无法解析，该方法抛出 `DateTimeParseException`。

下面的程序说明了 `parse()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalTime.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalTime object
        LocalTime lt
            = LocalTime.parse("10:15:45");

        // print result
        System.out.println("LocalTime : "
                           + lt);
    }
}
```

**输出：**

```java
LocalTime : 10:15:45
```

## parse(CharSequence text, DateTimeFormatter formatter)

`parse()` 是 `LocalTime` 类的一个方法，用于从字符串中获取 `LocalTime` 的实例，如使用特定的格式化程序作为参数传递的 "10:15:45"。使用特定的格式化程序来解析日期时间。

### 语法

```java
public static LocalTime parse(CharSequence text,
                              DateTimeFormatter formatter)
```

### 参数

这个方法接受两个参数：`text` 作为要解析的文本，`formatter` 作为要使用的格式化程序。

### 返回值

该方法返回 `LocalTime`，即解析后的本地日期时间。

### 异常

如果文本无法解析，该方法抛出 `DateTimeParseException`。

下面的程序说明了 `parse()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalTime.parse() method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a formatter
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_LOCAL_TIME;

        // create an LocalTime object and
        LocalTime lt
            = LocalTime
                  .parse("10:15:45",
                         formatter);

        // print result
        System.out.println("LocalTime : "
                           + lt);
    }
}
```

**输出：**

```java
LocalTime : 10:15:45
```

### 参考文献

*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#parse(java.lang.CharSequence)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#parse(java.lang.CharSequence))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))
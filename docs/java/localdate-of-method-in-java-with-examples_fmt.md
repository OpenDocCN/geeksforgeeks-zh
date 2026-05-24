# Java 中 LocalDate 的 of() 方法示例

> 原文：[https://www.geeksforgeeks.org/localdate-of-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-of-method-in-java-with-examples/)

## 1. `of(int, int, int)` 方法

`LocalDate` 类中的 `of(int, int, int)` 方法用于根据输入的年、月和日创建 `LocalDate` 实例。在此方法中，所有三个参数均以整数形式传入。

### 语法

```java
public static LocalDate of(int year,
                           int month,
                           int dayOfMonth)
```

### 参数
该方法接受三个参数：
*   `year` – 整数型，代表年份。取值范围从最小年到最大年。
*   `month` – 整数型，代表一年中的月份。取值范围从 1（一月）到 12（十二月）。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。取值范围从 1 到 31。

### 返回值
此方法返回 `LocalDate`。

### 异常
如果任何字段值超出范围，或者月日对于月年无效，则此方法抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int, int, int)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDate.of(int month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate
            = LocalDate.of(2020, 5, 13);

        // print full date
        System.out.println("Date: " + localdate);
    }
}
```

### 输出

```java
Date: 2020-05-13
```

### 程序 2

```java
// Java program to demonstrate
// LocalDate.of(int month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate
            = LocalDate.of(2020, 5, 13);

        // print year only
        System.out.println("Year: "
                           + localdate.getYear());
    }
}
```

### 输出

```java
Year: 2020
```

## 2. `of(int, Month, int)` 方法

`LocalDate` 类中的 `of(int, Month, int)` 方法用于根据输入的年、月和日获取 `LocalDate` 实例。在此方法中，参数年和日以整数形式传入，但月份以 `Month` 枚举实例的形式传入。

### 语法

```java
public static LocalDate of(int year,
                           Month month,
                           int dayOfMonth)
```

### 参数
该方法接受三个参数：
*   `year` – 整数型，代表年份。取值范围从最小年到最大年。
*   `month` – `Month` 类型，代表一年中的月份。取值范围从 `Month.JANUARY` 到 `Month.DECEMBER`。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。取值范围从 1 到 31。

### 返回值
此方法返回 `LocalDate`。

### 异常
如果任何字段值超出范围或月中的某一天对于月-年无效，此方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int, Month, int)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDate.of(Month month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate = LocalDate.of(
            2020, Month.MAY, 13);

        // print full date
        System.out.println("Date: "
                           + localdate);
    }
}
```

### 输出

```java
Date: 2020-05-13
```

### 程序 2

```java
// Java program to demonstrate
// LocalDate.of(Month month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate = LocalDate.of(
            2020, Month.MAY, 13);

        // print month only
        System.out.println("Month: "
                           + localdate.getMonth());
    }
}
```

### 输出

```java
Month: MAY
```

## 参考文献

1.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, int, int))
2.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, java.time.Month, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, java.time.Month, int))
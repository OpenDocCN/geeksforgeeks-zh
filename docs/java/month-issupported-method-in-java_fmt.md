# Java 中的 `isSupported()` 方法

> 原文: [https://www.geeksforgeeks.org/month-issupported-method-in-java/](https://www.geeksforgeeks.org/month-issupported-method-in-java/)

`isSupported()` 方法是 `Month` 枚举的内置方法，用于检查指定字段是否被支持。此方法接受字段作为参数，并根据字段是否受支持返回 `true` 或 `false`。

## 语法

```java
public boolean isSupported(TemporalField field)
```

## 参数

该方法接受单个参数 `field`，检查是否支持。

## 返回值

如果支持该字段，则该方法返回布尔值 `true`，否则返回 `false`。

下面的程序说明了上述方法：

### 程序 1

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args) {
        // Create a month instance
        Month month = Month.of(5);

        // check if the field is valid
        if (month.isSupported(ChronoField.MONTH_OF_YEAR))
            System.out.println("This field is supported!");
        else
            System.out.println("This field is not supported!");
    }
}
```

**输出:**

```java
This field is supported!
```

### 程序 2

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args) {
        // Create a month instance
        Month month = Month.of(5);

        // check if the field is valid
        if (month.isSupported(ChronoField.DAY_OF_WEEK))
            System.out.println("This field is supported!");
        else
            System.out.println("This field is not supported!");
    }
}
```

**输出:**

```java
This field is not supported!
```

**参考:** [https://www.tutorialspoint.com/javatime/javatime_month_issupported.htm](https://www.tutorialspoint.com/javatime/javatime_month_issupported.htm)
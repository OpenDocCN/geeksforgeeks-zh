# Java 中的 MonthDay toString() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/monthday-tostring-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-tostring-method-in-java-with-examples/)

`toString()` 方法是 `MonthDay` 类的方法，用于将这个月日表示为类似 `--08-23` 的字符串。输出格式为 `--MM-DD`。

**语法：**
```java
public String toString()
```

**参数：** 该方法不接受任何参数。
**返回值：** 这个方法返回这个月日的字符串表示。

以下程序说明了 `toString()` 方法：

## 示例 1

```java
// Java program to demonstrate
// MonthDay.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // print instance of MonthDay
        System.out.println("YearMonth: "
                           + month.toString());
    }
}
```

**Output:**
```java
YearMonth: --10-12
```

## 示例 2

```java
// Java program to demonstrate
// MonthDay.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--08-31");

        // print instance of MonthDay
        System.out.println("YearMonth: "
                           + month.toString());
    }
}
```

**Output:**
```java
YearMonth: --08-31
```

**参考文献：** [https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#toString()](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#toString())
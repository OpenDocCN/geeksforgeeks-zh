# Java 中基于时间单位的()方法，示例

> 原文: [https://www.geeksforgeeks.org/chronounit-istimebased-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronounit-istimebased-method-in-java-with-examples/)

`ChronoUnit` 枚举的 `isTimeBased()` 方法用于检查该计时单位是否为时间单位。从纳米到半日的所有计时单位都是基于时间的。

## 语法

```java
public boolean isTimeBased()
```

## 参数

此方法不接受任何内容。

## 返回值

如果是时间单位，该方法返回 `true`，如果是日期单位，则返回 `false`。

下面的程序说明了 `ChronoUnit.isTimeBased()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoUnit.isTimeBased() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("NANOS");

        // apply isTimeBased()
        boolean isTimeBasedAttribute
            = chronoUnit.isTimeBased();

        // print
        System.out.println(
            "NANOS"
            + " is Date based attribute:"
            + isTimeBasedAttribute);
    }
}
```

**Output:**

```java
NANOS is Date based attribute:true
```

### 程序 2

```java
// Java program to demonstrate
// ChronoUnit.isTimeBased() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("DAYS");

        // apply isTimeBased()
        boolean isTimeBasedAttribute
            = chronoUnit.isTimeBased();

        // print
        System.out.println(
            "DAYS"
            + " is Date based attribute:"
            + isTimeBasedAttribute);
    }
}
```

**Output:**

```java
DAYS is Date based attribute:false
```

参考文献: [https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isTimeBased()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isTimeBased())
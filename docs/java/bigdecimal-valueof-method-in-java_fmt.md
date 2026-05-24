# Java 中的 BigDecimal valueOf()方法

> 原文: [https://www.geeksforgeeks.org/bigdecimal-valueof-method-in-java/](https://www.geeksforgeeks.org/bigdecimal-valueof-method-in-java/)

## 1. `BigDecimal.valueOf(long val)` 方法

`java.math.BigDecimal.valueOf(long val)` 是 Java 中的一个内置方法，它将一个 `long` 值转换为一个标度为零的 `BigDecimal` 值。它允许我们重用常用的 `BigDecimal` 值，因此优先提供这个“静态工厂方法”而非 `(long)` 构造函数。

**语法:**

```java
public static BigDecimal valueOf(long val)
```

**参数:** 该方法接受 `Long` 数据类型的单个参数 `val`，表示需要转换为 `BigDecimal` 值的值。

**返回值:** 该方法返回一个表示 `long` 值 `val` 的 `BigDecimal`。

下面的程序举例说明了 `java.math.BigDecimal.valueOf(long val)` 方法的工作原理:

```java
// Program to demonstrate valueOf(long) method of BigDecimal
import java.math.*;

public class gfg {
    public static void main(String[] args) {
        // Creating a Long Object
        Long ln = new Long("745812345678");

        // Assigning the bigdecimal value of ln to b
        BigDecimal b = BigDecimal.valueOf(ln);

        // Displaying BigDecimal value
        System.out.println("The Converted BigDecimal value is: " + b);
    }
}
```

**Output:**

```java
The Converted BigDecimal value is: 745812345678
```

## 2. `BigDecimal.valueOf(double val)` 方法

`java.math.BigDecimal.valueOf(double val)` 是 Java 中的一个内置方法，它将一个 `double` 值转换为一个 `BigDecimal`，使用由 `Double.toString(double)` 方法提供的 `double` 的规范字符串表示形式。

**语法:**

```java
public static BigDecimal valueOf(double val)
```

**参数:** 该方法接受 `double` 数据类型的单个参数 `val`，表示需要转换为 `BigDecimal` 的值。

**返回值:** 该方法返回一个等于或近似等于 `double` 值 `val` 的 `BigDecimal`。

下面的程序说明了 `java.math.BigDecimal.valueOf(double val)` 方法的工作:

**程序 1:**

```java
// Program to demonstrate valueOf(double) method of BigDecimal
import java.math.*;

public class gfg {
    public static void main(String[] args) {
        // Creating a Double Object
        Double d = new Double("785.254");

        /// Assigning the bigdecimal value of ln to b
        BigDecimal b = BigDecimal.valueOf(d);

        // Displaying BigDecimal value
        System.out.println("The Converted BigDecimal value is: " + b);
    }
}
```

**Output:**

```java
The Converted BigDecimal value is: 785.254
```
# Java 中的 `ChronoUnit.values()` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronounit-values-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronounit-values-method-in-java-with-examples/)

`ChronoUnit` 枚举的 `values()` 方法用于返回一个包含该枚举所有常量的数组，顺序与它们声明的顺序相同。

## 语法

```java
public static ChronoUnit[] values()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回一个包含此枚举类型常量的数组，顺序与它们声明的顺序相同。

以下程序说明了 `ChronoUnit.values()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoUnit.values() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronounit
            = ChronoUnit.valueOf("FOREVER");

        // apply values()
        ChronoUnit[] array
            = chronounit.values();

        // print
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**输出：**

```java
Nanos
Micros
Millis
Seconds
Minutes
Hours
HalfDays
Days
Weeks
Months
Years
Decades
Centuries
Millennia
Eras
Forever
```

### 程序 2

```java
// Java program to demonstrate
// ChronoUnit.values() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronounit
            = ChronoUnit.valueOf("CENTURIES");

        // apply values()
        ChronoUnit[] array
            = chronounit.values();

        // print
        System.out.println("ChronoUnit length:"
                           + array.length);
    }
}
```

**输出：**

```java
ChronoUnit length:16
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#values()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#values())
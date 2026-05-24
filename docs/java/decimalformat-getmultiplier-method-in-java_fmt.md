# DecimalFormat getMultiplier() 方法

> 原文：[https://www.geeksforgeks.org/decimalformat-getmultiplier-method-in-java/](https://www.geeksforgeks.org/decimalformat-getmultiplier-method-in-java/)

`getMultiplier()` 方法是 `java.text.DecimalFormat` 类的内置方法，用于获取以不同格式使用的乘数，如百分比、千分位等。

## 语法

```java
public int getMultiplier()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回不同格式使用的乘数值。

下面是上述功能的实现：

### 程序 1

```java
// Java program to illustrate the
// getMultiplier() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the multiplier value
        System.out.println(deciFormat.getMultiplier());
    }
}
```

**输出:**

```java

```

### 程序 2

```java
// Java program to illustrate the
// getMultiplier() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.getPercentInstance();

        // Print the multiplier value
        System.out.println(deciFormat.getMultiplier());
    }
}
```

**输出:**

```java

```

**参考**：[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMultiplier()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMultiplier())
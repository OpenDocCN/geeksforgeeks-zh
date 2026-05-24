# Java 中的 DecimalFormat getMaximumIntegerDigits() 方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-getmaximumintegerdigits-method-in-java/](https://www.geeksforgeeks.org/decimalformat-getmaximumintegerdigits-method-in-java/)

`getMaximumIntegerDigits()` 方法是 Java 中 `java.text.DecimalFormat` 类的内置方法，用于获取一个数字的整数部分所允许的最大位数。数字的整数部分被定义为小数点前的部分。例如，在数字 123,45.678 中，整数部分是 123,45。

## 语法

```java
public int getMaximumIntegerDigits()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个数的整数部分允许的最大位数。

## 示例

下面是上述功能的实现：

### 程序 1

```java
// Java program to illustrate the
// getMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the Maximum Integral digits allowed
        System.out.println(deciFormat.getMaximumIntegerDigits());
    }
}
```

**输出：**

```java

```

### 程序 2

```java
// Java program to illustrate the
// getMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##.##");

        // Print the Maximum Integral digits allowed
        System.out.println(deciFormat.getMaximumIntegerDigits());
    }
}
```

**输出：**

```java

```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMaximumIntegerDigits()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMaximumIntegerDigits())
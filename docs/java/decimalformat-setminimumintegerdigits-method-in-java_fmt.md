# Java 中的 `setMinimumIntegerDigits()` 方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-setminimumintegerdigits-method-in-java/](https://www.geeksforgeeks.org/decimalformat-setminimumintegerdigits-method-in-java/)

`setMinimumIntegerDigits()` 方法是 `java.text.DecimalFormat` 类的内置方法，用于设置数字的整数部分允许的最小位数。数字的整数部分是显示在小数点之前的部分。

## 语法

```java
public void setMinimumIntegerDigits(int newVal)
```

## 参数

该函数接受一个参数 `newVal`，这是允许为此十进制格式实例设置的最小整数位数的新值。

## 返回值

函数不返回值。

## 示例

下面是上述功能的实现：

### 程序 1

```java
// Java program to illustrate the
// setMinimumIntegerDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args) {
        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMinimumIntegerDigits(6);

        System.out.println(deciFormat.format(1234.34));
    }
}
```

**输出：**

```java
001,234.34
```

### 程序 2

```java
// Java program to illustrate the
// setMinimumIntegerDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args) {
        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMinimumIntegerDigits(2);

        System.out.println(deciFormat.format(1234.34));
    }
}
```

**输出：**

```java
1,234.34
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMinimumIntegerDigits(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMinimumIntegerDigits(int))
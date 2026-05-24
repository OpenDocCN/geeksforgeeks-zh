# Java 中的 DecimalFormat.setMultiplier() 方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-setmultiplier-method-in-java/](https://www.geeksforgeeks.org/decimalformat-setmultiplier-method-in-java/)

`setMultiplier()` 方法是 `java.text.DecimalFormat` 类的一个内置方法，用于设置此 `DecimalFormat` 实例使用的一个乘数值。当使用百分比、百分位数等时，可以使用该乘数。

例如，对于乘数 10，数字 98.89 将被格式化为 988.9。

## 语法

```java
public void setMultiplier(int newVal)
```

## 参数

该函数接受一个参数 `newVal`，这是为这个十进制格式实例设置的新乘数值。

## 返回值

函数不返回值。

下面是上述功能的实现：

## 程序 1

```java
// Java program to illustrate the
// setMultiplier() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMultiplier(10);

        System.out.println(deciFormat.format(1234.345));
    }
}
```

## 输出

```java
12, 343.45
```

## 程序 2

```java
// Java program to illustrate the
// setMultiplier() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMultiplier(1000);

        System.out.println(deciFormat.format(1234.345));
    }
}
```

## 输出

```java
1, 234, 345
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMultiplier(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMultiplier(int))
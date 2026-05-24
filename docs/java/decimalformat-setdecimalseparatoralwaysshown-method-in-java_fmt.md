# DecimalFormat.setDecimalSeparatorAlwaysShown()方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-setdecimalseparatoralwaysshown-method-in-java/](https://www.geeksforgeeks.org/decimalformat-setdecimalseparatoralwaysshown-method-in-java/)

## 概述

`setDecimalSeparatorAlwaysShown()`方法是`java.text.DecimalFormat`类的内置方法，用于设置是否为此十进制格式实例设置十进制符号分隔符。如果此方法设置为`true`，那么对于整数值，十进制格式实例也将打印十进制分隔符（`.`）。

例如，如果该方法为`true`，则`1234`将被打印为“`1234.`”。

## 语法

```java
public void setDecimalSeparatorAlwaysShown(boolean val)
```

## 参数

该函数接受布尔类型的单个参数`val`。

## 返回值

函数不返回值。

## 示例

下面是上述功能的实现：

**程序 1**：

```java
// Java program to illustrate the
// setDecimalSeparatorAlwaysShown() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setDecimalSeparatorAlwaysShown(true);

        System.out.println(deciFormat.format(12345));
    }
}
```

**输出：**

```java
12,345.
```

**程序 2**：

```java
// Java program to illustrate the
// setDecimalSeparatorAlwaysShown() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setDecimalSeparatorAlwaysShown(false);

        System.out.println(deciFormat.format(12345));
    }
}
```

**输出：**

```java
12,345
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setDecimalSeparatorAlwaysShown(boolean)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setDecimalSeparatorAlwaysShown(boolean))
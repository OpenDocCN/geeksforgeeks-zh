# Java 中的 DecimalFormat.setParseBigDecimal() 方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-setparsebigdecimal-method-in-java/](https://www.geeksforgeeks.org/decimalformat-setparsebigdecimal-method-in-java/)

Java 中 `DecimalFormat` 类的 `setParseBigDecimal()` 方法用于设置 `DecimalFormat` 类的 `parse()` 方法是否返回 `BigDecimal` 类型的值。如果此方法设置为 `true`，则 `parse()` 方法将返回一个 `BigDecimal` 值。

## 语法

```java
public void setParseBigDecimal(boolean newValue)
```

## 参数

该方法接受布尔类型的单个参数 `newValue`。如果该值设置为 `true`，则 `parse()` 方法将返回一个 `BigDecimal` 值。

## 返回值

此方法不返回值。

下面的程序说明了上述方法：

## 程序 1

```java
// Java program to illustrate the
// setParseBigDecimal() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.setParseBigDecimal(true);

        System.out.println(deciFormat.isParseBigDecimal());
    }
}
```

## 输出

```java
true
```

## 程序 2

```java
// Java program to illustrate the
// setParseBigDecimal() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.setParseBigDecimal(false);

        System.out.println(deciFormat.isParseBigDecimal());
    }
}
```

## 输出

```java
false
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setParseBigDecimal(boolean)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setParseBigDecimal(boolean))
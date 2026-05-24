# Java 中的 `setZeroDigit()` 方法示例

> 原文：[DecimalFormatSymbols setZeroDigit() Method in Java with Examples](https://www.geeksforgeeks.org/decimalformatsymbols-setzerodigit-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 包中的 `setZeroDigit(char)` 方法。[Java 中的 `DecimalFormatSymbols` 类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/) 用于设置表示此数据格式符号的区域设置中零的字符。此方法接受一个字符作为参数。

## 语法

```java
public void setZeroDigit(char zeroDigit)
```

## 参数

该方法接受 `zeroDigit` 作为参数，该参数是用于表示此数据格式符号的零的字符。

## 返回值

此方法不返回任何内容。

## 异常

此方法不抛出任何异常。

## 程序

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs
            = new DecimalFormatSymbols();

        System.out.println("Current Character"
                           + " used for zero: "
                           + dfs.getZeroDigit());

        char zeroDigit = '*';

        dfs.setZeroDigit(zeroDigit);

        System.out.println("Updated Character "
                           + "used for zero: "
                           + dfs.getZeroDigit());
    }
}
```

## 输出

```java
Current Character used for zero: 0
Updated Character used for zero: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setZeroDigit-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setZeroDigit-char-)
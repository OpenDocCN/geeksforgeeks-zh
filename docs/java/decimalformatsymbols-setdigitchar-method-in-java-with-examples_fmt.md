# Java 中的 DecimalFormatSymbols.setDigit() 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setdigitchar-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setdigitchar-method-in-java-with-examples/)

`setDigit(char)` 方法属于 Java 中的 `DecimalFormatSymbols` 类，用于设置表示此十进制格式符号区域设置的数字的字符。此方法将表示数字的字符作为参数。

## 语法

```java
public void setDigit(char digit)
```

## 参数

该方法接受 `digit` 作为参数，该参数是将用于表示此十进制格式符号的数字的字符。

## 返回值

此方法不返回任何内容。

## 异常

此方法不抛出任何异常。

## 程序示例

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
                           + " used for digit: "
                           + dfs.getDigit());

        char digit = '*';

        dfs.setDigit(digit);

        System.out.println("Updated Character"
                           + " used for digit: "
                           + dfs.getDigit());
    }
}
```

## 输出

```java
Current Character used for digit: #
Updated Character used for digit: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setDigit-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setDigit-char-)
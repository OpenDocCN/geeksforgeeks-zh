# Java 中的十进制格式符号 `getDigit()` 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-getdigit-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getdigit-method-in-java-with-examples/)

[`DecimalFormatSymbols` 类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/) 的 [`getDigit()`](https://www.geeksforgeeks.org/tag/java-text-package/) 方法用于获取表示此十进制格式符号区域设置的数字的字符。此方法返回该区域设置数字的字符。

## 语法

```java
public char getDigit()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个带有默认区域设置的十进制格式符号的数字字符。

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

        System.out.println("Character used for digit: "
                           + dfs.getDigit());
    }
}
```

## 输出

```java
Character used for digit: #
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getDigit--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getDigit--)
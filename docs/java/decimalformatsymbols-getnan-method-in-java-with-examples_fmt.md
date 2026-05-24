# Java 中的十进制格式符号 getNaN()方法，带示例

> 原文：[`https://www.geeksforgeks.org/decimalformatsymbols-getnan-method-in-java-with-examples/`](https://www.geeksforgeeks.org/decimalformatsymbols-getnan-method-in-java-with-examples/)

`getNaN()` 方法属于 [`Java`](https://www.geeksforgeeks.org/tag/java-text-package/) 中的 [`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/) 类，用于获取表示此十进制格式符号区域设置的 NaN（非数字）的字符串。此方法返回该区域设置的 NaN 字符串。

## 语法

```java
public String getNaN()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回带有默认区域设置的十进制格式符号的 NaN 字符串。

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

        System.out.println("Character used"
                           + " for NaN: "
                           + dfs.getNaN());
    }
}
```

## 输出

```java
Character used for NaN: ?
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getNaN--`](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getNaN--)
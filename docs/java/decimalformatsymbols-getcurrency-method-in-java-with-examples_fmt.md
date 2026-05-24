# Java 中的十进制格式符号 getCurrency()方法，带示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-getcurrency-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getcurrency-method-in-java-with-examples/)

[`getCurrency()`](https://www.geeksforgeeks.org/tag/java-text-package/) 方法属于 Java 中的 `DecimalFormatSymbols` 类，用于获取此十进制格式符号的区域设置的货币。此方法返回货币字符。

## 语法

```java
public char getCurrency()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回带有区域设置的十进制格式符号的货币字符。

## 异常

这个方法不抛出任何异常。

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

        System.out.println("Current currency: "
                           + dfs.getCurrency());
    }
}
```

## 输出

```java
Current currency: USD
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getCurrency--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getCurrency--)
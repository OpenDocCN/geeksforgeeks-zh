# Java 中的十进制格式符号获取指数分隔符()方法，示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-getexponentseparator-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getexponentseparator-method-in-java-with-examples/)

[`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-text-package/) 类中的 `getExponentSeparator()` 方法用于获取表示此 `DecimalFormatSymbols` 的区域设置的指数分隔符的字符串。此方法返回该地区指数分隔符的字符串。

## 语法

```java
public String getExponentSeparator()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回这个十进制格式符号的指数分隔符。

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

        System.out.println("Character used for"
                           + " exponent separator: "
                           + dfs.getExponentSeparator());
    }
}
```

## 输出

```java
Character used for exponent separator: E
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getExponentSeparator--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getExponentSeparator--)